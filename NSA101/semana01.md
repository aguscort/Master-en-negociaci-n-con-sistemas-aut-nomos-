# Semana 1: Introducción y Repaso

## Definición de un Juego

La Teoría de Juegos se ocupa del estudio de situaciones en las que los resultados dependen de las acciones conjuntas de varios **tomadores de decisiones** (o jugadores) que interactúan estratégicamente. Un **juego** se define como una descripción de esta interacción estratégica.

La descripción de un juego incluye:
*   Las **restricciones** sobre las **acciones** que los **jugadores** pueden tomar.
*   Los **intereses** de los **jugadores**.

Es crucial notar que la definición de un juego describe la estructura de la interacción, pero **no especifica las acciones que los jugadores realmente toman**.

Un concepto relacionado es el de **solución**, que es una descripción sistemática de los **resultados** que **pueden surgir** en una familia de juegos. La teoría de juegos sugiere soluciones razonables para clases de juegos y examina sus propiedades.

Desde una perspectiva de **Ciencias Sociales**, la teoría de juegos busca entender el **comportamiento de agentes que interactúan**. Desde la perspectiva de los **Sistemas Multiagente**, los juegos modelan las interacciones entre **múltiples agentes inteligentes**.

## Jugadores

Los **jugadores** son los individuos o **agentes** que participan en la interacción estratégica. En el contexto de este curso, nos enfocamos en **agentes autónomos** [Título del curso], que en Sistemas Multiagente (MAS) tienen la capacidad de acción autónoma e interacción social.

Un juego tiene un conjunto de **jugadores** (denominado N en la notación formal). Se asume típicamente que los jugadores son **racionales**, lo que implica que toman decisiones de manera **consistente** en la búsqueda de sus propios objetivos [Análisis de la introducción].

Sin embargo, la teoría de juegos en su forma actual a menudo **omite diferencias en las habilidades** de los individuos. Al modelar juegos como el ajedrez, por ejemplo, se asume conocimiento perfecto de las reglas y habilidad analítica ideal, lo cual puede hacer que el juego parezca trivial teóricamente aunque sea complejo en la práctica debido a las limitaciones humanas. Esto es una simplificación de la **racionalidad acotada** (bounded rationality).

## Acciones, Resultados y Pagos

*   **Acciones (o Movimientos):** Son las opciones que los jugadores pueden tomar en un juego. En la forma estratégica, cada jugador elige una acción de su conjunto de acciones, y estas decisiones se toman **simultáneamente**.
*   **Estrategias:** Una **estrategia** de un jugador es un **plan** que especifica las acciones que elegirá en función de las circunstancias o la historia del juego [20, 59 footnote, 60, 87]. Para los juegos en **forma estratégica** (donde las decisiones son simultáneas), una estrategia pura es simplemente la elección de una acción.
*   **Resultados:** Son las configuraciones finales que surgen de las acciones elegidas por los jugadores. En juegos extensivos, un resultado puede ser una historia terminal.
*   **Pagos (o Utilidades):** Representan los **intereses** o **preferencias** de los jugadores sobre los resultados. Formalmente, se utilizan **funciones de utilidad** (u_i) que asignan un valor numérico real (R) a cada posible **perfil de acciones** (una combinación de acciones, una para cada jugador).

Cuando se permite que las elecciones de los jugadores sean **no determinísticas** (como en el caso de las estrategias mixtas) o hay **incertidumbre**, las preferencias de los jugadores se definen sobre **loterías** (distribuciones de probabilidad sobre los resultados). Se asume comúnmente que estas preferencias satisfacen las condiciones de von Neumann y Morgenstern, permitiendo que se representen por el **valor esperado** de alguna función de utilidad.

La forma en que los pagos de los jugadores dependen de las acciones elegidas es una parte esencial de la descripción del juego en forma estratégica.

## Juegos en Forma Normal (o Forma Estratégica)

El **juego en forma normal**, también conocido como **forma estratégica**, es la representación más fundamental y familiar de las interacciones estratégicas en la teoría de juegos.

Un **juego en forma estratégica** se define formalmente como una tupla que consta de:
*   Un conjunto de **jugadores** N.
*   Para cada jugador i en N, un conjunto de **acciones** disponibles para el jugador i (Ai o Ci).
*   Para cada jugador i en N, una **función de utilidad** u_i que asigna un pago al jugador i para cada posible **perfil de acciones** (una combinación de acciones, donde cada jugador elige una acción de su conjunto).

La característica clave de un juego en forma estratégica es que **cada jugador elige su plan de acción una vez y para siempre**, y todas las decisiones de los jugadores se toman **simultáneamente** (es decir, al elegir su acción, ningún jugador está informado de la acción elegida por ningún otro jugador).

Para juegos finitos con dos jugadores, la forma estratégica se puede describir convenientemente en una **tabla**. Las filas representan las acciones de un jugador y las columnas las acciones del otro. Cada celda de la tabla (que corresponde a un perfil de acciones) contiene los pagos para cada jugador para ese perfil.

La forma normal es fundamental porque otras representaciones de juegos, como los juegos en forma extensiva (con elemento de tiempo) o los juegos Bayesianos (con información incompleta), pueden **reducirse** a un juego en forma normal (aunque la forma normal resultante puede ser mucho más grande).

## Estrategias Puras y Mixtas

En un juego en forma normal:
*   Una **estrategia pura** de un jugador es simplemente la elección de **una acción específica** de su conjunto de acciones disponibles. En la notación formal de un juego estratégico 〈N, (Ai), (ui)〉, una estrategia pura para el jugador i es un elemento a_i ∈ Ai.
*   Una **estrategia mixta** de un jugador es una **distribución de probabilidad** sobre su conjunto de estrategias puras. Permite que un jugador aleatorice su elección de acción pura. Por ejemplo, un jugador puede decidir jugar la acción A con probabilidad p y la acción B con probabilidad 1-p. La teoría de juegos asume que los jugadores con estrategias mixtas tienen preferencias representadas por el **valor esperado** de su función de utilidad sobre las loterías inducidas por las estrategias mixtas elegidas por todos los jugadores.

El estudio de las estrategias mixtas es un tema central en la teoría de juegos, con diversas interpretaciones de lo que significa que un jugador elija una estrategia mixta en la práctica.
Espero que este material le sea útil para su estudio de la Semana 1. Estoy a su disposición para abordar cualquiera de estos temas con mayor profundidad o pasar al material de las semanas siguientes, basándome en los fuentes proporcionados.
