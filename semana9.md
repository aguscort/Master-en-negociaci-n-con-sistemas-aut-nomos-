# Semana 9: Aprendizaje Basado en Políticas en Deep Reinforcement Learning

Hasta ahora, hemos explorado algoritmos de Reinforcement Learning (RL) que se centran en aprender o estimar funciones de valor, como la función de valor de estado ($v_\pi(s)$) o la función de valor de acción ($q_\pi(s, a)$). Estos métodos, particularmente cuando se combinan con aproximadores de funciones como las redes neuronales profundas (resultando en Deep Q-Networks o DQN, como discutimos anteriormente), son muy potentes [conversación previa, 112]. El agente aprende a tomar acciones calculando los valores de acción estimados y eligiendo la acción con el valor más alto (o explorando de manera similar). Este es el enfoque de **métodos basados en valor**.

Sin embargo, existe otra familia fundamental de algoritmos de RL que adoptan un enfoque diferente: **los métodos basados en políticas**. En lugar de aprender una función de valor para guiar la selección de acciones, estos métodos aprenden y **optimizan directamente la política** del agente. La política, denotada $\pi(a|s)$, es la función que define la probabilidad de tomar una acción $a$ dado un estado $s$.

Los métodos basados en políticas tienen ventajas particulares. Por ejemplo, son naturalmente adecuados para:

*   Problemas con **espacios de acción continuos**, donde seleccionar la acción con el valor máximo (como en Q-learning o DQN) puede ser computacionalmente costoso o inviable. Una política parametrizada puede simplemente producir un valor de acción continuo o los parámetros de una distribución sobre acciones continuas.
*   Aprender **políticas estocásticas** (probabilísticas), lo cual puede ser importante para la exploración o en juegos contra oponentes donde una política determinista podría ser explotada. Aunque los métodos basados en valor pueden aprender políticas estocásticas (por ejemplo, $\epsilon$-greedy), los métodos basados en políticas pueden representarlas y aprenderlas de forma más natural y flexible.
*   A veces tienen **mejores propiedades de convergencia teórica** que los métodos basados en valor con aproximación de funciones, especialmente en el caso on-policy. Pequeños cambios en los parámetros pueden llevar a pequeños cambios en las probabilidades de acción, a diferencia de los métodos basados en valor donde un pequeño cambio en el valor estimado puede cambiar drásticamente la acción elegida (por ejemplo, en selección greedy o $\epsilon$-greedy).

La idea central es **parametrizar la política**. Esto significa que la política $\pi$ se convierte en una función $\pi(a|s, \boldsymbol{\theta})$, donde $\boldsymbol{\theta}$ es un vector de parámetros (por ejemplo, los pesos de una red neuronal). El objetivo del aprendizaje es encontrar el vector de parámetros $\boldsymbol{\theta}$ que maximice alguna medida de rendimiento, generalmente el valor esperado de la recompensa total (retorno).

### Aproximación de la Política

En el contexto de Deep RL, la parametrización de la política se realiza típicamente utilizando una **red neuronal profunda (DNN)**. La DNN toma el estado $s$ como entrada y produce como salida los parámetros de una distribución de probabilidad sobre las acciones. Por ejemplo:

*   Para espacios de acción discretos, la salida de la red podría ser una probabilidad para cada acción, a menudo usando una función softmax.
*   Para espacios de acción continuos, la red podría producir la media y la varianza de una distribución (como una Gaussiana) a partir de la cual se muestrea la acción.

El vector de pesos de esta red neuronal profunda constituye el vector de parámetros $\boldsymbol{\theta}$. Al ajustar $\boldsymbol{\theta}$ mediante el descenso de gradiente, podemos modificar la política para favorecer acciones que se espera que produzcan mayores recompensas.

### El Teorema del Gradiente de la Política (Policy Gradient Theorem)

Para optimizar la política parametrizada $\pi(a|s, \boldsymbol{\theta})$ mediante descenso de gradiente (o ascenso de gradiente, ya que queremos maximizar el rendimiento), necesitamos poder calcular el gradiente de la medida de rendimiento $J(\boldsymbol{\theta})$ con respecto a los parámetros $\boldsymbol{\theta}$. Aquí es donde el **Teorema del Gradiente de la Política** es fundamental.

El teorema proporciona una expresión analítica para el gradiente de la medida de rendimiento $J(\boldsymbol{\theta})$ con respecto al parámetro de política $\boldsymbol{\theta}$. Para el caso episódico, el teorema establece que el gradiente es *proporcional* a:

$\nabla J(\boldsymbol{\theta}) \propto \sum_{s} \mu(s) \sum_{a} q_\pi(s, a) \nabla \pi(a|s, \boldsymbol{\theta})$

