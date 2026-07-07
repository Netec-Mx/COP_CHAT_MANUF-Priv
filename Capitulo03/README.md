# Práctica 3 — Uso de Copilot para visualizar el impacto conjunto en la eficiencia y confiabilidad, eliminando los silos de información operativa.

## 1. Metadatos del Laboratorio

| Atributo | Detalle |
| :--- | :--- |
| **Duración** | $90$ minutos |
| **Complejidad** |Intermedia |
| **Audiencia** | Superintendentes de Planta, Jefes de Operaciones, Analistas de Business Intelligence (BI) e Ingenieros de Procesos y Confiabilidad |
| **Tecnologías** | Microsoft Copilot Chat (M365), Microsoft Excel, Microsoft PowerPoint y Microsoft Word |
| **Enfoque** | Integración de datos transversales. Correlación directa entre indisponibilidad por mantenimiento, pérdidas de velocidad por calidad y el impacto unificado en el $OEE$ (*Efectividad Global del Equipo*) con traducción visual para comités directivos. |

---

## 2. Descripción Corta

Este laboratorio avanzado de $90$ minutos destruye los silos de información tradicionales entre los departamentos de Mantenimiento, Calidad y Producción. Los estudiantes aprenderán a utilizar Microsoft Copilot para fusionar bases de datos dispersas en **Microsoft Excel**, correlacionando cómo las fallas mecánicas micro-crónicas derivan en pérdidas de velocidad de línea y defectos de acabado superficial (porcelanatos desportillados o con problemas de planitud). Finalmente, el flujo enseña a estructurar un informe técnico de correlación en **Microsoft Word** y a diseñar una presentación de alto impacto en **Microsoft PowerPoint** optimizada para justificar inversiones de automatización ante la junta directiva.

---

## 3. Objetivos del Laboratorio

Al finalizar este laboratorio, el estudiante será capaz de:
* **Integrar bases de datos heterogéneas** (Mantenimiento, Calidad y Producción) en Excel utilizando la asistencia lógica de la IA.
* **Calcular las tres variables del OEE** (Disponibilidad, Rendimiento y Calidad) analizando el impacto conjunto de micro-paros estructurales.
* **Identificar causas raíz multidimensionales** mediante el análisis cruzado de variables de proceso (ej: oscilaciones de presión en prensa vs. rechazo de calidad en clasificación).
* **Estructurar un Reporte Técnico Unificado en Word** con justificación económica sólida basada en pérdidas económicas consolidadas.
* **Diseñar un Storyboard Ejecutivo en PowerPoint** empleando prompts estructurados que traduzcan métricas analíticas en diapositivas visuales de nivel directivo.

---

## 4. Prerrequisitos

* Cuenta activa de **Microsoft 365** con acceso a **Copilot Chat**.
* Aplicación de **Microsoft Excel** abierta con un libro en blanco guardado como `Integracion_Eficiencia_Global.xlsx`.
* Aplicación de **Microsoft Word** abierta con un documento en blanco guardado como `Informe_Interdisciplinario_OEE.docx`.
* Aplicación de **Microsoft PowerPoint** abierta para estructurar la presentación ejecutiva.

---

## 5. Procedimiento Paso a Paso (Integración Analítica y Rompimiento de Silos)

### Fase A: Fusión de Datos de Producción, Confiabilidad y Calidad (Excel)

Tradicionalmente, Calidad maneja un reporte, Mantenimiento otro y Producción uno diferente. Usaremos Copilot para simular la consolidación de estos tres silos en una sola vista maestra.

1. En su libro de Excel, renombre la primera hoja como `1. Data_Maestra_Silos`.
2. Vaya al chat de **Copilot** e introduzca el siguiente prompt avanzado de ingeniería de datos cruzados:

