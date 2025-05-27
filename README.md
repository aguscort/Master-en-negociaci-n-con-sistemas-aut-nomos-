# Master Universitario en Negociación con Sistemas Autónomos
**Total Créditos ECTS:** 120

---
## Presentación del Programa

El Master en Negociación con Sistemas Autónomos es un programa pionero diseñado para formar a la próxima generación de expertos e investigadores en la interacción estratégica entre agentes inteligentes, tanto artificiales como humanos. En un mundo donde los sistemas autónomos toman decisiones cada vez más complejas y participan activamente en procesos de negociación, es imperativo comprender los fundamentos teóricos, algorítmicos, psicológicos y éticos que subyacen a estas interacciones. Este programa multidisciplinar ofrece una formación rigurosa en Teoría de Juegos, Aprendizaje por Refuerzo Multiagente, Psicología Cognitiva, Ética Computacional y Grandes Modelos de Lenguaje, combinada con una fuerte orientación práctica y de investigación aplicada para abordar los desafíos actuales y futuros de la negociación en la era de la IA.

---
## Perfil de Entrada

La maestría está dirigida a graduados con perfiles cuantitativos y técnicos, interesados en la intersección de la inteligencia artificial, la economía, la psicología y la ética. Se espera que los candidatos tengan una base sólida que les permita abordar los aspectos teóricos y prácticos del programa.

---
## Pre-requisitos de Entrada Obligatorios

*   **Programación Avanzada en Python:** Dominio del lenguaje y experiencia con librerías clave para computación científica (`NumPy`, `SciPy`, `Pandas`) y machine learning (`TensorFlow` o `PyTorch`, `scikit-learn`). Se valorará familiaridad con programación orientada a objetos y estructuras de datos eficientes.
*   **Fundamentos de Teoría de Juegos:** Conocimiento de juegos en forma normal y extensiva, estrategias puras y mixtas, dominancia, y el concepto de equilibrio de Nash. Familiaridad básica con juegos dinámicos e inducción hacia atrás.
*   **Estadística y Probabilidad:** Conocimiento de estadística descriptiva e inferencial, principales distribuciones de probabilidad, teorema de Bayes, y fundamentos de regresión lineal.
*   **Introducción a Machine Learning:** Comprensión de los conceptos básicos de aprendizaje supervisado (regresión, clasificación) y no supervisado (clustering), métricas de evaluación, y procesos de validación de modelos.
*   **Experiencia Práctica con LLMs:** Haber utilizado activamente al menos dos Grandes Modelos de Lenguaje (ej. ChatGPT, Gemini, Claude) para tareas de generación de texto, resumen, traducción, etc. Comprender los conceptos básicos de "prompting" (instrucción) y las capacidades/limitaciones generales de estos modelos.

---
## Estructura Modular del Programa

El programa se articula en dos años académicos, divididos en cuatro cuatrimestres, sumando un total de 120 ECTS.

*   **Año 1 (60 ECTS): Fundamentos Teórico-Técnicos e Interdisciplinarios**
    *   Cuatrimestre 1 (Q1): Pilares Cuantitativos y de IA (30 ECTS)
    *   Cuatrimestre 2 (Q2): Interacción, Cognición y Diseño (30 ECTS)
*   **Año 2 (60 ECTS): Aplicación, Investigación y Especialización**
    *   Cuatrimestre 3 (Q3): Sistemas Avanzados y Aplicaciones (30 ECTS)
    *   Cuatrimestre 4 (Q4): Práctica Profesional y Proyecto Final (30 ECTS)

---

## AÑO 1: Fundamentos Teórico-Técnicos e Interdisciplinarios (60 ECTS)

### CUATRIMESTRE 1 (Q1): Pilares Cuantitativos y de IA (30 ECTS)

![Separador](imagen1.png)
#### NSA-101: Teoría de Juegos para Agentes Autónomos

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
#### NSA-102: Aprendizaje por Refuerzo Multiagente (MARL)

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
#### NSA-103: Psicología y Ética en la Negociación

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
#### NSA-104: Protocolos Algorítmicos de Negociación

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
#### NSA-105: Grandes Modelos de Lenguaje y Diálogo Estratégico

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

