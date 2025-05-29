# AÑO 1: Fundamentos Teórico-Técnicos e Interdisciplinarios (60 ECTS)

## CUATRIMESTRE 1 (Q1): Pilares Cuantitativos y de IA (30 ECTS)

![Separador](imagen1.png)
### NSA-101: Teoría de Juegos para Agentes Autónomos

*   **Créditos:** 6 ECTS
*   **Dedicación:** 4 horas de teoría + 2 horas de laboratorio por semana (Total 12 semanas de docencia)
*   **Pre-requisitos:** Estadística básica, Fundamentos de teoría de juegos (entrada).
*   **Objetivos de Aprendizaje:**
    *   Modelar interacciones estratégicas complejas entre múltiples agentes autónomos.
    *   Identificar y analizar los conceptos de equilibrio relevantes en juegos estáticos y dinámicos con información completa e incompleta.
    *   Aplicar principios de diseño de mecanismos para inducir comportamientos estratégicos deseados en sistemas multiagente.
    *   Formalizar las preferencias y objetivos de los agentes utilizando funciones de utilidad, incluyendo la integración de factores no monetarios y éticos.
*   **Temario Detallado (12 semanas):**
    1.  **[Semana 1](NSA101/semana01.md)**: Introducción y Repaso. Definición de un juego. Jugadores, acciones, resultados, pagos. Juegos en forma normal. Estrategias puras y mixtas.
    2.  **[Semana 2](NSA101/semana02.md):** Dominancia y Eliminación Iterada. Estrategias estrictamente y débilmente dominadas. Relación con el equilibrio de Nash.
    3.  **[Semana 3](NSA102/semana03.md):** Equilibrio de Nash. Definición formal. Cálculo en juegos de matriz pequeños. Interpretaciones del equilibrio de Nash. Conceptos básicos de juegos repetidos y el Folk Theorem.
    4.  **[Semana 4](NSA101/semana04.md):** Juegos en Forma Extensiva. Árboles de juego. Información perfecta vs. imperfecta. Estrategias en forma extensiva.
    5.  **[Semana 5](NSA101/semana05.md):** Juegos Dinámicos con Información Completa. Inducción hacia atrás. Equilibrios perfectos en subjuegos. Aplicaciones simples a negociaciones secuenciales.
    6.  **[Semana 6](NSA102/semana06.md):** Juegos con Información Incompleta (Bayesiana). Tipos de jugadores. Creencias. Juegos en forma normal Bayesiana. Equilibrio Bayesiano de Nash.
    7.  **[Semana 7](NSA102/semana07.md):** Juegos Secuenciales con Información Incompleta. Equilibrio Perfecto Bayesiano (concepto intuitivo). Aplicaciones a señalización (ej. calidad de un producto) y screening (ej. aversión al riesgo).
    8.  **[Semana 8](NSA101/semana08.md):** Principios de Diseño de Mecanismos. Introducción al problema del diseñador. Objetivos (eficiencia, ingresos). El Principio de Revelación. Compatibilidad de Incentivos (Dominant Strategy IC vs. Bayesian Nash IC).
    9.  **[Semana 9](NSA101/semana09.md):** Diseño de Subastas. Tipos comunes de subastas (primer precio, segundo precio, holandesa, inglesa). Análisis de sus propiedades de compatibilidad de incentivos y eficiencia. El Teorema de Equivalencia de Ingresos (bajo ciertas condiciones).
    10. **[Semana 10](NSA101/semana10.md):** Mecanismos VCG. Diseño de mecanismos para asignación de bienes o tareas donde los valores son interdependientes. Mecanismos Vickrey-Clarke-Groves (VCG): concepto y cálculo. Desafíos computacionales y de implementación.
    11. **[Semana 11](NSA102/semana11.md):** Funciones de Utilidad. Teoría de la Utilidad Esperada (von Neumann-Morgenstern). Axiomas. Medición de la aversión al riesgo. Modelado de preferencias por múltiples atributos.
    12. **[Semana 12](NSA101/semana12.md):** Utilidades Híbridas y Factores No Monetarios. Integración de objetivos no económicos en la función de utilidad de un agente (ej. tiempo, energía, reputación, alineación de valores). Introducción al vector de valores éticos (V) y su ponderación (α) en `U(a; θ, V)`.
*   **Bibliografía Esencial:**
    *   Osborne, M. J., & Rubinstein, A. (1994). *A Course in Game Theory*. MIT Press.
    *   Myerson, R. B. (1991). *Game Theory: Analysis of Conflict*. Harvard University Press.
    *   Nisan, N., Roughgarden, T., Tardos, E., & Vazirani, V. V. (Eds.). (2007). *Algorithmic Game Theory*. Cambridge University Press. (Capítulos 1, 9, 13).
*   **Evaluación:**
    *   Problem sets (30%) - Típicamente 3-4 tareas que combinan ejercicios teóricos y pequeños problemas de modelado/cálculo.
    *   Proyecto "Diseño de Subasta Simple" (30%) - Implementación en Python de un tipo de subasta y análisis de estrategias de agentes simulados.
    *   Examen final teórico-práctico (40%) - Cubre todos los temas del curso.
*   **Laboratorio (2h/sem):**
    *   Semanas 1-5: Uso de librerías Python (`nashpy`, `gambit` o similar) para representar juegos en forma normal/extensiva y calcular equilibrios (Nash, perfectos en subjuegos).
    *   Semanas 6-7: Modelado y análisis de juegos Bayesianos simples en Python.
    *   Semanas 8-10: Implementación de diferentes tipos de subastas y mecanismos VCG básicos. Simulación con agentes con diferentes valoraciones.
    *   Semanas 11-12: Implementación de funciones de utilidad con aversión al riesgo. Ejercicios de modelado de preferencias simples que incluyan factores no monetarios.


![Separador](imagen1.png)
### NSA-102: Aprendizaje por Refuerzo Multiagente (MARL)

*   **Créditos:** 6 ECTS
*   **Dedicación:** 4 horas de teoría + 2 horas de laboratorio por semana (Total 12 semanas de docencia)
*   **Pre-requisitos:** NSA-101 (concurrente), Programación Avanzada.
*   **Objetivos de Aprendizaje:**
    *   Comprender los fundamentos del Aprendizaje por Refuerzo (RL) individual y su extensión a entornos con múltiples agentes.
    *   Implementar y aplicar algoritmos clásicos (Q-learning) y basados en Deep Learning (DQN, Policy Gradients) en escenarios multiagente.
    *   Analizar los desafíos específicos de MARL, como la no-estacionariedad, la asignación de crédito de recompensa y la exploración.
    *   Evaluar y comparar el desempeño de diferentes algoritmos MARL en tareas de negociación o coordinación.
