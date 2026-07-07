# Práctica 2 — Transformación del enfoque correctivo al preventivo/predictivo. Identificación de patrones de fallas, análisis del comportamiento de refacciones y evaluación de riesgos de indisponibilidad por línea de producción.

## 1. Metadatos del Laboratorio

| Atributo | Detalle |
| :--- | :--- |
| **Duración** | $90$ minutos |
| **Complejidad** | Intermedia |
| **Audiencia** | Superintendentes y Jefes de Producción, Jefes de Mantenimiento y Confiabilidad, Analistas de Calidad y Procesos en Manufactura Cerámica |
| **Tecnologías** | Microsoft Copilot Chat (M365), Microsoft Excel y Microsoft Word |
| **Enfoque** | Transformación del enfoque correctivo al preventivo/predictivo. Detección de patrones de fallas, análisis del ciclo de vida de refacciones críticas y evaluación de riesgos financieros de indisponibilidad. |

---

## 2. Descripción Corta

Este laboratorio de $90$ minutos entrena a los líderes de mantenimiento de plantas de recubrimientos en el uso de Microsoft Copilot como un analista de confiabilidad avanzada. Los estudiantes aprenderán a procesar el historial de paros imprevistos de equipos de alta complejidad (atomizadores, prensas, hornos) en **Microsoft Excel** para calcular métricas críticas de confiabilidad ($MTBF$, $MTTR$, Disponibilidad) y predecir el desgaste de refacciones expuestas a abrasión y choque térmico. Posteriormente, migrarán el flujo a **Microsoft Word** para redactar informes ejecutivos para la dirección y estructurar planes de mitigación predictivos que aseguren el $OEE$ (*Efectividad Global del Equipo*) de la planta.

---

## 3. Objetivos del Laboratorio

Al finalizar este laboratorio, el estudiante será capaz de:
* **Calcular e interpretar métricas de confiabilidad** (Tiempo Medio Entre Fallas - $MTBF$ y Tiempo Medio de Reparación - $MTTR$) asistido por IA para diagnosticar la salud de los activos.
* **Detectar patrones latentes de falla** analizando correlaciones entre variables de desgaste (vibración, temperatura, amperaje) e indisponibilidad física en Excel.
* **Optimizar el stock de refacciones críticas** mediante proyecciones dinámicas de vida útil y ventanas de cambio en Excel.
* **Estructurar una Matriz de Riesgo de Indisponibilidad** para priorizar los presupuestos de mantenimiento en las líneas de producción con mayor impacto en el $OEE$.
* **Automatizar reportes de confiabilidad en Word**, traduciendo datos analíticos complejos en planes de acción ejecutivos claros y justificaciones financieras ante la gerencia.

---

## 4. Prerrequisitos

* Cuenta activa de **Microsoft 365** con acceso a **Copilot Chat**.
* Aplicación de **Microsoft Excel** abierta con un libro en blanco guardado como `Predictivo_Mantenimiento_Confiabilidad.xlsx`.
* Aplicación de **Microsoft Word** abierta con un documento en blanco guardado como `Plan_Accion_Mantenimiento.docx`.

---

## 5. Procedimiento Paso a Paso (Flujo de Confiabilidad y Gestión de Activos)

### Fase A: Registro Histórico de Paros y Modos de Falla (Excel)

Para construir un plan predictivo, primero debemos estructurar la base de datos de paros imprevistos de los activos más complejos de la planta de cerámica.

1. En su libro de Excel, nombre la primera hoja como `1. Histórico_Fallas`.
2. Vaya al chat de **Copilot** e introduzca el siguiente prompt de auditoría de activos:

```
Actúa como un Ingeniero Senior de Confiabilidad Industrial en una planta de cerámica pesada y porcelanatos. Necesito estructurar una matriz en Excel para analizar el historial de paros imprevistos del último trimestre del año 2026.

Por favor, devuélveme una tabla limpia diseñada para Excel con 5 registros realistas que representen fallas en los siguientes activos clave: Atomizador de barbotina, Prensa Hidráulica de 10,000 toneladas y Horno de Rodillos.

La tabla debe incluir exactamente las siguientes columnas:
`| ID Activo | Nombre del Equipo | Componente Causante | Modo de Falla Detallado | Horas de Operación antes de Fallar | Tiempo de Reparación (Horas) | Impacto en Producción (m² perdidos) |`

Asegúrate de incluir modos de falla típicos del sector (ej: desgaste de boquillas por abrasión en el atomizador, fuga de sellos hidráulicos por sobrepresión en la prensa, o atasco de rodillos por fractura térmica en el horno).
```

