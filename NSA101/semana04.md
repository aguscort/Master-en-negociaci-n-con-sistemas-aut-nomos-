# Semana 4: Juegos en Forma Extensiva

En la Semana 3, estudiamos el Equilibrio de Nash, un concepto de solución central para juegos donde los jugadores eligen sus estrategias simultáneamente (juegos en forma estratégica o normal). Sin embargo, muchas situaciones de interacción estratégica se desarrollan a lo largo del tiempo, con jugadores tomando decisiones en secuencia y, a menudo, conociendo (parcial o totalmente) las acciones pasadas de otros. Los **juegos en forma extensiva** son el modelo diseñado para capturar esta estructura temporal y secuencial.

## Juegos en Forma Extensiva: La Estructura Secuencial

La forma extensiva es una descripción detallada de la estructura secuencial de los problemas de decisión que encuentran los jugadores en una situación estratégica. A diferencia de un juego estratégico, donde cada jugador elige su plan de acción "de una vez por todas" y las decisiones se consideran simultáneas (sin información sobre las elecciones de otros al decidir), el modelo de juego extensivo permite a un jugador considerar su plan de acción no solo al principio, sino también en cualquier momento en el que deba tomar una decisión.

Un juego extensivo es un **modelo dinámico**. Especifica las posibles órdenes de los eventos y cuándo y con qué información cada jugador debe tomar una decisión. Esta representación, a menudo visualizada como un árbol, es generalmente **exponencialmente más pequeña** que la forma normal inducida para el mismo juego, y a menudo más natural para razonar.

## Árboles de Juego

Aunque formalmente un juego extensivo se puede definir mediante componentes como el conjunto de jugadores, historias posibles y funciones de jugador que indican quién mueve después de cada historia, la manera más intuitiva y común de representar un juego extensivo, especialmente con información perfecta, es como un **árbol**.

*   En esta formulación, cada **nodo** del árbol corresponde a una **historia** posible del juego, es decir, una secuencia de acciones que llevaron a ese punto. La raíz del árbol es la historia inicial vacía.
*   Las **aristas** (o ramas) que salen de un nodo representan las **acciones** disponibles para el jugador cuyo turno es mover en ese nodo.
*   Los **nodos terminales** (las hojas del árbol) representan las **historias finales** o resultados posibles del juego. A cada nodo terminal se le asocia un **perfil de pagos** que especifica la utilidad (o preferencia) de cada jugador por ese resultado.
*   También puede haber nodos de "azar" para modelar la incertidumbre exógena. Las ramas que salen de un nodo de azar tienen probabilidades asociadas.

La definición precisa del juego especifica quién mueve en cada nodo no terminal, qué acciones están disponibles, cómo se agrupan los nodos en conjuntos de información (más sobre esto en Información Perfecta vs. Imperfecta), y las preferencias de los jugadores sobre los resultados terminales.

## Información Perfecta vs. Imperfecta

Una distinción fundamental en los juegos en forma extensiva es si los jugadores tienen **información perfecta** o **imperfecta** sobre las acciones pasadas.

1.  **Juegos con Información Perfecta:**
    *   **Definición:** Un juego extensivo tiene información perfecta si, cada vez que un jugador debe tomar una decisión (en cualquier nodo), está **perfectamente informado de todos los eventos que han ocurrido previamente**. Esto significa que el jugador sabe exactamente qué acciones tomaron los otros jugadores y el azar en todos los movimientos anteriores.
    *   **Característica Clave:** En la representación en árbol, esto implica que **cada nodo de decisión pertenece a un conjunto de información que contiene solo ese nodo**. El jugador, al estar en ese nodo, sabe precisamente dónde se encuentra en el árbol.
    *   **Ejemplos Típicos:** Juegos de mesa secuenciales como el ajedrez o las damas son ejemplos clásicos de juegos con información perfecta. Los juegos de negociación de ofertas alternadas también suelen modelarse con información perfecta.
    *   **Restricciones Simplificadoras (iniciales):** Para simplificar, a menudo se comienza estudiando juegos con información perfecta donde no hay dos jugadores moviendo al mismo tiempo y no hay movimientos de azar, aunque estos últimos pueden incorporarse.

