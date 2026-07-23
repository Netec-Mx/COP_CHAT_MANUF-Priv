# Práctica 8 — Planes de Capacitación y Estrategias de Motivación con Copilot

## 1. Metadatos del Laboratorio

| Atributo | Detalle |
| :--- | :--- |
| **Duración** | 90 minutos (Enfoque en Gestión del Talento, Cultura Organizacional y Liderazgo) |
| **Complejidad** | Avanzada |
| **Audiencia** | Gerentes de Planta, Superintendentes de Producción, Jefes de Turno, Líderes de Equipos de Alto Rendimiento y Coordinadores de HSEQ / Recursos Humanos |
| **Tecnologías** | Microsoft Copilot Chat (M365), Copilot Image Generator (DALL-E), Microsoft Excel y Microsoft Word |
| **Enfoque** | Diseño e instrumentación de un Plan de Desarrollo de Competencias Técnicas, la Matriz de Polivalencia del Personal y Programas de Reconocimiento y Motivación con IA para elevar la retención, disminuir el ausentismo y blindar el OEE de la planta. |

---

## 2. Descripción Corta

Este laboratorio de 90 minutos enseña a los líderes industriales a utilizar Microsoft Copilot como una herramienta estratégica para la gestión y el desarrollo del factor humano en entornos de alta demanda. Los participantes diseñarán un plan estructurado de entrenamiento técnico, automatizarán una Matriz de Polivalencia (Cross-Skilling) en **Microsoft Excel** para evitar cuellos de botella por ausencia de personal crítico, redactarán una política integral de incentivos y cultura en **Microsoft Word** y generarán una representación visual del mapa de liderazgo con el motor de imágenes de Copilot para su despliegue en las pizarras de gestión visual (Kamishibai/Tableros Kanban) de la planta.

---

## 3. Objetivos del Laboratorio

Al finalizar este laboratorio, el estudiante será capaz de:
* **Diseñar Planes de Capacitación Escales** asistidos por IA, alineando las necesidades técnicas de los equipos modernos con los objetivos de producción.
* **Estructurar Matrices de Polivalencia y Policompetencia** en Excel para mapear visualmente las habilidades cruzadas del equipo de piso.
* **Desarrollar Estrategias de Motivación e Incentivos** no económicos y basados en el desempeño, reduciendo la rotación y el ausentismo laboral.
* **Crear campañas de comunicación visual y liderazgo técnico** utilizando las capacidades de generación de imágenes de Copilot.
* **Redactar perfiles de puestos y planes de sucesión** en Word para puestos críticos de la operación manufacturera.

---

## 4. Prerrequisitos

* Cuenta activa de **Microsoft 365** con acceso a **Copilot Chat** y generación de imágenes habilitada.
* Aplicación de **Microsoft Excel** abierta con un libro en blanco guardado como `Matriz_Polivalencia_Talento.xlsx`.
* Aplicación de **Microsoft Word** abierta con un documento en blanco guardado como `Plan_Liderazgo_Capacitacion.docx`.

---

## 5. Procedimiento Paso a Paso (Liderazgo Efectivo y Capacitación)

### Fase A: Creación de la Matriz de Polivalencia y Competencias Cruzadas (Excel)

Un riesgo crítico en las líneas continuas es la dependencia de un único operador especialista (ej: el colorista o el prensista experto). Si esa persona falta, la línea se detiene o pierde calidad. Utilizaremos Copilot para estructurar un mapa de redundancia de talento.

1. En su libro de Excel, renombre la primera hoja como `1. Matriz_Polivalencia`.
2. Vaya al chat de **Copilot** e introduzca el siguiente prompt de diseño organizativo:

```
Actúa como un Gerente de Recursos Humanos Industrial y Especialista en Lean Manufacturing. Necesito diseñar una Matriz de Polivalencia para el equipo del área de Formación y Prensas de una planta cerámica. 

Por favor, proporcióname una tabla limpia y formateada para copiar y pegar directamente en la celda A1 de mi hoja de Excel. La tabla debe incluir exactamente las siguientes columnas:
| ID Colaborador | Nombre del Operador | Puesto Base | Nivel: Operación de Prensa PH5200 | Nivel: Cambio de Moldes | Nivel: Ajuste de Válvulas Piloto | Nivel: Control de Humedad de Barbotina | Brecha de Capacitación Crítica |

Incluye exactamente 4 registros de operadores realistas. Usa una escala numérica estándar para evaluar los niveles de competencia en cada tarea:
- 1: En entrenamiento / No autónomo.
- 2: Autónomo / Opera solo.
- 3: Experto / Puede entrenar a otros (MCT o tutor de piso).

Asegúrate de que la tabla muestre claramente una vulnerabilidad operativa (por ejemplo, que solo un operador tenga nivel 3 en el ajuste de válvulas piloto), especificando en la última columna la acción de capacitación urgente. Devuelve únicamente la tabla markdown, sin textos explicativos introductorios.
```

3. Seleccione la tabla generada por Copilot en el chat, cópiela (`Ctrl+C`) y péguela (`Ctrl+V`) en la celda `A1` de la hoja `1. Matriz_Polivalencia` en Excel.

