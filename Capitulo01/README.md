# Práctica 1 — Generación automatizada de gráficas y Paretos de costos de "no calidad" para anticipar comportamientos producto-proceso

## 1. Metadatos del Laboratorio

| Atributo | Detalle |
| :--- | :--- |
| **Duración** | 60 minutos (Guiado + Reto de Aplicación Autónoma) |
| **Complejidad** | Intermedia |
| **Audiencia** | Superintendentes y Jefes de Producción, Analistas de Calidad y Procesos en Manufactura Cerámica |
| **Tecnologías** | Microsoft Copilot Chat (M365) y Microsoft Excel |
| **Enfoque** | Generación automatizada de tablas de datos, análisis de Pareto de costos de no calidad (scrap, segundas, roturas) y detección anticipativa de desviaciones en variables críticas del proceso. |

---

## 2. Descripción Corta

Este laboratorio práctico entrena a los líderes de planta en el uso de Microsoft Copilot para migrar del típico reporte de calidad estático hacia un modelo de Costos de No Calidad (COQ) dinámico. Los participantes aprenderán a orquestar prompts lógicos para estructurar matrices de fallas cerámicas (corazón negro, grietas de enfriamiento, variaciones de calibre, defectos de esmalte) directamente en **Microsoft Excel**, calcular el impacto financiero real por lote defectuoso y automatizar la identificación del 20% de las causas raíz que generan el 80% de las pérdidas económicas en la línea de producción.

---

## 3. Objetivos del Laboratorio

Al finalizar este laboratorio, el estudiante será capaz de:
* **Estructurar matrices de fallas de producto en Excel** vinculando variables operativas con el costo financiero de desperdicio (scrap).
* **Aplicar el principio de Pareto asistido por IA** para clasificar y priorizar los defectos de mayor impacto monetario en las etapas de prensado y cocción.
* **Interpretar tendencias y anomalías de proceso** (como picos de humedad en el atomizado o caídas de presión en prensas) mediante análisis guiados en lenguaje natural.
* **Diseñar planes de contención inmediata en planta** basados en el comportamiento de las variables analizadas durante el turno.

---

## 4. Prerrequisitos

* Cuenta activa de **Microsoft 365** con acceso a **Copilot Chat**.
* Aplicación de **Microsoft Excel** abierta con un libro en blanco guardado como `Analisis_Costos_No_Calidad.xlsx`.

---

## 5. Procedimiento Paso a Paso (Flujo de Orquestación en Planta)

### Fase A: Registro Estructurado de Desviaciones y Defectos Cerámicos (Excel) 
El primer paso para un análisis 4.0 es contar con una matriz limpia de datos donde cada defecto esté tipificado y valorizado, superando el simple conteo de piezas rotas.

1. En su libro de Excel, nombre la primera hoja como `Registro de Defectos`.
2. Vaya al chat de **Copilot** e introduzca el siguiente prompt para estructurar la base de datos operativa:

```
Actúa como un Ingeniero Senior de Calidad y Procesos en una planta de manufactura de recubrimientos cerámicos y porcelanatos. Necesito estructurar una matriz de datos en Excel para registrar los defectos críticos detectados en la salida del horno de rodillos durante la última semana del año 2026.

Por favor, proporcióname una tabla limpia lista para copiar y pegar directamente en Excel con 5 registros de datos realistas (filas). La tabla debe contener exactamente las siguientes columnas:
- **ID Lote** (Ej: L-2026-01)
- **Tipo de Defecto Cerámico**: (Distribuye de forma realista entre: Corazón negro, Descalibrado, Grieta de enfriamiento, Pinholing/Punto de aguja, Desportillado).
- **Etapa de Origen Probable**: (Atomizado / Prensado / Esmaltado / Cocción).
- **Cantidad de Piezas Defectuosas (m²)**: (Valores realistas entre 80 m² y 450 m²).
- **Costo de No Calidad por m² ($ USD)**: (Define un costo de pérdida industrial según el defecto: por ejemplo, un descalibrado es categoría Segunda y pierde $1.5 USD/m², pero un corazón negro es Desperdicio Total/Scrap y cuesta $4.5 USD/m²).
- **Pérdida Financiera Total ($ USD)**: (Deja explícita la fórmula conceptual: `Cantidad m² * Costo de No Calidad por m²`).
```

