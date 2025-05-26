Okay, basándonos en los conceptos de RL y la conversación anterior, pasemos a la Semana 7 y el inicio del **Deep Reinforcement Learning (Deep RL)**, enfocándonos en un algoritmo fundamental: **Deep Q-Networks (DQN)**.

Hemos visto que algoritmos como Q-Learning funcionan bien en entornos tabulares (espacios de estado y acción discretos y finitos). Sin embargo, muchos problemas interesantes en el mundo real tienen espacios de estado o acción *muy grandes* o incluso *continuos*. En estos casos, no podemos simplemente almacenar una tabla Q para cada par (estado, acción). Necesitamos una forma de **generalizar** el valor aprendido de un estado-acción a otros estados-acción similares.

Aquí es donde entra el **Deep Learning**. La idea principal del Deep RL es utilizar **redes neuronales profundas (Deep Neural Networks - DNN)** como **aproximadores de funciones de valor** o **aproximadores de política**.

#### Introducción a Deep Q-Networks (DQN)

**DQN** es uno de los primeros y más influyentes algoritmos de Deep RL. Es una extensión directa del algoritmo **Q-Learning** que utiliza una **red neuronal profunda** para estimar la función de valor de acción $Q(s, a)$.

En lugar de una tabla $Q(s, a)$, ahora tenemos una red neuronal $Q(s, a; \mathbf{w})$ donde $\mathbf{w}$ representa los pesos de la red. Dado un estado $s$ (o una observación, como una imagen), la red neuronal toma este estado como entrada y predice el valor Q para *cada posible acción* $a$ en ese estado.

El objetivo del entrenamiento es ajustar los pesos $\mathbf{w}$ de la red para que la función Q estimada $Q(s, a; \mathbf{w})$ se aproxime a la función de valor óptima $q^*(s, a)$. La regla de actualización básica se basa en la ecuación de Bellman para $q^*$:

$q^*(s, a) = \mathbb{E}_{s' \sim P(\cdot|s,a)} \left[ r + \gamma \max_{a'} q^*(s', a') \right]$

La actualización de Q-Learning busca minimizar la diferencia temporal (TD error), que es la diferencia entre el valor Q actual y un "objetivo" basado en la recompensa observada y el valor Q del siguiente estado:

$Q(S_t, A_t) \leftarrow Q(S_t, A_t) + \alpha \left[ R_{t+1} + \gamma \max_{a} Q(S_{t+1}, a) - Q(S_t, A_t) \right]$

En DQN, utilizamos la red neuronal para calcular $Q(S_t, A_t; \mathbf{w})$ y el objetivo se calcula como $R_{t+1} + \gamma \max_{a} Q(S_{t+1}, a; \mathbf{w})$. La red se entrena para reducir la diferencia entre $Q(S_t, A_t; \mathbf{w})$ y este objetivo, utilizando un algoritmo de optimización como el descenso de gradiente estocástico (SGD) o una de sus variantes para actualizar los pesos $\mathbf{w}$.

**Problemas con la aproximación de funciones no lineales (como DNNs) en Q-Learning:**

Combinar Q-Learning (un método TD "bootstrapping" que actualiza estimaciones a partir de otras estimaciones) con aproximación de funciones no lineales (como DNNs) y aprendizaje off-policy (aprender una política greedy mientras se explora con una política $\epsilon$-greedy, por ejemplo) puede llevar a **inestabilidad e incluso divergencia** [32, 11.3]. A esto se le conoce a veces como "la tríada mortal". Las actualizaciones consecutivas basadas en experiencias correlacionadas pueden perturbar el aprendizaje de la red de forma destructiva. Cuando se aprende algo nuevo, puede interferir catastróficamente con lo aprendido previamente ("interferencia catastrófica").

DQN introdujo dos mecanismos clave para mejorar la estabilidad y el rendimiento: **Experiencia Replay** y **Target Networks**.

#### Experiencia Replay (Replay Buffer)

Esta técnica aborda el problema de las **experiencias correlacionadas**. En el aprendizaje por refuerzo estándar, el agente interactúa con el entorno, observa una transición $(S_t, A_t, R_{t+1}, S_{t+1})$ y usa inmediatamente esta transición para actualizar su función de valor o política. Si el agente simplemente aprende de estas transiciones en el orden en que ocurren, los datos de entrenamiento estarán altamente correlacionados (transiciones de estados vecinos en el tiempo).

