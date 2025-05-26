# Semana 5: Juegos Dinámicos con Información Completa

En la semana anterior, introdujimos los **Juegos en Forma Extensiva** como una manera de modelar interacciones estratégicas que se desarrollan a lo largo del tiempo, con jugadores tomando decisiones en secuencia. Vimos que la representación en árbol es fundamental en este contexto.

Esta semana nos centraremos en un tipo particular de juegos extensivos: aquellos con **información completa** (lo que significa que la estructura del juego, incluyendo los pagos, es conocimiento común) y, más específicamente, con **información perfecta**. Un juego tiene **información perfecta** si en cada momento que un jugador debe tomar una decisión, conoce perfectamente todos los eventos previos que han ocurrido. Esto implica saber exactamente qué acciones tomaron todos los jugadores y el azar en los movimientos anteriores. En un árbol de juego con información perfecta, esto se representa porque cada conjunto de información de un jugador contiene exactamente un único nodo. Los juegos de ajedrez o damas son ejemplos típicos.

En estos juegos secuenciales, el concepto de **Equilibrio de Nash** que aprendimos para juegos simultáneos puede ser insuficiente. La razón es que un Equilibrio de Nash puede incluir amenazas o promesas que no serían racionales si el jugador tuviera que cumplirlas más adelante en el juego. Para abordar esto, necesitamos un concepto de solución que exija racionalidad no solo al inicio del juego, sino en cada posible "sub-situación" que pueda surgir.

## Inducción Hacia Atrás (Backward Induction)

Para juegos extensivos **finitos** con **información perfecta**, existe un método poderoso para encontrar las estrategias racionales: la **Inducción Hacia Atrás** (a veces llamada "Backwards Induction").

El principio es simple: comenzamos analizando las decisiones en los **nodos terminales** del árbol (los que llevan directamente a un resultado y pagos) y trabajamos **hacia atrás** hacia la raíz del árbol.

1.  Identificamos los últimos nodos de decisión, es decir, aquellos nodos de un jugador cuyas únicas acciones disponibles conducen directamente a nodos terminales.
2.  Para cada uno de estos nodos de decisión finales, determinamos la acción que maximiza el pago del jugador cuyo turno es mover en ese nodo. Como es la última decisión del jugador, solo considera sus pagos directos para ese punto.
3.  "Podamos" el árbol, reemplazando este subárbol final con el pago resultante de la acción óptima elegida en el paso anterior.
4.  Repetimos el proceso: ahora analizamos los nodos que se han convertido en los nuevos "últimos" nodos de decisión en el árbol podado. Determinamos la acción óptima para el jugador en esos nodos, asumiendo que los jugadores que mueven después jugarán de manera óptima (según ya hemos determinado).
5.  Continuamos este proceso hacia atrás hasta llegar al nodo inicial (la raíz del árbol).

El resultado de la inducción hacia atrás es un **perfil de estrategias puras**, donde cada jugador especifica la acción óptima en cada uno de sus nodos de decisión, asumiendo que el juego pueda llegar a ese nodo y que todos los jugadores subsiguientes también jugarán sus acciones óptimas determinadas por la inducción hacia atrás.

La inducción hacia atrás tiene una propiedad fundamental: para juegos extensivos **finitos** con **información perfecta**, el resultado de la inducción hacia atrás es siempre un **Equilibrio Perfecto en Subjuegos**. Además, el procedimiento de inducción hacia atrás identifica *el conjunto* de Equilibrios Perfectos en Subjuegos en tales juegos.

## Subjuegos y Equilibrio Perfecto en Subjuegos (SPE)

Para formalizar la idea de que las estrategias deben ser racionales "en cada parte del juego", introducimos la noción de **subjuego**.

Un **subjuego** de un juego extensivo con información perfecta es el juego que comienza en cualquier **nodo** (no terminal) del árbol y consiste en ese nodo y todas las acciones, nodos y pagos que le siguen. En un juego con información perfecta, cada nodo no terminal da inicio a un subjuego distinto.