3. Seleccione la tabla generada por Copilot, cópiela (`Ctrl+C`), vaya a su archivo de **Excel**, ubíquese en la celda `A1` y péguela. 

---

### Fase B: Automatización de la Tabla de Priorización de Pareto (Excel) — [15 Minutos]
Con los datos en Excel, utilizaremos a Copilot para procesar de forma agregada las pérdidas económicas por tipo de defecto, ordenándolas de mayor a menor y calculando el porcentaje acumulado para aislar los problemas críticos.

1. En su libro de Excel, cree una segunda hoja llamada `Análisis de Pareto`.
2. Regrese al chat de Copilot e introduzca el siguiente prompt de ordenamiento y acumulación financiera:

```
Actúa como un Analista de Control de Procesos Industriales. Basándote en los tipos de defectos cerámicos y sus pérdidas financieras totales calculadas en la Fase A, necesito que generes una tabla consolidada para construir un Diagrama de Pareto de Costos de No Calidad.

Entrégame una tabla estructurada para Excel con las siguientes columnas ordenadas estrictamente de mayor a menor pérdida económica:
1. **Tipo de Defecto Cerámico**
2. **Pérdida Financiera Consolidada ($ USD)**
3. **Porcentaje del Total (%)** (Fórmula conceptual: `Pérdida del Defecto / Pérdida Total de todos los defectos`)
4. **Porcentaje Acumulado (%)** (Suma consecutiva de los porcentajes individuales)

Al final de la tabla, añade una fila de "Total" y escribe un breve párrafo explicativo indicando cuáles son los 2 defectos principales que acumulan aproximadamente el 80% del impacto económico en la planta (Puntos críticos de control).
```

3. Copie la tabla procesada por Copilot y péguela en la hoja `Análisis de Pareto` en la celda `A1`. 

---

### Fase C: Correlación de Variables de Proceso y Alertas Tempranas (Copilot) — [15 Minutos]
El análisis de Pareto nos dice *dónde* está la pérdida, pero el enfoque anticipativo exige correlacionarla con las variables de las máquinas del turno (Prensas, Atomizadores, Hornos) antes de que el lote llegue a clasificación.

1. Introduzca en el chat de Copilot el siguiente prompt para cruzar las fallas físicas con las variables operativas críticas:

```
Actúa como un Superintendente de Planta de Manufactura Cerámica. El análisis de Pareto identificó que el 'Corazón Negro' (por oxidación incompleta de la materia orgánica) y las 'Grietas de Enfriamiento' son los defectos que concentran el mayor costo de no calidad en la línea.

Analiza las siguientes mediciones en tiempo real tomadas por los sensores de la planta durante el turno de la mañana:
- *Variable Hornos*: Temperatura en la zona de precalentamiento cayó 15°C por debajo del estándar; velocidad de avance de los rodillos aumentó un 5%.
- *Variable Prensas*: Humedad del polvo atomizado subió al 7.2% (el estándar es 5.5% - 6.0%).

Por favor, redacta un diagnóstico técnico industrial de 3 puntos que explique detalladamente:
1. Cómo la combinación de la alta humedad del polvo en la prensa junto con la caída de temperatura en el precalentamiento del horno actúa como el detonante directo del defecto de **Corazón Negro**.
2. Una regla lícita de alarma temprana: si la humedad del atomizado supera el 6.5%, qué acción correctiva inmediata debe ejecutar el operador de prensas para evitar el scrap masivo.
```

2. Analice la respuesta técnica provista por la IA. Copie el diagnóstico estratégico y guárdelo temporalmente en un bloque de notas o léalo con atención para comprender la física del proceso aplicada a la toma de decisiones.