```
Actúa como un Líder de Business Intelligence (BI) y Analista de Procesos Industriales en una planta de revestimientos cerámicos de gran formato. Necesito consolidar una tabla maestra para Excel que unifique los datos de un mes de operación de la Línea de Molienda y Atomización.

Por favor, proporcióname una tabla limpia formateada para Excel con 5 registros representativos que crucen las tres áreas operativas. Las columnas deben ser exactamente:
`| ID Lote / Turno | Activo Crítico | Horas de Paro Mecánico (Silo Mantenimiento) | Velocidad Real de Operación vs. Nominal (%) (Silo Producción) | Porcentaje de Producto de Primera Calidad (%) (Silo Calidad) | Defecto Principal Detectado en Clasificación |`

Asegúrate de que los datos muestren una correlación lógica industrial. Por ejemplo: si un lote registra horas de paro mecánico altas en el atomizador por boquillas desgastadas, la velocidad de operación nominal debió caer al $78\%$ debido a la baja presión, y el porcentaje de producto de primera calidad debió verse afectado (ej: $89.5\%$) debido a variaciones en la granulometría del polvo atomizado.
```

3. Seleccione la tabla generada, cópiela (`Ctrl+C`) y péguela (`Ctrl+V`) en la celda `A1` de la hoja `1. Data_Maestra_Silos`.

---

### Fase B: Cálculo y Diagnóstico del OEE Consolidado (Excel)

Con la data integrada, calcularemos el indicador global de eficiencia de la planta ($OEE$) multiplicando la Disponibilidad (afectada por Mantenimiento), el Rendimiento (afectado por las pérdidas de velocidad de Producción) y la Calidad.

1. En su libro de Excel, cree una segunda hoja llamada `2. Analítica_OEE`.
2. Introduzca el siguiente prompt en el chat de Copilot para procesar matemáticamente las pérdidas ocultas:

```
Actúa como un Consultor Lean Six Sigma experto en Lean Manufacturing Cerámico. Tomando como base la estructura de datos unificada de la Fase A, necesito generar una matriz de rendimiento de OEE para evaluar la eficiencia real de la línea de producción.

Entrégame una tabla estructurada para Excel con las siguientes columnas:
`| ID Lote / Turno | Factor Disponibilidad ($D$) | Factor Rendimiento ($R$) | Factor Calidad ($C$) | OEE Total Calculado ($OEE = D * R * C$) | Pérdida Financiera Estimada ($ USD) |`

Usa los porcentajes de la tabla anterior como los factores correspondientes (ej: si la velocidad real fue $85\%$, Rendimiento = $0.85$; si el producto de primera fue $92\%$, Calidad = $0.92$). Asume un costo base de pérdida operativa de $\$1,500$ USD por cada punto porcentual que el OEE final se ubique por debajo del estándar internacional del $85\%$. Incluye una fila de promedios globales al final.
```

3. Copie la tabla de analítica de OEE generada por Copilot y péguela en la celda `A1` de la hoja `2. Analítica_OEE`.

---

### Fase C: Redacción del Reporte Técnico Interdisciplinario (Word)

Para romper formalmente los silos, el análisis de datos debe transformarse en una narrativa técnica que alinee a los tres jefes de departamento hacia una solución común.

1. Abra su archivo de **Word** (`Informe_Interdisciplinario_OEE.docx`) y coloque como encabezado principal: `# Informe de Correlación Operativa: Impacto de la Confiabilidad de Activos en el OEE y la Calidad Final`.
2. Vaya a Copilot e inyecte el siguiente prompt para automatizar la redacción técnica:

```
Actúa como un Director de Operaciones Industriales. Necesito redactar un informe ejecutivo estructurado en 3 secciones claras para los Jefes de Mantenimiento, Producción y Calidad, basándome en los hallazgos de pérdidas cruzadas y OEE calculados en la Fase B.

Genera el contenido formal optimizado para mi documento de Word con los siguientes componentes:
1. **Análisis de la Causa Raíz Multidimensional (Mantenimiento-Calidad)**: Explica de manera técnica detallada cómo los micro-paros y variaciones en los activos (como el desgaste físico de componentes en el atomizador o caídas de presión en prensas) destruyen el factor de Rendimiento de Producción y alteran la densidad del polvo cerámico, impactando directamente el indicador de Calidad en la etapa de clasificación final.
2. **Impacto Financiero Unificado**: Presenta un argumento macroeconómico que demuestre que ver los departamentos como silos aislados oculta las pérdidas reales de la planta, utilizando como base la penalización financiera calculada del OEE por debajo del estándar mundial.
3. **Planes de Acción de Eficiencia Compartida**: Propón 3 acciones conjuntas que involucren inspecciones predictivas obligatorias cuando la velocidad nominal caiga más de un $5\%$, controlando así la calidad antes de generar desperdicio de m² de cerámica.
```

