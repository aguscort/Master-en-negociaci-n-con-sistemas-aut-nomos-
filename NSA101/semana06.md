# Semana 6: Juegos con Información Incompleta (Bayesiana)

En semanas anteriores, nos centramos en juegos con **información completa**, donde la estructura del juego (incluyendo los pagos) es conocimiento común entre todos los jugadores. En la Semana 5, además, vimos juegos con **información perfecta**, donde los jugadores conocen toda la historia del juego cuando toman una decisión.

Sin embargo, en la vida real y en muchas aplicaciones interesantes (negociaciones, subastas, interacciones estratégicas entre agentes con diferentes capacidades o preferencias), los jugadores a menudo no están seguros de las características de los otros jugadores. Por ejemplo, un negociador puede no saber cuán ansioso está el otro por llegar a un acuerdo, o una empresa puede no conocer los costos exactos de producción de su competidor.

Estos escenarios se modelan como **Juegos con Información Incompleta**, también conocidos como **Juegos Bayesianos**, un marco desarrollado por John Harsanyi.

## ¿Qué son los Juegos con Información Incompleta?

Un juego tiene **información incompleta** si, al inicio del juego, algunos jugadores tienen información privada sobre el juego que otros jugadores no conocen. Esta información privada puede referirse a los pagos, las acciones disponibles, las creencias o cualquier otra característica relevante del juego o de los otros jugadores.

Harsanyi propuso modelar esta incertidumbre transformando un juego con información incompleta en un juego con **información imperfecta** (donde los jugadores no conocen exactamente qué "estado de la naturaleza" ha ocurrido) pero con **información completa** (la estructura del juego ampliado, incluyendo las posibles "características" de los jugadores y sus probabilidades, es conocimiento común).

## Tipos de Jugadores

El concepto central en los juegos Bayesianos es el de **"tipo"** de un jugador. La información privada inicial que un jugador tiene al comienzo del juego, cuando empieza a planificar sus movimientos, se llama su **tipo**.

*   El tipo de un jugador encapsula toda la información relevante que posee y que no es conocimiento común.
*   Por ejemplo, en una negociación sobre un pastel, el tipo de un jugador podría incluir su valoración del pastel, su paciencia (tasa de descuento), o sus otras oportunidades fuera de la negociación. En un contexto de agentes autónomos, podría ser su función de utilidad específica, su capacidad computacional, o el éxito de una acción pasada que solo él observó.
*   El modelo de Harsanyi asume que la incertidumbre sobre las características de los jugadores se debe a un movimiento inicial de la **"Naturaleza"** (Chance), que asigna un **tipo** a cada jugador de un conjunto de posibles tipos.

Formalmente, en un juego Bayesiano, además del conjunto de jugadores ($N$), acciones ($A_i$ para cada jugador $i$) y funciones de utilidad ($u_i$), hay un conjunto de posibles **estados de la naturaleza** ($\Omega$) o un conjunto de **tipos** para cada jugador ($T_i$). La utilidad de un jugador no solo depende de las acciones tomadas por todos, sino también del estado de la naturaleza o del perfil de tipos. Cada jugador $i$ observa su propio tipo $t_i \in T_i$, pero no el tipo de los otros jugadores $t_{-i} \in T_{-i}$.

## Creencias

Dado que un jugador $i$ conoce su propio tipo $t_i$ pero no el tipo de los demás, su incertidumbre sobre los tipos de los otros jugadores $t_{-i}$ se modela mediante una **creencia**. Una creencia de un jugador $i$ de tipo $t_i$ es una distribución de probabilidad subjetiva sobre los posibles tipos de los otros jugadores $t_{-i} \in T_{-i}$. Esta creencia, denotada $p_i(\cdot|t_i)$, representa lo que el jugador $i$ cree sobre los tipos de los demás, dado que él es de tipo $t_i$.

*   La teoría de decisión Bayesiana postula que un jugador debe tener una distribución de probabilidad subjetiva sobre las incertidumbres.
*   En muchos modelos aplicados, se asume que las creencias de los jugadores son **consistentes con una creencia previa común** (a common prior) sobre el conjunto de todos los perfiles de tipos $(t_1, \dots, t_N)$. Esto significa que todos los jugadores parten de la misma distribución de probabilidad inicial sobre los estados de la naturaleza/perfiles de tipos, y sus creencias $p_i(\cdot|t_i)$ se derivan de esta creencia previa común utilizando la Regla de Bayes, condicionando en su propio tipo observado.

Un aspecto importante es que las decisiones de un jugador no solo dependen de sus creencias sobre los tipos de los demás (creencias de primer orden), sino también de sus creencias sobre lo que los demás creen sobre los tipos de otros (creencias de segundo orden), y así sucesivamente (creencias de orden superior). El modelo de tipos encapsula toda esta jerarquía de creencias.

## Juegos en Forma Normal Bayesiana

Para analizar formalmente los juegos Bayesianos, es común convertirlos a una **forma normal Bayesiana** (también llamada forma estratégica Bayesiana). Esta es una generalización de la forma normal (o estratégica) que vimos en juegos simultáneos con información completa.

En la forma normal Bayesiana:

1.  Los jugadores siguen siendo los mismos ($N$).
2.  Las **estrategias puras** de cada jugador $i$ son funciones que especifican la acción que el jugador $i$ elegiría para *cada posible tipo* que pudiera tener. Si un jugador $i$ tiene un conjunto de tipos $T_i$ y un conjunto de acciones $A_i$, una estrategia pura $s_i$ es una función $s_i: T_i \to A_i$. El conjunto de estrategias puras de $i$, $S_i$, es el conjunto de todas estas funciones posibles.
3.  Los **pagos** se definen para un perfil de estrategias *y* un perfil de tipos. La función de pago de un jugador $i$, $u_i(a_1, \dots, a_n; t_1, \dots, t_n)$, depende de las acciones elegidas y de los tipos de todos los jugadores.

