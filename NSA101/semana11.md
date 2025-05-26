# Semana 11: Funciones de Utilidad. Teoría de la Utilidad Esperada (von Neumann-Morgenstern). Axiomas. Medición de la aversión al riesgo. Modelado de preferencias por múltiples atributos.

En el estudio de la toma de decisiones y las interacciones entre individuos, especialmente en campos como la teoría de juegos y la economía, es fundamental contar con una forma de representar las **preferencias** de los agentes racionales. Las **funciones de utilidad** son una herramienta clave para esto.

## ¿Qué son las Funciones de Utilidad?

En esencia, una función de utilidad asigna un valor numérico a diferentes resultados o "acuerdos", reflejando cuán deseable es ese resultado para un individuo. Representa las preferencias de un jugador sobre un conjunto de resultados posibles. Por ejemplo, en un problema de decisión individual, una función *u: A × Ω → R* (donde A es un conjunto de acciones y Ω un conjunto de estados) puede representar las preferencias del individuo sobre resultados que dependen tanto de la acción elegida como del estado que ocurra.

Las fuentes señalan que la idea de utilidad se fundamenta en un concepto más básico: las **preferencias**. Las preferencias se pueden definir mediante relaciones como "preferir débilmente" (o1 ≽ o2), "ser indiferente" (o1 ∼ o2) o "preferir estrictamente" (o1 ≻ o2) entre diferentes resultados.

Es importante destacar que la utilidad se especifica en sus propias unidades, no en unidades monetarias, aunque a veces se puedan establecer conversiones (por ejemplo, en entornos cuasilineales donde, por conveniencia, se asume que la utilidad puede expresarse en dólares, implicando neutralidad al riesgo y utilidad transferible).

## Teoría de la Utilidad Esperada (von Neumann-Morgenstern)

La teoría más influyente que fundamenta el concepto de utilidad a partir de las preferencias es la debida a **von Neumann y Morgenstern**. Esta teoría es particularmente relevante cuando los resultados no son ciertos, es decir, cuando las preferencias son sobre **loterías** (situaciones con resultados inciertos).

La teoría de von Neumann-Morgenstern, bajo ciertos supuestos sobre las preferencias del individuo sobre loterías, demuestra que existe una función de utilidad que representa estas preferencias de tal manera que el individuo prefiere las loterías que le proporcionan el **mayor valor de utilidad esperado**. Estas funciones de utilidad, conocidas como **funciones de utilidad de von Neumann–Morgenstern**, tienen una propiedad clave: son **únicas solo hasta una transformación afín positiva**. Esto significa que si *u(·)* es una función de utilidad VNM que representa las preferencias, entonces *a*u(·) + *b* también lo hace, para cualquier constante *a* > 0 y *b*. Esta propiedad es crucial y la distingue de otras posibles representaciones de preferencias (como la utilidad ordinal).

El **Teorema de Maximización de la Utilidad Esperada** (mencionado como Teorema 1.1 o 1.4 en las fuentes) es el resultado central de esta teoría. Deriva la maximización de la utilidad esperada a partir de **axiomas** que se consideran consistentes para una caracterización de preferencias racionales.

## Axiomas de la Teoría de la Utilidad Esperada

Aunque las fuentes no listan explícitamente todos los axiomas, mencionan que el teorema de maximización de la utilidad esperada se deriva de **supuestos débiles de consistencia**. El supuesto clave, que a menudo se llama **"axioma de la cosa segura"** (sure-thing axiom) o **axioma de sustitución**, se parafrasea informalmente de la siguiente manera: "Si un tomador de decisiones preferiría la opción 1 sobre la opción 2 cuando ocurre el evento A, y preferiría la opción 1 sobre la opción 2 cuando el evento A no ocurre, entonces debería preferir la opción 1 sobre la opción 2 incluso antes de saber si el evento A ocurrirá o no". Este tipo de supuesto, junto con algunas condiciones técnicas de regularidad, es suficiente para garantizar que exista una escala de utilidad tal que el individuo siempre prefiera las opciones que dan el **mayor valor de utilidad esperado**.