3. Copie el texto técnico generado y péguelo en su archivo de Word justo debajo del título principal.

---

### Fase D: Diseño de Storyboard Ejecutivo para la Junta Directiva (PowerPoint)

La aprobación de presupuestos requiere traducir los datos de Excel y Word en láminas visuales ejecutivas de alto impacto para exponer ante directores que no están en el día a día de la planta.

1. Abra **Microsoft PowerPoint** y mantenga una presentación en blanco lista.
2. Vaya al chat de Copilot e introduzca el siguiente prompt para estructurar la lógica visual, los mensajes clave y los elementos gráficos de las diapositivas:

```
Actúa como un Diseñador Instruccional y Consultor de Negocios de Alto Nivel. Necesito presentar este proyecto de "Eliminación de Silos Operativos mediante la Integración de Datos y OEE" ante la junta directiva y el Gerente General.

Por favor, desarróllame el Storyboard detallado para una presentación de 4 diapositivas de alto impacto. Para cada diapositiva, entrégame la siguiente estructura exacta:
* **Número y Título de la Diapositiva**
* **Mensaje Central / Frase Gancho Ejecutiva**
* **Contenido Escrito (Puntos clave concisos)**
* **Sugerencia de Elemento Visual u Gráfico Recomendado** (Ej: Gráfico de cascada para pérdidas, matriz de correlación de silos, tablas comparativas, etc.)

Asegura que el flujo inicie con el problema del aislamiento de datos (Silos), pase por la revelación analítica del OEE Real y concluya con el retorno de inversión de implementar un monitoreo integrado asistido por IA.
```

3. Utilice la estructura analítica detallada entregada por Copilot para construir de forma ágil el contenido técnico y visual dentro de las diapositivas de su archivo de **PowerPoint**.

---

### Fase E: Reto de Aplicación Autónoma – Simulación de Desviación Súbita en la Línea de Prensado

**Instrucciones para el estudiante:** Te enfrentas a una crisis de variabilidad operativa en tiempo real. Los sensores inteligentes integrados muestran que la Prensa Hidráulica de 10,000 toneladas (Línea 1) ha registrado una caída silenciosa en su rendimiento del $95\%$ al $82\%$ de su velocidad nominal debido a micro-oscilaciones intermitentes de presión en el circuito hidráulico principal. De manera paralela, el sistema de visión artificial en la salida del horno reporta que el defecto de *Falta de Planitud y Fisuras de Bordes (Caleo)* en las piezas de porcelanato se ha disparado de un aceptable $1.2\%$ a un crítico $7.8\%$ en las últimas 4 horas. El Jefe de Calidad culpa a la curva de cocción del horno, el Jefe de Producción exige operar a máxima marcha y el de Mantenimiento asegura que la prensa no está en paro total.

#### El Desafío:
Debes utilizar ingeniería de prompts para actuar como un *Mediador Técnico e Ingeniero de Procesos Cerámicos Senior*. Tu objetivo es crear un prompt avanzado que obligue a Copilot a procesar esta desviación de datos cruzados, demostrando matemáticamente que la raíz del problema de calidad no es el horno, sino la pérdida de velocidad y presión acumulada en la prensa, y estimando el impacto financiero conjunto en el OEE por turno.