### CUATRIMESTRE 2 (Q2): Interacción, Cognición y Diseño (30 ECTS)
![Separador](imagen1.png)
#### NSA-106: Interacción Humano-Agente en Negociación

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
#### NSA-107: Aprendizaje Inverso y Modelado de Agentes

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

*   **Bibliografía:** Ng & Russell (2000). *Algorithms for Inverse Reinforcement Learning*. Abbeel & Ng (2004). *Apprenticeship Learning via Inverse Reinforcement Learning*. Ziebart et al. (2008). *Maximum Causal Entropy IRL*. Baker et al. (2009). *Goal Inference as Inverse Planning*. Papers recientes sobre IRL, Cooperative IRL, ToM computacional en MARL y negociación.

*   **Evaluación:**
    *   Implementación de Algoritmo IRL (40%) - Implementar un algoritmo IRL (ej. Max Entropy IRL o BIRL simplificado) en un entorno de simulación simple.
    *   Proyecto Bayesiano de Modelado de Oponentes (30%) - Desarrollar un modelo Bayesiano para inferir el "tipo" de un agente (ej. sus preferencias, su BATNA) a partir de una secuencia de ofertas en un juego de negociación simulado.
    *   Examen final (30%) - Cubre conceptos teóricos y la aplicación de métodos de modelado.
*   **Laboratorio (2h/sem):**
    *   Semanas 1-5: Implementación de algoritmos IRL en Python usando datos de trayectorias generadas por agentes sintéticos o pre-entrenados. Uso de librerías de optimización.
    *   Semanas 6-10: Trabajo en el proyecto Bayesiano de Modelado: uso de librerías de modelado probabilístico (ej. `PyMC3`, `Stan`, `Pyro`) para definir y ajustar modelos de agentes. Aplicar técnicas de inferencia (ej. MCMC, Variational Inference) a datos de negociación simulada o datasets públicos (ej. `Dataset of Negotiation Dialogues` si está disponible).
    *   Semanas 11-12: Experimentación con la integración de modelos de oponentes simples en un agente de negociación. Análisis de cómo la precisión del modelo del oponente afecta el resultado de la negociación.


![Separador](imagen1.png)
#### NSA-108: Programación avanzada con LLMs

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
#### NSA-109: Ética Aplicada y Gobernanza de Sistemas Autónomos Negociadores

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
#### NSA-110: Seminario de Investigación y Temas de Vanguardia

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

---

## AÑO 2: Aplicación, Investigación y Especialización (60 ECTS)

### CUATRIMESTRE 3 (Q3): Sistemas Avanzados y Aplicaciones (30 ECTS)

**Cursos Obligatorios (24 ECTS)**
![Separador](imagen1.png)
#### NSA-201. Sistemas de Negociación Híbrida Humano-IA

*   **Créditos:** 6 ECTS
*   **Dedicación:** 4h teoría/seminario + 2h laboratorio/proyecto por semana
*   **Pre-requisitos:** NSA-106, NSA-105, NSA-107.
*   **Objetivos:** Diseñar e implementar sistemas donde humanos y agentes de IA colaboren eficazmente en procesos de negociación; desarrollar AI como asistente inteligente (copiloto) para negociadores humanos; analizar la división de tareas y la comunicación en equipos de negociación híbridos.
*   **Temario (12 semanas):** Modelos de colaboración Humano-IA (ej. mixed-initiative systems). IA como asistente: análisis de información en tiempo real, sugerencia de tácticas óptimas, evaluación de ofertas del oponente, simulación de posibles escenarios y resultados. Diseño de interfaces de colaboración H-AI efectivas y transparentes. Canales de comunicación entre humanos y AIs en el contexto de la negociación. Confianza, dependencia mutua ycalibration. Modelado de la creencia del humano sobre las capacidades de la IA y viceversa. Casos de uso y requisitos específicos: negociación de ventas complejas, fusiones y adquisiciones, resolución de disputas legales, toma de decisiones estratégicas en grupo. Desafíos éticos específicos: el humano delegando responsabilidades excesivamente, la IA influyendo decisiones humanas de manera sutil o sesgada. Evaluación de equipos de negociación híbridos.
*   **Evaluación:** Proyecto de Sistema Híbrido (50%) - Diseño e implementación de un prototipo funcional de sistema de negociación asistida por IA o un sistema donde un humano colabora activamente con un agente negociador. Seminarios de discusión/presentación (30%). Examen final (20%).
*   **Laboratorio/Proyecto:** Trabajo intensivo en el proyecto. Integración de modelos de LLM (para interfaz conversacional o análisis de texto), motores de decisión (basados en RL o Juegos), y interfaces de usuario (web, desktop). Desarrollo de protocolos de comunicación interna entre módulos. Pruebas de usabilidad y funcionalidad con usuarios simulados o reales (si es posible a pequeña escala).


