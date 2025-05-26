### Semana 2: Ecuaciones de Bellman, Predicción y Control, Iteración de Valor y Política

En esta segunda semana, exploramos la estructura matemática de los Procesos de Decisión de Markov (MDPs) centrándonos en las **Ecuaciones de Bellman**, cómo los problemas de **predicción** y **control** se abordan dentro de este marco, y los algoritmos de **Programación Dinámica (DP)** como **Iteración de Política** e **Iteración de Valor** que permiten encontrar soluciones óptimas cuando el modelo del entorno es conocido.

1.  **Las Ecuaciones de Bellman**
    *   Las funciones de valor, tanto la función de valor de estado $v_\pi(s)$ como la función de valor de acción $q_\pi(s, a)$, satisfacen un conjunto de relaciones recursivas fundamentales llamadas **Ecuaciones de Bellman**.
    *   Estas ecuaciones expresan el **valor de un estado** (o de un par estado-acción) en términos de los valores de los **estados (o pares estado-acción) sucesores**.
    *   Capturan la idea de que el valor de una situación se basa en las recompensas inmediatas esperadas más el valor descontado de las situaciones futuras a las que se puede llegar. Las ecuaciones promedian sobre todas las posibilidades de transición del entorno, ponderadas por sus probabilidades.
    *   Son la **base teórica** de muchos algoritmos de Aprendizaje por Refuerzo.

    *   **Ecuación de Bellman para $v_\pi$**: Para una política $\pi$ dada, el valor de un estado $s$, $v_\pi(s)$, puede expresarse en términos del valor de los estados sucesores posibles:
        $v_\pi(s) = E_\pi[R_{t+1} + \gamma v_\pi(S_{t+1}) | S_t=s]$
        Expandiendo la expectativa, considerando las acciones que toma la política $\pi$ y las transiciones del entorno $p(s', r|s, a)$:
        $v_\pi(s) = \sum_{a} \pi(a|s) \sum_{s',r} p(s', r|s, a) [r + \gamma v_\pi(s')]$
        La función de valor $v_\pi$ es la **única solución** a su Ecuación de Bellman (implícito en).

    *   **Ecuación de Bellman de Optimalidad para $v^*$**: Para la función de valor óptima de estado $v^*$, la relación se convierte en una maximización sobre las acciones, ya que el agente actúa óptimamente:
        $v^*(s) = \max_{a} E[R_{t+1} + \gamma v^*(S_{t+1}) | S_t=s, A_t=a]$
        Expandiendo:
        $v^*(s) = \max_{a} \sum_{s',r} p(s', r|s, a) [r + \gamma v^*(s')]$
        Esta es la Ecuación de Bellman de Optimalidad para $v^*$, popularizada por Richard Bellman como la "ecuación funcional básica". Para MDPs finitos, esta ecuación tiene una **solución única**.

    *   También existen Ecuaciones de Bellman para las funciones de valor de acción $q_\pi$ y $q^*$. La Ecuación de Bellman de Optimalidad para $q^*$ es:
        $q^*(s, a) = \sum_{s',r} p(s', r|s, a) [r + \gamma \max_{a'} q^*(s', a')]$
        La función $q^*$ es la **única solución** a su Ecuación de Bellman de Optimalidad (implícito en). La política óptima puede ser recuperada fácilmente de $q^*$, ya que $\pi^*(s) = \arg \max_a q^*(s, a)$.

2.  **El Problema de Predicción y Control**
    *   El Aprendizaje por Refuerzo a menudo distingue entre dos tareas principales:
        *   **Predicción:** **Evaluar una política dada**. Esto significa calcular o estimar la función de valor ($v_\pi$ o $q_\pi$) para una política $\pi$ que ya conocemos. En la literatura de DP, esto se llama **Evaluación de Política**.
        *   **Control:** **Encontrar una política óptima** ($\pi^*$). Esto implica encontrar las funciones de valor óptimas ($v^*$ o $q^*$) asociadas a una política que maximiza el retorno esperado.

3.  **Programación Dinámica (DP)**
    *   La Programación Dinámica es un conjunto de algoritmos utilizados para calcular **políticas óptimas asumiendo un modelo perfecto del entorno** como un MDP (es decir, se conocen las probabilidades de transición $p(s', r|s, a)$).
    *   Aunque los algoritmos de DP clásicos tienen limitaciones prácticas (requieren el modelo y pueden ser computacionalmente costosos), son **teóricamente muy importantes**. Proporcionan la base sobre la cual se construyen muchos métodos de RL.
    *   Los algoritmos de DP convierten las Ecuaciones de Bellman correspondientes (para $v_\pi$, $v^*$, etc.) en **reglas de actualización iterativas**. Estas actualizaciones "propagan" información de valor hacia atrás a través del espacio de estados.
    *   Típicamente, operan haciendo "barridos" (sweeps) sobre el conjunto de estados, aplicando una operación de actualización a cada estado.

4.  **Iteración de Política (Policy Iteration)**
    *   La Iteración de Política es un método de DP para resolver el problema de control [implícito en 46]. Fue desarrollada por Ronald Howard.
    *   Funciona mediante un **ciclo que alterna entre dos pasos principales**:
        *   **Evaluación de Política:** Dada una política $\pi$ actual, se calcula su función de valor $v_\pi$. Esto se hace iterativamente utilizando la Ecuación de Bellman para $v_\pi$ como regla de actualización hasta que $v_\pi$ converge:
            $v_{k+1}(s) = \sum_{a} \pi(a|s) \sum_{s',r} p(s', r|s, a) [r + \gamma v_k(s')]$ [similar a 47, 39]
        *   **Mejora de Política:** Dada la función de valor $v_\pi$ calculada, se deriva una nueva política $\pi'$ que es **voraz (greedy)** con respecto a $v_\pi$. Esto significa que para cada estado $s$, la nueva política elige la acción que maximiza $E[R_{t+1} + \gamma v_\pi(S_{t+1}) | S_t=s, A_t=a]$ [similar a la lógica de 47, 76]. Esto a menudo se calcula implícitamente o explícitamente a través de $q_\pi(s, a)$. Si la nueva política $\pi'$ es diferente de $\pi$, se repite el ciclo con $\pi'$. Si $\pi' = \pi$, entonces la política actual debe ser la política óptima $\pi^*$ [similar a la descripción de Policy Improvement en 76-80].
    *   La Iteración de Política es un ejemplo de **Generalized Policy Iteration (GPI)**.

5.  **Iteración de Valor (Value Iteration)**
    *   La Iteración de Valor es otro método de DP para resolver el problema de control.
    *   Puede verse como un caso especial de Iteración de Política donde la fase de Evaluación de Política se detiene después de **una sola iteración** de actualización [implícito por comparación de algoritmos en fuentes como 49].
    *   Utiliza la **Ecuación de Bellman de Optimalidad para $v^*$** como la regla de actualización iterativa:
        $v_{k+1}(s) = \max_{a} \sum_{s',r} p(s', r|s, a) [r + \gamma v_k(s')]$ [49, similar a 47]
    *   Este proceso iterativo converge a la función de valor óptima $v^*$.
    *   Una vez que $v^*$ se ha calculado, la política óptima $\pi^*$ se puede derivar fácilmente tomando la acción voraz en cada estado con respecto a $v^*$ (o $q^*$ si se usa la versión de Iteración de Valor para $q^*$).
    *   La iteración de valor para $q^*$ utiliza la Ecuación de Bellman de Optimalidad para $q^*$ como regla de actualización:
        $q_{k+1}(s, a) = \sum_{s',r} p(s', r|s, a) [r + \gamma \max_{a'} q_k(s', a')]$ [29, similar a 47]

6.  **Convergencia**
    *   Los algoritmos de Programación Dinámica, como la evaluación de política iterativa, la iteración de política y la iteración de valor, están **garantizados para converger** a las funciones de valor (de política o óptimas) y políticas óptimas correspondientes.
    *   La convergencia ocurre cuando las actualizaciones ya no producen cambios significativos en los valores, lo que indica que se ha alcanzado el punto fijo de la Ecuación de Bellman relevante.
    *   Esta convergencia está garantizada bajo condiciones estándar para MDPs (por ejemplo, factor de descuento $\gamma < 1$ o tareas episódicas) (conceptos de MDPs discutidos en fuentes como).
    *   Es importante notar que, si bien la DP con un modelo conocido converge, la combinación de aprendizaje a partir de la experiencia (bootstrapping), la aproximación de funciones y el entrenamiento off-policy puede llevar a la divergencia ("la triada mortal"), un problema que no ocurre en la DP clásica tabular.

En resumen, las Ecuaciones de Bellman son las relaciones fundamentales que definen las funciones de valor. Los problemas de RL se dividen en Predicción (evaluar una política) y Control (encontrar la política óptima). La Programación Dinámica (DP) ofrece soluciones a estos problemas cuando se conoce el modelo del entorno, utilizando la Iteración de Política y la Iteración de Valor, algoritmos iterativos basados en las Ecuaciones de Bellman, que están garantizados para converger a la solución óptima en este contexto.