La **experiencia replay** almacena las transiciones vividas por el agente en una base de datos circular llamada **replay memory** o **replay buffer**. Durante el entrenamiento, en lugar de usar solo la transición más reciente, se muestrean aleatoriamente **mini-batches** de transiciones de este buffer.

**Ventajas de Experiencia Replay:**

*   **Rompe Correlaciones:** Al muestrear aleatoriamente, se entrenan las actualizaciones de la red con datos menos correlacionados, lo que hace que el proceso de entrenamiento sea más parecido al entrenamiento supervisado estándar y mejora la estabilidad.
*   **Reutiliza Datos:** Cada transición puede ser utilizada para múltiples actualizaciones, no solo la que ocurre inmediatamente después de experimentarla. Esto aumenta la eficiencia del aprendizaje.
*   **Atenúa el Olvido Catastrófico:** Reintroducir datos antiguos ayuda a la red a retener lo que aprendió previamente mientras aprende cosas nuevas.

La experiencia replay es posible en DQN porque Q-Learning es un algoritmo **off-policy**, lo que significa que puede aprender de experiencias generadas por una política de comportamiento (por ejemplo, $\epsilon$-greedy) mientras aprende sobre una política objetivo diferente (por ejemplo, greedy).

Lin (1992) es acreditado con el estudio inicial del concepto de replay buffer.

#### Target Networks (Redes Objetivo)

El segundo mecanismo clave en DQN es el uso de una **target network**. En Q-Learning, el objetivo de la actualización $R_{t+1} + \gamma \max_{a} Q(S_{t+1}, a)$ depende de la misma función Q que se está actualizando. Esto crea un bucle de retroalimentación: estamos tratando de alcanzar un objetivo que se mueve constantemente a medida que aprendemos, lo que puede ser inestable.

La idea de la target network es usar **dos copias** de la red Q:
1.  La **red principal (online network)**: $Q(s, a; \mathbf{w})$, que se actualiza en cada paso de entrenamiento usando el descenso de gradiente. Esta red es la que se usa para seleccionar acciones (a través de una política $\epsilon$-greedy).
2.  La **red objetivo (target network)**: $Q(s, a; \mathbf{w}^-)$, que es una copia de la red principal, pero sus pesos $\mathbf{w}^-$ se actualizan **periódicamente** (por ejemplo, cada K pasos de entrenamiento) copiando los pesos $\mathbf{w}$ de la red principal.

La regla de actualización para la red principal en DQN utiliza la red objetivo para calcular el valor del siguiente estado:

$Q(S_t, A_t; \mathbf{w}) \leftarrow Q(S_t, A_t; \mathbf{w}) + \alpha \left[ R_{t+1} + \gamma \max_{a} Q(S_{t+1}, a; \mathbf{w}^-) - Q(S_t, A_t; \mathbf{w}) \right]$

(O, más precisamente para entrenamiento con SGD en mini-batches: se calcula la pérdida cuadrática entre $Q(S_t, A_t; \mathbf{w})$ y el objetivo $R_{t+1} + \gamma \max_{a} Q(S_{t+1}, a; \mathbf{w}^-)$, y se usa el gradiente de esta pérdida para actualizar $\mathbf{w}$).

**Ventaja de la Target Network:**

*   **Estabilidad:** Al usar una red objetivo con pesos fijos durante un período, el objetivo de la actualización $R_{t+1} + \gamma \max_{a} Q(S_{t+1}, a; \mathbf{w}^-)$ se vuelve temporalmente **estacionario**. Esto proporciona un objetivo más estable para la red principal, ayudando a la convergencia del aprendizaje.

Mnih et al., en su trabajo pionero sobre DQN aplicado a juegos de Atari, encontraron que el uso conjunto de experiencia replay y una red objetivo duplicada mejoró drásticamente el rendimiento. La arquitectura usó una red neuronal profunda convolucional para procesar las imágenes de los juegos, aprendiendo features relevantes directamente del input visual.

En resumen, DQN combina Q-Learning con redes neuronales profundas para manejar grandes espacios de estado. Supera los problemas de estabilidad inherentes a esta combinación utilizando **experiencia replay** para descorrelacionar los datos de entrenamiento y una **target network** para estabilizar el objetivo de la actualización. Estos avances permitieron a los agentes de RL alcanzar niveles de rendimiento comparables o superiores a los humanos en tareas visualmente ricas y complejas como jugar juegos de Atari.