#### Pistas de Ingeniería de Prompts para el Éxito:
Diseña tu prompt considerando los siguientes parámetros críticos para la simulación:
* **Rol de la IA:** Configura a Copilot como un *Auditor de Procesos Industriales y Experto en Correlación de Defectos Físicos de Prensado*.
* **Variables del Evento Técnico:** Detalla que la prensa genera piezas de $120 \times 120 \text{ cm}$, que las micro-oscilaciones son de $+/- 15 \text{ bar}$ en el ciclo de compactación, y que el defecto de planitud se genera por falta de compactación homogénea del polvo atomizado antes de la entrada al horno.
* **Formato de Salida para Excel (Integración de Datos de Crisis):** Pídele una tabla de balance de impacto inmediato por turno con las columnas: `| Variable de Presión Afectada | Pérdida de Rendimiento de Prensa (%) | Incremento Directo en Rechazo de Calidad (%) | Caída Neta del OEE del Turno (%) | Costo de Desperdicio de Material ($ USD/Turno) |`.
* **Formato de Salida para Word/PowerPoint (Argumento de Contención):** Solicita una minuta ejecutiva de 2 párrafos dirigida a los tres jefes de departamento que justifique la detención inmediata de la prensa por 20 minutos para calibrar la válvula proporcional de presión, demostrando que continuar operando en degradación cuesta 5 veces más en desperdicio de calidad que el tiempo de mantenimiento invertido.

#### Cierre del Laboratorio:
1. Copie la tabla de balance de la crisis de prensado generada por Copilot. Vaya a su archivo de **Excel** (`Integracion_Eficiencia_Global.xlsx`), cree una tercera hoja llamada `3. Reto_Crisis_Silos` y pegue la información en la celda `A1`.
2. Copie la minuta ejecutiva de contención técnica. Vaya al final de su archivo de **Word** (`Informe_Interdisciplinario_OEE.docx`), cree una sección titulada `## Anexo de Emergencia: Resolución de Desviación Cruzada Prensa-Calidad` y pegue la información.
3. Guarde todos sus archivos de trabajo. Tu ecosistema analítico interconectado para la toma de decisiones sin silos está listo.

---

## 6. Conceptos Clave para Recordar

* **El Peligro de los Silos Operativos:** Optimizar un departamento de forma aislada puede dañar a otro. Por ejemplo, forzar a producción a operar al $100\%$ de velocidad nominal con refacciones desgastadas satura el área de calidad con m² defectuosos inservibles, destruyendo la rentabilidad real del negocio.
* **El OEE como Indicador de Consenso Técnico:** El OEE es la métrica de balance perfecta de una planta de manufactura avanzada porque unifica las responsabilidades de Mantenimiento (Disponibilidad), Operaciones (Rendimiento) y Calidad en un solo valor numérico correlacionado.
* **Comunicación Multidisciplinaria Basada en Datos:** Traducir métricas operativas crudas de ingeniería a pérdidas monetarias claras en documentos ejecutivos (Word) y presentaciones visuales sintéticas (PowerPoint) es indispensable para alinear los esfuerzos técnicos con la estrategia financiera corporativa.

---

## 7. Resultado Esperado

Al concluir los $90$ minutos de este laboratorio integrador, el estudiante entregará y presentará las evidencias consolidadas del ecosistema Microsoft 365:

1. **Archivo `Integracion_Eficiencia_Global.xlsx` (Excel):**
   * **Hoja 1 (`1. Data_Maestra_Silos`):** Matriz mensual consolidada que fusiona variables de mantenimiento, producción y calidad en un solo origen de datos.
   * **Hoja 2 (`2. Analítica_OEE`):** Tabla de cálculo de factores individuales ($D$, $R$, $C$), consolidación del porcentaje de OEE Global y la proyección financiera de brechas respecto al estándar industrial.
   * **Hoja 3 (`3. Reto_Crisis_Silos`):** Modelo analítico de contingencia del **Reto Autónomo** que correlaciona de forma matemática las fluctuaciones de presión de la prensa con las mermas de calidad terminada.
2. **Archivo `Informe_Interdisciplinario_OEE.docx` (Word):**
   * Un reporte estratégico de alta densidad redactado para la gerencia que expone la causa raíz cruzada de las variaciones operativas, la justificación del impacto financiero total y el plan estructurado de acciones transversales.
   * **Anexo de Emergencia:** Minuta técnica de contención para la crisis simulada de la prensa hidráulica.
3. **Estructura en PowerPoint:**
   * Un Storyboard corporativo de 4 diapositivas que traduce de forma inmediata el análisis analítico de datos duros en un guion ejecutivo visual y persuasivo listo para la toma de decisiones en el comité central.