![Separador](imagen1.png)
#### NSA-202. Diseño de Mercados y Plataformas de Negociación Autónoma

*   **Créditos:** 6 ECTS
*   **Dedicación:** 4h teoría/seminario + 2h laboratorio/proyecto por semana
*   **Pre-requisitos:** NSA-104, NSA-108.
*   **Objetivos:** Comprender los principios de diseño e implementación de plataformas tecnológicas para facilitar la negociación entre agentes autónomos a gran escala; abordar los desafíos de escalabilidad, seguridad, privacidad y robustez de estas plataformas; diseñar mecanismos de coordinación y resolución de conflictos dentro de la plataforma.
*   **Temario (12 semanas):** Arquitecturas de plataformas de negociación multiagente (centralizadas vs. federadas vs. descentralizadas). Middleware para sistemas multiagente (ej. FIPA ACL, estándares de comunicación). Consideraciones de Bases de Datos y almacenamiento para el tracking de negociaciones (ej. bases de datos de grafos para relaciones, bases de datos temporales para historiales). Seguridad de la Plataforma: ataques comunes (DoS, inyección de mensajes maliciosos, impersonación), protección contra colusiones y Sybil attacks a nivel de plataforma. Criptografía en negociación (conceptos básicos de zero-knowledge proofs para verificar información sin revelarla). Smart Contracts (ej. en Ethereum, Cardano, etc.) para automatizar la ejecución de acuerdos de negociación (conceptos avanzados y limitaciones). Privacidad: técnicas de k-anonimato, privacidad diferencial aplicada a datos de negociación agregados. Escalabilidad: optimización de bases de datos, uso de tecnologías de Big Data, sharding, negociación peer-to-peer. Robustez frente a fallos de agentes individuales o de la red. Ejemplos de plataformas reales o simuladas: mercados energéticos, gestión de tráfico autónomo, mercados de datos descentralizados.
*   **Evaluación:** Proyecto de Plataforma Simplificada (50%) - Diseño e implementación de un prototipo a pequeña escala de una plataforma de negociación autónoma que permita la interacción entre múltiples agentes. Seminarios de discusión (30%). Examen final (20%).
*   **Laboratorio/Proyecto:** Trabajo intensivo en el proyecto. Uso de frameworks para sistemas multiagente (ej. `SPADE` en Python, o frameworks en Java/Scala). Exploración de tecnologías de smart contracts y simulación de su ejecución. Experimentación con arquitecturas distribuidas y protocolos de comunicación. Pruebas de escalabilidad (simulada) y seguridad básicas. Uso de herramientas de monitorización.


![Separador](imagen1.png)
#### NSA-203. Seguridad Adversarial en Negociación con Sistemas Autónomos