3. Seleccione la tabla generada por Copilot, cópiela (`Ctrl+C`), vaya a su archivo de **Excel**, ubíquese en la celda `A1` de la hoja `1. Histórico_Fallas` y péguela (`Ctrl+V`).

---

### Fase B: Cálculo de Confiabilidad MTBF y MTTR por Activo (Excel)

Con los datos de paros en Excel, calcularemos los dos indicadores que definen el comportamiento predictivo de la planta: el Tiempo Medio Entre Fallas ($MTBF$) y el Tiempo Medio de Reparación ($MTTR$), analizando la disponibilidad física global.

1. En su libro de Excel, cree una segunda hoja llamada `2. Indicadores_Confiabilidad`.
2. Vaya al chat de Copilot e introduzca el siguiente prompt de procesamiento de datos:

```
Actúa como un Especialista en Gestión de Activos (ISO 55001) en manufactura cerámica. Tomando como base los datos de la Fase A, necesito generar una tabla resumen en Excel que consolide las métricas de confiabilidad por equipo para el Atomizador, la Prensa y el Horno.

Por favor, devuélveme una tabla formateada para Excel con las siguientes columnas:
`| Nombre del Equipo | Número de Fallas Registradas | MTBF Promedio (Horas) | MTTR Promedio (Horas) | Disponibilidad Mecánica (%) |`

Usa las fórmulas conceptuales estándar para los cálculos (Disponibilidad = $MTBF / (MTBF + MTTR)$). Al final de la tabla, añade un bloque de texto que actúe como un diagnóstico rápido indicando cuál de los tres equipos representa el mayor "cuello de botella" operativo debido a un MTTR excesivamente alto.
```

3. Copie la tabla procesada por Copilot y péguela en la hoja `2. Indicadores_Confiabilidad` a partir de la celda `A1`.

---

### Fase C: Modelado Predictivo de Ciclo de Vida de Refacciones (Excel)

El desgaste abrasivo de las arcillas y el choque térmico exigen planificar el cambio de componentes críticos antes de que fallen físicamente para evitar tiempos muertos catastróficos.

1. En su libro de Excel, cree una tercera hoja llamada `3. Análisis_Refacciones`.
2. Inyecte en el chat de Copilot el siguiente prompt enfocado en el almacén técnico de mantenimiento:

```
Actúa como un Planner de Mantenimiento y Almacén de Refacciones en una planta de azulejos y porcelanatos. Necesito proyectar el comportamiento y consumo de repuestos críticos en base a su ciclo de vida estimado bajo condiciones de operación 24/7.

Por favor, entrégame una tabla estructurada para Excel con los siguientes componentes de desgaste:
1. **Camisas de moldes de prensa** (Sometidas a fricción constante por polvo atomizado).
2. **Boquillas de carburo de tungsteno** (Atomizador de barbotina).
3. **Rodillos cerámicos de alta temperatura** (Zona de cocción rápida del horno).

Estructura la tabla con las columnas:
`| Refacción / Repuesto | Componente Asociado | Vida Útil Estimada (Horas de Operación) | Horas de Uso Actuales del Lote | Ventana de Cambio Predictivo (Fórmula: Vida Útil - Horas Actuales) | Criticidad de Stock (Alta / Media / Baja) | Acción Recomendada (Comprar / Inspeccionar / Monitorear) |`
```

3. Copie la matriz de refacciones entregada por Copilot y péguela en la hoja `3. Análisis_Refacciones` en la celda `A1`.

---

### Fase D: Matriz de Riesgo de Indisponibilidad por Línea (Excel)

Evaluaremos las líneas de producción cruzando la probabilidad de falla de sus activos críticos con el costo financiero por hora de paro involuntario, asegurando justificar la prioridad de los presupuestos.

1. En su libro de Excel, cree una cuarta hoja llamada `4. Evaluación_Riesgos`.
2. Regrese al chat de Copilot e introduzca el siguiente prompt de matriz de riesgos:

```
Actúa como un Gerente de Planta y Gestión de Riesgos Operacionales. Necesito construir una matriz en Excel que evalúe el riesgo de indisponibilidad total en las 3 líneas principales de producción de la fábrica (Línea 1: Porcelanato de Gran Formato, Línea 2: Cerámica de Muro, Línea 3: Revestimientos Especiales).

Por favor, devuélveme una tabla para Excel estructurada con las siguientes columnas exactas:
`| Línea de Producción | Activo Crítico Asociado | Probabilidad de Falla Imprevista (Escala 1 a 5) | Impacto Financiero por Hora de Paro ($ USD/Hora) | Nivel de Riesgo Consolidado (Fórmula: Probabilidad * Impacto) | Clasificación del Riesgo (Crítico / Alto / Moderado) | Estrategia Predictiva de Mitigación (Ej: Monitoreo de vibraciones por ultrasonido, termografía infrarroja, etc.) |`

Asegura valores de impacto financiero realistas para la industria cerámica (donde un paro en la línea de porcelanato es sumamente costoso debido al valor por m²).
```

3. Seleccione la matriz de riesgo financiero generada por Copilot, cópiela y péguela en la hoja `4. Evaluación_Riesgos` en la celda `A1`.

---

### Fase E: Automatización del Reporte de Confiabilidad y Plan de Acción (Word)

Con las hojas numéricas consolidadas en Excel, es momento de traducir esos datos en un plan de acción formal de mantenimiento predictivo enfocado en la alta dirección para solicitar los recursos necesarios.

1. Abra su archivo de **Word** (`Plan_Accion_Mantenimiento.docx`) y escriba como título principal: `# Propuesta Técnica y Plan de Acción: Migración al Mantenimiento Predictivo 4.0`.
2. Vaya al chat de Copilot e introduzca el siguiente prompt de comunicación y gestión:

```
Actúa como un Gerente de Mantenimiento y Confiabilidad en una planta de pisos y recubrimientos cerámicos. Necesito redactar un informe ejecutivo de 3 secciones para la Gerencia de Operaciones basado en las tablas de confiabilidad, refacciones y riesgos que estructuramos en los pasos anteriores en Excel.

Por favor, redacta el documento formal listo para mi archivo de Word con la siguiente estructura:
1. **Justificación Económica del Mantenimiento Predictivo**: Un párrafo de alta densidad técnica que demuestre por qué seguir con un esquema correctivo está destruyendo el OEE de la planta, citando el costo por hora de paro de los activos analizados en la Fase D.
2. **Plan de Monitoreo de Condición de Refacciones Críticas**: Un listado explicativo detallando cómo se inspeccionarán mecánicamente las camisas de los moldes de prensa, las boquillas del atomizador y los rodillos del horno para actuar dentro de sus ventanas de cambio predictivo calculadas en la Fase C.
3. **Estrategia de Mitigación del Activo Cuello de Botella**: El plan de choque predictivo directo para el equipo que representó la peor disponibilidad en la Fase B (ej: si fue la Prensa por sellos hidráulicos, propone la instalación de sensores de microfiltración de aceite y análisis de partículas de desgaste).
```

4. Copie el reporte estratégico generado por Copilot y péguelo bajo el título principal en su documento de **Word**.

---

### Fase F: Reto de Aplicación Autónoma – Predicción de Falla por Fatiga Térmica Crítica

**Instrucciones para el estudiante:** Has dominado el análisis de confiabilidad estándar. Ahora la planta se enfrenta a una situación real de riesgo latente en el turno actual. El analista de predictivo te entrega el reporte de termografía del Horno A (Línea 1): los termopares de la zona de cocción muestran fluctuaciones de calor anómalas de $\pm 35^\circ \text{C}$ y el consumo de gas natural se ha elevado un $8.5\%$ en las últimas 48 horas, lo que sugiere una degradación acelerada del aislamiento refractario o una fisura inminente en los rodillos cerámicos de soporte.

#### El Desafío:
Debes utilizar ingeniería de prompts de forma totalmente independiente para obligar a Copilot a actuar como un *Especialista en Termodinámica Industrial y Confiabilidad Térmica de Hornos*. Tu meta es estructurar un plan de contingencia predictivo que determine el tiempo estimado de vida útil remanente (RUL - *Remaining Useful Life*) y justifique una intervención programada antes de que el horno sufra una rotura catastrófica de rodillos en marcha.