Donde:
*   $\nabla J(\boldsymbol{\theta})$ es el gradiente de la medida de rendimiento con respecto a $\boldsymbol{\theta}$.
*   $\mu(s)$ es la distribución de visitación de estados bajo la política actual $\pi$ (específicamente, la distribución on-policy).
*   $q_\pi(s, a)$ es la verdadera función de valor de acción para la política actual $\pi$.
*   $\nabla \pi(a|s, \boldsymbol{\theta})$ es el gradiente de la probabilidad de acción con respecto a $\boldsymbol{\theta}$.

La gran importancia de este teorema radica en que **proporciona una fórmula para el gradiente que no involucra la derivada de la distribución de estados ($\mu(s)$)**. Calcular la derivada de cómo cambia la distribución de estados cuando se cambian los parámetros de la política sería extremadamente difícil o imposible en la práctica. El teorema del gradiente de la política nos permite evitar este problema, proporcionando una base teórica para algoritmos de aprendizaje de políticas basados en gradiente.

Aunque la fórmula involucra $q_\pi(s, a)$ y la distribución $\mu(s)$, que generalmente son desconocidas, el teorema establece que el *valor esperado* de ciertos muestreos de las experiencias del agente bajo la política $\pi$ es *proporcional* al gradiente verdadero. Esto nos permite estimar el gradiente a partir de la experiencia.

### Algoritmos REINFORCE (Monte Carlo Policy Gradient)

El algoritmo **REINFORCE** es el algoritmo de aprendizaje basado en políticas más simple que se deriva directamente del Teorema del Gradiente de la Política. Es un método de **Monte Carlo**, lo que significa que **aprende de episodios completos de experiencia**.

La idea básica de REINFORCE es actualizar los parámetros de la política $\boldsymbol{\theta}$ en la dirección del gradiente estimado, utilizando el retorno Monte Carlo (la suma total de recompensas descontadas) obtenido después de realizar una acción. Para cada paso de tiempo $t$ en un episodio que finaliza en el tiempo $T$, la acción $A_t$ tomada en el estado $S_t$ es reforzada (o castigada) en proporción al retorno total $G_t$ que se obtuvo desde ese momento en adelante (en REINFORCE básico, se usa $G_{t:T}$).

La actualización conceptual para cada paso $(S_t, A_t)$ del episodio, aplicada al final del episodio, es proporcional a:
$\boldsymbol{\theta} \leftarrow \boldsymbol{\theta} + \alpha G_t \nabla \ln \pi(A_t|S_t, \boldsymbol{\theta})$ [similar a, usando $G_t$ en lugar del error TD, y el término de gradiente logarítmico como "eligibility vector"]

Donde:
*   $\alpha$ es la tasa de aprendizaje (step size).
*   $G_t$ es el retorno Monte Carlo observado desde el paso $t$.
*   $\nabla \ln \pi(A_t|S_t, \boldsymbol{\theta})$ es el gradiente del logaritmo de la probabilidad de haber tomado la acción $A_t$ en el estado $S_t$ dado $\boldsymbol{\theta}$. Este término indica cómo cambiar $\boldsymbol{\theta}$ para hacer que la probabilidad de $A_t$ en $S_t$ sea más (o menos) probable.

Si $G_t$ es positivo, los parámetros se ajustan para aumentar la probabilidad de $A_t$ en $S_t$. Si $G_t$ es negativo, los parámetros se ajustan para disminuir esa probabilidad (meta del actor).

Un problema con REINFORCE es que el retorno $G_t$ puede tener una **alta varianza**. Esto puede hacer que el aprendizaje sea inestable y lento. Una técnica común para mitigar esto es introducir un **valor de referencia o "baseline"**.

### REINFORCE con Baseline

La idea es que no es la magnitud absoluta del retorno lo que importa, sino si el retorno fue mejor o peor de lo esperado para ese estado. La actualización se vuelve menos variable si restamos una línea base $b(S_t)$ del retorno $G_t$. El término de actualización se modifica a:

$\boldsymbol{\theta} \leftarrow \boldsymbol{\theta} + \alpha (G_t - b(S_t)) \nabla \ln \pi(A_t|S_t, \boldsymbol{\theta})$ [análogo a usando $G_t - b(S_t)$ como error]

Donde $b(S_t)$ es el baseline para el estado $S_t$. Un baseline común es una estimación del valor del estado $v(S_t)$, a menudo aprendida por separado. Si el baseline es el valor verdadero del estado $v_\pi(S_t)$, esto no introduce sesgo en el gradiente esperado, solo reduce la varianza. En la práctica, se usa una estimación aprendida del valor del estado, $\hat{v}(S_t, \mathbf{w})$, donde $\mathbf{w}$ son los pesos de una red neuronal separada (o de la misma red) que aproxima la función de valor.