2.  **Juegos con Información Imperfecta:**
    *   **Definición:** Un juego extensivo tiene información imperfecta si un jugador, al tomar una acción en un nodo, puede tener solo **información parcial sobre las acciones tomadas previamente**.
    *   **Característica Clave:** Para modelar esto, los nodos de decisión de cada jugador se agrupan en **conjuntos de información**. Si dos o más nodos pertenecen al mismo conjunto de información, el jugador **no puede distinguir entre ellos**. Es decir, cuando el jugador se encuentra en un nodo dentro de un conjunto de información con múltiples nodos, sabe que está en *alguno* de esos nodos, pero no sabe en cuál específicamente. La representación visual utiliza líneas punteadas o agrupaciones para indicar qué nodos son indistinguibles para un jugador. Las acciones disponibles deben ser las mismas en todos los nodos dentro de un mismo conjunto de información.
    *   **Ejemplos Típicos:** La mayoría de los juegos de cartas son juegos con información imperfecta (los jugadores no saben qué cartas tienen los oponentes o cuáles han salido exactamente del mazo). Los juegos con movimientos simultáneos (como el Dilema del Prisionero o Batalla de los Sexos) también pueden representarse como juegos extensivos con información imperfecta, donde los movimientos del oponente se agrupan en un único conjunto de información para reflejar la falta de conocimiento sobre su elección al momento de decidir.
    *   **Conceptos Relacionados:** La **información incompleta** (incertidumbre sobre las funciones de pagos o tipos de jugadores) a menudo se modela transformándola en información imperfecta mediante la introducción de nodos de azar iniciales. La noción de **recuerdo perfecto** (perfect recall) es otra propiedad relacionada con la información, donde un jugador recuerda todo lo que sabía previamente.

## Estrategias en Forma Extensiva

En un juego extensivo, una **estrategia** de un jugador es un **plan completo de acciones** que especifica qué acción elegirá el jugador en **cada punto donde tenga que tomar una decisión**, basándose en la información que tiene en ese momento.

*   **Para Juegos con Información Perfecta:** Una estrategia pura especifica una acción para cada **nodo** del árbol en el que el jugador tiene que mover. Incluso si un nodo particular no se alcanza jugando esa estrategia, la estrategia debe especificar una acción para ese nodo, ya que la estrategia es un plan *completo* que cubre todas las contingencias posibles.
*   **Para Juegos con Información Imperfecta:** Una estrategia pura especifica una acción para cada **conjunto de información** del jugador. Esto es porque el jugador no puede distinguir entre los nodos dentro de un mismo conjunto de información, por lo que su elección debe ser la misma para todos ellos. La estrategia asigna una acción a lo que el jugador sabe en ese momento (su conjunto de información).
*   **Pure vs. Mixed vs. Behavioral Strategies:**
    *   Una **estrategia pura** es una elección determinista para cada punto de decisión (o conjunto de información).
    *   Una **estrategia mixta** es una distribución de probabilidad sobre el conjunto de estrategias puras del jugador.
    *   Una **estrategia de comportamiento (behavioral strategy)**, particularmente relevante en juegos extensivos, es una colección de distribuciones de probabilidad, una para cada conjunto de información del jugador, especificando las probabilidades con las que elige cada acción disponible *en ese conjunto de información*. En juegos con recuerdo perfecto, cualquier estrategia mixta tiene una estrategia de comportamiento equivalente en términos de resultados. Sin embargo, en juegos sin recuerdo perfecto, una estrategia de comportamiento puede no ser equivalente a ninguna estrategia mixta.

La definición de estrategia es crucial porque permite representar el juego extensivo como un juego estratégico equivalente (la "forma estratégica inducida" o "normal representation"), donde los jugadores eligen sus estrategias (planes completos) simultáneamente al principio del juego. Sin embargo, esta conversión puede ocultar la estructura secuencial y llevar a redundancias, como vimos en la relación entre la forma normal y la extensiva.

## Más Allá de Nash en Juegos Extensivos

Si bien los Equilibrios de Nash de un juego extensivo pueden encontrarse analizando su forma estratégica inducida, el concepto de Nash tiene limitaciones en juegos secuenciales. Un perfil de estrategias de Nash puede incluir amenazas "no creíbles" o planes de acción subóptimos en partes del árbol de juego que no se alcanzan si todos juegan el equilibrio. Esto ignora la naturaleza secuencial del juego y la posibilidad de que los jugadores "reconsideren sus planes" a medida que avanza el juego.

Por esta razón, en juegos extensivos, especialmente con información perfecta, se utilizan conceptos de solución más refinados, como el **Equilibrio Perfecto en Subjuegos** (Subgame Perfect Equilibrium), que exige que las estrategias constituyan un Equilibrio de Nash en cada "subjuego" del juego original (es decir, en cada posible continuación a partir de cualquier nodo). Esto nos lleva naturalmente a los temas de la próxima semana.