#### Pistas de Ingeniería de Prompts para el Éxito:
Diseña un prompt avanzado en el chat considerando las siguientes directrices operativas:
* **Rol Avanzado:** Ordena a Copilot actuar como un *Ingeniero Senior de Mantenimiento Predictivo con especialidad en Sistemas Térmicos Continuos*.
* **Variables del Evento:** Infórmale a la IA que el horno opera a $1,220^\circ \text{C}$, que el consumo de gas está excedido, y que la velocidad de los rodillos presenta micro-variaciones de torque (amperaje intermitente).
* **Formato de Salida para Excel:** Pídele que te devuelva una tabla de contingencia predictiva con las columnas: `| Parámetro Térmico Anómalo | Causa Raíz Física Probable | Tiempo Estimado para Falla (Días) | Costo de Reparación Programada ($ USD) | Costo de Reparación si es Correctivo Catastrófico ($ USD) | Impacto Neto Evitado ($ USD) |`.
* **Formato de Salida para Word:** Solicita un párrafo ejecutivo de cierre redactado para la junta donde se detalle por qué apagar el horno de manera controlada por $12$ horas para cambiar rodillos e insolación evita un paro forzado de $6$ días si los rodillos se fracturan con material adentro.

#### Cierre del Laboratorio:
1. Copie la tabla de pronóstico de fatiga térmica generada por Copilot. Vaya a su archivo de **Excel** (`Predictivo_Mantenimiento_Confiabilidad.xlsx`), cree una quinta hoja llamada `5. Reto_Predictivo_Hornos` y pegue la información en la celda `A1`.
2. Copie el argumento técnico de justificación de parada controlada. Vaya al final de su archivo de **Word** (`Plan_Accion_Mantenimiento.docx`), cree un título llamado `## Anexo Técnico: Plan de Parada Programada de Emergencia - Horno A` y pegue la información.
3. Guarde y cierre ambos archivos. Su ecosistema de confiabilidad y planeación predictiva para la planta cerámica está completado con éxito.

---

## 6. Conceptos Clave para Recordar

* **Confiabilidad Basada en MTBF/MTTR:** El $MTBF$ mide la efectividad del diseño y del mantenimiento predictivo; el $MTTR$ mide la eficiencia logística y técnica para resolver la avería. Reducir el $MTTR$ exige estandarización técnica e inventarios de refacciones controlados.
* **Mantenimiento Basado en la Condición (CBM):** Intervenir la maquinaria basándose en el análisis de variables físicas (vibración, temperatura) en lugar de intervalos rígidos de tiempo calendario evita desgastes catastróficos involuntarios e introducciones de fallas infantiles por manipulación humana innecesaria.
* **Costo de Indisponibilidad de Activos:** Un activo parado detiene toda la cadena aguas abajo (el horno parado detiene la esmaltadora y la prensa). Calcular el impacto neto evitado al realizar intervenciones controladas es la única forma de validar la rentabilidad de las tecnologías de mantenimiento predictivo ante la alta gerencia.

---

## 7. Resultado Esperado

Al finalizar los $90$ minutos de la sesión práctica, el estudiante entregará dos archivos completados:

1. **Archivo `Predictivo_Mantenimiento_Confiabilidad.xlsx` (Excel):**
   * **Hoja 1 (`1. Histórico_Fallas`):** Base de datos con la tipificación de paros, componentes desgastados y m² perdidos.
   * **Hoja 2 (`2. Indicadores_Confiabilidad`):** Matriz de métricas operativas con el cálculo de $MTBF$, $MTTR$ e indicador de Disponibilidad Mecánica.
   * **Hoja 3 (`3. Análisis_Refacciones`):** Modelo de planeación de stock con cálculos de ventanas de cambio predictivo basadas en vida útil de componentes mecánicos y térmicos.
   * **Hoja 4 (`4. Evaluación_Riesgos`):** Matriz de criticidad de líneas que cruza probabilidad de colapso con impacto financiero para orientar el presupuesto.
   * **Hoja 5 (`5. Reto_Predictivo_Hornos`):** Análisis del **Reto Autónomo** que detalla el costo de reparación predictivo frente al correctivo para el horno.
2. **Archivo `Plan_Accion_Mantenimiento.docx` (Word):**
   * Una propuesta técnica estructurada de mantenimiento predictivo que incluye la justificación económica de la inversión, las metodologías de monitoreo para las $3$ refacciones clave y el plan de choque para mitigar fallas en la prensa.
   * **Anexo Autónomo:** El plan técnico de parada controlada para el Horno A que justifica el apagado de emergencia ante el comité operativo de la planta.
