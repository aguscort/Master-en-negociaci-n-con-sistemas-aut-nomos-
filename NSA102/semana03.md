### Semana 3: Aprendizaje por Refuerzo Sin Modelo, Q-Learning, SARSA y Exploración-Explotación

Hasta ahora, hemos visto cómo los algoritmos de Programación Dinámica (DP) pueden resolver problemas de RL cuando tenemos un **modelo perfecto del entorno**. Sin embargo, en la práctica, a menudo no conocemos las probabilidades de transición o la función de recompensa; solo podemos **experimentar** con el entorno. Aquí es donde entran los métodos de **Aprendizaje por Refuerzo sin modelo**.

Los métodos **Model-Free** aprenden la política óptima o la función de valor directamente de la **experiencia** (ya sea interacción real o simulada), sin construir explícitamente un modelo del entorno. Se les ve a menudo como aprendices por ensayo y error.

Dentro de los métodos sin modelo, una distinción clave es si son **"on-policy"** o **"off-policy"**.

*   **On-policy** methods learn the value of the policy *currently being followed* by the agent.
*   **Off-policy** methods learn the value of a *different* policy (la "target policy") than the one used to generate the data (la "behavior policy"). Esto permite aprender sobre una política óptima mientras se sigue una política más exploratoria.

Dos algoritmos fundamentales en RL sin modelo son SARSA y Q-Learning, ambos basados en las ideas de **Aprendizaje por Diferencias Temporales (TD)**.

1.  **SARSA (On-Policy TD Control)**
    *   SARSA es un método de control TD **on-policy**.
    *   Su nombre proviene de los elementos que utiliza para su actualización: **S**tate, **A**ction, **R**eward, **S**tate, **A**ction [similar a la descripción implícita en el bucle de Sarsa en 74].
    *   La regla de actualización para la función de valor acción $Q(s, a)$ se basa en el error TD calculado a partir de la experiencia inmediata $(S_t, A_t, R_{t+1}, S_{t+1}, A_{t+1})$ [similar a la forma del error TD en 77, 78 y el bucle en 74]:
        $Q(S_t, A_t) \leftarrow Q(S_t, A_t) + \alpha [R_{t+1} + \gamma Q(S_{t+1}, A_{t+1}) - Q(S_t, A_t)]$
        Donde $A_{t+1}$ es la **acción seleccionada por la *misma* política que se está evaluando y mejorando** para el estado $S_{t+1}$ [implícito en la descripción "on-policy" 63 y pseudocódigo 74].
    *   Debido a que SARSA es on-policy, aprende la función de valor para la política que actualmente está utilizando, incluyendo su comportamiento exploratorio.
    *   **Ejemplo de Cliff Walking**: En el problema del acantilado (Cliff Walking), SARSA, al ser on-policy y considerar la acción que *realmente* toma (incluyendo exploración), aprende un **camino más seguro** (alejado del acantilado) en lugar del camino óptimo teórico (justo al borde del acantilado), porque valora la penalización de caer en el acantilado que puede ocurrir debido a la exploración.

2.  **Q-Learning (Off-Policy TD Control)**
    *   Q-Learning es un método de control TD **off-policy**.
    *   Aprende la función de valor acción $Q^*$ para la **política óptima**, independientemente de la política que se use para generar los datos (la política de comportamiento).
    *   La regla de actualización para $Q(s, a)$ utiliza el valor máximo de la acción en el siguiente estado, en lugar del valor de la acción seleccionada por la política de comportamiento [similar a la forma del error TD con max en 66, 67]:
        $Q(S_t, A_t) \leftarrow Q(S_t, A_t) + \alpha [R_{t+1} + \gamma \max_{a} Q(S_{t+1}, a) - Q(S_t, A_t)]$
    *   Esta regla directamente se basa en la Ecuación de Bellman de Optimalidad para $q^*$ [similar a 29, 47, 49, 66, 67].
    *   Q-Learning converge a la función de valor óptima $Q^*$ para el modelo, lo que le permite derivar la política óptima.
    *   **Ejemplo de Cliff Walking**: En contraste con SARSA, Q-Learning aprende los valores para la **política óptima** (la que va por el borde del acantilado). Sin embargo, si la política de comportamiento utilizada (por ejemplo, ε-greedy) ocasionalmente elige una acción exploratoria que lo lleva al acantilado, el agente Q-Learning puede caerse a pesar de conocer la política óptima, porque la política de *comportamiento* no sigue estrictamente la política target (óptima) en cada paso.

3.  **La Exploración vs. Explotación**
    *   Este es un dilema fundamental en el Aprendizaje por Refuerzo.
    *   Para encontrar una buena política, el agente debe probar diferentes acciones y explorar el entorno (exploración).
    *   Pero para maximizar su recompensa, debe elegir las acciones que sabe que ya le han dado altas recompensas (explotación).
    *   Un agente que solo explora puede nunca capitalizar lo que aprende. Un agente que solo explota puede quedarse atascado en acciones subóptimas tempranamente descubiertas y nunca encontrar la mejor política.
    *   Se necesita un **equilibrio** entre exploración y explotación.

    *   **Estrategias de Exploración:**
        *   **ε-greedy:** Es una estrategia simple y muy común. Con probabilidad $1 - \epsilon$, el agente elige la acción *voraz* (la que tiene el valor estimado más alto). Con una pequeña probabilidad $\epsilon$, elige una acción **al azar** (posiblemente incluyendo la acción voraz). Esto asegura que todas las acciones se prueben eventualmente [implícito por la aleatoriedad].
        *   **Decaimiento de ε:** Para garantizar la convergencia a la política óptima, la exploración a menudo necesita **disminuir con el tiempo**. Esto se puede lograr reduciendo gradualmente el valor de $\epsilon$ a medida que el agente aprende.
        *   **Valores Iniciales Optimistas:** Otra técnica simple para fomentar la exploración es inicializar los valores de acción de forma optimista (por encima de las recompensas esperadas). Esto hace que las acciones no visitadas parezcan atractivas, animando al agente a explorarlas hasta que las recompensas reales le "decepcionen". Sin embargo, este método es temporal y no es ideal para problemas no estacionarios.
        *   **Boltzmann (Soft-max):** Las fuentes mencionan la selección de acción **soft-max**. Si bien el término "Boltzmann" aparece en el índice, las fuentes proporcionadas no describen explícitamente la selección de acción Boltzmann ni su relación con soft-max. En general, la selección de acción soft-max elige acciones con una probabilidad que depende exponencialmente de sus valores estimados, lo que permite explorar acciones con valores subóptimos pero con menor probabilidad que la acción voraz.

**En resumen:**

Los métodos sin modelo como **SARSA** (on-policy) y **Q-Learning** (off-policy) permiten aprender en RL directamente de la experiencia, sin un modelo explícito del entorno. Ambos son métodos de control TD que actualizan funciones de valor acción. Su principal diferencia radica en cómo manejan la acción siguiente en su actualización, lo que lleva a SARSA a aprender sobre la política *actual* (incluyendo exploración) y a Q-Learning a aprender sobre la política *óptima*. Resolver el dilema de **exploración-explotación** es crucial, y estrategias como **ε-greedy** (con decaimiento) y valores iniciales optimistas son formas de abordarlo, aunque otros métodos como soft-max (relacionado con Boltzmann) también existen.