El uso de un baseline, especialmente una función de valor aprendida, puede hacer que REINFORCE aprenda **mucho más rápido**.

### Introducción a los Métodos Actor-Critic

Los métodos **Actor-Critic** combinan elementos de los métodos basados en políticas (el "actor") y los métodos basados en valor (el "critic").

*   El **Actor** es la política parametrizada $\pi(a|s, \boldsymbol{\theta})$, responsable de seleccionar y realizar las acciones.
*   El **Critic** es una función de valor parametrizada (por ejemplo, $v(s, \mathbf{w})$ o $q(s, a, \mathbf{w})$), responsable de evaluar las acciones tomadas por el actor.

La interacción es la siguiente: el actor toma una acción en un estado. El entorno proporciona una recompensa y el siguiente estado. El critic utiliza esta experiencia para calcular un **error de diferencia temporal (TD error)**. Este error TD es una medida de cuán mejor (o peor) fue la recompensa observada más el valor estimado del siguiente estado, en comparación con el valor estimado del estado actual.

El **error TD** sirve como una señal de "refuerzo" para el **actor**, reemplazando el retorno Monte Carlo completo $G_t$ utilizado en REINFORCE. El actor utiliza este error TD para actualizar sus parámetros $\boldsymbol{\theta}$ y hacer que las acciones que llevaron a un error TD positivo sean más probables en el futuro, y las que llevaron a un error TD negativo sean menos probables.

La actualización del actor en un método Actor-Critic de un paso es conceptualmente similar a REINFORCE con baseline, pero usando el error TD $\delta_t$ como la señal de refuerzo/baseline combinado:
$\boldsymbol{\theta} \leftarrow \boldsymbol{\theta} + \alpha_\theta \delta_t \nabla \ln \pi(A_t|S_t, \boldsymbol{\theta})$ [basado en]
Donde $\delta_t = R_{t+1} + \gamma v(S_{t+1}, \mathbf{w}) - v(S_t, \mathbf{w})$ (para un critic de valor de estado).

Al mismo tiempo, el **critic** utiliza el error TD para actualizar sus propios parámetros $\mathbf{w}$, con el objetivo de **reducir la magnitud del error TD**, mejorando así su precisión en la predicción de valor.

**Beneficios de Actor-Critic:**

*   Pueden ser **más eficientes en el uso de los datos** que los métodos Monte Carlo como REINFORCE, ya que utilizan bootstrapping (el error TD se basa en la estimación del valor del siguiente estado).
*   Permiten **actualizaciones online e incrementales** en cada paso de tiempo, sin tener que esperar hasta el final del episodio como REINFORCE.
*   Generalmente tienen **menor varianza** que los métodos Monte Carlo porque el error TD depende de una sola transición y una estimación de valor, en lugar de la suma de todas las recompensas futuras.
*   Son la base de muchos algoritmos Deep RL modernos y complejos, y tienen conexiones plausibles con mecanismos de aprendizaje en el cerebro (donde se cree que la dopamina actúa como una señal de error TD para el aprendizaje en el estriado, que actúa como actor y critic).

**Desafíos de Actor-Critic:**

*   Introducen **sesgo** en la estimación del gradiente de la política debido al bootstrapping.
*   Requieren el aprendizaje y ajuste de **dos conjuntos de parámetros** ($\boldsymbol{\theta}$ para el actor y $\mathbf{w}$ para el critic), lo que puede ser más complejo.
*   Pueden ser **menos estables** que REINFORCE en algunos casos, aunque el uso de técnicas como las eligibility traces puede mejorar esto. Combinar aproximación de funciones, bootstrapping y aprendizaje off-policy (si el critic aprende de datos de una política diferente a la del actor) puede llevar a inestabilidad (la "tríada mortal"), aunque los algoritmos actor-critic on-policy son generalmente más estables que los métodos de valor off-policy con aproximación.

Existen diversas variantes de métodos Actor-Critic, incluyendo versiones con **n-step returns** y **eligibility traces**, que permiten ajustar el grado de bootstrapping entre Monte Carlo y TD de un paso.

En resumen, los métodos basados en políticas, anclados en el Teorema del Gradiente de la Política, ofrecen una alternativa poderosa a los métodos basados en valor, especialmente útiles para espacios de acción continuos y el aprendizaje de políticas estocásticas. REINFORCE es una implementación fundamental de Monte Carlo, y los métodos Actor-Critic extienden esta idea utilizando el bootstrapping para obtener actualizaciones online y de menor varianza.
