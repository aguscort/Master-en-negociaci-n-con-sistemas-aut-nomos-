### Semana 4: Introducción a MARL, Juegos Estocásticos y Tipos de Entornos Multiagente

Hasta ahora, nos hemos centrado en el problema de un **solo agente** que aprende a tomar decisiones secuenciales en un entorno para maximizar su recompensa a largo plazo. Sin embargo, en muchos escenarios del mundo real (como robótica de enjambre, juegos online, mercados económicos), múltiples agentes autónomos interactúan y aprenden simultáneamente. Aquí es donde entra el **Aprendizaje por Refuerzo Multiagente (MARL)**.

En MARL, el entorno ya no es estático desde la perspectiva de un agente; cambia en función de las acciones *de todos los agentes*. El "entorno" de un agente incluye ahora a los otros agentes, que también están aprendiendo y adaptando sus estrategias. Esta interdependencia hace que el aprendizaje sea significativamente más complejo.

1.  **Juegos Estocásticos (Multiagent MDPs) como Formalismo**
    *   Para formalizar la toma de decisiones secuenciales con múltiples agentes que interactúan, el modelo estándar utilizado es el de los **Juegos Estocásticos**. A veces se les conoce informalmente como Multiagent MDPs (MMDPs), ya que son una extensión natural de los Procesos de Decisión de Markov (MDPs) al caso multiagente.
    *   Un Juego Estocástico es conceptualmente una colección de juegos en forma normal que se juegan repetidamente.
    *   Formalmente, un Juego Estocástico incluye un conjunto de jugadores $N$, un conjunto de estados del mundo (o "estados de la naturaleza", o simplemente "estados" como en MDPs), y para cada jugador, un conjunto de acciones (o "movimientos") posibles.
    *   La clave es que el estado del sistema transiciona probabilísticamente en función del estado actual y de las **acciones conjuntas** de *todos* los agentes.
    *   Además, cada agente recibe una recompensa (que puede ser individual o compartida) después de cada transición.
    *   Los Juegos Estocásticos son un marco muy amplio que **generaliza** tanto a los MDPs (que son Juegos Estocásticos con un solo jugador) como a los Juegos Repetidos (que son Juegos Estocásticos con un solo juego de etapa).

2.  **Tipos de Entornos Multiagente (Según la Interacción)**
    La naturaleza de la interacción entre los agentes define diferentes tipos de entornos multiagente, lo que a su vez influye en los objetivos de aprendizaje y los algoritmos apropiados. Las fuentes clasifican los juegos de diversas maneras, pero una distinción fundamental, especialmente relevante en MARL, se basa en si los intereses de los agentes están alineados o en conflicto:

    *   **Entornos Cooperativos Puros:**
        *   En estos entornos, todos los agentes comparten un **objetivo común** y reciben la **misma señal de recompensa**.
        *   Los agentes buscan maximizar una **recompensa conjunta** o una medida de bienestar colectivo.
        *   El principal desafío es la **coordinación** entre los agentes para lograr el mejor resultado para el grupo. La teoría de juegos cooperativos a menudo analiza cómo los grupos de jugadores ("coaliciones") pueden trabajar juntos y cómo se deben dividir los beneficios.
        *   Desde la perspectiva de un solo agente, otros agentes no son adversarios, sino compañeros de equipo.

    *   **Entornos Competitivos Puros:**
        *   Los agentes tienen **intereses opuestos**.
        *   El caso extremo es el de los **juegos de suma cero** (o juegos estrictamente competitivos), donde la ganancia de un agente es exactamente igual a la pérdida de los otros agentes, por lo que la suma de las recompensas es siempre cero.
        *   El objetivo de un agente es maximizar su propia recompensa, lo que inherentemente implica minimizar la recompensa de los oponentes.
        *   Conceptos de solución como las estrategias minimax son relevantes aquí, donde un agente elige una estrategia que minimiza su pérdida máxima, asumiendo que los oponentes jugarán para maximizarla.

    *   **Entornos Mixtos (o de Suma No Cero):**
        *   La mayoría de los escenarios multiagente del mundo real caen en esta categoría.
        *   Los agentes tienen una **mezcla de intereses cooperativos y competitivos**.
        *   Puede haber oportunidades para la cooperación mutua, pero también incentivos para actuar egoístamente en detrimento de otros.
        *   El famoso juego del **Dilema del Prisionero** es un ejemplo clásico de un juego de suma no cero con incentivos mixtos. La versión repetida de este juego es fundamental para estudiar la emergencia de la cooperación a través de estrategias condicionales (como "ojo por ojo" o Tit-for-Tat).
        *   Los problemas de negociación también son ejemplos de juegos de suma no cero, donde los jugadores pueden cooperar para llegar a un acuerdo (beneficio mutuo), pero compiten sobre los términos de ese acuerdo (distribución del beneficio).

En síntesis, al pasar de RL a MARL, cambiamos el foco de un agente aislado a sistemas de múltiples agentes que interactúan estratégicamente. Los **Juegos Estocásticos** proporcionan el formalismo matemático para modelar estos sistemas secuenciales multiagente. La clasificación de los entornos en **cooperativos, competitivos y mixtos** es crucial porque determina los objetivos de aprendizaje de los agentes y los tipos de algoritmos y conceptos de solución de la teoría de juegos (como Nash equilibrium, que es un concepto clave mencionado en otras partes de las fuentes para juegos estratégicos) que son aplicables.