*   **Créditos:** 6 ECTS
*   **Dedicación:** 4h teoría/seminario + 2h laboratorio por semana
*   **Pre-requisitos:** NSA-102, NSA-107, NSA-109.
*   **Objetivos:** Identificar y analizar las vulnerabilidades de los agentes negociadores y los protocolos de negociación frente a ataques adversarios; diseñar estrategias y algoritmos para aumentar la robustez y la seguridad de los agentes y las interacciones.
*   **Temario (12 semanas):** Introducción a la seguridad en IA y MARL. Modelos de atacante. Ataques a modelos de RL: envenenamiento de datos de entrenamiento (data poisoning), ataques de evasión (adversarial examples en espacios de estado/observación), recompensa hackeada. Ataques a la "mente" del agente: manipulación de la inferencia de objetivos (engañar al agente sobre las preferencias del oponente), impersonación de identidad, inyección de información falsa en el proceso de modelado del oponente. Ataques a protocolos de negociación: colusión entre agentes para manipular resultados (ej. bid rigging en subastas), manipulación de mercados de predicción (wash trading), denegación de servicio en protocolos de regateo (inundando con ofertas). Seguridad de LLMs en diálogo estratégico: inyección de prompt maliciosa (jailbreaking para inducir comportamiento no deseado, extraer información sensible), ataques de extracción de datos privados del modelo. Diseño de agentes robustos frente a adversarios: aprendizaje adversarial (entrenar contra un oponente que busca explotar vulnerabilidades), detección de anomalías en el comportamiento del oponente, aprendizaje de políticas robustas. Técnicas de defensa: pruebas de conocimiento cero (conceptos básicos para verificar información sin revelarla), mecanismos criptográficos (hash commitments para ofertas). El incentivo al engaño en la negociación y cómo mitigarlo algorítmicamente y mediante diseño de protocolos.
*   **Bibliografía:** Papers recientes de conferencias de seguridad (CCS, S&P, USENIX Security) y IA (NeurIPS, ICML, ICLR, AAMAS, IJCAI, AAAI) sobre seguridad en RL, MARL, LLMs y teoría de juegos adversarial. Referencias sobre seguridad en teoría de juegos algorítmica.
*   **Evaluación:**
    *   Análisis de Vulnerabilidades (40%) - Análisis teórico y/o práctico de las vulnerabilidades de un agente negociador o protocolo de negociación específico frente a un tipo de ataque adversarial. Documento o presentación.
    *   Proyecto de Agente Robusto (40%) - Implementación de un agente negociador con defensas básicas (ej. detección de anomalías, filtrado de prompts maliciosos, estrategia robusta simple) contra un tipo de ataque adversarial en un entorno simulado.
    *   Seminarios de discusión (20%) - Presentación y discusión de papers y casos de estudio.
*   **Laboratorio (2h/sem):**
    *   Semanas 1-4: Experimentación con la implementación de ataques simples (ej. envenenamiento de recompensas en un entorno MARL simple, crafting de prompts adversariales básicos) en entornos de simulación.
    *   Semanas 5-8: Implementación de mecanismos de detección de anomalías en secuencias de ofertas o mensajes. Experimentación con técnicas de filtrado de prompts.
    *   Semanas 9-12: Trabajo en el proyecto de Agente Robusto: implementación de defensas y evaluación de su efectividad frente a ataques simulados. Análisis comparativo de diferentes estrategias de defensa.


![Separador](imagen1.png)
#### NSA-204. Taller Integrado de Diseño de Agentes Negociadores

*   **Créditos:** 6 ECTS
*   **Dedicación:** 2h teoría/coordinación + 4h trabajo en proyecto por semana
*   **Pre-requisitos:** Todos los cursos de Q1 y Q2 completados.
*   **Objetivos:** Integrar conocimientos y habilidades de todas las asignaturas previas para diseñar, implementar y evaluar un sistema complejo de agentes negociadores para un escenario realista a gran escala.
*   **Formato:** Proyecto de grupo grande (ej. 4-6 estudiantes). Se propone un escenario complejo (ej. simulación de un mercado energético donde agentes negocian precios y asignación de recursos, gestión de una cadena de suministro con múltiples proveedores y clientes autónomos y heterogéneos, subasta compleja de espectro radioeléctrico, negociación para la asignación de tareas en una flota de drones). Los grupos deben abordar el problema completo: modelado formal del escenario (Teoría de Juegos), diseño de la arquitectura del sistema multiagente, implementación de los agentes (motores de decisión basados en RL/búsqueda/algoritmos específicos), diseño de módulos de comunicación/diálogo (usando LLMs si aplica), diseño de protocolos de interacción, integración de componentes éticos/de seguridad básicos, y evaluación del rendimiento del sistema en una simulación robusta. El taller incluye sesiones semanales de revisión de diseño, hitos de implementación y una presentación final del sistema, sus resultados y lecciones aprendidas.
*   **Evaluación:**
    *   Documento de Diseño Detallado (30%) - Descripción completa de la arquitectura, modelado, algoritmos, protocolos y componentes éticos/de seguridad del sistema propuesto.
    *   Implementación y Funcionalidad (40%) - Evaluación del código, la integración de los módulos y la funcionalidad del sistema implementado.
    *   Evaluación del Rendimiento en Simulación (20%) - Análisis riguroso de los resultados obtenidos en la simulación utilizando métricas relevantes (ej. eficiencia, equidad, estabilidad).
    *   Presentación Final (10%) - Comunicación clara del proyecto, los resultados y las lecciones aprendidas.

