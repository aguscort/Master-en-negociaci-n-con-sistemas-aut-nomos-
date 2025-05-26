# Semana 10: Actor-Critic Multiagente y MADDPG

Los sistemas multiagente (MAS) son aquellos que incluyen múltiples entidades autónomas con información o intereses divergentes, o ambas cosas. El estudio de estos sistemas a menudo recurre a conceptos de teoría de juegos para analizar conflictos y cooperación,,,,. En entornos multiagente, las estrategias de los agentes pueden volverse muy complejas, ya que la acción de un agente en cualquier momento puede depender de la historia completa de las acciones hasta ese punto.

La aplicación del aprendizaje por refuerzo (RL) a sistemas multiagente presenta desafíos adicionales en comparación con el aprendizaje de un solo agente. Uno de los principales desafíos es la *no estacionalidad* del entorno desde la perspectiva de cualquier agente individual. Como otros agentes también están aprendiendo y cambiando su comportamiento, el entorno con el que interactúa un agente está en constante evolución, lo que dificulta el proceso de aprendizaje.

Los métodos Actor-Critic representan un enfoque importante en el aprendizaje por refuerzo,, inspirados en modelos biológicos de aprendizaje,,. Estos métodos se han desarrollado para controlar sistemas al aprender una política de acción y una función de valor de manera conjunta.

## Métodos Actor-Critic

En un método Actor-Critic, existen dos componentes principales que trabajan en conjunto:

1.  **El Actor:** Este componente es responsable de aprender la política del agente, que es la función que mapea estados (o observaciones) a acciones. El actor decide qué acción tomar en un estado dado,. La política puede ser determinística (elige una única acción) o estocástica (define una distribución de probabilidad sobre las acciones),.
2.  **El Critic:** Este componente es responsable de evaluar las acciones tomadas por el actor. Aprende una función de valor, típicamente una función de valor estado-acción (Q-función) o una función de valor estado (V-función),. El critic utiliza la experiencia del agente (estados, acciones, recompensas, siguientes estados) para estimar el valor esperado de estar en un estado o de tomar una acción en un estado,,.

La interacción entre el actor y el critic sigue un patrón de "iteración de política generalizada" (GPI),. El critic evalúa la política actual del actor, y el actor mejora su política basándose en la evaluación del critic. El critic a menudo utiliza métodos de aprendizaje de Diferencia Temporal (TD), como el error TD ($\delta$), para actualizar su función de valor. Este error TD, que mide la discrepancia entre el valor estimado actual y una estimación bootstraped (que incluye la estimación del siguiente estado) más precisa, sirve como señal de retroalimentación para actualizar tanto al critic como al actor,,.

Una ventaja de los métodos Actor-Critic es que a menudo son superiores a otros métodos, como los puramente basados en gradientes de política, en términos de varianza y "congenialidad computacional". El critic, al estimar el valor, proporciona una señal de error TD con menor varianza que el retorno total de un episodio, lo que puede hacer que el aprendizaje del actor sea más estable.

Los métodos Actor-Critic pueden ser *on-policy* (la política que se evalúa es la misma que genera los datos) o *off-policy* (se aprende sobre una política objetivo diferente a la política de comportamiento que genera los datos),,. Los métodos *off-policy* con aproximación de funciones y bootstrapping pueden ser susceptibles a la inestabilidad, un problema conocido como la "triada mortal",.

## El Desafío en Entornos Continuos y Multiagente

Muchos problemas complejos, como el control robótico o las simulaciones físicas, involucran espacios de estados y acciones continuos, en lugar de discretos,,,. Los métodos que funcionan bien con espacios discretos pueden no ser directamente aplicables. Los entornos multiagente con espacios de acción continuos presentan un desafío adicional debido a la combinación de la complejidad de las acciones continuas con la no estacionalidad intrínseca de la interacción entre agentes que aprenden,.

## Hacia MADDPG: Aprendizaje Centralizado con Ejecución Descentralizada

Multi-Agent Deep Deterministic Policy Gradient (MADDPG) es un algoritmo diseñado para abordar algunos de estos desafíos en entornos multiagente con espacios de acción continuos. Aunque los detalles específicos de la arquitectura y entrenamiento de MADDPG no se describen en las fuentes proporcionadas, podemos entender su enfoque conceptual basándonos en los principios de sistemas multiagente,, métodos Actor-Critic, y el manejo de entornos continuos,.

El principio central de MADDPG es el **entrenamiento centralizado con ejecución descentralizada**. Esto significa que durante la fase de entrenamiento, los agentes tienen acceso a más información de la que tendrán durante la ejecución (o prueba), lo que ayuda a estabilizar el proceso de aprendizaje.

1.  **Arquitectura Conceptual (Durante el Entrenamiento):**
    *   Cada agente *i* tiene su propio **actor** ($\pi_i$). Este actor es una red neuronal (de ahí "Deep") que toma la observación local del agente ($o_i$) como entrada y produce una acción determinística ($a_i$) para espacios de acción continuos (de ahí "Deterministic Policy Gradient"),.
    *   Cada agente *i* tiene también un **critic** ($Q_i$). Durante el entrenamiento, el critic del agente *i* no solo toma la observación local del agente *i* ($o_i$) y su acción ($a_i$) como entrada, sino que **también tiene acceso a las observaciones ($o_j$) y acciones ($a_j$) de *todos* los demás agentes ($j \neq i$) en el sistema**. Es decir, el critic es "centralizado" en el sentido de que utiliza información global del sistema para evaluar la situación. Esta entrada adicional de información conjunta ayuda al critic a obtener una evaluación más estable del valor de la acción del agente *i*, ya que tiene en cuenta el contexto completo del sistema, incluida la dinámica cambiante de los otros agentes.

2.  **Entrenamiento Conceptual:**
    *   El entrenamiento procede para cada agente *i* utilizando su par actor-critic.
    *   Los críticos ($Q_i$) se entrenan para minimizar el error de Bellman (similar a los métodos TD,) utilizando la información conjunta (observaciones y acciones de todos los agentes). Esta información conjunta aborda el problema de la no estacionalidad: aunque la política de un agente *j* cambia, el critic del agente *i* puede observar directamente los cambios en la acción de *j*, lo que hace que el estado *conjunto* del sistema sea más estacional que la observación local del agente *i* por sí sola.
    *   Los actores ($\pi_i$) se actualizan utilizando el gradiente de política (de ahí "Policy Gradient"),, basado en la retroalimentación del critic correspondiente ($Q_i$). La actualización del actor tiene como objetivo ajustar la política del agente *i* para tomar acciones que el critic $Q_i$ evalúa como de alto valor, dadas las observaciones y acciones de todos los agentes.

3.  **Ejecución Descentralizada:**
    *   Una vez entrenados, los agentes operan de forma independiente. Durante la ejecución (o prueba), **cada agente *i* utiliza solo su actor ($\pi_i$) y su observación local ($o_i$) para decidir su acción ($a_i$)**. El critic y la información conjunta ya no son necesarios. El actor entrenado es capaz de tomar decisiones efectivas basándose únicamente en su percepción local, ya que fue entrenado en un entorno más estable (gracias al critic centralizado) que reflejaba las acciones de los otros agentes.

Este enfoque permite entrenar políticas efectivas para agentes individuales que operan en entornos multiagente complejos y continuos, superando parcialmente el desafío de la no estacionalidad durante el aprendizaje al centralizar la información en la fase de entrenamiento del critic, mientras se mantiene la capacidad de los agentes para ejecutar sus políticas de forma descentralizada en la práctica.