*   **Temario Detallado (12 semanas):**
    1.  **[Semana 1](NSA102/semana01.md):** Introducción al RL. El problema del agente. MDPs: estados, acciones, recompensas, transiciones. La función de valor y la función Q.
    2.  **[Semana 2](NSA102/semana02.md):** Ecuaciones de Bellman. El problema de predicción y control. Value Iteration y Policy Iteration. Convergencia.
    3.  **[Semana 3](NSA102/semana03.md):** RL sin modelo. Q-Learning. SARSA. La exploración-explotación: ε-greedy, decaimiento, Boltzmann.
    4.  **[Semana 4](NSA102/semana04.md):** Introducción a MARL. Juegos Estocásticos (MMDPs) como formalismo. Tipos de entornos multiagente (cooperativo, competitivo, mixto).
    5.  **[Semana 5](NSA102/semana05.md):** Desafíos en MARL. La no-estacionariedad. El problema del "Credit Assignment" multiagente. Escalabilidad.
    6.  **[Semana 6](NSA102/semana06.md):** Algoritmos MARL Descentralizados. Independent Q-Learning (IQL): implementación y limitaciones.
    7.  **[Semana 7](NSA102/semana07.md):** Deep RL Básico. Introducción a Deep Q-Networks (DQN). Experiencia Replay. Target Networks.
    8.  **[Semana 8](NSA102/semana08.md):** Deep MARL Cooperativo (Centralized Training, Decentralized Execution). Value Decomposition Networks (VDN). QMIX: idea principal y arquitectura. Experiencia replay multiagente.
    9.  **[Semana 9](NSA102/semana09.md):** Aprendizaje Basado en Políticas. Policy Gradient Theorem. Algoritmos REINFORCE. Introducción a Actor-Critic.
    10. **[Semana 10](NSA102/semana10.md):** Actor-Critic Multiagente. Multi-Agent Deep Deterministic Policy Gradient (MADDPG): arquitectura y entrenamiento. Entornos continuos.
    11. **[Semana 11](NSA102/semana11.md):** Estrategias de Entrenamiento Multiagente. Self-play. Fictitious play. Entrenamiento con población de agentes. Reward Shaping en MARL.
    12. **[Semana 12](NSA102/semana12.md):** Evaluación y Benchmarking. Métricas de desempeño en MARL (recompensa agregada, tasa de éxito, equidad). Uso de entornos de benchmarking estándar (`PettingZoo`, `Melting Pot`).
*   **Bibliografía Esencial:**
    *   Sutton, R. S., & Barto, A. G. (2018). *Reinforcement Learning: An Introduction* (2nd ed.). MIT Press. (Capítulos 1-8, 13).
    *   Shoham, Y., & Leyton-Brown, K. (2008). *Multiagent Systems: Algorithmic, Game-Theoretic, and Logical Foundations*. Cambridge University Press. (Capítulos sobre juegos estocásticos y aprendizaje multiagente).
    *   Papers seminales: DQN (Mnih et al., 2015), VDN (Sunehag et al., 2018), QMIX (Rashid et al., 2018), MADDPG (Lowe et al., 2017).
*   **Evaluación:**
    *   Implementaciones de algoritmos (40%) - 4-5 tareas de implementación incremental en entornos de simulación.
    *   Proyecto MARL (30%) - Implementar y entrenar agentes usando un algoritmo MARL en un juego o escenario de negociación/coordinación más complejo.
    *   Examen final práctico (30%) - Demostración de habilidades de implementación y análisis en un entorno de simulación.
*   **Laboratorio (2h/sem):**
    *   Semanas 1-3: Implementación de Value/Policy Iteration y Q-Learning/SARSA en entornos `gym`.
    *   Semanas 4-6: Configuración de entornos multiagente en `PettingZoo` o `Melting Pot`. Implementación de IQL.
    *   Semanas 7-8: Implementación de DQN básico y su extensión a MARL cooperativo (ej. `pytorch-lightning` o `tensorflow_probability` ejemplos).
    *   Semanas 9-11: Implementación de un algoritmo basado en políticas (ej. A2C o MADDPG simplificado). Experimentos con self-play.
    *   Semana 12: Benchmarking y análisis comparativo de los agentes entrenados. Ajuste de hiperparámetros.


![Separador](imagen1.png)
### NSA-103: Psicología y Ética en la Negociación

*   **Créditos:** 5 ECTS
*   **Dedicación:** 3 horas de teoría + 2 horas de laboratorio/seminario por semana (Total 12 semanas de docencia)
*   **Pre-requisitos:** NSA-101 (concurrente).
*   **Objetivos de Aprendizaje:**
    *   Analizar los principales sesgos cognitivos y conductuales que afectan la toma de decisiones y la negociación humana.
    *   Comprender las teorías éticas fundamentales y su relevancia para el diseño y operación de agentes autónomos.
    *   Formalizar y integrar principios éticos (justicia, transparencia, no maleficencia) en los sistemas de control y recompensa de agentes.
    *   Evaluar el comportamiento de los agentes negociadores desde una perspectiva ética, utilizando métricas de fairness y diseñando sistemas de puntuación moral.
*   **Temario Detallado (12 semanas):**
    1.  **Semana 1:** Introducción a la Psicología de la Decisión. Modelos de racionalidad limitada. La Prospect Theory (teoría de las expectativas). Aversión a la pérdida.
    2.  **Semana 2:** Heurísticas y Sesgos en la Negociación. Sesgos comunes: anclaje, framing, exceso de confianza. El papel de las emociones y los estados afectivos.
    3.  **Semana 3:** Elementos Psicológicos de la Negociación. La Zona de Posible Acuerdo (ZOPA). BATNA (Mejor Alternativa a un Acuerdo Negociado). El rol de la confianza, la reputación y la reciprocidad (positivo/negativo).
    4.  **Semana 4:** Introducción a la Ética Filosófica. Utilitarismo (consecuencialismo). Deontología (imperativo categórico Kantiano). Ética de la Virtud (Aristóteles). Aplicación a la IA.
    5.  **Semana 5:** Principios Éticos para la IA. Justicia, Transparencia/Explicabilidad, Responsabilidad, Seguridad/No Maleficencia, Privacidad, Beneficencia. Guías éticas de organizaciones y gobiernos.
    6.  **Semana 6:** El Problema de la Alineación de Valores. Garantizar que los objetivos de la IA estén alineados con los valores humanos. Desafíos en entornos multiagente.
    7.  **Semana 7:** Formalización de la Ética en Agentes. Integración del vector de valores (V) en la función de utilidad/recompensa. Ejemplo: `U(a; θ, V) = U_econ(a; θ) + α * U_eticos(a; V)`.
    8.  **Semana 8:** Sistemas de Recompensa Ética. Penalizaciones por acciones no éticas. Recompensas intrínsecas por seguir principios éticos. Aprendizaje por Refuerzo a partir de Feedback Humano (RLHF) como mecanismo de alineación (conceptos básicos).
    9.  **Semana 9:** Fairness en Sistemas Multiagente. Definiciones de fairness (individual, grupal, procedimental, distributiva). Métricas comunes de fairness (disparidad demográfica, igualdad de oportunidades). Trade-offs entre fairness y eficiencia.
    10. **Semana 10:** Transparencia y Explicabilidad (XAI). ¿Por qué un agente negociador tomó una decisión? Métodos de XAI aplicados a modelos de decisión y LLMs (LIME, SHAP - conceptos). Auditabilidad de los algoritmos.
    11. **Semana 11:** Diseño de un "Score Moral" o "Índice Ético". Cómo cuantificar el comportamiento ético de un agente a lo largo del tiempo. Definición de criterios y ponderaciones.
    12. **Semana 12:** Gobernanza y Regulación. Propuestas de marcos regulatorios (ej. Ley de IA de la UE - aspectos relevantes para agentes autónomos). Responsabilidad e imputabilidad. Dilemas éticos en casos de estudio (ej. uso de agentes negociadores en mercados financieros o sistemas críticos).
