### Semana 6: Algoritmos MARL Descentralizados - Independent Q-Learning (IQL)

Hemos visto que MARL presenta desafíos significativos como la no-estacionariedad, la asignación de crédito multiagente y la escalabilidad. Para abordar estos problemas, existen diferentes enfoques algorítmicos. Una clasificación fundamental es entre algoritmos **centralizados** y **descentralizados**.

*   **Centralizados:** Hay una entidad central que toma decisiones para todos los agentes o coordina su aprendizaje. Esto puede mitigar la no-estacionariedad (la entidad central ve el sistema completo) y la asignación de crédito (la entidad central puede entender las contribuciones conjuntas), pero a menudo sufre enormemente con la **escalabilidad** debido al tamaño del espacio de acción conjunta.
*   **Descentralizados:** Cada agente toma sus propias decisiones y aprende de forma individual, basándose únicamente en su propia experiencia (observaciones, acciones, recompensas). Esta arquitectura suele ser mucho más escalable, ya que la complejidad computacional de cada agente es independiente del número total de agentes (o solo crece linealmente con él), pero tiene dificultades intrínsecas con los desafíos multiagente.

**Independent Q-Learning (IQL)** es el ejemplo más básico de un algoritmo **descentralizado**.

#### Concepto e Implementación del Independent Q-Learning (IQL)

En pocas palabras, IQL es la aplicación más directa del algoritmo de Aprendizaje por Refuerzo para un solo agente, **Q-Learning**, a un entorno multiagente.

Imagina un escenario con varios agentes. En IQL, cada agente:

1.  Tiene su propia función de valor de acción (Q-function), por ejemplo, $Q_i(s_i, a_i)$ para el agente $i$, que estima el valor esperado de tomar la acción $a_i$ en el estado local $s_i$.
2.  Utiliza el **algoritmo estándar de Q-Learning** para actualizar su función Q.

El algoritmo base de Q-Learning para un solo agente, según las fuentes, estima la función de valor de acción óptima $q^*$. La regla de actualización de Q-Learning para un par estado-acción $(S_t, A_t)$ observado en el tiempo $t$ es:

$Q(S_t, A_t) \leftarrow Q(S_t, A_t) + \alpha [R_{t+1} + \gamma \max_a Q(S_{t+1}, a) - Q(S_t, A_t)]$

Donde:
*   $Q(S_t, A_t)$ es el valor estimado del par estado-acción actual.
*   $\alpha$ es la tasa de aprendizaje.
*   $R_{t+1}$ es la recompensa recibida después de tomar la acción $A_t$ en el estado $S_t$.
*   $\gamma$ es el factor de descuento.
*   $S_{t+1}$ es el estado siguiente observado.
*   $\max_a Q(S_{t+1}, a)$ es el valor máximo esperado en el estado siguiente $S_{t+1}$ (la acción óptima que el agente podría tomar en el estado siguiente según su Q-function actual).

En IQL, cada agente $i$ aplica *esta misma regla de actualización* utilizando su propia recompensa $R_{i,t+1}$ (o la recompensa compartida si es un entorno cooperativo), su propio estado (o observación) $S_{i,t}$, su propia acción $A_{i,t}$ y el siguiente estado (o observación) $S_{i,t+1}$. Desde la perspectiva del agente $i$, el "entorno" incluye a todos los demás agentes y su comportamiento.

**Pseudocódigo (Basado en Q-Learning):**

Para cada agente $i$ (independientemente):

Inicializar $Q_i(s, a)$, para todo estado $s$ y acción $a$ del agente $i$, arbitrariamente (excepto $Q_i(\text{terminal}, \cdot) = 0$).
Loop para cada episodio:
  Inicializar estado $S_i$
  Loop para cada paso del episodio:
    Elegir acción $A_i$ desde $S_i$ usando una política derivada de $Q_i$ (e.g., $\epsilon$-greedy)
    Tomar acción $A_i$ (junto con las acciones de los otros agentes en el entorno conjunto)
    Observar recompensa $R_{i,t+1}$ y siguiente estado $S_{i,t+1}$
    Actualizar $Q_i$: $Q_i(S_i, A_i) \leftarrow Q_i(S_i, A_i) + \alpha \left[R_{i,t+1} + \gamma \max_{a'_i} Q_i(S_{i,t+1}, a'_i) - Q_i(S_i, A_i)\right]$
    $S_i \leftarrow S_{i,t+1}$
  hasta que $S_i$ sea terminal