---

**Cursos Optativos (elige 1, 6 ECTS)**

El estudiante elige uno de los siguientes cursos para profundizar en un área de especialización. La disponibilidad puede variar cada año.

*   **NSA-205A: Negociación Autónoma en Finanzas:**
    *   **Temario:** Mercados financieros como sistemas multiagente. Trading algorítmico: estrategias basadas en RL, arbitraje autónomo. Diseño de subastas electrónicas y mecanismos de matching de órdenes. Agentes de alta frecuencia y sus implicaciones. Modelado del mercado y detección de manipulación. Regulación y ética en la negociación financiera autónoma. Simulación de mercados financieros.
*   **NSA-205B: Negociación Autónoma en Cadena de Suministro y Logística:**
    *   **Temario:** La cadena de suministro como red de agentes negociadores. Agentes para la adquisición de bienes/servicios (e-procurement), gestión de inventarios, asignación de recursos logísticos (transporte, almacén). Negociación contractual y resolución autónoma de disputas. Mercados multiagente para la optimización global de la cadena.
*   **NSA-205C: Mediación Legal Asistida por IA:**
    *   **Temario:** Introducción al derecho y la negociación legal. Uso de agentes conversacionales y sistemas de IA para facilitar la mediación y la negociación en disputas legales (Online Dispute Resolution - ODR). Análisis de texto legal con LLMs para identificar posiciones, argumentos y generar propuestas de acuerdo. Sistemas expertos y de recomendación para negociadores legales. Ética y regulación específica en el ámbito legal (privacidad, imparcialidad, responsabilidad).
*   **NSA-205D: LLMs Avanzados en Estrategia:**
    *   **Temario:** Arquitecturas avanzadas de LLMs (ej. Mixture-of-Experts, modelos multimodales). Fine-tuning y entrenamiento por refuerzo a gran escala (RLHF avanzado). Uso de LLMs para el razonamiento estratégico: Tree-of-Thoughts, Self-Refine, simulación de agentes. Generación de lenguaje persuasivo y retórico. Detección y generación de engaño con LLMs. Modelado de creencias y conocimiento explícito con LLMs y su integración con bases de conocimiento.
*   **NSA-205E: Teoría de Juegos Computacional Avanzada:**
    *   **Temario:** Temas avanzados en Teoría de Juegos Algorítmica. Juegos repetidos avanzados y aprendizabilidad. Evolución de estrategias y estabilidad evolutiva. Juegos estocásticos avanzados y equilibrios de Markov. Computabilidad en teoría de juegos. Algoritmos avanzados para encontrar equilibrios (computación de Nash, equilibrio correlacionado, etc.). Diseño de experimentos computacionales en teoría de juegos.

---

**Seminario de Tesis (0 ECTS)**
Sesiones a lo largo del cuatrimestre dedicadas a la presentación y discusión de las ideas de proyecto de TFM de cada estudiante. Definición precisa de la pregunta de investigación u objetivos del proyecto, revisión preliminar y profundización del estado del arte, diseño metodológico detallado, planificación del trabajo y cronograma. Feedback del director de tesis asignado y de los compañeros.

---

### CUATRIMESTRE 4 (Q4): Prácticum y Proyecto Final (30 ECTS)

#### Prácticum Profesional

