# AÑO 2: Aplicación, Investigación y Especialización (60 ECTS)

## CUATRIMESTRE 3 (Q3): Sistemas Avanzados y Aplicaciones (30 ECTS)

**Cursos Obligatorios (24 ECTS)**
![Separador](imagen1.png)
### NSA-201. Sistemas de Negociación Híbrida Humano-IA

*   **Créditos:** 6 ECTS
*   **Dedicación:** 4h teoría/seminario + 2h laboratorio/proyecto por semana
*   **Pre-requisitos:** NSA-106, NSA-105, NSA-107.
*   **Objetivos:** Diseñar e implementar sistemas donde humanos y agentes de IA colaboren eficazmente en procesos de negociación; desarrollar AI como asistente inteligente (copiloto) para negociadores humanos; analizar la división de tareas y la comunicación en equipos de negociación híbridos.
*   **Temario (12 semanas):** Modelos de colaboración Humano-IA (ej. mixed-initiative systems). IA como asistente: análisis de información en tiempo real, sugerencia de tácticas óptimas, evaluación de ofertas del oponente, simulación de posibles escenarios y resultados. Diseño de interfaces de colaboración H-AI efectivas y transparentes. Canales de comunicación entre humanos y AIs en el contexto de la negociación. Confianza, dependencia mutua ycalibration. Modelado de la creencia del humano sobre las capacidades de la IA y viceversa. Casos de uso y requisitos específicos: negociación de ventas complejas, fusiones y adquisiciones, resolución de disputas legales, toma de decisiones estratégicas en grupo. Desafíos éticos específicos: el humano delegando responsabilidades excesivamente, la IA influyendo decisiones humanas de manera sutil o sesgada. Evaluación de equipos de negociación híbridos.
*   **Evaluación:** Proyecto de Sistema Híbrido (50%) - Diseño e implementación de un prototipo funcional de sistema de negociación asistida por IA o un sistema donde un humano colabora activamente con un agente negociador. Seminarios de discusión/presentación (30%). Examen final (20%).
*   **Laboratorio/Proyecto:** Trabajo intensivo en el proyecto. Integración de modelos de LLM (para interfaz conversacional o análisis de texto), motores de decisión (basados en RL o Juegos), y interfaces de usuario (web, desktop). Desarrollo de protocolos de comunicación interna entre módulos. Pruebas de usabilidad y funcionalidad con usuarios simulados o reales (si es posible a pequeña escala).


![Separador](imagen1.png)
### NSA-202. Diseño de Mercados y Plataformas de Negociación Autónoma

*   **Créditos:** 6 ECTS
*   **Dedicación:** 4h teoría/seminario + 2h laboratorio/proyecto por semana
*   **Pre-requisitos:** NSA-104, NSA-108.
*   **Objetivos:** Comprender los principios de diseño e implementación de plataformas tecnológicas para facilitar la negociación entre agentes autónomos a gran escala; abordar los desafíos de escalabilidad, seguridad, privacidad y robustez de estas plataformas; diseñar mecanismos de coordinación y resolución de conflictos dentro de la plataforma.
*   **Temario (12 semanas):** Arquitecturas de plataformas de negociación multiagente (centralizadas vs. federadas vs. descentralizadas). Middleware para sistemas multiagente (ej. FIPA ACL, estándares de comunicación). Consideraciones de Bases de Datos y almacenamiento para el tracking de negociaciones (ej. bases de datos de grafos para relaciones, bases de datos temporales para historiales). Seguridad de la Plataforma: ataques comunes (DoS, inyección de mensajes maliciosos, impersonación), protección contra colusiones y Sybil attacks a nivel de plataforma. Criptografía en negociación (conceptos básicos de zero-knowledge proofs para verificar información sin revelarla). Smart Contracts (ej. en Ethereum, Cardano, etc.) para automatizar la ejecución de acuerdos de negociación (conceptos avanzados y limitaciones). Privacidad: técnicas de k-anonimato, privacidad diferencial aplicada a datos de negociación agregados. Escalabilidad: optimización de bases de datos, uso de tecnologías de Big Data, sharding, negociación peer-to-peer. Robustez frente a fallos de agentes individuales o de la red. Ejemplos de plataformas reales o simuladas: mercados energéticos, gestión de tráfico autónomo, mercados de datos descentralizados.
*   **Evaluación:** Proyecto de Plataforma Simplificada (50%) - Diseño e implementación de un prototipo a pequeña escala de una plataforma de negociación autónoma que permita la interacción entre múltiples agentes. Seminarios de discusión (30%). Examen final (20%).
*   **Laboratorio/Proyecto:** Trabajo intensivo en el proyecto. Uso de frameworks para sistemas multiagente (ej. `SPADE` en Python, o frameworks en Java/Scala). Exploración de tecnologías de smart contracts y simulación de su ejecución. Experimentación con arquitecturas distribuidas y protocolos de comunicación. Pruebas de escalabilidad (simulada) y seguridad básicas. Uso de herramientas de monitorización.