#### Limitaciones del Independent Q-Learning (IQL)

Aunque IQL es simple y fácil de implementar, sus limitaciones derivan directamente de su suposición fundamental y los desafíos inherentes de MARL que no aborda:

1.  **La No-Estacionariedad:** Este es el problema principal. Los algoritmos de RL para un solo agente, como Q-Learning, garantizan la convergencia bajo la suposición de que las dinámicas del entorno (transiciones de estado y recompensas) son **estacionarias** (fijas). En IQL, el "entorno" de un agente individual incluye las políticas de los otros agentes. Como *todos* los agentes están aprendiendo y cambiando sus políticas simultáneamente, la dinámica percibida por cualquier agente individual **no es estacionaria**. Cada agente persigue un objetivo móvil creado por los demás.
    *   *Referencia a fuentes:* Si bien las fuentes no definen "no-estacionariedad" *causada por otros agentes en aprendizaje*, sí discuten procedimientos de aprendizaje para "oponentes estacionarios" vs. "oponentes no estacionarios", reconociendo que aprender en presencia de entidades cambiantes es más complejo. Las pruebas de convergencia para Q-Learning asumen un MDP subyacente, que es estacionario por definición. La violación de esta suposición en IQL es la raíz del problema.

2.  **El Problema del "Credit Assignment" Multiagente:** Aunque IQL usa la actualización de Q-Learning que asigna crédito *temporalmente*, no resuelve el problema de la asignación de crédito *entre agentes*.
    *   En tareas **cooperativas** con recompensa compartida, todos los agentes reciben la misma recompensa. Si el equipo tiene éxito (recompensa alta) o fracasa (recompensa baja), un agente individual usando IQL no tiene un mecanismo directo para determinar *qué acciones conjuntas* (incluyendo las de los otros agentes) llevaron a ese resultado. El algoritmo de Q-Learning solo mira la propia acción $A_{i,t}$ y la recompensa $R_{i,t+1}$. Esto dificulta que los agentes aprendan a coordinarse eficazmente.
    *   *Referencia a fuentes:* Las fuentes discuten la asignación de crédito para consecuencias a largo plazo en un contexto general de RL (mencionado en la descripción del desafío la semana pasada, pero no detallado en los fragmentos actuales), pero no explican cómo se agrava en el contexto multiagente ni cómo Q-Learning *no* lo resuelve en ese caso. La necesidad de entender interacciones y equilibrar necesidades en sistemas multiagente subraya la importancia de una asignación de crédito adecuada.

3.  **Escalabilidad (limitaciones de la base Q-Learning):** Si bien la arquitectura *descentralizada* de IQL ayuda con la escalabilidad en términos del número de agentes (cada agente es computacionalmente independiente), hereda las limitaciones de escalabilidad del Q-Learning tabular base.
    *   El Q-Learning tabular requiere almacenar una tabla $Q(s,a)$ para cada par estado-acción. Si el espacio de estados local de un agente o su espacio de acciones es muy grande, esta tabla se vuelve intratable.
    *   Para abordar esto, se suele recurrir a la aproximación de funciones de valor (usando redes neuronales, por ejemplo). Sin embargo, combinar la aproximación de funciones, el bootstrapping (actualizar a partir de estimaciones futuras, como hace Q-Learning) y el aprendizaje off-policy (aprender sobre la política greedy mientras se ejecuta una política de exploración como $\epsilon$-greedy) puede llevar a la inestabilidad, un problema conocido como la "tríada mortal" en RL de un solo agente. En el entorno *no estacionario* de MARL, esta inestabilidad potencial se ve a menudo exacerbada.
    *   Aunque IQL evita la complejidad combinatoria *del espacio de acción conjunta global* inherente a los métodos centralizados, la complejidad del espacio de estado *individual* o las interacciones complejas aún pueden hacer que el aprendizaje sea difícil o requiera técnicas avanzadas de aproximación, que a su vez introducen otros problemas de estabilidad.

En conclusión, Independent Q-Learning es un punto de partida didáctico para entender MARL descentralizado. Es simple de implementar, pero su fracaso en abordar la no-estacionariedad y el problema de la asignación de crédito multiagente, así como las limitaciones de escalabilidad de su componente base de Q-Learning (especialmente cuando se requiere aproximación de funciones), lo hacen ineficaz en muchos entornos multiagente complejos e interactivos. A pesar de estas limitaciones, su simplicidad lo convierte en una línea base útil para comparar algoritmos MARL más sofisticados.