La validez de estos axiomas hace que los modelos basados en la maximización de la utilidad esperada sean considerados de **aplicabilidad y relevancia amplias** en las ciencias sociales matemáticas. Se espera que la maximización de la utilidad esperada sea **predictivamente precisa** en situaciones donde las personas han tenido tiempo suficiente para aprender y pensar claramente, ya que intentan no cometer errores.

La **utilidad esperada** de un jugador en una situación con incertidumbre se calcula ponderando la utilidad de cada resultado posible por la probabilidad de que ocurra ese resultado. Por ejemplo, en un juego bayesiano, la utilidad esperada de un agente con un cierto "tipo" (que define su información privada sobre el juego) se calcula sumando sobre los posibles "tipos" de los otros agentes y los posibles perfiles de acciones, ponderando las utilidades resultantes por las probabilidades condicionadas de esos tipos y acciones. El problema de computar esta utilidad esperada es fundamental en ciertos contextos.

## Medición de la Aversión al Riesgo

Las fuentes indican que las funciones de utilidad pueden **reflejar las preferencias de riesgo**. La teoría de la utilidad esperada proporciona un marco para modelar la toma de decisiones bajo incertidumbre, y la **forma** de la función de utilidad de von Neumann-Morgenstern está ligada a la actitud del individuo hacia el riesgo. Por ejemplo, una función de utilidad cóncava generalmente representa aversión al riesgo, una convexa a propensión al riesgo, y una lineal a neutralidad al riesgo.

Sin embargo, las fuentes **no profundizan en cómo se mide la aversión al riesgo** formalmente (por ejemplo, coeficientes de aversión absoluta o relativa al riesgo, o cómo derivarlos de la función de utilidad específica). Una fuente menciona que la conveniencia de asumir **neutralidad al riesgo** y utilidad transferible (donde la utilidad puede expresarse en dólares) facilita el análisis en ciertos modelos económicos (como los cuasilineales). Otra fuente plantea la pregunta de cómo se reconcilia la maximización de la utilidad esperada con el hecho de que las personas pueden mostrar diferentes disposiciones a participar en loterías justas (con valor esperado cero) dependiendo del tamaño de la apuesta, lo que sugiere actitudes hacia el riesgo más allá del simple valor esperado de la utilidad. Pero no se ofrece una respuesta formal a cómo modelar o medir esto dentro del marco VNM.

## Modelado de Preferencias por Múltiples Atributos

Las fuentes presentan ejemplos donde la utilidad de un individuo depende de **múltiples factores o atributos** que definen el resultado. Por ejemplo, la utilidad puede depender de la acción elegida y del estado de la naturaleza, o del precio y el tiempo de un acuerdo, o de las acciones de todos los jugadores y sus "tipos" privados en un juego bayesiano.

Sin embargo, las fuentes **no describen una teoría o metodología específica para modelar preferencias cuando los resultados tienen múltiples características distintas** (como la salud, la riqueza, el impacto ambiental) que necesitan ser agregadas o combinadas en una única función de utilidad. Se muestra la utilidad como una función de un resultado multidimensional o complejo (un par (p, t), un vector de acciones *a* y tipos *θ*), pero **no se detalla cómo se construye esta función de utilidad a partir de las valoraciones de cada atributo por separado**.

En resumen, las funciones de utilidad, especialmente en el marco de la Teoría de la Utilidad Esperada de von Neumann-Morgenstern basada en axiomas de consistencia, son herramientas esenciales para representar y analizar las decisiones de agentes racionales bajo incertidumbre, permitiendo calcular la utilidad esperada de diferentes opciones. Si bien este marco permite reflejar diferentes actitudes hacia el riesgo, las fuentes no detallan cómo medir la aversión al riesgo de manera específica ni presentan un enfoque formal para construir funciones de utilidad a partir de preferencias sobre múltiples atributos distintos.