*   **Créditos:** 15 ECTS
*   **Dedicación:** Equivalente a 150 horas de trabajo (aprox. 4-5 semanas a tiempo completo o equivalente a tiempo parcial a lo largo del cuatrimestre).
*   **Formato:** Experiencia práctica en una empresa, centro de investigación o institución relevante, bajo la supervisión de un tutor de la entidad y un tutor académico de la maestría. El prácticum debe permitir al estudiante aplicar los conocimientos y habilidades adquiridos a un problema o proyecto real relacionado con la negociación, sistemas autónomos, IA, mercados algorítmicos, ética de la IA, o interacción H-AI. Se fomenta la búsqueda activa de prácticum por parte del estudiante, con apoyo de la universidad.
*   **Entregable:** Informe detallado (aprox. 25-30 páginas) sobre el trabajo realizado, los desafíos técnicos y conceptuales encontrados, las soluciones propuestas y aprendidas, y la relación del trabajo con los contenidos de la maestría. Presentación de los resultados del prácticum ante un comité evaluador interno.

#### Tesis de Master (TFM - Proyecto Final)

*   **Créditos:** 25 ECTS
*   **Dedicación:** Trabajo autónomo intensivo bajo la supervisión del director de tesis. Equivalente a aprox. 625 horas de trabajo. Es el trabajo central del año 2.
*   **Formato:** Realización de un proyecto de investigación original y significativo o un proyecto de desarrollo avanzado que suponga una contribución al campo. Puede ser teórico (nuevo modelo), algorítmico (nuevo protocolo o algoritmo de aprendizaje), experimental (estudio H-A, benchmarking de agentes), de diseño (propuesta de sistema ético/regulatorio, arquitectura de plataforma), o una combinación. Se espera un nivel de rigor científico y técnico elevado y que el trabajo sea defendible en el contexto de la investigación de vanguardia.
*   **Entregables:**
    *   Documento escrito (TFM, aprox. 15.000-25.000 palabras o equivalente, incluyendo código, documentación, datos de experimentos según el tipo de proyecto). Debe incluir: introducción y motivación, estado del arte detallado, metodología, desarrollo del trabajo, resultados, discusión, conclusiones y trabajo futuro.
    *   Si es un proyecto de desarrollo, se entregará también el código fuente y documentación técnica del prototipo.
    *   Defensa pública del TFM ante un comité evaluador.
*   **Posible Resultado:** Se anima a los estudiantes a buscar la publicación de su TFM en una conferencia o revista científica especializada, o la presentación de un prototipo en eventos relevantes.

#### Seminarios Avanzados y Seguimiento de TFM (0 ECTS)

Sesiones periódicas (ej. quincenales) a lo largo del cuatrimestre para el seguimiento individual o en pequeños grupos del progreso de los TFMs. Presentaciones parciales de los estudiantes sobre avances, problemas encontrados y resultados preliminares, para recibir feedback de profesores y compañeros. Espacio para discutir problemas técnicos o metodológicos comunes y compartir recursos. Peer-review de secciones del TFM escrito entre estudiantes.

---

## Infraestructura y Recursos Necesarios