*   **Bibliografía Esencial:**
    *   Kahneman, D. (2011). *Thinking, Fast and Slow*. Penguin Books. (Capítulos seleccionados sobre heurísticas y sesgos).
    *   Bazerman, M. H., & Moore, D. A. (2013). *Judgment in Managerial Decision Making* (9th ed.). Wiley. (Capítulos 9-11 sobre negociación).
    *   Wallach, W., & Allen, C. (2009). *Moral Machines: Teaching Robots Right from Wrong*. Oxford University Press.
    *   Mittelstadt, B. D., et al. (2016). *The Ethics of Algorithms: Mapping the Debate*. AI & Society, 31(3), 317-331.
    *   Papers recientes sobre Fairness in AI, Value Alignment, y XAI.
*   **Evaluación:**
    *   Ensayos (30%) - 3 ensayos cortos (aprox. 1000 palabras cada uno) analizando casos de estudio o conceptos éticos/psicológicos.
    *   Diseño de un Score Moral (30%) - Documento que proponga y justifique un sistema para puntuar el comportamiento ético de agentes en un escenario dado.
    *   Proyecto Agente Ético (20%) - Implementación básica en laboratorio de un agente simple con una restricción o función de recompensa ética.
    *   Examen final (20%) - Cubre conceptos teóricos y su aplicación a casos.
*   **Laboratorio/Seminario (2h/sem):**
    *   Semanas 1-3: Discusión de casos de negociación famosos analizados desde la perspectiva de sesgos cognitivos. Ejercicios prácticos para identificar sesgos.
    *   Semanas 4-6: Análisis y debate de dilemas éticos clásicos y su adaptación al contexto de IA. Discusión de guías éticas de IA.
    *   Semanas 7-9: Trabajo en el proyecto "Agente Ético": modelado de funciones de utilidad con componentes éticos, implementación de penalizaciones en un entorno de simulación simple. Uso de herramientas XAI básicas (ej. LIME/SHAP en un modelo de decisión simple) para "inspeccionar" por qué un agente tomó una acción.
    *   Semanas 10-12: Trabajo en el proyecto "Score Moral". Análisis de métricas de fairness en datasets sintéticos. Debates estructurados sobre casos de gobernanza y regulación.


![Separador](imagen1.png)
### NSA-104: Protocolos Algorítmicos de Negociación

*   **Créditos:** 6 ECTS  
*   **Dedicación:** 4 horas de teoría + 2 horas de laboratorio por semana (Total 14 semanas de docencia)  
*   **Pre-requisitos:** NSA-101, NSA-102 (concurrente).
*   **Objetivos de Aprendizaje:**
    *   Diseñar e implementar algoritmos para protocolos de negociación estructurados en entornos complejos con información parcial, incertidumbre dinámica y estructuras de red.
    *   Aplicar algoritmos de búsqueda y planificación (MCTS, POMCP) a problemas de negociación secuencial y decisión bajo incertidumbre.
    *   Analizar las propiedades algorítmicas de protocolos de negociación (eficiencia computacional, estabilidad, robustez, escalabilidad).
    *   Desarrollar algoritmos de negociación que escalen a gran número de agentes, múltiples atributos o entornos de alta dimensionalidad.
    *   Integrar modelos de lenguaje y conocimiento estructurado para mejorar el desempeño estratégico en negociaciones complejas.
*   **Temario Detallado (14 semanas):**
    1. **Semana 1:** Fundamentos y Limitaciones de Modelos Clásicos. Revisión de negociación en entornos simples. Limitaciones de juegos en forma normal/extensiva y regateo clásico. Repaso de diseño de mecanismos: IC, DSIC, BNIC.
    2. **Semana 2:** Negociación en Entornos Parcialmente Observables. POMDPs multiagente: representación de estado, observación, acción, transición, recompensa. Belief states y tracking de creencias.
    3. **Semana 3:** Algoritmos para POMDPs en Negociación. Value Iteration para POMDPs y limitaciones computacionales. Point-Based Value Iteration (PBVI). Métodos de muestreo y Particle Filters para belief tracking.
    4. **Semana 4:** Mecanismos Combinatorios y Subastas Complejas. Subastas combinatorias: problema de determinación del ganador. VCG para entornos combinatorios. Subastas online y adaptativas. Sybil attacks.
    5. **Semana 5:** Negociación Bilateral y Multilateral Estructurada. Modelos de regateo alternado: modelo de Rubinstein con descuento. Extensión a negociaciones multi-parte: coordinación y formación de coaliciones.
    6. **Semana 6:** Negociación en Redes (Networked Negotiation). Modelos de interacción estratégica en estructuras de red. Efectos de topología. Propagación de ofertas y algoritmos de coordinación distribuida.
    7. **Semana 7:** Protocolos de Concesión Multi-atributo. Negociación sobre múltiples dimensiones: precio, cantidad, calidad, tiempo. Modelos de utilidad multi-atributo. Estrategias de concesión en espacios multi-dimensionales.
    8. **Semana 8:** Algoritmos de Búsqueda en Árboles (MCTS). Monte Carlo Tree Search: selección, expansión, simulación, backpropagation. Aplicaciones en juegos con información perfecta e imperfecta.
    9. **Semana 9:** MCTS Aplicado a Negociación Secuencial. Extensiones de MCTS para POMDPs (POMCP). Uso para planificar secuencias de ofertas y contra-ofertas en regateo complejo y subastas secuenciales.
    10. **Semana 10:** Mercados de Predicción y Agregación de Información. Concepto y funcionamiento de mercados de predicción. Market Scoring Rules: Logarithmic Market Scoring Rule (LMSR). Agregación descentralizada de información.
    11. **Semana 11:** Tácticas Algorítmicas y Robustez contra Manipulación. Estrategias de anclaje algorítmico. Técnicas de escalada y devaluación. Detección de tácticas adversarias. Prevención de manipulación y resistencia a colusiones.
    12. **Semana 12:** Escalabilidad y Algoritmos Aproximados. Estrategias de descomposición para entornos de alta dimensionalidad. Negociación peer-to-peer vs centralizada. Algoritmos aproximados para muchos agentes.
    13. **Semana 13:** Integración de Conocimiento y LLMs. Uso de LLMs para procesar información textual relevante. Integración con Knowledge Graphs y bases de datos. Modelos híbridos para estrategia de negociación.
    14. **Semana 14:** Simulación, Benchmarking y Evaluación Comparativa. Simulaciones multiagente a gran escala. Métricas de evaluación: eficiencia de Pareto, equidad (coeficiente Gini), velocidad de convergencia, resistencia a manipulación.