---

### Fase B: Estructuración del Plan Semestral de Capacitación Técnica (Excel)

Con las brechas detectadas en la Fase A, utilizaremos a Copilot para programar las horas, los temas clave y las metodologías de entrenamiento en piso (Training Within Industry - TWI) para nivelar al equipo.

1. En su libro de Excel, cree una segunda hoja llamada `2. Plan_Entrenamiento`.
2. Introduzca el siguiente prompt en el chat de Copilot para desarrollar el plan de capacitación táctico:

```
Actúa como un Facilitador de Entrenamiento Técnico de Planta. Tomando como base la brecha crítica identificada en la Fase A (dependencia de un solo experto en el Ajuste de Válvulas Piloto e Hidráulicas), necesito estructurar un Plan Semestral de Capacitación Técnica.

Por favor, devuélveme una tabla formateada para copiar y pegar directamente en la celda A1 de Excel con las siguientes columnas exactas:
| Módulo de Capacitación | Objetivo Técnico | Duración (Horas) | Método de Instrucción (Teórico/Práctico TWI) | Indicador de Éxito (KPI) | Frecuencia de Evaluación |

Asegúrate de que los contenidos cubran desde la seguridad LOTO en sistemas hidráulicos de alta presión (320 bar), hasta técnicas avanzadas de diagnóstico de fallas y calibración de válvulas proporcionales en prensas, asegurando la transferencia efectiva del conocimiento del experto hacia los operadores de nivel 1 y 2. Entrega únicamente la tabla markdown.
```

3. Copie la tabla generada por Copilot en el chat y péguela (`Ctrl+V`) en la celda `A1` de la hoja `2. Plan_Entrenamiento` en Excel.

---

### Fase C: Interacción Práctica – Diseño Visual de la Campaña de Reconocimiento (Copilot)

Para fomentar una cultura de polivalencia en la planta, lanzaremos un programa de reconocimiento llamado "Operador Multihabilidad de Oro". Utilizaremos la IA para generar el póster oficial del programa que se colocará en los tableros de comunicación de las líneas.

1. En el chat de Copilot, introduzca el siguiente prompt para activar el motor de imágenes:

```
Crea una ilustración conceptual estilo póster corporativo moderno que represente el "Liderazgo, Desarrollo del Talento y Trabajo en Equipo en la Industria 4.0".

El diseño debe mostrar de forma limpia y nítida los siguientes elementos centrales:
1. En el centro: Un grupo de tres operarios industriales de perfil multiétnico (hombres y mujeres portando cascos de seguridad, gafas de protección y chalecos reflectantes profesionales) sonriendo con confianza y mirando hacia el futuro.
2. Al fondo: Siluetas limpias y estilizadas de brazos robóticos de paletizado y paneles digitales de control de OEE con métricas en verde, integrados armoniosamente.
3. Elemento simbólico: Engranajes dorados conectados de forma perfecta flotando sutilmente sobre el fondo, simbolizando la sinergia y la polivalencia del equipo.

La paleta de colores debe ser profesional (azul marino, blanco brillante y detalles en amarillo/oro de éxito), con un acabado nítido y limpio de vector o fotografía publicitaria corporativa, evitando textos caóticos, desorden o distorsiones visuales.
```

2. Una vez generada la imagen, haga clic en ella dentro del chat, seleccione **Descargar** y guárdela localmente con el nombre `Poster_Operador_Polivalente.png`.

---

### Fase D: Redacción del Plan de Motivación y Retención del Personal (Word)

Traduciremos los esfuerzos analíticos y de entrenamiento en una política formal de retención que alinee los incentivos con la productividad (OEE) de la planta.

1. Abra su archivo de **Word** (`Plan_Liderazgo_Capacitacion.docx`) y escriba el título principal: `# Estrategia de Liderazgo Efectivo, Capacitación Cruzada y Reconocimiento en Planta`.
2. Use el siguiente prompt en Copilot para redactar el marco estratégico:

```
Actúa como un Director de Operaciones y Líder de Cultura Organizacional en Manufactura Avanzada. Necesito redactar un plan formal de motivación y retención de talento humano para mi archivo de Word, vinculado directamente con el cumplimiento de las metas operativas de la planta.

Por favor, genera el texto formal estructurado exactamente en estas 3 secciones:
1. **Filosofía de Liderazgo 4.0 y Empoderamiento**: Un párrafo técnico corporativo que describa cómo el empoderamiento del operario a través del conocimiento y el entrenamiento técnico autónomo reduce el ausentismo y eleva el compromiso en el piso de producción.
2. **Estrategia de Incentivos No Económicos por Polivalencia**: Diseña una política clara que explique cómo los operarios que avancen de nivel en la Matriz de Polivalencia (de Nivel 1 a Nivel 2 o 3) recibirán reconocimiento público, prioridad en la selección de turnos de descanso y oportunidades de liderar proyectos especiales (círculos de calidad).
3. **Métricas de Evaluación de Clima Laboral y Productividad**: Define los KPIs esenciales para medir el impacto de esta estrategia, cruzando indicadores humanos (tasa de ausentismo, índice de retención de operarios expertos) con indicadores mecánicos (reducción de microparos por error operativo y mejora general del OEE).
```