---

### Fase D: Reto de Aplicación Autónoma – Plan de Mitigación de Desviación Súbita (15 minutos)

**Instrucciones para el estudiante:** Has completado la fase guiada. Ahora te encuentras solo al frente de la planta en el turno de la noche. El sensor óptico en la salida de la línea de esmaltado acaba de disparar una alerta: el 18% de las piezas de porcelanato presenta *Pinholing* (pequeños poros o puntos de aguja en la superficie vitrificada), elevando el costo de no calidad de este lote en $3,200 USD por hora si no detienes la desviación.

#### El Desafío:
Debes utilizar ingeniería de prompts por tu cuenta de forma totalmente independiente para obligar a Copilot a actuar como un *Especialista en Reología de Esmaltes y Defectología Cerámica* para estructurar un plan de acción de emergencia en el acto.

#### Pistas de Ingeniería de Prompts para el Éxito:
Diseña un prompt avanzado en el chat considerando las siguientes directrices operativas:
* **Asignación de Rol de Confiabilidad:** Exige a Copilot actuar como un *Ingeniero de Procesos Térmicos y Formulador de Esmaltes Cerámicos*.
* **Inyección de Variables Físicas:** Infórmale a la IA que el *Pinholing* suele ocurrir por un exceso de viscosidad en la suspensión del esmalte, una densidad incorrecta o una liberación tardía de gases de la arcilla base en el horno.
* **Solicitud de Salida Tabular para Excel:** Pídele que te devuelva una matriz de acciones inmediatas organizada estrictamente en una tabla con las columnas: `| Variable a Medir en Línea | Valor Estándar Teórico | Acción Correctiva si está Desviado | Responsable en Turno (Prensas / Esmaltado / Hornos) |`.

#### Cierre del Laboratorio:
1. Copie la tabla de mitigación autónoma generada por Copilot.
2. Vaya a su archivo de **Excel** (`Analis_Costos_No_Calidad.xlsx`), cree una tercera hoja llamada `4. Plan_Contención_Pinholing` y pegue la información en la celda `A1`.
3. Guarde su archivo de Excel. Su reporte de calidad predictivo 4.0 está consolidado.

---

## 6. Conceptos Clave para Recordar

* **Costo de No Calidad (COQ):** En la industria cerámica, contar piezas defectuosas no es suficiente. Traducir el scrap físico a dólares perdidos (diferenciando m² de Segunda de desperdicio total en horno) es lo que permite capturar la atención de la gerencia para autorizar inversiones operativas.
* **La Regla del 80/20 en Manufactura:** El análisis automatizado de Pareto aísla el "ruido" diario de la planta para que los superintendentes concentren los recursos de mantenimiento y control de procesos en los dos o tres defectos que verdaderamente desequilibran el costo operativo.
* **Monitoreo Anticipativo Inter-Etapa:** Un defecto detectado en la clasificación final (Horno) casi siempre se sembró en las etapas iniciales (Atomizado o Prensado). Correlacionar variables térmicas y de humedad en tiempo real evita fabricar lotes defectuosos ciegamente.

---

## 7. Resultado Esperado

Al finalizar los 60 minutos de la práctica, el estudiante entregará un archivo consolidado:

1. **Archivo `Analis_Costos_No_Calidad.xlsx` (Excel):**
   * **Hoja 1 (`Registro de Defectos`):** Base de datos con la clasificación de m² afectados, tipología de fallas y costeo financiero automatizado por lote cerámico.
   * **Hoja 2 (`Análisis de Pareto`):** Matriz analítica con ordenamiento descendente, cálculo de frecuencias acumuladas e identificación explícita del 80% de la pérdida económica.
   * **Hoja 3 (`4. Plan_Contención_Pinholing`):** Entregable del **Reto Autónomo** que lista el protocolo de emergencia de control de variables físicas (densidad, viscosidad, curvas térmicas) para erradicar el defecto de puntos de aguja en la línea de esmaltado.
