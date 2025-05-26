# Semana 2: Dominancia y Eliminación Iterada

En la semana anterior, definimos los juegos en forma normal (o estratégica), donde los jugadores eligen sus acciones simultáneamente. Esta semana, exploraremos cómo la racionalidad de los jugadores puede ayudarnos a predecir o refinar el conjunto de posibles resultados, eliminando estrategias que un agente racional nunca elegiría.

El concepto clave aquí es la **dominancia**: una estrategia es dominada si existe otra estrategia que siempre le ofrece al jugador un resultado al menos tan bueno, y a veces estrictamente mejor, sin importar lo que hagan los otros jugadores. Esta idea se aplica a los juegos en forma estratégica.

Existen diferentes "sabores" o tipos de dominancia, que tienen distintas implicaciones para el análisis: la dominancia estricta y la dominancia débil.

## Estrategias Estrictamente Dominadas

Una **estrategia estrictamente dominada** es aquella que un jugador racional **nunca elegiría**. Es el tipo de dominancia más fuerte.

*   **Definición Formal:** Una acción (o estrategia pura) `a_i` de un jugador `i` en un juego estratégico es **estrictamente dominada** si existe una **estrategia mixta** `α_i` (una distribución de probabilidad sobre las acciones puras de `i`) tal que el pago esperado de `α_i` es **estrictamente mayor** que el pago de `a_i`, *para cualquier posible combinación de acciones* de los otros jugadores [15, 59 footnote]. En juegos finitos, esta definición es equivalente a que la estrategia `a_i` sea estrictamente dominada por una estrategia *pura* si el conjunto de acciones de los oponentes es finito.
*   **Base Racional:** Una estrategia estrictamente dominada es una **"never-best response"**. Esto significa que, sin importar las creencias que un jugador tenga sobre lo que harán los otros jugadores, nunca será óptimo (nunca será una mejor respuesta) jugar una estrategia estrictamente dominada. Por lo tanto, un jugador racional, que busca maximizar su pago esperado, nunca elegirá una estrategia estrictamente dominada.
*   **Eliminación Iterada de Estrategias Estrictamente Dominadas:** Dado que las estrategias estrictamente dominadas nunca serán elegidas por jugadores racionales, podemos eliminarlas del juego. Este proceso se puede repetir: una vez que se eliminan algunas estrategias, otras que antes no eran estrictamente dominadas podrían volverse estrictamente dominadas en el juego reducido. Este procedimiento de **eliminación iterada de estrategias estrictamente dominadas** (Iterated Elimination of Strictly Dominated Actions) es un concepto de solución deductivo.
    *   Una propiedad crucial de este proceso es que el **orden en que se eliminan las estrategias estrictamente dominadas no afecta el conjunto final** de estrategias que sobreviven. Este es un resultado matemático importante (relacionado con la propiedad Church-Rosser).
    *   Este procedimiento **preserva el conjunto de Equilibrios de Nash** del juego original. Esto significa que cualquier Equilibrio de Nash del juego original se encuentra dentro del conjunto de estrategias que sobreviven a la eliminación iterada estricta.
    *   En juegos finitos, el conjunto de perfiles de acciones que sobreviven a la eliminación iterada de estrategias estrictamente dominadas es exactamente el conjunto de perfiles de acciones **racionalizables**.

## Estrategias Débilmente Dominadas

Las estrategias débilmente dominadas son similares a las estrictamente dominadas, pero la condición de dominancia es menos estricta.

*   **Definición:** Una acción (o estrategia pura) de un jugador es **débilmente dominada** si existe otra estrategia (pura o mixta) para ese jugador que le da un pago **al menos tan bueno** contra cualquier combinación de acciones de los oponentes, y un pago **estrictamente mejor** contra **al menos una** combinación de acciones de los oponentes.
*   **Base Racional (Más Cuestionable):** A diferencia de las estrategias estrictamente dominadas, una estrategia débilmente dominada *puede ser* una mejor respuesta si el jugador cree con certeza (probabilidad 1) que sus oponentes no elegirán las acciones que la hacen estrictamente peor que la estrategia dominante. Dado que no hay una ventaja estricta en usar una estrategia débilmente dominada, eliminarla parece natural como método de simplificación, pero el argumento racional para su eliminación es más débil que para la dominancia estricta.
*   **Eliminación Iterada de Estrategias Débilmente Dominadas:** Al igual que con la dominancia estricta, se puede definir un proceso de eliminación iterada para estrategias débilmente dominadas. Sin embargo, un problema técnico importante surge aquí: el **orden en que se eliminan las estrategias débilmente dominadas puede afectar el conjunto final** de estrategias que sobreviven al proceso. Esto hace que el resultado de la eliminación iterada débil sea sensible a la secuencia de eliminación elegida. A pesar de esto, es una herramienta útil en el análisis de juegos y se utiliza en relación con otros conceptos de solución, como el equilibrio perfecto en subjuegos.

## Relación con el Equilibrio de Nash

La dominancia y el Equilibrio de Nash son ambos conceptos de solución, pero operan de manera diferente y tienen distintas "fuerzas" predictivas:

*   **Dominancia y Existencia de Nash:** Si en un juego cada jugador tiene una **estrategia dominante** (ya sea estricta o débil), entonces el perfil donde cada jugador juega su estrategia dominante es un **Equilibrio de Nash**. Si las estrategias son **estrictamente dominantes** para todos, este perfil de estrategias dominantes es el **único Equilibrio de Nash** del juego.
*   **Eliminación Estricta y Nash:** Como se mencionó, la eliminación iterada *estricta* es consistente con el Equilibrio de Nash, ya que preserva el conjunto de equilibrios. Esto significa que si un perfil de estrategias es un Equilibrio de Nash, todas las estrategias que lo componen deben sobrevivir a cualquier secuencia de eliminación iterada estricta.
*   **Dominancia vs. Equilibrio de Nash:**
    *   Una estrategia dominante es una mejor respuesta contra *cualquier* acción de los oponentes.
    *   Una estrategia que es parte de un Equilibrio de Nash es una mejor respuesta solo contra las *estrategias de equilibrio* (posiblemente mixtas) de los oponentes.
*   **Conceptos de Solución:** La racionalizabilidad y la eliminación iterada de estrategias dominadas (especialmente la estricta) se consideran conceptos de solución "deductivos" que identifican estrategias "razonables" o aquellas que no serían jugadas por agentes racionales que asumen la racionalidad de los demás. El Equilibrio de Nash se considera un concepto de solución más "fuerte", a menudo interpretado como un estado estacionario donde cada jugador tiene conocimiento del equilibrio. El conjunto de Equilibrios de Nash es típicamente un subconjunto (posiblemente más pequeño) del conjunto de perfiles de estrategias que sobreviven a la eliminación iterada estricta.

En resumen, la dominancia, en sus variantes estricta y débil, nos permite eliminar estrategias que son claramente inferiores. La eliminación iterada de estrategias estrictamente dominadas es una poderosa herramienta analítica que, al preservar el conjunto de Equilibrios de Nash y ser independiente del orden, nos ayuda a acotar el conjunto de resultados posibles en juegos donde la racionalidad y el conocimiento común de la racionalidad son supuestos clave.