*   **Bibliografía Esencial:**
    *   Nisan, N., Roughgarden, T., Tardos, E., & Vazirani, V. V. (Eds.). (2007). *Algorithmic Game Theory*. Cambridge University Press. (Capítulos 9, 11, 13, 18).
    *   Boutilier, C., Dean, T., & Hanks, S. (2006). "Decision-Theoretic Planning under Uncertainty." *Journal of AI Research*, 11, 1-94.
    *   Osborne, M. J., & Rubinstein, A. (1990). *Bargaining and Markets*. Academic Press.
    *   Browne, C., Powley, E., et al. (2012). "A Survey of Monte Carlo Tree Search Methods." *IEEE Trans. on Computational Intelligence and AI in Games*, 4(1), 1-43.
    *   Papers recientes sobre negociación en redes, POMDPs multiagente, MCTS aplicado a negociación, y mercados de predicción (AAMAS, IJCAI, AAAI).
*   **Evaluación:**
    *   Problem sets (25%) - 4 conjuntos de problemas sobre POMDPs, algoritmos de búsqueda, escalabilidad y diseño de protocolos.
    *   Proyecto MCTS para Negociación Compleja (40%) - Implementar MCTS/POMCP para resolver negociación secuencial con incertidumbre, comparando con al menos un protocolo estructurado alternativo.
    *   xamen final teórico-algorítmico (35%) - Cubre conceptos teóricos, propiedades de algoritmos y diseño de protocolos robustos.
*   **Laboratorio (2h/sem):**
    *   Semanas 1-3: Configuración de entornos POMDP multiagente usando `Gymnasium` y `PettingZoo`. Implementación de belief tracking básico. Simulación de negociación con información parcial.
    *   Semanas 4-6: Implementación de subastas combinatorias básicas y modelos de regateo Rubinstein. Algoritmos de negociación en redes usando `networkx`. Propagación de acuerdos y coordinación distribuida.
    *   Semanas 7-10: Implementación de MCTS básico y adaptación a negociación secuencial. Experimentación con POMCP. Implementación de Market Scoring Rules y simulación de mercados de predicción.
    *   Semanas 11-14: Desarrollo de tácticas algorítmicas avanzadas. Integración de APIs de LLMs para procesamiento de información contextual. Configuración de simulaciones multiagente comparativas y análisis de métricas de rendimiento.



![Separador](imagen1.png)
### NSA-105: Grandes Modelos de Lenguaje y Diálogo Estratégico

*   **Créditos:** 6 ECTS
*   **Dedicación:** 4 horas de teoría + 2 horas de laboratorio por semana (Total 12 semanas de docencia)
*   **Pre-requisitos:** Experiencia práctica con LLMs (entrada), Programación Avanzada.
*   **Objetivos de Aprendizaje:**
    *   Comprender en profundidad la arquitectura Transformer y el ciclo de vida (pre-entrenamiento, fine-tuning) de los LLMs.
    *   Dominar técnicas avanzadas de "prompt engineering" para guiar a los LLMs en tareas de generación de lenguaje estratégico y negociador.
    *   Diseñar e implementar módulos de diálogo que permitan a los agentes negociadores comunicarse de manera coherente, persuasiva y estratégica en lenguaje natural.
    *   Integrar LLMs con otros componentes de un agente negociador (motor de decisión, módulo de estado) y evaluar el desempeño del diálogo.
*   **Temario Detallado (12 semanas):**
    1.  **Semana 1:** Introducción a los Modelos de Lenguaje. Del N-grama a las Redes Neuronales Recurrentes (repaso conceptual). La limitación de la memoria y la dependencia a largo plazo.
    2.  **Semana 2:** La Arquitectura Transformer. Atención y auto-atención ("Attention Is All You Need"). Codificadores y decodificadores. Positional Encoding.
    3.  **Semana 3:** Modelos Pre-entrenados. BERT (Encoder-only) para tareas de comprensión. GPT (Decoder-only) para generación. Estrategias de pre-entrenamiento (Masked Language Modeling, Next Token Prediction).
    4.  **Semana 4:** Fine-tuning e Instruction Tuning. Adaptación de modelos a tareas específicas. Fine-tuning supervisado. Instruction Tuning: entrenar modelos para seguir instrucciones en lenguaje natural.
    5.  **Semana 5:** Principios Fundamentales de Prompt Engineering. Claridad, especificidad, concisión. El rol del Agente (Persona). Contexto. Formato de salida deseado.
    6.  **Semana 6:** Técnicas Avanzadas de Prompting. Zero-shot, Few-shot prompting: aprendizaje in-contexto. Prompting con ejemplos de negociación.
    7.  **Semana 7:** Chain-of-Thought (CoT) y Razonamiento. Inducir al modelo a "pensar paso a paso". Aplicación de CoT para generar justificaciones de ofertas o analizar argumentos del oponente.
    8.  **Semana 8:** Prompting para Tareas de Negociación Específicas. Generación de ofertas. Generación de contra-ofertas. Redacción de argumentos de persuasión. Resumen de la posición del oponente.
    9.  **Semana 9:** Modelado del Diálogo Negociador. Seguimiento del estado del diálogo: parsing de ofertas/demandas del lenguaje natural. Representación interna del estado de la negociación.
    10. **Semana 10:** Gestión de Información Privada y Concesiones. Cómo diseñar prompts para que el LLM gestione información que no debe revelar. Generación de concesiones graduales y estratégicas.
    11. **Semana 11:** Coherencia y Consistencia Estratégica. Asegurar que las respuestas del LLM se alineen con la estrategia global del agente (definida por el motor de decisión). Manejo de alucinaciones en el diálogo de negociación.
    12. **Semana 12:** Integración y Evaluación de Agentes Conversacionales. Conectar el módulo LLM con el motor de decisión (basado en Teoría de Juegos/RL). Métricas de evaluación del diálogo (fluidez, coherencia, éxito de la negociación, credibilidad). Detección básica de engaño o manipulación en el lenguaje.

*   **Bibliografía Esencial:**
    *   Vaswani et al. (2017). *Attention Is All You Need*. NeurIPS.
    *   Lewis, M., Yin, Y., Batra, D., Zitnick, C. L., & Parikh, D. (2017). *Deal or No Deal? End-to-End Learning for Negotiation Dialogues*. ICLR.
    *   Wei, J., Zhou, X., Schuurmans, D., & Le, Q. V. (2022). *Chain-of-Thought Prompting Elicits Reasoning in Large Language Models*. arXiv preprint arXiv:2201.11903.
    *   Jurafsky, D., & Martin, J. H. (2023). *Speech and Language Processing* (3rd ed. draft). (Capítulos relevantes sobre modelos de lenguaje, diálogo).
    *   Documentación y research papers de modelos específicos (GPT-4, Gemini, Claude, Llama).

