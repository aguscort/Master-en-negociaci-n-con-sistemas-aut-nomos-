La Semana 1 sienta las bases del Aprendizaje por Refuerzo (RL) y el marco formal que se utiliza para describirlo, los Procesos de Decisión de Markov (MDPs).

1.  **Introducción al Aprendizaje por Refuerzo (RL)**
    *   El Aprendizaje por Refuerzo trata sobre **aprender de la interacción cómo comportarse para lograr un objetivo**.
    *   Se formaliza utilizando ideas de la teoría de sistemas dinámicos, específicamente como el **control óptimo de Procesos de Decisión de Markov (MDPs) incompletamente conocidos**.
    *   Implica **retroalimentación evaluativa** (recompensas) y un aspecto asociativo: elegir diferentes acciones en diferentes situaciones.

2.  **El Problema del Agente**
    *   En RL, el **aprendiz y tomador de decisiones se llama agente**.
    *   El agente **interactúa con su entorno** a lo largo de una secuencia de pasos de tiempo discretos.
    *   En cada paso de tiempo, el agente **recibe una representación del estado del entorno** y, basándose en ello, **selecciona una acción**.
    *   El entorno, en parte como consecuencia de la acción del agente, presenta nuevas situaciones y **emite una recompensa**.
    *   El agente busca **maximizar la cantidad total de recompensa** que recibe con el tiempo.

3.  **Procesos de Decisión de Markov (MDPs)**
    *   Los MDPs son una **formalización clásica de la toma de decisiones secuenciales**.
    *   En un MDP, las acciones influyen no solo en las recompensas inmediatas, sino también en las situaciones (estados) subsiguientes y, a través de ellas, en las recompensas futuras. Esto implica **recompensa retardada** y la necesidad de equilibrar recompensa inmediata y futura.
    *   Un MDP finito es una tupla (S, A, p, R) o, más explícitamente en la notación utilizada en una de las fuentes, sus dinámicas están dadas por un conjunto de probabilidades p(s', r | s, a) para todos los estados (S), acciones (A), recompensas (R) y siguientes estados (S'). Un MDP finito tiene conjuntos S, A y R finitos.
    *   Los elementos clave de un MDP son:
        *   **Estados (States - S):** Una representación de la situación del entorno que el agente recibe. El estado debe incluir información sobre todos los aspectos de la interacción pasada que afecten el futuro. Los estados pueden tomar una amplia variedad de formas, desde lecturas de sensores hasta decisiones de alto nivel. El estado debe tener la **propiedad de Markov**, lo que significa que la probabilidad de cada valor posible para el siguiente estado y la recompensa depende solo del estado y la acción inmediatamente anteriores. En teoría de juegos, el concepto de estado también se usa para codificar características de la historia relevantes para la elección de un jugador.
        *   **Acciones (Actions - A):** Las elecciones que realiza el agente. El conjunto de acciones posibles puede depender del estado. Las acciones pueden ser controles de bajo nivel o decisiones de alto nivel. En sistemas multiagente o teoría de juegos, también se habla de acciones (o movimientos) tomadas por los agentes o jugadores.
        *   **Recompensas (Rewards - R):** Una señal numérica especial que el entorno envía al agente para formalizar el objetivo. El objetivo del agente es maximizar la recompensa acumulada a largo plazo. La **hipótesis de la recompensa** postula que todo objetivo puede ser concebido como la maximización de la recompensa total esperada. La recompensa en un paso de tiempo t se denota como Rt+1. La recompensa puede ser un valor simple o, en aplicaciones prácticas como las de Modelos de Recompensa para LLMs, puede ser un puntaje agregado que combine preferencias humanas y señales de verificación de corrección.
        *   **Transiciones (Transitions):** Definen la dinámica del entorno. Para cada par estado-acción (s, a), la función de dinámica p(s', r | s, a) especifica la **probabilidad de terminar en el siguiente estado s' con la recompensa r**. Esta función de cuatro argumentos caracteriza completamente la dinámica del entorno en un MDP. Desde p(s', r | s, a), se pueden derivar las probabilidades de transición de estado p(s' | s, a) y las recompensas esperadas r(s, a) o r(s, a, s'). El concepto de función de transición también aparece en la descripción de autómatas como representación de estrategias en teoría de juegos.

4.  **La Función de Valor**
    *   Casi todos los algoritmos de RL implican la **estimación de funciones de valor**.
    *   Las funciones de valor son **funciones de estados (o pares estado-acción)** que estiman **"cuán bueno" es estar en un estado dado** (o realizar una acción dada en un estado dado).
    *   La noción de "cuán bueno" se define en términos de las **recompensas futuras esperadas**, o más precisamente, en términos del **retorno esperado**.
    *   El retorno (Gt) es alguna función de la secuencia de recompensas futuras. Comúnmente, es la **suma descontada de las recompensas** futuras, donde un factor de descuento $\gamma \in$ valora las recompensas inmediatas más que las futuras.
    *   Las funciones de valor se definen con respecto a **políticas particulares**. Una política ($\pi$) es un mapeo de estados a probabilidades de seleccionar cada acción posible. Si un agente sigue la política $\pi$, $\pi(a|s)$ es la probabilidad de tomar la acción $a$ en el estado $s$.

5.  **La Función Q (Función de Valor-Acción)**
    *   Existen dos tipos principales de funciones de valor:
        *   La **función de valor de estado** ($v_\pi(s)$): El retorno esperado al comenzar en el estado $s$ y luego seguir la política $\pi$.
        *   La **función de valor-acción** ($q_\pi(s, a)$): El retorno esperado al comenzar en el estado $s$, tomar la acción $a$, y luego seguir la política $\pi$.
    *   En MDPs, a menudo se estima $q^*(s, a)$ o $v^*(s)$ para las selecciones de acciones óptimas.

6.  **Bellman Equations (Adelanto)**
    *   Las funciones de valor satisfacen relaciones recursivas que son fundamentales en RL, conocidas como las Ecuaciones de Bellman. Estas relacionan el valor de un estado con los valores de sus estados sucesores (o el valor de un par estado-acción con sus sucesores).

En resumen, la Semana 1 introduce el **problema central del RL** (un agente que aprende a actuar para maximizar su recompensa a largo plazo a través de la interacción) y lo formaliza utilizando los **MDPs**, que describen el entorno en términos de **estados, acciones, recompensas y transiciones probabilísticas**. Se define el objetivo como la maximización del **retorno esperado** (a menudo descontado), lo que lleva a la necesidad de estimar **funciones de valor** ($v_\pi$ y $q_\pi$) que predicen la recompensa futura esperada bajo una política dada.