3. Copie el texto generado por Copilot en el chat y péguelo directamente en su documento de Word.
4. Inserte la imagen `Poster_Operador_Polivalente.png` descargada en la Fase C justo debajo del segundo apartado para ilustrar visualmente la campaña de reconocimiento.

---

### Fase E: Reto de Aplicación Autónoma – Plan de Sucesión de Emergencia para Puestos Críticos

**Instrucciones para el estudiante:** El Supervisor Senior de la Línea de Selección y Atomizadores ha anunciado su jubilación dentro de las próximas 4 semanas. Es el único en toda la organización que conoce los parámetros exactos de mezcla de arcillas y humedad para los productos de formato extra grande sin usar recetas digitales escritas. Su partida sin un plan de contingencia puede generar un colapso en la consistencia de la pasta cerámica.

#### El Desafío:
Aplica tus habilidades de liderazgo e ingeniería de prompts de forma autónoma con Copilot para solucionar esta crisis de conocimiento:
1. **Matriz de Plan de Sucesión (Excel):** Diseña un prompt para que Copilot te entregue una tabla estructurada para Excel (en una hoja nueva llamada `3. Reto_Plan_Sucesion`) que evalúe a 2 candidatos internos actuales del turno B y C bajo los criterios de: `Capacidad Técnica actual (1-5)`, `Liderazgo y Manejo de Personal (1-5)`, `Alineación con Valores Culturales (1-5)` y `Tiempo de Nivelación requerido (Meses)`.
2. **Estrategia de Shadowing Estructurado (Word):** Pídele a la IA que redacte un cronograma intensivo de 4 semanas de "Mantenimiento del Conocimiento Crítico / Shadowing (Acompañamiento en Sombra)", detallando cómo el Supervisor Senior transferirá sus técnicas de inspección táctil y visual al candidato seleccionado antes de su salida definitiva.

#### Pistas de Ingeniería de Prompts para el Éxito:
* **Para la Tabla de Sucesión:** Pide las columnas listadas arriba y añade una columna de `Puntuación Total de Idoneidad` para automatizar la selección del mejor candidato.
* **Para el Prompt de Shadowing:** Usa un comando asertivo: `"Actúa como un Consultor de Gestión del Conocimiento Industrial. Genera un plan estructurado semana a semana para documentar y transferir las habilidades empíricas del supervisor de atomizadores..."`

#### Cierre del Laboratorio:
1. Copie la tabla del reto e insértela en la hoja `3. Reto_Plan_Sucesion` en la celda `A1` de su archivo de Excel.
2. Guarde ambos archivos (`Matriz_Polivalencia_Talento.xlsx` y `Plan_Liderazgo_Capacitacion.docx`). Tu ecosistema estratégico para el desarrollo del talento, la polivalencia del personal y el liderazgo efectivo en la planta de manufactura está 100% completo.

---

## 6. Conceptos Clave para Recordar

* **Matriz de Polivalencia (Cross-Skilling):** Es un pilar del Lean Manufacturing que mitiga el riesgo operativo. Tener un equipo donde todos saben operar únicamente su propia máquina fragmenta el proceso; la polivalencia asegura flexibilidad y resiliencia ante contingencias humanas.
* **Metodología TWI (Training Within Industry):** El entrenamiento en el piso de producción debe basarse en el saber hacer ("mostrar, guiar, ejecutar y supervisar"), reduciendo drásticamente los tiempos de la curva de aprendizaje en comparación con las capacitaciones teóricas en aula.
* **Incentivos Basados en el Crecimiento:** La motivación sustentable en la manufactura moderna no depende exclusivamente de bonos económicos; el reconocimiento al desarrollo de nuevas habilidades técnicas y el diseño de planes de carrera claros generan mayor retención del personal calificado.

---

## 7. Resultado Esperado

Al concluir los 90 minutos de esta sesión práctica, el estudiante entregará los siguientes productos integrados:

1. **Archivo `Matriz_Polivalencia_Talento.xlsx` (Excel):**
   * **Hoja 1 (`1. Matriz_Polivalencia`):** Diagnóstico visual de las capacidades técnicas del equipo e identificación de monopolios de conocimiento.
   * **Hoja 2 (`2. Plan_Entrenamiento`):** Cronograma táctico y objetivos de capacitación semestral orientados a cerrar las brechas críticas del área de prensas.
   * **Hoja 3 (`3. Reto_Plan_Sucesion`):** Matriz analítica para la evaluación objetiva y selección de candidatos para puestos de supervisión.
2. **Archivo `Plan_Liderazgo_Capacitacion.docx` (Word):**
   * Un documento maestro corporativo que reúne las políticas de empoderamiento, las bases del programa "Operador Multihabilidad de Oro", la justificación técnica de la estrategia frente a la gerencia de operaciones y la campaña visual integrada `Poster_Operador_Polivalente.png`.