*   **Evaluación:**
    *   Talleres de Prompting (30%) - 4-5 entregas prácticas de prompts diseñados para tareas de negociación, con análisis de las respuestas de los LLMs.
    *   Implementación Módulo Conversacional (40%) - Desarrollo de un pipeline básico que use un LLM para procesar y generar turnos de diálogo en un escenario de negociación simulado simple.
    *   Proyecto de Agente Conversacional (30%) - Integración del módulo conversacional con un motor de decisión simple y demostración del agente negociando en un entorno básico.
*   **Laboratorio (2h/sem):**
    *   Semanas 1-4: Uso de APIs de LLMs comerciales y open-source (OpenAI API, Google AI Studio, Hugging Face). Experimentación con arquitecturas (uso de modelos encoder/decoder para tareas específicas). Fine-tuning básico con datasets pequeños (ej. dataset de diálogos de negociación).
    *   Semanas 5-8: Diseño y prueba intensiva de prompts. Comparación de resultados con diferentes técnicas (zero-shot vs few-shot vs CoT). Uso de herramientas para evaluar la calidad de la generación de texto.
    *   Semanas 9-11: Desarrollo del módulo conversacional: parsing de texto, extracción de información clave (ofertas), integración con un estado interno de la negociación en Python. Generación de texto condicionado al estado y a la estrategia.
    *   Semana 12: Trabajo en el proyecto final: conexión con un motor de decisión simple, ejecución de simulaciones de negociación con el agente completo, evaluación de su desempeño conversacional y estratégico.


---

## CUATRIMESTRE 2 (Q2): Interacción, Cognición y Diseño (30 ECTS)
![Separador](imagen1.png)
### NSA-106: Interacción Humano-Agente en Negociación

*   **Créditos:** 6 ECTS
*   **Dedicación:** 4h teoría + 2h laboratorio/seminario por semana
*   **Pre-requisitos:** NSA-101, NSA-103, NSA-105.
*   **Objetivos de Aprendizaje:**
    *   Analizar las dinámicas psicológicas y cognitivas que emergen en negociaciones donde participan humanos y agentes de IA.
    *   Diseñar interfaces de usuario y protocolos de interacción que faciliten la comprensión mutua, la confianza y la colaboración (o competencia justa) entre humanos y agentes.
    *   Evaluar la percepción humana del comportamiento de los agentes negociadores (justicia, competencia, intencionalidad).
    *   Aplicar principios de diseño centrado en el humano (HCD) para crear sistemas de negociación asistida por IA o sistemas donde el agente es un negociador directo.
*   **Temario (12 semanas):**
    1.  **Semana 1:** Introducción a la Interacción Humano-IA. Modelos de H-AI. Desafíos específicos en contextos de decisión y negociación.
    2.  **Semana 2:** Modelos de Confianza Humano-IA. Confianza basada en el desempeño, el proceso, la intención. Factores que influyen en la confianza (predictibilidad, fiabilidad, explicabilidad).
    3.  **Semana 3:** Psicología de la Interacción con Agentes Artificiales. Antropomorfismo. Atribución de intenciones y creencias a agentes. Percepción de la agencia.
    4.  **Semana 4:** Diseño de Interfaces para la Negociación H-A. Visualización del estado de la negociación, historial de ofertas, ZOPA estimada. Diseño de controles para la delegación y supervisión del agente.
    5.  **Semana 5:** XAI en la Práctica. Adaptando explicaciones sobre las decisiones del agente negociador a un usuario humano (post-hoc, justificaciones verbales usando LLMs).
    6.  **Semana 6:** Sistemas de Negociación Asistida por IA (AI como Copiloto). Diseño de herramientas que aumenten las capacidades del negociador humano (análisis de texto, sugerencia de tácticas, simulación de escenarios).
    7.  **Semana 7:** Evaluación de la Percepción Humana. Métricas de usabilidad (SUS, NASA-TLX). Medición de la justicia percibida, la competencia percibida, la intención percibida.
    8.  **Semana 8:** Metodologías de Investigación en H-A. Diseño de experimentos con participantes humanos (diseños between-subjects, within-subjects). Variables dependientes e independientes.
    9.  **Semana 9:** Conducción de Experimentos. Reclutamiento de participantes. Procedimientos experimentales. Consideraciones éticas (consentimiento informado, debriefing).
    10. **Semana 10:** Análisis de Datos de Interacción. Análisis cuantitativo (estadísticas descriptivas, inferenciales) y cualitativo (protocolos de pensamiento, entrevistas).
    11. **Semana 11:** Ética de la Interacción H-A. Riesgos de manipulación por parte del agente. Dependencia humana excesiva en la IA. Pérdida de habilidades de negociación humanas ("automation bias").
    12. **Semana 12:** Presentación de Proyectos y Discusión.

*   **Bibliografía:** Dix et al. (2004). *Human-Computer Interaction*. Shneiderman et al. (2016). *Designing the User Interface*. Lee & See (2004). *Trust in Automation*. Papers recientes en ACM CHI, HRI, CSCW, AI & Society sobre interacción Humano-IA, confianza y XAI.

*   **Evaluación:**
    *   Diseño de Experimento H-A (40%) - Propuesta detallada (protocolo, métricas, diseño) para un experimento que estudie un aspecto de la negociación H-A.
    *   Análisis de Datos de Interacción (30%) - Análisis cuantitativo y cualitativo de un dataset proporcionado de interacciones H-A simuladas o reales.
    *   Informe de Diseño de Interfaz/Usabilidad (30%) - Prototipo básico (maquetas interactivas) de una interfaz para negociación H-A y su evaluación con usuarios (mini user study).
*   **Laboratorio/Seminario (2h/sem):**
    *   Semanas 1-4: Análisis de interfaces existentes de negociación H-A. Discusión de casos de estudio.
    *   Semanas 5-8: Prototipado de interfaces en frameworks web (ej. Flask/Django con HTML/JS) o herramientas de prototipado rápido (ej. Figma, Adobe XD). Diseño de encuestas y métricas de usabilidad/percepción.
    *   Semanas 9-12: Configuración y ejecución de experimentos con participantes (usando plataformas online como Prolific o reclutamiento local simulado). Análisis cuantitativo (ej. usando `pingouin` o `statsmodels` en Python) y cualitativo de datos de interacción y percepción. Preparación de informes.


![Separador](imagen1.png)
### NSA-107: Aprendizaje Inverso y Modelado de Agentes

*   **Créditos:** 6 ECTS
*   **Dedicación:** 4h teoría + 2h laboratorio por semana
*   **Pre-requisitos:** NSA-102, NSA-101.
*   **Objetivos de Aprendizaje:**
    *   Inferir las funciones de recompensa o utilidad de agentes observando sus trayectorias de comportamiento.
    *   Aplicar técnicas de Aprendizaje Inverso por Refuerzo (IRL) para entender los objetivos implícitos de otros agentes.
    *   Modelar las creencias, el conocimiento y el "tipo" de otros agentes utilizando enfoques Bayesianos o basados en Teoría de la Mente Computacional.
    *   Utilizar estos modelos para predecir el comportamiento futuro del oponente y adaptar la propia estrategia de negociación.
