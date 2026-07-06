# Práctica 5 — Análisis de Paretos de Paradas y Matrices de Riesgos con Copilot

## 1. Metadatos del Laboratorio

| Atributo | Detalle |
| :--- | :--- |
| **Duración** | 90 minutos (Densidad Táctica y de Priorización) |
| **Complejidad** | Avanzada |
| **Audiencia** | Jefes de Planta, Planners de Mantenimiento, Ingenieros de Confiabilidad, Superficies de Producción y Analistas de Procesos |
| **Tecnologías** | Microsoft Copilot Chat (M365), Copilot Image Generator (DALL-E), Microsoft Excel y Microsoft Word |
| **Enfoque** | Identificación del "20% de las causas que generan el 80% de los paros" (Principio de Pareto) e integración con matrices de riesgo operativo (AMFE) para optimizar el plan de mantenimiento anual. |

---

## 2. Descripción Corta

Este laboratorio de 90 minutos enseña a los estudiantes a utilizar Microsoft Copilot para realizar un análisis de Pareto automatizado a partir de un listado bruto de eventos de fallas en **Microsoft Excel**. Los participantes identificarán cuáles son los activos y componentes que concentran la mayor cantidad de horas de indisponibilidad y m² de producción perdidos. Posteriormente, estructurarán una matriz de riesgo operativo basada en el Número de Prioridad de Riesgo (NPR), redactarán un plan estratégico de mitigación en **Microsoft Word** y generarán un gráfico conceptual o infografía visual con el motor de imágenes de Copilot para ilustrar las prioridades de la planta ante el equipo técnico.

---

## 3. Objetivos del Laboratorio

Al finalizar este laboratorio, el estudiante será capaz de:
* **Aplicar el Principio de Pareto (80/20)** asistido por IA para clasificar y priorizar las pérdidas por paradas imprevistas en Excel.
* **Calcular el Número de Prioridad de Riesgo (NPR)** evaluando los factores de Severidad, Ocurrencia y Detección dentro de una matriz AMFE en Excel.
* **Correlacionar fallas repetitivas** con causas raíz físicas y operativas específicas de la manufactura cerámica.
* **Generar representaciones visuales e infografías** de Pareto y criticidad utilizando comandos avanzados de generación de imágenes en Copilot.
* **Redactar planes de acción ejecutivos en Word** que traduzcan los hallazgos analíticos en directrices claras para la planeación del mantenimiento preventivo.

---

## 4. Prerrequisitos

* Cuenta activa de **Microsoft 365** con acceso a **Copilot Chat** y generación de imágenes habilitada.
* Aplicación de **Microsoft Excel** abierta con un libro en blanco guardado como `Pareto_Matrices_Riesgo.xlsx`.
* Aplicación de **Microsoft Word** abierta con un documento en blanco guardado como `Plan_Priorizacion_Mantenimiento.docx`.

---

## 5. Procedimiento Paso a Paso (Análisis de Pareto y Criticidad Operativa)

### Fase A: Clasificación y Distribución de Fallas para Análisis de Pareto (Excel)

Para optimizar los recursos, debemos procesar el historial de paros e identificar los pocos componentes críticos que sabotean la continuidad del proceso.

1. En su libro de Excel, renombre la primera hoja como `1. Datos_Paradas`.
2. Vaya al chat de **Copilot** e introduzca el siguiente prompt de generación analítica:

```
Actúa como un Planner de Mantenimiento Senior en una fábrica de revestimientos cerámicos. Necesito una tabla de datos robusta para realizar un análisis de Pareto sobre los paros imprevistos acumulados en el último semestre.

Por favor, proporcióname una tabla formateada de forma limpia para que pueda copiarla y pegarla directamente en Microsoft Excel. Los datos deben simular una distribución de Pareto (80/20) basada en exactamente 3 registros reales de alto impacto en la industria:
1. Horno Rodillos N°2 (Rodamientos ventilador extracción) -> 142 horas de paro, frecuencia de 3.2 eventos al mes, pérdida de 118000 USD.
2. Prensa Hidráulica SACMI PH5200 (Válvula proporcional hidráulica) -> 118 horas de paro, frecuencia de 2.8 eventos al mes, pérdida de 98000 USD.
3. Atomizador Spray Dryer (Boquillas de atomización) -> 96 horas de paro, frecuencia de 4.1 eventos al mes, pérdida de 79000 USD.

La tabla debe tener exactamente estas columnas:
| ID Evento | Activo / Equipo | Componente Específico | Horas de Paro Acumuladas | Frecuencia de Falla (Eventos al mes) | Pérdida Económica ($ USD) |

Genera únicamente la tabla markdown estándar sin textos introductorios ni explicaciones, lista para copiar y pegar en la celda A1 de Excel.
```

3. Seleccione la tabla completa generada por Copilot en su chat, cópiela (`Ctrl+C`) y péguela (`Ctrl+V`) en la celda `A1` de la hoja `1. Datos_Paradas` en Excel.

---

### Fase B: Diseño de la Matriz AMFE y Cálculo del NPR (Excel)

Una vez identificados los componentes críticos mediante Pareto, utilizaremos la metodología AMFE (Análisis de Modo y Efecto de Fallas) para calcular el Número de Prioridad de Riesgo (NPR = Severidad x Ocurrencia x Detección), asegurando una planeación basada en criticidad real.

1. En su libro de Excel, cree una segunda hoja llamada `2. Matriz_AMFE`.
2. Introduzca el siguiente prompt en el chat de Copilot para estructurar la matriz de confiabilidad:

```
Actúa como un Ingeniero de Confiabilidad Experto. Tomando como base exacta los tres componentes críticos que estructuramos en la Fase A:
1. Horno Rodillos N°2 - Rodamientos ventilador extracción
2. Prensa Hidráulica SACMI PH5200 - Válvula proporcional hidráulica
3. Atomizador Spray Dryer - Boquillas de atomización

Necesito diseñar una matriz AMFE en formato de tabla limpia para copiar y pegar directamente en la celda A1 de mi hoja de Excel. 

La tabla debe contener exactamente las siguientes columnas:
| Componente Crítico | Modo de Falla Potencial | Efecto de la Falla en el OEE | Severidad (S: 1-10) | Ocurrencia (O: 1-10) | Detección (D: 1-10) | NPR Total | Acción Recomendada para Reducir Riesgo |

Asigna las siguientes puntuaciones de criticidad realistas para la industria cerámica:
- Para los rodamientos del horno: Severidad = 9 (debido al lento proceso de enfriamiento térmico), Ocurrencia = 4, Detección = 4.
- Para la válvula proporcional de la prensa: Severidad = 8 (detiene el ciclo de compactación), Ocurrencia = 3, Detección = 5.
- Para las boquillas del atomizador: Severidad = 7 (afecta la granulometría de la barbotina), Ocurrencia = 6 (alto desgaste abrasivo), Detección = 3.

En la columna "NPR Total", muestra el resultado numérico de la multiplicación (S * O * D) para cada componente. Devuelve únicamente la tabla markdown, sin textos adicionales ni introducciones.
```

3. Copie la matriz AMFE generada por Copilot en el chat y péguela en la celda `A1` de la hoja `2. Matriz_AMFE`.

---

### Fase C: Interacción Práctica – Generación del Diagrama Visual de Prioridades (Copilot)

Para comunicar el plan de mantenimiento al equipo de técnicos de piso, crearemos una representación gráfica que ilustre conceptualmente el impacto de concentrar los esfuerzos en el 20% crítico.

1. En el chat de Copilot, introduzca el siguiente prompt en español para activar el motor de imágenes:

```
Crea una ilustración conceptual o gráfico infográfico de estilo industrial moderno que represente el "Principio de Pareto 80/20 en el Mantenimiento de Plantas". 

El diseño debe mostrar de manera clara y limpia dos secciones principales:
1. **El 20% de las Causas (Izquierda):** Una representación estilizada de componentes mecánicos críticos (un engranaje dorado brillante y una válvula hidráulica de precisión) etiquetados sutilmente con el texto "20% Activos Críticos".
2. **El 80% del Impacto (Derecha):** Una gran flecha dinámica de flujo ascendente de color azul o verde que se transforma en una gráfica de barras vertical limpia, mostrando la protección del "80% del OEE de la Planta".

El fondo debe ser un entorno técnico de sala de control de manufactura automatizada, de apariencia profesional, nítido, sin texto caótico ni desorden visual, optimizado para un manual de entrenamiento operativo.
```

2. Una vez generada la imagen, haga clic en ella dentro del chat, seleccione **Descargar** y guárdela localmente con el nombre `Diagrama_Pareto_Planta.png`.

---

### Fase D: Redacción del Plan Estratégico de Mitigación y Pareto (Word)

Traduciremos los números de Excel y la imagen en una política de mantenimiento formal para la superintendencia de la planta.

1. Abra su archivo de **Word** (`Plan_Priorizacion_Mantenimiento.docx`) y escriba el título principal: `# Estrategia de Priorización del Mantenimiento: Enfoque de Pareto y AMFE para la Reducción de Tiempos Muertos`.
2. Use el siguiente prompt en Copilot para redactar los argumentos técnicos:

```
Actúa como un Gerente de Mantenimiento y Planeación Industrial. Necesito redactar un plan de acción estratégico de 3 secciones para mi archivo de Word, basado en el análisis de Pareto y la matriz AMFE que estructuramos previamente para el Horno N°2, la Prensa SACMI PH5200 y el Atomizador Spray Dryer.

Por favor, genera el texto formal con la siguiente estructura:
1. **Diagnóstico del Impacto del 20% Crítico**: Un párrafo técnico sólido que explique cómo el análisis de Pareto demostró que una minoría de componentes causa la mayor parte del lucro cesante y las pérdidas en metros cuadrados en la planta cerámica.
2. **Despliegue de Acciones Basadas en el NPR**: Una guía detallada que establezca que cualquier componente con un NPR superior a 150 puntos (según la Fase B) requiere una orden de trabajo predictiva obligatoria inmediata, detallando las tareas para los componentes con mayor puntuación.
3. **Indicadores de Seguimiento y Control**: Define las métricas clave para evaluar el éxito del plan, específicamente la reducción del número de paros imprevistos y el aumento del tiempo de operación continua.
```

3. Copie el texto generado por Copilot y péguelo en su documento de Word.
4. Inserte la imagen `Diagrama_Pareto_Planta.png` descargada en la Fase C justo debajo del primer apartado para ilustrar la estrategia 80/20.

---

### Fase E: Reto de Aplicación Autónoma – Análisis de Desviación de Causa Raíz en Prensas de Gran Formato

**Instrucciones para el estudiante:** Te encuentras ante una anomalía recurrente. El histórico muestra que la Prensa Hidráulica 2 ha sufrido 4 paros imprevistos en las últimas dos semanas por "Falta de presión en el ciclo de llenado del molde". El equipo mecánico de piso insiste en que la causa es el desgaste del pistón principal (lo que exigiría un paro de 48 horas y un costo de $15,000 USD). Sin embargo, tú sospechas que el análisis de Pareto de micro-eventos apunta a una causa raíz diferente: la contaminación por partículas abrasivas en las válvulas solenoides piloto.