*   **Laboratorios de Computación:** Salas equipadas con estaciones de trabajo de alto rendimiento y acceso a un clúster de GPUs (`NVIDIA A100`, `H100` o similar) para tareas intensivas de entrenamiento de modelos de Deep Learning y MARL.
*   **Acceso a Plataformas de IA:** Licencias institucionales o acceso a APIs de Grandes Modelos de Lenguaje comerciales de última generación (ej. `GPT-4`, `Gemini Ultra`, `Claude 3`) y recursos computacionales suficientes para desplegar, fine-tunear y experimentar con modelos open-source (`Llama 3`, `Mistral`, etc.) en la infraestructura local o en la nube.
*   **Entornos de Simulación Multiagente:** Servidores y software para ejecutar simulaciones a gran escala utilizando plataformas consolidadas (`PettingZoo`, `Unity ML-Agents`, `Gymnasium`) y simuladores ad-hoc para escenarios complejos (ej. mercados energéticos, gestión de tráfico autónomo, cadenas de suministro).
*   **Bases de Datos y Repositorios:** Acceso a colecciones de datos de negociaciones reales (anonimizadas, ej. de plataformas ODR, mercados simulados) y acceso a repositorios públicos de datasets (ej. Hugging Face Datasets) y modelos pre-entrenados.
*   **Biblioteca Digital y Física:** Amplio acceso a libros, revistas científicas y actas de conferencias en las áreas clave del programa (Teoría de Juegos, IA, Machine Learning, NLP, Economía, Psicología, Ética) a través de bases de datos académicas líderes (ej. ACM Digital Library, IEEE Xplore, SpringerLink, ScienceDirect, JSTOR, etc.).
*   **Software Especializado:** Licencias de software para modelado matemático y optimización (ej. `Gurobi`, `CPLEX`), análisis estadístico avanzado (`R`, `SPSS`, librerías Python), desarrollo de software (IDEs, herramientas de control de versiones como `Git`), y herramientas de prototipado rápido y diseño de interfaces (`Figma`, `Adobe XD`).
*   **Espacios para Experimentación Humano-Agente:** Laboratorio equipado específicamente para realizar estudios con participantes humanos, con estaciones de trabajo separadas, herramientas de registro de datos (video, audio, keylogging, eye-tracking básico), y software para el diseño y la ejecución de experimentos controlados.
*   **Profesorado:** Claustro de profesores con experiencia investigadora activa y publicaciones relevantes en las áreas clave del programa, complementado por profesores con experiencia en la industria.
*   **Conferencistas Invitados:** Programa regular de charlas con expertos de la industria y la academia a nivel nacional e internacional para exponer a los estudiantes a la vanguardia del campo.

---

## Carreras Profesionales y Salidas Laborales

Los graduados de la Master en Negociación con Sistemas Autónomos estarán altamente cualificados para roles de liderazgo técnico y conceptual en sectores de vanguardia, dada su formación multidisciplinar única y su profundo conocimiento de la interacción estratégica en sistemas inteligentes. Las salidas profesionales incluyen:

*   **Ingeniería e Investigación en IA Avanzada:**
    *   Ingeniero de Agentes Inteligentes / Ingeniero de Sistemas Multiagente.
    *   Científico de Datos con especialización en Interacción Estratégica.
    *   Investigador en laboratorios de I+D de empresas tecnológicas, universidades o centros de investigación.
    *   Ingeniero de Machine Learning / Deep Learning con enfoque en RL/MARL y LLMs para sistemas interactivos.
*   **Fintech y Mercados Cuantitativos:**
    *   Diseñador de Algoritmos de Trading y Estrategias Cuantitativas.
    *   Analista Cuantitativo (Quant) especializado en mercados electrónicos y negociación algorítmica.
    *   Desarrollador de Plataformas de Negociación Electrónica.
    *   Especialista en Detección de Manipulación de Mercado.
*   **Consultoría Tecnológica y Estratégica:**
    *   Consultor especializado en Automatización de Procesos y Sistemas Multiagente para empresas de diversos sectores.
    *   Asesor estratégico en la adopción e implementación de IA para la toma de decisiones complejas.
    *   Especialista en Diseño de Mecanismos para plataformas digitales.
*   **Desarrollo de Software y Arquitectura de Sistemas:**
    *   Arquitecto de Sistemas para entornos multiagente complejos y plataformas descentralizadas.
    *   Ingeniero de Software especializado en el desarrollo de agentes autónomos.
    *   Desarrollador de soluciones basadas en Smart Contracts para acuerdos automatizados.
*   **Ética, Regulación y Cumplimiento de IA:**
    *   Analista de Riesgos Éticos y Sociales de Sistemas de IA.
    *   Especialista en Cumplimiento Normativo (Compliance) para agentes autónomos (ej. Ley de IA de la UE).
    *   Consultor o Asesor para gobiernos u organismos internacionales en políticas de IA y gobernanza algorítmica.
    *   Auditor de Algoritmos.
*   **Sectores Aplicados:**
    *   Roles de especialista en IA estratégica en logística y cadena de suministro, gestión energética, sistemas de transporte autónomo, e-commerce avanzado, y el sector legal (mediación asistida).
*   **Academia:**
    *   Continuación de estudios de doctorado en IA, Teoría de Juegos, Economía Computacional, Ética de la IA, o campos relacionados, para seguir una carrera investigadora o académica.