*   **Temario (12 semanas):**
    1.  **Semana 1:** Introducción al Aprendizaje Inverso (Inverse Reinforcement Learning - IRL). Diferencia entre RL e IRL. El problema de IRL: dada una política (supuestamente) óptima, inferir la función de recompensa que la justifica.
    2.  **Semana 2:** IRL como Optimización. Enfoques tempranos (Ng & Russell). Abstraction from Observed Behavior.
    3.  **Semana 3:** IRL Basado en Entropía Máxima. Max Causal Entropy IRL (Ziebart et al.). Conexión con el aprendizaje de políticas estocásticas.
    4.  **Semana 4:** Bayesian IRL (BIRL). Modelado probabilístico de la función de recompensa. Uso de métodos de inferencia (ej. MCMC) para estimar distribuciones de recompensas.
    5.  **Semana 5:** Conexiones de IRL con GANs. Generative Adversarial Imitation Learning (GAIL - conceptos): aprender políticas que se parezcan a las del experto sin inferir explícitamente la recompensa.
    6.  **Semana 6:** Aplicaciones de IRL a la Negociación. Inferir las preferencias o la función de utilidad del oponente a partir de sus ofertas, contra-ofertas y decisiones (modelado de preferencias).
    7.  **Semana 7:** Modelado de Oponentes Basado en Inferencia de Parámetros. Estimación de parámetros clave del modelo del oponente (ej. factor de descuento, aversión al riesgo, BATNA) usando métodos Bayesianos.
    8.  **Semana 8:** Introducción a la Teoría de la Mente Computacional (ToM). Modelado de las creencias del oponente sobre el mundo y sobre otros agentes. Niveles de recursión (agente modela al oponente, que modela al agente, etc.).
    9.  **Semana 9:** Modelado de Creencias y Conocimiento del Oponente. Representación computacional del estado epistémico del oponente. Actualización de creencias a partir de observaciones.
    10. **Semana 10:** Aprendizaje de Preferencias Humanas. Técnicas para aprender la función de recompensa o utilidad de un usuario humano a partir de demostraciones, comparaciones o feedback explícito. Aplicación a sistemas de negociación asistida.
    11. **Semana 11:** Integración de Modelado de Oponentes en la Estrategia de Negociación. Cómo usar la inferencia de la "mente" del oponente para adaptar la propia estrategia (ej. elegir la próxima oferta, decidir cuándo ceder).
    12. **Semana 12:** Casos de Estudio y Temas Avanzados. IRL en juegos complejos, modelado de agentes heterogéneos, detección de engaño mediante modelado de intenciones.

*   **Bibliografía:**
   *   Ng & Russell (2000). *Algorithms for Inverse Reinforcement Learning*.
   *   Abbeel & Ng (2004). *Apprenticeship Learning via Inverse Reinforcement Learning*.
   *   Ziebart et al. (2008). *Maximum Causal Entropy IRL*.
   *   Baker et al. (2009). *Goal Inference as Inverse Planning*.
   *   Papers recientes sobre IRL, Cooperative IRL, ToM computacional en MARL y negociación.

*   **Evaluación:**
    *   Implementación de Algoritmo IRL (40%) - Implementar un algoritmo IRL (ej. Max Entropy IRL o BIRL simplificado) en un entorno de simulación simple.
    *   Proyecto Bayesiano de Modelado de Oponentes (30%) - Desarrollar un modelo Bayesiano para inferir el "tipo" de un agente (ej. sus preferencias, su BATNA) a partir de una secuencia de ofertas en un juego de negociación simulado.
    *   Examen final (30%) - Cubre conceptos teóricos y la aplicación de métodos de modelado.
*   **Laboratorio (2h/sem):**
    *   Semanas 1-5: Implementación de algoritmos IRL en Python usando datos de trayectorias generadas por agentes sintéticos o pre-entrenados. Uso de librerías de optimización.
    *   Semanas 6-10: Trabajo en el proyecto Bayesiano de Modelado: uso de librerías de modelado probabilístico (ej. `PyMC3`, `Stan`, `Pyro`) para definir y ajustar modelos de agentes. Aplicar técnicas de inferencia (ej. MCMC, Variational Inference) a datos de negociación simulada o datasets públicos (ej. `Dataset of Negotiation Dialogues` si está disponible).
    *   Semanas 11-12: Experimentación con la integración de modelos de oponentes simples en un agente de negociación. Análisis de cómo la precisión del modelo del oponente afecta el resultado de la negociación.


![Separador](imagen1.png)
### NSA-108: Programación avanzada con LLMs

*   **Créditos:** 6 ECTS  
*   **Dedicación:** 4 horas de teoría + 2 horas de laboratorio por semana (Total 14 semanas de docencia)  
*   **Pre-requisitos:** Programación Avanzada, Fundamentos de IA, Procesamiento de Lenguaje Natural básico  
*   **Objetivos de Aprendizaje:**
    *   Diseñar y implementar pipelines complejos de LLMs que van más allá del prompting básico, utilizando control de flujo, restricciones semánticas y orquestación multi-llamada
    *   Evaluar y seleccionar frameworks de programación de LLMs (LMQL, DSPy, SGLang, LLMCompiler) según requisitos específicos de rendimiento, costo y funcionalidad
    *   Optimizar automáticamente prompts y cadenas de razonamiento mediante técnicas de meta-aprendizaje y compilación declarativa
    *   Implementar sistemas de generación controlada con restricciones sintácticas y semánticas aplicadas durante la decodificación
    *   Desarrollar aplicaciones multi-agente escalables con paralelización inteligente y manejo eficiente de recursos computacionales