![Separador](imagen1.png)
### NSA-203. Seguridad Adversarial en Negociación con Sistemas Autónomos

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
### NSA-204. Taller Integrado de Diseño de Agentes Negociadores

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

### **Cursos Optativos (elige 1, 6 ECTS)**

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

### **Seminario de Tesis (0 ECTS)**
Sesiones a lo largo del cuatrimestre dedicadas a la presentación y discusión de las ideas de proyecto de TFM de cada estudiante. Definición precisa de la pregunta de investigación u objetivos del proyecto, revisión preliminar y profundización del estado del arte, diseño metodológico detallado, planificación del trabajo y cronograma. Feedback del director de tesis asignado y de los compañeros.

---

## CUATRIMESTRE 4 (Q4): Prácticum y Proyecto Final (30 ECTS)

### Prácticum Profesional

*   **Créditos:** 15 ECTS
*   **Dedicación:** Equivalente a 150 horas de trabajo (aprox. 4-5 semanas a tiempo completo o equivalente a tiempo parcial a lo largo del cuatrimestre).
*   **Formato:** Experiencia práctica en una empresa, centro de investigación o institución relevante, bajo la supervisión de un tutor de la entidad y un tutor académico de la maestría. El prácticum debe permitir al estudiante aplicar los conocimientos y habilidades adquiridos a un problema o proyecto real relacionado con la negociación, sistemas autónomos, IA, mercados algorítmicos, ética de la IA, o interacción H-AI. Se fomenta la búsqueda activa de prácticum por parte del estudiante, con apoyo de la universidad.
*   **Entregable:** Informe detallado (aprox. 25-30 páginas) sobre el trabajo realizado, los desafíos técnicos y conceptuales encontrados, las soluciones propuestas y aprendidas, y la relación del trabajo con los contenidos de la maestría. Presentación de los resultados del prácticum ante un comité evaluador interno.

### Tesis de Master (TFM - Proyecto Final)

*   **Créditos:** 25 ECTS
*   **Dedicación:** Trabajo autónomo intensivo bajo la supervisión del director de tesis. Equivalente a aprox. 625 horas de trabajo. Es el trabajo central del año 2.
*   **Formato:** Realización de un proyecto de investigación original y significativo o un proyecto de desarrollo avanzado que suponga una contribución al campo. Puede ser teórico (nuevo modelo), algorítmico (nuevo protocolo o algoritmo de aprendizaje), experimental (estudio H-A, benchmarking de agentes), de diseño (propuesta de sistema ético/regulatorio, arquitectura de plataforma), o una combinación. Se espera un nivel de rigor científico y técnico elevado y que el trabajo sea defendible en el contexto de la investigación de vanguardia.
*   **Entregables:**
    *   Documento escrito (TFM, aprox. 15.000-25.000 palabras o equivalente, incluyendo código, documentación, datos de experimentos según el tipo de proyecto). Debe incluir: introducción y motivación, estado del arte detallado, metodología, desarrollo del trabajo, resultados, discusión, conclusiones y trabajo futuro.
    *   Si es un proyecto de desarrollo, se entregará también el código fuente y documentación técnica del prototipo.
    *   Defensa pública del TFM ante un comité evaluador.
*   **Posible Resultado:** Se anima a los estudiantes a buscar la publicación de su TFM en una conferencia o revista científica especializada, o la presentación de un prototipo en eventos relevantes.

### Seminarios Avanzados y Seguimiento de TFM (0 ECTS)

Sesiones periódicas (ej. quincenales) a lo largo del cuatrimestre para el seguimiento individual o en pequeños grupos del progreso de los TFMs. Presentaciones parciales de los estudiantes sobre avances, problemas encontrados y resultados preliminares, para recibir feedback de profesores y compañeros. Espacio para discutir problemas técnicos o metodológicos comunes y compartir recursos. Peer-review de secciones del TFM escrito entre estudiantes.