Dado un perfil de estrategias $(s_1, \dots, s_n)$, la utilidad **esperada** de un jugador $i$ de tipo $t_i$ se calcula promediando los pagos posibles sobre los posibles perfiles de tipos de los otros jugadores $t_{-i} \in T_{-i}$, ponderados por la creencia de $i$ sobre estos tipos $p_i(t_{-i}|t_i)$. La acción que tomaría cada jugador $j$ (incluyendo a $i$) si tuviera tipo $t_j$ está dada por la estrategia $s_j(t_j)$. Así, la utilidad esperada para el tipo $t_i$ del jugador $i$ es:

$EU_i(s_1, \dots, s_n | t_i) = \sum_{t_{-i} \in T_{-i}} u_i(s_1(t_1), \dots, s_n(t_n); t_1, \dots, t_n) \cdot p_i(t_{-i}|t_i)$

La utilidad **ex ante** esperada de un jugador $i$ (antes de que se le revele su tipo) es el promedio de sus utilidades esperadas para cada tipo posible, ponderadas por la probabilidad de cada tipo según la creencia previa común:

$EU_i(s_1, \dots, s_n) = \sum_{t_i \in T_i} EU_i(s_1, \dots, s_n | t_i) \cdot p(t_i)$ (donde $p(t_i)$ es la probabilidad del tipo $t_i$ según la creencia previa).

La forma normal Bayesiana inducida tiene como conjunto de "acciones" para cada jugador $i$ el conjunto de sus estrategias puras $S_i$, y como pago de un perfil de estrategias $(s_1, \dots, s_n)$ para el jugador $i$, su utilidad *ex ante* esperada $EU_i(s_1, \dots, s_n)$.

## Equilibrio Bayesiano de Nash (Bayes-Nash Equilibrium - BNE)

El concepto de solución principal para los juegos Bayesianos es el **Equilibrio Bayesiano de Nash**. Se define de manera análoga al Equilibrio de Nash para juegos con información completa: un perfil de estrategias es un BNE si la estrategia de cada jugador es una mejor respuesta a las estrategias de los otros jugadores. La diferencia radica en que, en los juegos Bayesianos, la "mejor respuesta" debe considerar la incertidumbre sobre los tipos de los demás y maximizar la utilidad **esperada**.

Un perfil de estrategias $(s_1^*, \dots, s_n^*)$ es un Equilibrio Bayesiano de Nash si, para cada jugador $i$ y para cada tipo posible $t_i \in T_i$, la acción especificada por $s_i^*(t_i)$ es una mejor respuesta a las estrategias de los otros jugadores $s_{-i}^*(\cdot)$ (que son funciones de sus tipos), dadas las creencias del jugador $i$ de tipo $t_i$ sobre los tipos de los demás:

Para todo $i \in N$ y todo $t_i \in T_i$,
$s_i^*(t_i) \in \argmax_{a_i \in A_i} \sum_{t_{-i} \in T_{-i}} u_i(s_1^*(t_1), \dots, s_i^*(t_i)=a_i, \dots, s_n^*(t_n); t_1, \dots, t_n) \cdot p_i(t_{-i}|t_i)$

Es crucial notar que la condición de mejor respuesta debe cumplirse para *cada tipo* posible de cada jugador. Incluso si un jugador $i$ sabe que es de tipo $t_i$, su estrategia $s_i^*$ debe especificar acciones óptimas para *todos* sus tipos posibles $t_i' \in T_i$. Esto se debe a que, para que el jugador $i$ de tipo $t_i$ calcule su utilidad esperada, necesita saber qué harían los otros jugadores $j$ para *todos* sus tipos posibles $t_j' \in T_j$, lo cual viene dado por sus estrategias $s_j^*(t_j')$. A su vez, las estrategias $s_j^*$ solo son óptimas si son mejores respuestas para *cada* tipo de $j$.

La existencia del Equilibrio Bayesiano de Nash está garantizada en juegos finitos (con conjuntos finitos de jugadores, tipos y acciones) porque, como mencionamos, un juego Bayesiano puede transformarse en un juego en forma normal (mucho más grande) cuyas estrategias son las funciones tipo-a-acción, y cuyos pagos son las utilidades ex ante esperadas. Los Equilibrios Bayesiano de Nash del juego Bayesiano corresponden precisamente a los Equilibrios de Nash de esta forma normal inducida. El Teorema de Nash sobre la existencia de Equilibrios de Nash en estrategias mixtas (o puras en ciertos casos) se aplica directamente a esta forma normal inducida.

El BNE es un concepto de equilibrio que exige racionalidad condicionada a la información privada de cada jugador (su tipo). Como ejemplo de por qué es necesario, el análisis de equilibrios de Nash para cada posible "sub-juego de información completa" (donde los tipos de todos fueran conocidos) por separado puede llevar a predicciones absurdas en el juego Bayesiano real, porque los jugadores podrían tener incentivos para "manipular" la información si la comunicación fuera posible. El BNE integra la incertidumbre y las creencias de manera coherente desde el principio.

En resumen, esta semana hemos dado un salto a los juegos donde la incertidumbre sobre los demás es fundamental. El modelo Bayesiano de Harsanyi, utilizando tipos y creencias, nos permite representar esta incertidumbre y encontrar un concepto de equilibrio, el Equilibrio Bayesiano de Nash, que extiende la idea de racionalidad estratégica a este contexto de información incompleta.