*   **Temario Detallado (12 semanas):**
    1.  **Semana 1: Introducción y Fundamentos**  Evolución del prompting a la programación estructurada. Definición de Language Model Programming (LMP). Diferencias con prompting tradicional. Componentes básicos: texto, scripting, control de flujo, restricciones. Casos de uso industriales y limitaciones del enfoque convencional.
    2.  **Semana 2: Arquitecturas de Programas LLM**  Anatomía de un programa LLM: entrada, procesamiento, salida. Patrones de orquestación: secuencial, paralelo, condicional, iterativo. Gestión de contexto y estado en aplicaciones multi-llamada. Principios de composabilidad y modularidad. Variables, holes y referencias entre llamadas.
    3.  **Semana 3: Restricciones y Generación Controlada**  Tipos de restricciones: sintácticas (formato, longitud), semánticas (contenido, coherencia), pragmáticas (intención, contexto). Técnicas de enmascaramiento a nivel de token. Evaluación eager vs lazy. Gramáticas formales para estructuración de salidas. Trade-offs entre control y creatividad.
    4.  **Semana 4: LMQL - Language Model Query Language**  Sintaxis declarativa e imperativa. Definición de consultas con holes `[variable]` y referencias `{variable}`. Cláusula `where` para restricciones. Métodos de decodificación (argmax, beam, sample). Control de flujo con Python embebido. Optimizaciones para minimizar llamadas al modelo.
    5.  **Semana 5: DSPy - Programación Declarativa Auto-optimizable**  Módulos declarativos vs templates hardcodeados. Firmas de lenguaje natural como especificaciones. Grafos de transformación de texto. Sistema de compilación automática. Optimización de métricas objetivo. Técnicas de few-shot learning automático. Integración con pipelines de ML.
    6.  **Semana 6: SGLang - Structured Generation Language**  Arquitectura frontend/backend. Primitivas de generación: `gen`, `select`, `fork`, `join`. Control explícito de paralelismo. Manejo de multimodalidad (`image`, `video`, `audio`). Optimizaciones de runtime: batching dinámico, gestión de memoria, prefetching. Integración como backend para frameworks de alto nivel.
    7.  **Semana 7: LLMCompiler y Orquestación Paralela**  Descomposición de tareas en DAGs (Directed Acyclic Graphs). Análisis de dependencias y paralelización automática. Componentes: Planner, Task Fetcher, Executor. Optimización de latencia y throughput. Manejo de fallos y estrategias de recuperación. Comparación con enfoques secuenciales.
    8.  **Semana 8: Análisis Comparativo de Frameworks**  Criterios de evaluación: expresividad, rendimiento, facilidad de uso, ecosistema. Benchmarks estándar y métricas de comparación. LMQL vs DSPy vs SGLang vs LLMCompiler: fortalezas y casos de uso. Interoperabilidad y migración. Frameworks emergentes: Guidance, Outlines, LangChain.
    9.  **Semana 9: Optimización y Eficiencia**  Métricas de rendimiento: latencia, throughput, costo por token, calidad de salida. Técnicas de caching y reutilización de computación. Estrategias de batching y paralelización. Análisis de complejidad computacional. Optimización de prompts para reducir tokens. Trade-offs rendimiento-precisión.
    10.  **Semana 10: Sistemas Multi-Agente con LLMs**  Patrones de comunicación inter-agente. Coordinación distribuida y protocolos de consenso. Especialización de roles y división de tareas. Gestión de conflictos y negociación automática. Escalabilidad horizontal. Aplicaciones: traducción colaborativa, sistemas de recomendación multi-perspectiva.
    11.  **Semana 11: Evaluación y Testing de Sistemas LLM**  Métricas de calidad: coherencia, factualidad, relevancia, consistencia. Testing automatizado y suites de regresión. Generación automática de casos de prueba. Benchmarking comparativo entre implementaciones. Detección de degradación de rendimiento. A/B testing para optimización de prompts.
    12.  **Semana 12: Aplicaciones Empresariales y Deployment**  Arquitecturas de microservicios con LLMs. Gestión de configuración y versionado de prompts. Monitoreo, logging y observabilidad en producción. Escalado automático y load balancing. Consideraciones de costo y presupuesto. Integración con sistemas legacy.
    13.  **Semana 13: Ética, Sesgo y Seguridad**  Detección y mitigación de sesgos algorítmicos en generación. Técnicas de red-teaming y adversarial testing. Filtros de contenido y moderación automática. Transparencia e interpretabilidad de decisiones. Consideraciones de privacidad y protección de datos. Marco regulatorio (AI Act, GDPR).
    14.  **Semana 14: Tendencias Futuras y Proyecto Final**  Integración con modelos multimodales avanzados. Técnicas de fine-tuning específico para programación. Edge computing y inferencia local. Presentación y evaluación de proyectos finales. Roadmaps tecnológicos y oportunidades de investigación.

*   **Bibliografía Esencial:**
    *   Beurer-Kellner, L., Fischer, M., & Vechev, M. (2023). "Prompting Is Programming: A Query Language for Large Language Models." *PLDI 2023*.
    *   Khattab, O., Singhvi, A., Wang, P., et al. (2023). "DSPy: Compiling Declarative Language Model Calls into Self-Improving Pipelines." *arXiv:2310.03714*.
    *   Zheng, L., Yin, L., Xie, Z., et al. (2023). "SGLang: Structured Generation Language for Large Language Models." *arXiv:2312.07104*.
    *   Kim, G., Bae, S., Kang, D., et al. (2024). "LLMCompiler: An LLM Compiler for Parallel Function Calling." *ICML 2024*.
    *   Weng, L. (2024). *Programming Large Language Models: A Practical Guide*. O'Reilly Media. (Capítulos 3, 5, 8, 12).

*   **Evaluación:**
    *   **Problem sets (30%)** - 4 tareas prácticas que combinan implementación de algoritmos y análisis de rendimiento en diferentes frameworks.
    *   **Proyecto "Sistema Multi-Framework" (35%)** - Implementación de una aplicación compleja que integre al menos 2 frameworks diferentes, con análisis comparativo de rendimiento y costo.
    *   **Examen final teórico-práctico (35%)** - Diseño de arquitecturas LLM, optimización de prompts, y resolución de problemas de programación estructurada.
*   **Laboratorio (2h/sem):**
    *   **Semanas 1-3:** Configuración de entornos de desarrollo. Implementación de pipelines básicos con llamadas múltiples. Ejercicios de prompting estructurado vs tradicional.
    *   **Semanas 4-5:** Desarrollo con LMQL. Implementación de consultas con restricciones complejas. Optimización de consultas y análisis de rendimiento.
    *   **Semanas 6-7:** Programación declarativa con DSPy. Creación de módulos auto-optimizables. Comparación de métricas antes/después de compilación automática.
    *   **Semanas 8-9:** Desarrollo con SGLang. Implementación de sistemas paralelos y multimodales. Optimización de runtime y gestión de recursos.
    *   **Semanas 10-11:** Orquestación con LLMCompiler. Diseño de DAGs complejos. Implementación de sistemas multi-agente con coordinación automática.
    *   **Semanas 12-14:** Integración de frameworks. Desarrollo del proyecto final. Testing, debugging y optimización de aplicaciones complejas. Preparación de demostraciones.


![Separador](imagen1.png)
### NSA-109: Ética Aplicada y Gobernanza de Sistemas Autónomos Negociadores

*   **Créditos:** 6 ECTS
*   **Dedicación:** 4h teoría/seminario + 2h laboratorio/seminario por semana
*   **Pre-requisitos:** NSA-103.
*   **Objetivos de Aprendizaje:**
    *   Analizar casos de uso complejos de agentes negociadores autónomos desde múltiples perspectivas éticas y sociales.
    *   Diseñar e implementar mecanismos de auditoría y rendición de cuentas para las decisiones y el comportamiento de los agentes.
    *   Evaluar críticamente los marcos regulatorios existentes y propuestos para la IA y la negociación autónoma.
    *   Debatir y proponer soluciones para los desafíos de responsabilidad, transparencia y equidad en la operación de sistemas de negociación a gran escala.