El **Equilibrio Perfecto en Subjuegos (SPE)** es un concepto de solución más restrictivo que el Equilibrio de Nash para juegos extensivos. Un perfil de estrategias se considera un SPE si las estrategias de los jugadores, cuando se restringen a **cualquier subjuego** del juego original, constituyen un **Equilibrio de Nash** en ese subjuego.

La exigencia del SPE es que el plan de acción de cada jugador debe ser óptimo no solo desde el principio del juego, sino también desde cualquier punto intermedio que se pueda alcanzar. Esto descarta estrategias basadas en amenazas no creíbles, porque una amenaza no creíble implicaría una acción subóptima en algún subjuego, lo que violaría la condición de Equilibrio de Nash para ese subjuego. En esencia, el SPE requiere que el jugador reevalue sus planes a medida que el juego avanza.

Como se mencionó, para juegos finitos con información perfecta, el conjunto de estrategias que sobreviven a la inducción hacia atrás coincide con el conjunto de Equilibrios Perfectos en Subjuegos. Para juegos con información perfecta, el concepto de Equilibrio Perfecto en Subjuegos y el de Equilibrio Secuencial (que veremos más adelante para juegos con información imperfecta) coinciden.

## Aplicaciones Simples: Negociaciones Secuenciales

Los juegos de negociación son un área natural de aplicación para los juegos extensivos con información perfecta y el concepto de SPE. Un modelo clásico es el **Juego de Negociación de Ofertas Alternadas**.

Consideremos un escenario simple donde dos jugadores, Jugador 1 y Jugador 2, negocian cómo dividir un "pastel" (un recurso de tamaño 1). Las ofertas se hacen secuencialmente a lo largo del tiempo (o en periodos discretos).

*   En el Periodo 1, el Jugador 1 propone una división (por ejemplo, Jugador 1 recibe $x$, Jugador 2 recibe $1-x$).
*   El Jugador 2 puede aceptar la oferta (y el juego termina con ese resultado) o rechazarla.
*   Si el Jugador 2 rechaza, el juego pasa al Periodo 2. En este periodo, el Jugador 2 propone una división (por ejemplo, Jugador 2 recibe $y$, Jugador 1 recibe $1-y$).
*   El Jugador 1 puede aceptar o rechazar.
*   Este proceso continúa, con los jugadores alternando quién hace la oferta.

Para que los jugadores tengan un incentivo para llegar a un acuerdo pronto, se introduce algún tipo de "costo" del tiempo. Esto puede modelarse de varias maneras:
*   **Descuento:** Los pagos futuros valen menos que los pagos presentes, ponderados por un factor de descuento (los jugadores son impacientes).
*   **Riesgo de ruptura:** En cada periodo, hay una probabilidad exógena de que la negociación se rompa y ambos jugadores reciban un pago de desacuerdo bajo o cero.

Analizar la versión finita de este juego con inducción hacia atrás o, más generalmente, encontrar el SPE en la versión infinita (donde los subjuegos a partir de cada turno de oferta son estructuralmente idénticos al juego completo), revela que, bajo ciertas condiciones, existe un **único SPE** y el acuerdo se alcanza **inmediatamente** en el primer periodo. Por ejemplo, con impaciencia (descuento), la división resultante en el SPE dependerá de los factores de descuento de los jugadores, con el jugador más paciente obteniendo una porción mayor del pastel. El Jugador 1 anticipa la oferta que el Jugador 2 haría si su propia oferta es rechazada, y hace una oferta inicial que deja al Jugador 2 justo indiferente entre aceptar ahora o rechazar y hacer su propia oferta en el siguiente periodo (obteniendo su pago de SPE descontado).

Este modelo simple, resuelto mediante SPE, proporciona una predicción clara sobre cómo se dividirá el recurso y por qué las partes llegan a un acuerdo sin demora en el equilibrio, ilustrando el poder del análisis secuencial y la inducción hacia atrás/SPE en juegos dinámicos con información completa.
