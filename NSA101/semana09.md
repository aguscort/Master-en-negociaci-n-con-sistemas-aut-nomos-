# Semana 9: Diseño de Subastas

El diseño de subastas es una aplicación central del **Diseño de Mecanismos**, un campo de la teoría de juegos que se ocupa de diseñar reglas para una interacción estratégica con el fin de lograr un resultado deseado, incluso cuando los participantes tienen información privada. En el contexto de las subastas, el diseñador (a menudo el vendedor) busca asignar un artículo (o varios) a un comprador (o varios) basándose en sus valoraciones privadas y maximizando objetivos como los ingresos o la eficiencia.

## Tipos Comunes de Subastas

Las fuentes mencionan varios tipos de subastas:

*   **Subasta a Primer Precio (First-Price Sealed Bid):** Los postores presentan ofertas selladas simultáneamente. El postor con la oferta más alta gana el artículo y paga un precio igual a su propia oferta.
*   **Subasta a Segundo Precio (Second-Price Sealed Bid):** Los postores presentan ofertas selladas simultáneamente. El postor con la oferta más alta gana el artículo, pero paga un precio igual a la segunda oferta más alta. Las fuentes relacionan el mecanismo VCG (Vickrey-Clarke-Groves) con una extensión de la subasta a segundo precio, y señalan que la subasta a segundo precio para un solo artículo es un ejemplo de mecanismo VCG.
*   **Subasta Inglesa (English Auction):** Una subasta ascendente, donde el precio se incrementa progresivamente y los postores abandonan hasta que solo queda uno, quien gana el artículo al precio al que el postor anterior abandonó. Las fuentes mencionan su equivalencia (débil) con las subastas japonesa y de segundo precio bajo valores privados independientes (IPV).
*   **Subasta Holandesa (Dutch Auction):** Una subasta descendente, donde el precio comienza alto y desciende progresivamente. El primer postor que acepta un precio gana el artículo a ese precio. Las fuentes señalan su equivalencia estratégica con las subastas a primer precio.
*   **Subasta Japonesa (Japanese Auction):** Similar a la inglesa, pero los postores permanecen activamente en la subasta a medida que sube el precio, indicando su voluntad de pagar el precio actual. Un postor abandona saliendo de la subasta. Las fuentes la mencionan como equivalente (débil) a las subastas inglesa y de segundo precio bajo IPV.

Las fuentes también hacen referencia a subastas generalizadas a primer y segundo precio.

## **Análisis de sus Propiedades: Compatibilidad de Incentivos y Eficiencia**

Un objetivo clave del diseño de mecanismos es la **compatibilidad de incentivos (IC)**, que asegura que los agentes tengan un incentivo para revelar su información privada de forma veraz. Otro objetivo importante es la **eficiencia**, a menudo entendida como eficiencia de Pareto o, en el contexto de subastas, asignación eficiente (que el artículo vaya a quien más lo valora).

*   **Compatibilidad de Incentivos:**
    *   La **subasta a segundo precio** es notable por ser **compatible con incentivos en estrategia dominante** bajo el supuesto de valores privados independientes (IPV). Esto significa que la estrategia óptima para cada postor es ofertar su verdadera valoración del artículo, independientemente de lo que hagan o puedan hacer los otros postores. Reportar honestamente es una estrategia dominante en los mecanismos VCG, de los cuales la subasta a segundo precio es un caso particular para un solo ítem.
    *   Las **subastas japonesas** también son **compatibles con incentivos en estrategia dominante** cuando los agentes tienen valores privados independientes.
    *   La equivalencia estratégica entre las **subastas holandesas** y las **subastas a primer precio** implica que la estrategia de ofertar verazmente **no** es una estrategia dominante en estas subastas bajo las condiciones típicas (como la aversión al riesgo). En estas subastas, la oferta óptima de un postor depende de sus creencias sobre las ofertas de los demás, lo que las relaciona con el concepto de equilibrio de Bayes-Nash.
    *   El **Principio de Revelación**, discutido previamente, es fundamental aquí: si una regla de asignación puede ser implementada por algún mecanismo (como una subasta indirecta como la inglesa o la holandesa), entonces puede ser implementada por un mecanismo directo y honesto (donde los agentes reportan sus tipos y es óptimo ser veraz). Esto simplifica la búsqueda de mecanismos óptimos.

