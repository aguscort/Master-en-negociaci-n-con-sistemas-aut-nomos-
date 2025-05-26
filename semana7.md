# Semana 7: Deep RL Básico - Introducción a Deep Q-Networks (DQN)

Hasta ahora, hemos visto algoritmos como Q-Learning que funcionan muy bien en entornos donde podemos representar la función de valor Q como una tabla (entornos tabulares). Sin embargo, en problemas más complejos y realistas, los espacios de estado o acción son a menudo muy grandes o incluso continuos. Intentar almacenar una tabla Q completa en estos casos es inviable debido a la "maldición de la dimensionalidad". Necesitamos una forma de **generalizar** lo que aprendemos sobre el valor de una acción en un estado a otros estados y acciones similares.

Aquí es donde las **redes neuronales profundas (DNNs)** se vuelven herramientas poderosas para la aproximación de funciones de valor. El **Deep Reinforcement Learning** combina la potencia de las DNNs con los algoritmos de RL.

## Introducción a Deep Q-Networks (DQN)

**Deep Q-Networks (DQN)** es uno de los primeros y más exitosos algoritmos que aplica redes neuronales al Q-Learning. La idea central es reemplazar la tabla Q con una **red neuronal profunda** que actúe como un **aproximador de la función de valor de acción** $Q(s, a)$.

En lugar de una tabla, tenemos una red neuronal, a la que llamaremos la **red Q**, parametrizada por un vector de pesos $\mathbf{w}$. Dado un estado $s$ como entrada, esta red produce como salida el valor Q estimado $Q(s, a; \mathbf{w})$ para cada acción posible $a$ en ese estado.

El objetivo es entrenar esta red para que $Q(s, a; \mathbf{w})$ se aproxime a la función de valor óptima $q^*(s, a)$. Al igual que en Q-Learning, el aprendizaje se basa en reducir la diferencia temporal (TD error) entre el valor Q actual y un "objetivo" basado en la ecuación de Bellman.

La ecuación de Bellman óptima es $q^*(s, a) = \mathbb{E}_{s' \sim P(\cdot|s,a)} \left[ r + \gamma \max_{a'} q^*(s', a') \right]$.
La actualización de Q-Learning es $Q(S_t, A_t) \leftarrow Q(S_t, A_t) + \alpha \left[ R_{t+1} + \gamma \max_{a} Q(S_{t+1}, a) - Q(S_t, A_t) \right]$.

En DQN, usamos la red Q para calcular $Q(S_t, A_t; \mathbf{w})$. El objetivo para la actualización (conocido como el "target") se basa en la recompensa $R_{t+1}$ y el valor Q máximo del siguiente estado $S_{t+1}$, predicho también por la red Q: $R_{t+1} + \gamma \max_{a} Q(S_{t+1}, a; \mathbf{w})$. La red se entrena para minimizar la diferencia entre $Q(S_t, A_t; \mathbf{w})$ y este objetivo, típicamente usando descenso de gradiente sobre el error cuadrático.

**El Desafío de la Estabilidad:**

Combinar la aproximación de funciones no lineales (como las DNNs), el "bootstrapping" (actualizar estimaciones basadas en otras estimaciones, como en TD y Q-Learning), y el aprendizaje off-policy (aprender sobre una política objetivo - greedy - mientras se actúa con otra política de comportamiento - $\epsilon$-greedy, por ejemplo) crea lo que se conoce como la **"tríada mortal"**. Esta combinación puede llevar a **inestabilidad y divergencia** en el proceso de aprendizaje.

Los problemas incluyen:
*   **Correlación de datos:** Las transiciones consecutivas de la interacción con el entorno están altamente correlacionadas. Entrenar una red neuronal con datos tan secuenciales y dependientes puede ser inestable.
*   **Objetivo en movimiento:** El objetivo de la actualización ($R_{t+1} + \gamma \max_{a} Q(S_{t+1}, a; \mathbf{w})$) depende de la misma red $Q$ que estamos entrenando. Es como perseguir un blanco que se mueve al mismo tiempo que intentamos alcanzarlo, lo que dificulta la convergencia.

Para abordar estos problemas de estabilidad, DQN introdujo dos técnicas clave (que, aunque no se nombran específicamente "Experience Replay" o "Target Networks" en las partes de los textos proporcionados que describen la inestabilidad, son las soluciones estándar utilizadas en DQN para mitigarla):

## Experiencia Replay (Replay Buffer)

Esta técnica rompe la correlación temporal de los datos. El agente no aprende de las transiciones $(S_t, A_t, R_{t+1}, S_{t+1})$ inmediatamente y en secuencia. En su lugar, estas transiciones se almacenan en una memoria (el **replay buffer**). Durante el entrenamiento, se muestrean aleatoriamente **mini-batches** de transiciones del buffer.

**Beneficios:**
*   **Descorrelación:** El muestreo aleatorio rompe las dependencias entre muestras consecutivas, haciendo que las actualizaciones de la red sean más estables, similar al entrenamiento estándar con SGD.
*   **Reutilización de datos:** Las transiciones se pueden usar varias veces para el entrenamiento, aumentando la eficiencia del aprendizaje.

## Target Networks (Redes Objetivo)

Para estabilizar el objetivo de la actualización, DQN utiliza una segunda red neuronal, llamada la **target network** $Q(s, a; \mathbf{w}^-)$. Esta red es una copia de la red principal $Q(s, a; \mathbf{w})$, pero sus pesos $\mathbf{w}^-$ se mantienen fijos durante un número determinado de pasos de entrenamiento.

La regla de actualización de la red principal utiliza ahora el valor Q del siguiente estado predicho por la **target network**:

$Q(S_t, A_t; \mathbf{w}) \leftarrow Q(S_t, A_t; \mathbf{w}) + \alpha \left[ R_{t+1} + \gamma \max_{a} Q(S_{t+1}, a; \mathbf{w}^-) - Q(S_t, A_t; \mathbf{w}) \right]$

(O, en la práctica, la actualización de pesos $\mathbf{w}$ se hace mediante descenso de gradiente de la pérdida entre $Q(S_t, A_t; \mathbf{w})$ y el objetivo $R_{t+1} + \gamma \max_{a} Q(S_{t+1}, a; \mathbf{w}^-)$).

Los pesos de la target network $\mathbf{w}^-$ solo se actualizan periódicamente (por ejemplo, cada 10000 pasos) copiando los pesos actuales de la red principal $\mathbf{w}$.

**Beneficio:**
*   **Estabilidad del objetivo:** Al usar una target network con pesos fijos, el objetivo de la actualización $R_{t+1} + \gamma \max_{a} Q(S_{t+1}, a; \mathbf{w}^-)$ se vuelve temporalmente estacionario, proporcionando un blanco más estable para la red principal y ayudando a mitigar la inestabilidad causada por un objetivo en constante movimiento.

Combinando Experiencia Replay y Target Networks, el algoritmo DQN original pudo entrenar eficazmente agentes para jugar juegos de Atari directamente desde la entrada visual, superando el rendimiento humano en muchos casos. Si bien los fuentes proporcionados detallan la inestabilidad teórica de combinar los elementos de la "tríada mortal", estas dos técnicas son las soluciones prácticas clave introducidas por DQN para lograr estabilidad en la práctica.