#### El Desafío:
Utiliza ingeniería de prompts de forma autónoma para que Copilot actúe como un *Especialista en Análisis de Causa Raíz (RCA) e Ingeniería de Fluidos*. Tu objetivo es:
1. **Modelar la Frecuencia vs. Severidad (Excel):** Generar una tabla de sub-componentes de la prensa que demuestre matemáticamente que las válvulas piloto (falla de bajo costo unitario pero alta frecuencia) representan el 75% de la indisponibilidad real de ese activo.
2. **Generar el Diagrama Visual de Causa Raíz (Imagen):** Solicitar a Copilot una imagen conceptual en español que ilustre un análisis de tipo *Diagrama de Ishikawa (Espina de Pescado)* enfocado en la "Contaminación de Aceite Hidráulico por Polvo Cerámico", mostrando el camino de las partículas desde el entorno hasta el bloque de válvulas.

#### Pistas de Ingeniería de Prompts para el Éxito:
* **Para la Tabla Analítica:** Informa a la IA que la prensa opera a 320 bar, y pide las columnas: `| Sub-componente de Prensa | Frecuencia Semanal | Tiempo de Reparación por Evento (Horas) | Horas de Paro Totales | Diagnóstico RCA Recomendado |`.
* **Para el Prompt de Imagen:** Usa una descripción clara para el motor gráfico: `"Un diagrama industrial profesional que muestra una estructura limpia de causa y efecto de diagrama de Ishikawa (espina de pescado) para la falla de un sistema hidráulico por contaminación de polvo cerámico. Estilo técnico moderno, líneas vectoriales claras para un reporte de ingeniería."`

#### Cierre del Laboratorio:
1. Copie la tabla del reto e insértela en una tercera hoja de su archivo de **Excel** llamada `3. Reto_RCA_Prensa` en la celda `A1`.
2. Descargue la imagen del diagrama de Ishikawa generada por la IA como `Ishikawa_Prensa.png`. Vaya al final de su archivo de **Word**, cree una sección titulada `## Anexo Técnico: Análisis de Causa Raíz (RCA) - Inestabilidad de Presión en Prensa 2` y pegue la justificación analítica junto a la imagen.
3. Guarde ambos documentos. Tu ecosistema de planeación, priorización y análisis de fallas está completo.

---

## 6. Conceptos Clave para Recordar

* **Principio de Pareto (80/20):** En el entorno de la manufactura, el 20% de los modos de falla típicamente genera el 80% de los costos de indisponibilidad. Identificar este grupo crítico evita dispersar los recursos de mantenimiento en tareas preventivas ineficaces.
* **Métrica NPR (Número de Prioridad de Riesgo):** El NPR proporciona un marco objetivo que equilibra la gravedad de una avería con la probabilidad de que ocurra y la facilidad técnica de detectarla antes de que detenga la línea de producción.
* **Análisis de Causa Raíz (RCA):** Confundir el síntoma (pérdida de presión) con la causa raíz (filtración deficiente o contaminación abrasiva) conduce a reparaciones repetitivas, gastos innecesarios y caídas prolongadas del OEE.

---

## 7. Resultado Esperado

Al concluir los 90 minutos, el estudiante entregará los siguientes entregables integrados:

1. **Archivo `Pareto_Matrices_Riesgo.xlsx` (Excel):**
   * **Hoja 1 (`1. Datos_Paradas`):** Historial real parametrizado con los eventos del Horno N°2, la Prensa SACMI y el Atomizador.
   * **Hoja 2 (`2. Matriz_AMFE`):** Evaluación formal de Severidad, Ocurrencia y Detección con el cálculo dinámico del indicador NPR por componente.
   * **Hoja 3 (`3. Reto_RCA_Prensa`):** Matriz analítica del reto autónomo que aísla las fallas crónicas de las válvulas piloto de la prensa.
2. **Archivo `Plan_Priorizacion_Mantenimiento.docx` (Word):**
   * Un informe corporativo unificado que contiene el diagnóstico de prioridades 80/20, el estándar operativo para activar preventivos basados en el umbral numérico de NPR y las recomendaciones técnicas de mitigación.
   * **Elements Visuales Incorporados:** Contiene el `Diagrama_Pareto_Planta.png` y el diagrama analítico `Ishikawa_Prensa.png` generados durante la sesión práctica.