*   **Temario (12 semanas):**
    1.  **Semana 1:** Repaso de Fundamentos Éticos y Desafíos en IA. Principios éticos clave. El problema de la alineación. Fairness y sus métricas.
    2.  **Semana 2:** Casos de Estudio Éticos en Negociación (I). Mercados financieros: estabilidad vs. manipulación por agentes de alta frecuencia. Riesgos sistémicos.
    3.  **Semana 3:** Casos de Estudio Éticos en Negociación (II). Ámbito legal: Mediación asistida por IA, negociación de sentencias (plea bargaining autónomo). Riesgos de inequidad y pérdida de derechos.
    4.  **Semana 4:** Casos de Estudio Éticos en Negociación (III). Gestión de recursos compartidos (agua, energía): equidad intergeneracional, acceso justo. Negociación en plataformas online: moderación de contenido, términos de servicio.
    5.  **Semana 5:** Diseño de Sistemas de Auditoría para Agentes Negociadores. Registro detallado de decisiones, ofertas, información procesada. Formatos de log.
    6.  **Semana 6:** Justificaciones Post-Hoc y Explicabilidad Avanzada. Métodos de XAI aplicados a modelos complejos (ej. LRP, SHAP para Deep RL). Generación de explicaciones textuales usando LLMs sobre las decisiones del agente.
    7.  **Semana 7:** Marcos de Responsabilidad. Modelos de responsabilidad (basada en el actor, basada en el diseño, compartida). Imputabilidad: ¿quién es responsable cuando un agente autónomo negocia un mal acuerdo o actúa de forma no ética?
    8.  **Semana 8:** Marcos Regulatorios (I). La Ley de IA de la UE: clasificación de riesgos, requisitos para sistemas de alto riesgo. Cómo aplicar estos requisitos a agentes negociadores en diferentes dominios.
    9.  **Semana 9:** Marcos Regulatorios (II). Otros enfoques regulatorios internacionales (EE. UU., Asia). Estándares técnicos y certificación ética. Sandboxes regulatorios.
    10. **Semana 10:** Gobernanza de Sistemas de Negociación a Gran Escala. Desafíos en sistemas con muchos agentes heterogéneos. Gobernanza descentralizada: el rol de DAOs y Smart Contracts en la aplicación de reglas de negociación.
    11. **Semana 11:** Sesgos Algorítmicos Avanzados en Negociación. Cómo los sesgos en los datos de entrenamiento pueden manifestarse en estrategias de negociación discriminatorias. Métodos avanzados para detectar y mitigar sesgos en el diseño y la operación.
    12. **Semana 12:** El Futuro Socioeconómico. Impacto de la negociación autónoma en el mercado laboral, la distribución de la riqueza y el poder de negociación. Discusión de futuros escenarios y cómo gobernarlos éticamente.

*   **Bibliografía:** Wallach & Allen (2009) - Revisitado. Floridi et al. (2019). *AI in Public Sphere: Towards an Ethical Framework*. Jobin et al. (2019). *Global approaches to AI ethics*. Papers sobre AI Law, Auditability, Accountability, AI Governance de conferencias (AAAI/ACM AIES, ACM FAccT) y revistas (AI & Society, Ethics and Information Technology). Documentos regulatorios (EU AI Act, NIST AI Risk Management Framework). Libros y artículos sobre ética aplicada en finanzas, derecho, etc.

*   **Evaluación:**
    *   Análisis Forense de Simulación (40%) - Análisis detallado (usando logs) de una simulación compleja de negociación multiagente para identificar, documentar y analizar incidentes éticos (ej. comportamiento unfair, manipulador, errores con consecuencias éticas).
    *   Propuesta Regulatoria/de Gobernanza (30%) - Documento (aprox. 15 páginas) proponiendo un marco regulatorio o un esquema de gobernanza para un caso de uso específico y de "alto riesgo" de negociación autónoma.
    *   Debate Estructurado y Participación (30%) - Participación activa y argumentada en debates grupales sobre dilemas éticos complejos planteados en clase.
*   **Laboratorio/Seminario (2h/sem):**
    *   Semanas 1-4: Discusión y análisis profundo de los casos de estudio propuestos. Análisis de las implicaciones éticas y sociales.
    *   Semanas 5-7: Trabajo práctico con logs de simulaciones (proporcionados o generados en NSA-104/NSA-204). Desarrollar scripts básicos en Python para extraer métricas éticas y de fairness. Uso de herramientas XAI básicas aplicadas a la explicación de decisiones en el log.
    *   Semanas 8-11: Análisis comparativo de textos legales y regulatorios. Diseño de simulaciones de "sandboxes" regulatorios (definición de reglas y métricas de cumplimiento). Preparación para los debates.
    *   Semana 12: Debate final.


![Separador](imagen1.png)
### NSA-110: Seminario de Investigación y Temas de Vanguardia

*   **Créditos:** 6 ECTS
*   **Dedicación:** 3h seminario/discusión + 3h trabajo autónomo por semana
*   **Pre-requisitos:** Todos los cursos del Q1.
*   **Objetivos de Aprendizaje:**
    *   Desarrollar habilidades avanzadas de lectura crítica y análisis de la literatura científica reciente en el campo.
    *   Identificar los problemas abiertos y las fronteras de investigación actuales en negociación con sistemas autónomos.
    *   Practicar la comunicación oral y escrita de conceptos científicos complejos.
    *   Explorar áreas de investigación potencial y refinar intereses para el Proyecto Final de Master (TFM).
*   **Formato:** Seminario semanal. Cada semana, uno o dos estudiantes (o el profesor) presentan y lideran la discusión de 1-2 papers seminales o muy recientes sobre un tema de vanguardia. Los temas cubren las intersecciones de IA, Juegos, Ética, LLMs en negociación, incluyendo: negociación con información cuántica, agentes que aprenden a engañar o a detectar engaños, el impacto socioeconómico de la negociación autónoma, la negociación en real-time o a gran escala, negociación con recursos finitos, etc. Se requiere lectura previa y participación activa de todos. Hacia el final del semestre, se dedica tiempo a presentar ideas iniciales para el TFM y recibir feedback.
*   **Bibliografía:** Artículos recientes de las principales conferencias (NeurIPS, ICML, ICLR, AAMAS, IJCAI, AAAI, ACM AIES, ACM FAccT, etc.) y revistas (AIJ, JAIR, Games and Economic Behavior, AI & Society, Ethics and Information Technology, etc.) relevantes. Se definen los papers específicos cada semestre.
*   **Evaluación:**
    *   Presentación(es) de paper(s) (40%).
    *   Participación en la discusión (30%).
    *   Propuesta de Roadmap para TFM (30%) - Documento breve (aprox. 5-10 páginas) outlining posibles temas, preguntas de investigación, revisión preliminar de la literatura, metodología inicial, y cronograma propuesto para el TFM.
*   **Laboratorio/Trabajo Autónomo (3h/sem):** Lectura intensiva de papers. Preparación de presentaciones. Investigación de literatura adicional sobre temas de interés. Trabajo inicial en la definición del tema y la búsqueda bibliográfica para la propuesta de TFM.