*   **Eficiencia:**
    *   En entornos con preferencias cuasilineales (donde la utilidad puede medirse en dinero), un criterio importante de eficiencia es maximizar la suma de las valoraciones de los agentes.
    *   Los mecanismos VCG, que incluyen la **subasta a segundo precio** para un solo artículo, son conocidos por lograr **asignaciones eficientes**, es decir, asignar el artículo al postor que lo valora más alto.
    *   Las subastas **inglesa** y **japonesa** (ascendentes), al continuar mientras haya al menos dos postores dispuestos a pujar, también tienden a asignar el artículo al postor con la valoración más alta, logrando así la eficiencia de asignación bajo supuestos estándar.

## El Teorema de Equivalencia de Ingresos (Revenue Equivalence Theorem)

Las fuentes se refieren a este concepto al hablar de la **equivalencia estratégica** y la **equivalencia de pagos** entre diferentes tipos de subastas. El teorema establece, bajo ciertas condiciones, que un conjunto de diferentes formatos de subasta producirán el mismo ingreso esperado para el vendedor.

Las condiciones bajo las cuales suele cumplirse el teorema (y que son mencionadas o implícitas en las fuentes al discutir la equivalencia) incluyen:

1.  **Valores Privados Independientes (IPV):** La valoración que cada postor tiene del artículo es privada y se extrae independientemente de una distribución conocida.
2.  **Postores Racionales y que Buscan Maximizar su Utilidad Esperada:** Los postores son racionales y estratégicos.
3.  **Postores Neutrales al Riesgo:** Los postores evalúan los resultados basándose únicamente en su valor esperado, sin considerar la variabilidad.
4.  **El Artículo se Asigna al Postor con la Valoración Más Alta:** El mecanismo de subasta asigna el artículo de manera eficiente.
5.  **Los Pagos Dependen Únicamente de las Ofertas (y del propio tipo del postor en algunos casos) y de la regla de asignación.**

Bajo estas y otras condiciones (como que cada postor desea solo una unidad del bien), las fuentes indican que la **equivalencia estratégica** existe entre la **subasta holandesa y la de primer precio**, y la **equivalencia (más débil) entre la japonesa, la inglesa y la de segundo precio** bajo IPV. Más formalmente, las fuentes afirman que los mecanismos Groves (que incluyen VCG) son **equivalentes en pagos** a todos los demás mecanismos eficientes que son compatibles con incentivos Bayes-Nash. Una versión del teorema de equivalencia de ingresos se aplica a pares de subastas que comparten la misma regla de asignación.

Es importante notar que estas equivalencias se rompen si se relajan algunos de estos supuestos, por ejemplo, si los postores son aversos al riesgo (rompiendo la equivalencia entre primer precio/holandesa y segundo precio/inglesa/japonesa) o si los valores de los postores están correlacionados.

En resumen, el diseño de subastas aplica los principios de diseño de mecanismos para crear interacciones que incentiven a los agentes a revelar información privada, buscando objetivos como la eficiencia (asignar al que más valora el artículo) y la generación de ingresos. La subasta a segundo precio y las subastas ascendentes (inglesa/japonesa) destacan por su fuerte compatibilidad con incentivos bajo supuestos comunes, mientras que el Teorema de Equivalencia de Ingresos muestra que, bajo ciertas condiciones ideales, diferentes formatos de subasta pueden generar el mismo ingreso esperado a pesar de sus diferentes propiedades estratégicas.
