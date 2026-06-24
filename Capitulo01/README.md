---LAB_START---
LAB_ID: 01-00-01
---MARKDOWN---
# Práctica 1 — Generación automatizada de gráficas y Paretos de costos de "no calidad" para anticipar comportamientos producto-proceso

## 1. Metadatos

| Atributo | Detalle |
|---|---|
| **Duración estimada** | 60 minutos |
| **Complejidad** | Fácil |
| **Nivel Bloom** | Crear |
| **Capítulo asociado** | Capítulo 1 — Análisis Avanzado de Calidad 4.0 |
| **ID de práctica** | 01-00-01 |

---

## 2. Descripción General

En esta práctica aplicarás los principios de **Calidad 4.0** presentados en la Lección 1.1 para transformar un dataset simulado de defectos y costos de no calidad en visualizaciones accionables utilizando **Microsoft 365 Copilot integrado en Excel y Word**. Partirás de datos crudos en una hoja de cálculo estructurada y, mediante una secuencia progresiva de al menos cinco prompts en Copilot, generarás tablas dinámicas, gráficas de Pareto y un análisis de concentración de costos por SKU, formato de producto y tipología de defecto. El entregable final será un reporte ejecutivo de calidad con el Pareto comentado, generado con apoyo de Copilot en Word, que podrás utilizar como modelo replicable en tu entorno real de planta.

---

## 3. Objetivos de Aprendizaje

Al completar esta práctica, serás capaz de:

- [ ] **Comprender** el rol estratégico de Microsoft 365 Copilot como herramienta de análisis de calidad en entornos de manufactura, vinculando los conceptos de Calidad 4.0 con casos de uso concretos sobre datos de planta.
- [ ] **Generar** gráficas de Pareto automatizadas de costos de no calidad por SKU utilizando Copilot en Excel a partir de un dataset simulado de manufactura.
- [ ] **Identificar** los principales SKUs y tipologías de defectos que concentran el mayor costo de no calidad mediante análisis asistido por inteligencia artificial.
- [ ] **Formular** prompts efectivos y progresivos en Copilot para extraer insights de calidad por formato y tipología de producto desde hojas de cálculo estructuradas.
- [ ] **Producir** un reporte ejecutivo de análisis de calidad con Pareto comentado utilizando Copilot en Word como herramienta de redacción asistida.

---

## 4. Prerrequisitos

### 4.1 Conocimientos Previos

| Área | Nivel Requerido |
|---|---|
| Microsoft Excel (tablas, filtros, gráficas simples) | Básico |
| Conceptos de costos de no calidad en manufactura | Conceptual |
| Navegación general en Microsoft 365 | Básico |
| Lectura de la Lección 1.1 del Capítulo 1 | Completada |

### 4.2 Accesos y Recursos Necesarios

| Recurso | Estado requerido antes de iniciar |
|---|---|
| Cuenta corporativa Microsoft 365 con licencia Copilot activa | ✅ Verificada |
| Archivo `dataset_calidad_SKU.xlsx` cargado en OneDrive for Business | ✅ Disponible |
| Acceso a Microsoft Excel (versión 2308 o posterior) | ✅ Instalado |
| Acceso a Microsoft Word (versión 2308 o posterior) | ✅ Instalado |
| Acceso a Copilot Chat en [copilot.microsoft.com](https://copilot.microsoft.com) con cuenta corporativa | ✅ Verificado |
| Conexión a internet estable (mínimo 10 Mbps) | ✅ Activa |

> ⚠️ **Nota de privacidad:** Asegúrate de utilizar el modo **"Trabajo" (Work)** en copilot.microsoft.com antes de cargar o pegar cualquier dato. Este modo garantiza que la información no se use para entrenar modelos externos. Todos los datos de esta práctica son simulados y anonimizados; **no cargues datos reales de producción de tu empresa**.

---

## 5. Entorno de Laboratorio

### 5.1 Hardware Recomendado

| Componente | Mínimo | Recomendado |
|---|---|---|
| Procesador | Intel Core i5 8va gen / AMD Ryzen 5 | Intel Core i7 / AMD Ryzen 7 |
| RAM | 8 GB | 16 GB |
| Resolución de pantalla | 1366 × 768 | 1920 × 1080 |
| Almacenamiento disponible | 5 GB libres | 10 GB libres |
| Conexión a internet | 10 Mbps | 25 Mbps (red cableada) |

### 5.2 Software Requerido

| Aplicación | Versión mínima | Uso en esta práctica |
|---|---|---|
| Microsoft Excel | 365 Apps v2308+ | Análisis de datos, tablas dinámicas, Pareto |
| Microsoft Word | 365 Apps v2308+ | Reporte ejecutivo final |
| Microsoft 365 Copilot (Excel) | Integrado en v2308+ | Generación de análisis y gráficas |
| Microsoft 365 Copilot (Word) | Integrado en v2308+ | Redacción del reporte |
| OneDrive for Business | Incluido en M365 | Almacenamiento del dataset |
| Copilot Chat (Web) | copilot.microsoft.com | Prompts de apoyo y validación |

### 5.3 Configuración Inicial del Entorno

Realiza los siguientes pasos de configuración **antes** de comenzar los pasos del laboratorio:

**Paso A — Verificar acceso a Copilot en Excel:**
1. Abre Microsoft Excel desde el menú de inicio o desde office.com.
2. Abre cualquier libro en blanco.
3. En la cinta de opciones, verifica que aparezca el botón **Copilot** (ícono de constelación/estrella) en la pestaña **Inicio** o **Inicio de sesión**.
4. Si el botón no aparece, contacta a tu administrador de TI antes de continuar.

**Paso B — Verificar modo Trabajo en Copilot Chat:**
1. Abre un navegador y dirígete a [https://copilot.microsoft.com](https://copilot.microsoft.com).
2. Inicia sesión con tu **cuenta corporativa** (usuario@tuempresa.com).
3. Confirma que en la parte superior aparezca la indicación **"Trabajo"** o el nombre de tu organización. Si aparece "Personal", cierra sesión y vuelve a ingresar con tu cuenta corporativa.

**Paso C — Confirmar archivo en OneDrive:**
1. Abre un navegador y navega a [https://onedrive.microsoft.com](https://onedrive.microsoft.com).
2. Inicia sesión con tu cuenta corporativa.
3. Localiza el archivo `dataset_calidad_SKU.xlsx` en la carpeta indicada por tu instructor (generalmente: `Documentos > Curso_Copilot_Manufactura > Práctica_01`).
4. Si el archivo no está disponible, solicítalo al instructor antes de continuar.

---

## 6. Pasos del Laboratorio

> 📋 **Instrucción general:** Esta práctica está dividida en **cuatro fases** que siguen el flujo de trabajo de un analista de calidad en planta: exploración de datos → análisis con Copilot → visualización → reporte. Sigue los pasos en orden y documenta las respuestas de Copilot en una hoja de notas personal para el paso de validación final.

---

### Fase 1: Exploración y Comprensión del Dataset

**Objetivo de la fase:** Familiarizarte con la estructura del dataset simulado y verificar que está correctamente formateado para que Copilot pueda analizarlo eficientemente.

---

#### Paso 1.1 — Abrir y examinar el dataset en Excel

**Objetivo:** Abrir el archivo `dataset_calidad_SKU.xlsx` desde OneDrive y revisar su estructura antes de involucrar a Copilot.

**Instrucciones:**

1. Abre Microsoft Excel.
2. En la pantalla de inicio de Excel, selecciona **Abrir > OneDrive - [Nombre de tu organización]**.
3. Navega a la carpeta `Documentos > Curso_Copilot_Manufactura > Práctica_01`.
4. Haz doble clic en `dataset_calidad_SKU.xlsx` para abrirlo.
5. Una vez abierto, examina las columnas disponibles. El dataset debe contener al menos las siguientes columnas:

| Columna | Descripción |
|---|---|
| `Fecha` | Fecha del registro de defecto (formato DD/MM/AAAA) |
| `SKU` | Código de identificación del producto |
| `Formato_Producto` | Categoría de formato (ej. Bolsa 500g, Caja 1kg, Botella 750ml) |
| `Linea_Produccion` | Identificador de la línea donde ocurrió el defecto |
| `Tipo_Defecto` | Clasificación del defecto (ej. Sellado deficiente, Peso fuera de rango, Etiqueta mal colocada) |
| `Cantidad_Defectos` | Número de unidades defectuosas en el registro |
| `Costo_NoCalidad_MXN` | Costo monetario asociado al defecto en pesos mexicanos |
| `Turno` | Turno en que ocurrió (Matutino / Vespertino / Nocturno) |
| `Operador_ID` | Identificador anonimizado del operador |

6. Verifica que los datos estén organizados como una **tabla de Excel** (con encabezados en negrita y filas con color alterno). Si no están como tabla, selecciona todo el rango de datos y presiona `Ctrl + T` para convertirlos en tabla.
7. Anota en tu hoja de notas: ¿Cuántas filas de datos contiene el dataset? ¿Cuántos SKUs únicos puedes identificar visualmente?

**Salida esperada:** El archivo debe mostrar aproximadamente 200–350 registros de defectos distribuidos entre 8–12 SKUs diferentes, con datos de al menos 4 semanas de producción simulada.

**Verificación:** Confirma que la tabla tiene encabezados visibles, no hay columnas vacías entre los datos, y el archivo está guardado en OneDrive (el ícono en la barra de título debe mostrar la nube de OneDrive, no un disco local).

---

#### Paso 1.2 — Formatear el dataset como tabla inteligente de Excel

**Objetivo:** Asegurarse de que el dataset esté en formato de tabla estructurada para que Copilot pueda referenciarlo correctamente.

**Instrucciones:**

1. Haz clic en cualquier celda dentro del rango de datos.
2. Si los datos **no** están ya en formato tabla, presiona `Ctrl + T`. En el cuadro de diálogo, verifica que la opción **"La tabla tiene encabezados"** esté marcada. Haz clic en **Aceptar**.
3. En la pestaña **Diseño de tabla** (que aparece al seleccionar la tabla), asigna el nombre `Tabla_Calidad` en el campo **Nombre de tabla** (esquina superior izquierda de la cinta).
4. Verifica que la columna `Costo_NoCalidad_MXN` esté formateada como **Número** o **Moneda**. Si aparece como texto, selecciona la columna, haz clic derecho > **Formato de celdas** > selecciona **Número** con 2 decimales.
5. Guarda el archivo con `Ctrl + S`.

**Salida esperada:** La tabla debe tener un nombre asignado (`Tabla_Calidad`), encabezados visibles y la columna de costos formateada numéricamente.

**Verificación:** Haz clic en cualquier celda de la tabla. En el cuadro de nombre (esquina superior izquierda de Excel) debe aparecer la referencia de celda, y en la pestaña **Diseño de tabla** debe aparecer el nombre `Tabla_Calidad`.

---

### Fase 2: Análisis con Copilot en Excel — Secuencia de 5 Prompts Progresivos

**Objetivo de la fase:** Utilizar Copilot integrado en Excel para pasar progresivamente de datos crudos a insights accionables de calidad, formulando prompts estructurados que incrementan en profundidad analítica.

> 💡 **Nota sobre variabilidad de respuestas:** Copilot es generativo; sus respuestas pueden variar entre sesiones. Los resultados mostrados en esta guía son **referenciales**. Si la respuesta de Copilot difiere del ejemplo, evalúa si el contenido es igualmente válido antes de decidir si reformular el prompt. El instructor enfatizará este punto durante la práctica.

---

#### Paso 2.1 — Abrir el panel de Copilot en Excel

**Objetivo:** Activar el panel de Copilot dentro del archivo de Excel abierto.

**Instrucciones:**

1. Con el archivo `dataset_calidad_SKU.xlsx` abierto y la tabla `Tabla_Calidad` seleccionada, haz clic en el botón **Copilot** en la cinta de opciones (pestaña **Inicio**, grupo derecho).
2. Se abrirá un panel lateral derecho con el chat de Copilot.
3. Verifica que en la parte superior del panel aparezca un mensaje similar a: *"Copilot puede ayudarte a analizar los datos de tu tabla. ¿Qué te gustaría explorar?"*
4. Si Copilot muestra un aviso de que no puede analizar los datos, verifica que: (a) el cursor esté dentro de la tabla `Tabla_Calidad`, y (b) el archivo esté guardado en OneDrive (no en disco local).

**Salida esperada:** Panel de Copilot abierto en el lado derecho de Excel, mostrando el campo de entrada de texto y sugerencias de análisis predefinidas.

**Verificación:** El panel debe mostrar sugerencias automáticas como *"Resumir datos"*, *"Mostrar información clave"* o *"Crear tabla dinámica"*.

---

#### Paso 2.2 — Prompt 1: Resumen general del dataset

**Objetivo:** Obtener una visión panorámica de los datos antes de profundizar en análisis específicos.

**Instrucciones:**

1. En el campo de texto del panel de Copilot, escribe el siguiente prompt exactamente como se muestra:

```
Analiza los datos de la tabla Tabla_Calidad y proporciona un resumen ejecutivo que incluya: 
1) El número total de registros de defectos, 
2) El costo total de no calidad en MXN, 
3) Los 3 SKUs con mayor costo acumulado de no calidad, 
4) Los 3 tipos de defecto más frecuentes. 
Presenta los resultados en formato de lista clara.
```

2. Presiona **Enter** o haz clic en el botón de envío (flecha).
3. Espera la respuesta de Copilot (puede tomar entre 5 y 20 segundos dependiendo de la conexión).
4. Lee la respuesta completa y **anota en tu hoja de notas** los tres SKUs identificados y los tres tipos de defecto más frecuentes.

**Salida esperada (referencial):** Copilot debe responder con una lista estructurada similar a:

> *"La tabla contiene 287 registros de defectos con un costo total de no calidad de $1,234,567 MXN. Los 3 SKUs con mayor costo son: SKU-0042 ($312,450), SKU-0018 ($287,900), SKU-0031 ($198,200). Los 3 tipos de defecto más frecuentes son: Sellado deficiente (89 registros), Peso fuera de rango (67 registros), Etiqueta mal colocada (54 registros)."*

**Verificación:** La respuesta debe incluir valores numéricos concretos (no rangos vagos), debe mencionar al menos 3 SKUs distintos y debe estar basada en los datos reales de la tabla (los números coincidirán aproximadamente con lo que puedes calcular manualmente con `SUMAR.SI` en Excel).

---

#### Paso 2.3 — Prompt 2: Tabla dinámica de costos por SKU

**Objetivo:** Solicitar a Copilot que genere una tabla dinámica que concentre los costos de no calidad por SKU para preparar el análisis de Pareto.

**Instrucciones:**

1. En el panel de Copilot, escribe el siguiente prompt:

```
Crea una tabla dinámica que muestre el costo total de no calidad en MXN agrupado por SKU, 
ordenada de mayor a menor costo. Incluye también el porcentaje que representa cada SKU 
sobre el costo total. Agrega la tabla dinámica en una nueva hoja llamada "Pareto_SKU".
```

2. Presiona **Enter** y espera la respuesta.
3. Copilot puede: (a) generar la tabla dinámica automáticamente en una nueva hoja, o (b) proporcionarte instrucciones paso a paso para crearla. En cualquier caso, sigue las indicaciones hasta tener la tabla dinámica creada.
4. Si Copilot generó la tabla automáticamente, navega a la hoja `Pareto_SKU` y verifica que los datos estén ordenados de mayor a menor costo.
5. Si Copilot proporcionó instrucciones, síguelas. Si la hoja no se nombró automáticamente `Pareto_SKU`, renómbrala haciendo doble clic en la pestaña de la hoja.

**Salida esperada:** Una hoja nueva llamada `Pareto_SKU` con una tabla que muestre al menos las columnas: `SKU`, `Costo_Total_MXN`, `Porcentaje_del_Total`, ordenada de mayor a menor costo.

**Verificación:** Suma manualmente los valores de `Costo_Total_MXN` en la tabla dinámica. El total debe coincidir con el costo total reportado por Copilot en el Prompt 1 (tolerancia de ±1% por redondeos).

---

#### Paso 2.4 — Prompt 3: Análisis por tipología de defecto y formato de producto

**Objetivo:** Profundizar el análisis cruzando dos dimensiones: tipo de defecto y formato de producto, para identificar combinaciones críticas.

**Instrucciones:**

1. Regresa a la hoja principal con los datos originales (`dataset_calidad_SKU.xlsx` > hoja `Datos` o equivalente).
2. Haz clic dentro de la tabla `Tabla_Calidad` para que Copilot la reconozca como contexto.
3. En el panel de Copilot, escribe el siguiente prompt:

```
Analiza la relación entre Tipo_Defecto y Formato_Producto. 
¿Qué combinaciones de formato de producto y tipo de defecto concentran el mayor costo de no calidad? 
Muestra los 5 pares más costosos (Formato_Producto + Tipo_Defecto) con su costo total en MXN 
y el porcentaje acumulado que representan sobre el costo total. 
¿Hay algún patrón producto-proceso que debería investigarse con urgencia?
```

4. Lee la respuesta de Copilot con atención crítica. Evalúa si los patrones identificados tienen lógica operativa (por ejemplo, si "Sellado deficiente" aparece concentrado en un formato específico como "Bolsa 500g", esto tiene sentido industrial).
5. Anota en tu hoja de notas los 5 pares identificados y cualquier patrón mencionado por Copilot.

**Salida esperada (referencial):** Copilot debe identificar los 5 pares más costosos y hacer una observación analítica, por ejemplo:

> *"El par Bolsa 500g + Sellado deficiente representa el 23.4% del costo total de no calidad ($289,100 MXN). Le sigue Caja 1kg + Peso fuera de rango con 18.7% ($230,890 MXN). Se observa que el formato Bolsa 500g concentra el 41% del costo total, lo que sugiere una vulnerabilidad en el proceso de sellado de este formato que requiere revisión prioritaria."*

**Verificación:** Confirma que los 5 pares identificados son distintos entre sí (no hay duplicados de formato ni de tipo de defecto en posiciones consecutivas que no tengan sentido) y que los porcentajes suman menos del 100% (es un análisis de concentración, no exhaustivo).

---

#### Paso 2.5 — Prompt 4: Generación de gráfica de Pareto

**Objetivo:** Solicitar a Copilot que genere o guíe la creación de una gráfica de Pareto visual basada en los datos de costos por SKU.

**Instrucciones:**

1. Navega a la hoja `Pareto_SKU` donde está la tabla dinámica generada en el Paso 2.3.
2. Haz clic dentro de esa tabla dinámica.
3. En el panel de Copilot, escribe el siguiente prompt:

```
Con base en la tabla de costos por SKU ordenada de mayor a menor, 
crea una gráfica de Pareto que muestre en el eje Y izquierdo el costo total de no calidad en MXN 
por SKU (barras), y en el eje Y derecho el porcentaje acumulado (línea). 
Agrega una línea de referencia en el 80% para identificar el umbral de Pareto. 
Nombra la gráfica "Pareto de Costos de No Calidad por SKU".
```

4. Sigue las instrucciones de Copilot. Si genera la gráfica automáticamente, verifícala. Si proporciona pasos manuales, síguelos:
   - Selecciona los datos de la tabla dinámica (`SKU` y `Costo_Total_MXN`).
   - Ve a **Insertar > Gráficos recomendados > Histograma > Pareto** (Excel 365 tiene tipo de gráfico Pareto nativo).
   - Alternativamente, si Copilot sugiere un gráfico de barras + línea combinado, sigue esa instrucción.
5. Ajusta el título de la gráfica a: **"Pareto de Costos de No Calidad por SKU"**.
6. Verifica que la línea de porcentaje acumulado sea visible y que el punto donde cruza el 80% sea identificable.

**Salida esperada:** Una gráfica de Pareto en la hoja `Pareto_SKU` con barras descendentes por SKU y línea de porcentaje acumulado, con título visible.

**Verificación:** Identifica visualmente qué SKUs quedan a la izquierda de la línea del 80% (el "grupo vital"). Deben ser entre 2 y 4 SKUs (regla empírica del Pareto 80/20). Si todos los SKUs tienen costos casi iguales, el dataset puede no mostrar concentración clara; esto también es un hallazgo válido para reportar.

---

#### Paso 2.6 — Prompt 5: Insights accionables y anticipación de comportamientos

**Objetivo:** Utilizar Copilot para ir más allá de la descripción estadística y obtener recomendaciones concretas de acción preventiva, cerrando el ciclo del análisis de Calidad 4.0.

**Instrucciones:**

1. Regresa a la hoja principal de datos.
2. En el panel de Copilot, escribe el siguiente prompt (el más estratégico de la secuencia):

```
Con base en el análisis de costos de no calidad por SKU, formato de producto y tipo de defecto 
que hemos realizado, identifica:
1) Los 3 SKUs o combinaciones producto-proceso con mayor riesgo de incrementar su costo 
   de no calidad en las próximas semanas si no se interviene.
2) Para cada uno, sugiere una acción preventiva concreta que un supervisor de calidad 
   podría implementar en los próximos 5 días hábiles.
3) ¿Qué datos adicionales deberíamos recolectar para hacer este análisis más predictivo?
Responde en formato de tabla con columnas: SKU/Combinación, Riesgo Identificado, 
Acción Preventiva, Plazo Sugerido.
```

3. Evalúa la respuesta de Copilot con **pensamiento crítico**: ¿Las acciones preventivas sugeridas son realistas para tu tipo de planta? ¿Los riesgos identificados tienen lógica operativa? Recuerda que Copilot trabaja con los datos del dataset simulado, no con el contexto real de tu planta.
4. Anota al menos **2 insights** que consideres más relevantes y realistas para tu contexto de trabajo.
5. Guarda el archivo Excel con `Ctrl + S`.

**Salida esperada (referencial):** Copilot debe generar una tabla con 3 filas, similar a:

| SKU/Combinación | Riesgo Identificado | Acción Preventiva | Plazo Sugerido |
|---|---|---|---|
| SKU-0042 / Bolsa 500g | Tendencia creciente en defectos de sellado en turno nocturno | Revisión de parámetros de temperatura de selladora + capacitación operadores turno nocturno | 3 días hábiles |
| SKU-0018 / Caja 1kg | Concentración de defectos de peso en una sola línea de producción | Calibración de básculas de línea L3, verificación de set points | 2 días hábiles |
| SKU-0031 / Botella 750ml | Incremento en etiquetas mal colocadas en últimas 2 semanas | Inspección de sistema de aplicación de etiquetas, revisión de tensión de banda | 5 días hábiles |

**Verificación:** La tabla de Copilot debe tener al menos 3 filas, cada acción preventiva debe ser específica (no genérica como "mejorar el proceso"), y los plazos deben ser concretos. Si la respuesta es muy genérica, reformula el prompt añadiendo: *"Sé específico con las acciones; menciona equipos, parámetros o procedimientos concretos."*

---

### Fase 3: Generación del Reporte Ejecutivo en Word con Copilot

**Objetivo de la fase:** Trasladar los hallazgos del análisis en Excel a un reporte ejecutivo estructurado en Microsoft Word, utilizando Copilot como asistente de redacción.

---

#### Paso 3.1 — Crear el documento base en Word

**Objetivo:** Abrir un nuevo documento de Word en OneDrive y preparar la estructura del reporte.

**Instrucciones:**

1. Abre Microsoft Word (desde el menú de inicio o desde office.com).
2. Selecciona **Nuevo documento en blanco**.
3. Guarda inmediatamente el documento en OneDrive: **Archivo > Guardar como > OneDrive - [Tu organización]**, navega a la carpeta `Documentos > Curso_Copilot_Manufactura > Práctica_01` y guárdalo con el nombre: `Reporte_Calidad_Pareto_[TuNombre].docx`.
4. Verifica que el documento esté guardado en OneDrive (ícono de nube en la barra de título).
5. Escribe el siguiente esquema de secciones manualmente como estructura base (solo los títulos, el contenido lo generará Copilot):

```
1. Resumen Ejecutivo
2. Análisis de Pareto — Costos de No Calidad por SKU
3. Hallazgos por Tipología de Defecto y Formato de Producto
4. Riesgos Identificados y Acciones Preventivas Recomendadas
5. Conclusiones y Próximos Pasos
```

6. Formatea cada título con el estilo **Título 2** (selecciona el texto > pestaña **Inicio** > grupo **Estilos** > **Título 2**).

**Salida esperada:** Documento Word guardado en OneDrive con 5 secciones tituladas y formateadas con estilo Título 2.

**Verificación:** El panel de navegación del documento (Vista > Panel de navegación) debe mostrar las 5 secciones como elementos de navegación.

---

#### Paso 3.2 — Activar Copilot en Word y generar el contenido del reporte

**Objetivo:** Utilizar Copilot en Word para redactar el contenido de cada sección del reporte basándose en los hallazgos documentados en tu hoja de notas.

**Instrucciones:**

1. En Word, haz clic en el botón **Copilot** en la cinta de opciones (pestaña **Inicio** o **Revisar**). Se abrirá el panel de Copilot.
2. Haz clic al final del título **"1. Resumen Ejecutivo"** y presiona **Enter** para crear una línea en blanco.
3. En el panel de Copilot, escribe el siguiente prompt para generar el resumen ejecutivo:

```
Redacta un resumen ejecutivo profesional de máximo 150 palabras para un reporte de análisis 
de costos de no calidad de una línea de manufactura. 
Incluye los siguientes datos del análisis:
- Total de registros analizados: [número que anotaste en el Paso 2.2]
- Costo total de no calidad: [cifra que anotaste en el Paso 2.2] MXN
- Los 3 SKUs con mayor costo: [SKUs que anotaste en el Paso 2.2]
- Hallazgo principal: [el patrón producto-proceso más relevante del Paso 2.4]
El tono debe ser formal, orientado a la toma de decisiones gerenciales en manufactura.
```

> 📝 **Instrucción:** Reemplaza los valores entre corchetes `[ ]` con los datos reales que anotaste en tu hoja de notas durante los pasos anteriores.

4. Presiona **Enter** y espera la respuesta de Copilot.
5. Si el texto generado es adecuado, haz clic en **"Insertar"** o **"Mantener"** para agregarlo al documento. Si necesita ajustes, usa el botón **"Regenerar"** o edita manualmente.
6. Repite el proceso para la sección **"4. Riesgos Identificados y Acciones Preventivas Recomendadas"** usando el siguiente prompt:

```
Redacta la sección de riesgos y acciones preventivas para un reporte de calidad en manufactura. 
Presenta en formato de tabla los siguientes 3 casos identificados por el análisis de Pareto:
[Pega aquí la tabla de 3 filas que generó Copilot en el Paso 2.6]
Agrega un párrafo introductorio de 2-3 oraciones que contextualice la urgencia de estas acciones 
desde la perspectiva de la Calidad 4.0 y la gestión preventiva.
```

7. Para la sección **"5. Conclusiones y Próximos Pasos"**, usa el siguiente prompt:

```
Redacta una sección de conclusiones y próximos pasos de máximo 120 palabras para un reporte 
de análisis de costos de no calidad. Las conclusiones deben enfatizar el valor del análisis 
de Pareto como herramienta de priorización, el potencial de Microsoft Copilot para acelerar 
este tipo de análisis en planta, y la transición del enfoque reactivo al preventivo en la 
gestión de calidad. Los próximos pasos deben incluir: revisión de los SKUs críticos identificados, 
implementación de las acciones preventivas en los plazos indicados, y propuesta de revisión 
mensual del análisis de Pareto.
```

8. Guarda el documento con `Ctrl + S`.

**Salida esperada:** Documento Word con al menos las secciones 1, 4 y 5 con contenido redactado por Copilot, formateado profesionalmente.

**Verificación:** El documento debe tener al menos 400 palabras de contenido generado, las secciones deben estar numeradas correctamente, y la tabla de riesgos debe ser visible y legible.

---

#### Paso 3.3 — Insertar la gráfica de Pareto en el reporte

**Objetivo:** Integrar la gráfica de Pareto generada en Excel dentro del reporte de Word para crear un documento de análisis completo.

**Instrucciones:**

1. Regresa al archivo Excel `dataset_calidad_SKU.xlsx`.
2. Navega a la hoja `Pareto_SKU`.
3. Haz clic en la gráfica **"Pareto de Costos de No Calidad por SKU"**.
4. Cópiala con `Ctrl + C`.
5. Regresa al documento Word.
6. Coloca el cursor debajo del título **"2. Análisis de Pareto — Costos de No Calidad por SKU"**.
7. Pega la gráfica con `Ctrl + V`. Selecciona la opción de pegado **"Imagen"** o **"Mantener formato de origen"** para que la gráfica se incruste como imagen estática.
8. Ajusta el tamaño de la gráfica para que ocupe el ancho de la página (aproximadamente 15 cm de ancho).
9. Agrega un pie de figura debajo de la gráfica: haz clic debajo de la imagen y escribe:

```
Figura 1. Pareto de Costos de No Calidad por SKU — Dataset simulado de manufactura. 
Los SKUs a la izquierda de la línea del 80% representan el grupo vital de intervención prioritaria.
```

10. Guarda el documento.

**Salida esperada:** La gráfica de Pareto aparece en la sección 2 del documento Word con su pie de figura correspondiente.

**Verificación:** La gráfica debe ser legible (no pixelada), el título de la gráfica debe ser visible, y el pie de figura debe estar en fuente más pequeña que el texto principal (puedes usar el estilo **Subtítulo** o reducir a 10pt).

---

### Fase 4: Revisión Final y Preparación del Entregable

**Objetivo de la fase:** Revisar la calidad del reporte generado, aplicar un último prompt de revisión con Copilot y preparar el archivo final para entrega.

---

#### Paso 4.1 — Revisión final del reporte con Copilot en Word

**Objetivo:** Utilizar Copilot para hacer una revisión de coherencia y calidad del reporte antes de la entrega.

**Instrucciones:**

1. Con el documento Word abierto, selecciona todo el texto del documento (`Ctrl + A`).
2. En el panel de Copilot en Word, escribe el siguiente prompt:

```
Revisa el documento completo y proporciona:
1) Una evaluación de la coherencia entre las secciones del reporte.
2) Tres sugerencias específicas para mejorar la claridad o el impacto ejecutivo del documento.
3) Verifica si hay inconsistencias numéricas entre las secciones (por ejemplo, si el resumen 
   ejecutivo menciona cifras diferentes a las de la sección de riesgos).
```

3. Lee las sugerencias de Copilot e implementa al menos **2 de las 3 mejoras sugeridas** directamente en el documento.
4. Guarda el documento final.

**Salida esperada:** Copilot debe proporcionar retroalimentación específica sobre el documento, no comentarios genéricos. Las sugerencias deben referirse a secciones concretas del texto.

**Verificación:** Después de implementar las mejoras, el documento debe tener consistencia numérica entre secciones (los mismos valores de costo y SKU deben aparecer en el resumen ejecutivo y en la sección de riesgos).

---

#### Paso 4.2 — Nombrar y organizar los entregables finales

**Objetivo:** Organizar todos los archivos generados en la práctica en la carpeta correcta de OneDrive.

**Instrucciones:**

1. Verifica que los siguientes archivos estén guardados en la carpeta `Documentos > Curso_Copilot_Manufactura > Práctica_01` de tu OneDrive:

| Archivo | Descripción |
|---|---|
| `dataset_calidad_SKU.xlsx` | Dataset original con tabla `Tabla_Calidad` y hoja `Pareto_SKU` con gráfica |
| `Reporte_Calidad_Pareto_[TuNombre].docx` | Reporte ejecutivo con Pareto comentado |

2. Abre OneDrive en el navegador y confirma que ambos archivos están sincronizados (ícono de palomita verde, no de sincronización en proceso).
3. Comparte el reporte Word con tu instructor: en OneDrive, haz clic derecho en el archivo > **Compartir** > ingresa el correo de tu instructor > selecciona **"Puede ver"** > haz clic en **Enviar**.

**Salida esperada:** Dos archivos correctamente nombrados y sincronizados en OneDrive, con el reporte compartido con el instructor.

**Verificación:** El instructor debe confirmar que recibió la notificación de acceso al archivo. Si no hay confirmación en 5 minutos, verifica la dirección de correo utilizada.

---

## 7. Validación y Pruebas

Al finalizar todos los pasos, realiza la siguiente lista de verificación completa para confirmar que la práctica fue completada exitosamente:

### Lista de Verificación de Entregables

| # | Criterio de Validación | ✅ / ❌ |
|---|---|---|
| 1 | El archivo `dataset_calidad_SKU.xlsx` contiene la tabla `Tabla_Calidad` con nombre asignado | |
| 2 | Existe una hoja `Pareto_SKU` con tabla dinámica de costos ordenada de mayor a menor | |
| 3 | La gráfica "Pareto de Costos de No Calidad por SKU" está presente en la hoja `Pareto_SKU` | |
| 4 | La gráfica muestra barras descendentes por SKU y línea de porcentaje acumulado | |
| 5 | Se formularon y ejecutaron al menos 5 prompts distintos en Copilot durante la práctica | |
| 6 | El reporte Word tiene las 5 secciones con contenido (no solo títulos vacíos) | |
| 7 | La gráfica de Pareto está insertada en la sección 2 del reporte Word | |
| 8 | La sección 4 del reporte incluye la tabla de riesgos y acciones preventivas | |
| 9 | El documento Word tiene más de 400 palabras de contenido | |
| 10 | Ambos archivos están guardados y sincronizados en OneDrive | |
| 11 | El reporte Word fue compartido con el instructor | |

### Prueba de Calidad del Análisis

Responde las siguientes preguntas en tu hoja de notas para validar la profundidad del análisis:

1. **¿Qué SKUs conforman el "grupo vital" del Pareto (aquellos que concentran el 80% del costo de no calidad)?** — Debes poder responder con nombres/códigos específicos de SKU.
2. **¿Cuál es la combinación Formato_Producto + Tipo_Defecto más costosa identificada?** — Debe ser una combinación específica, no una respuesta genérica.
3. **¿Qué acción preventiva concreta recomendarías implementar esta semana si este fuera un análisis real de tu planta?** — Esta pregunta evalúa tu capacidad de transferir el aprendizaje a tu contexto real.

> 🎯 **Criterio de éxito:** Si puedes responder las tres preguntas con datos específicos del análisis, has completado exitosamente los objetivos de la práctica.

---

## 8. Solución de Problemas

### Problema 1: Copilot no aparece o no responde en Excel

**Síntoma:** El botón de Copilot no aparece en la cinta de opciones de Excel, o al hacer clic no abre el panel, o el panel aparece pero muestra el mensaje *"Copilot no está disponible para este archivo"*.

**Causa probable:** El archivo no está guardado en OneDrive for Business (Copilot en Excel requiere que el archivo esté en la nube corporativa, no en disco local). Alternativamente, la licencia de Microsoft 365 Copilot puede no estar correctamente asignada a la cuenta del usuario.

**Solución:**
1. **Verifica la ubicación del archivo:** Mira la barra de título de Excel. Si dice *"Guardado en este PC"* o muestra una ruta local (ej. `C:\Users\...`), el archivo está en disco local. Ve a **Archivo > Guardar una copia > OneDrive - [Tu organización]** y guarda el archivo en OneDrive.
2. **Cierra y vuelve a abrir el archivo** desde OneDrive (no desde el historial reciente de Excel, sino navegando directamente a OneDrive).
3. **Verifica la licencia:** Ve a [https://office.com](https://office.com), inicia sesión con tu cuenta corporativa y busca el ícono de Copilot en el menú principal. Si no aparece, contacta a tu administrador de TI para verificar que la licencia Copilot esté asignada a tu cuenta.
4. **Verifica la versión de Excel:** Ve a **Archivo > Cuenta > Acerca de Excel**. La versión debe ser 2308 o posterior. Si es anterior, actualiza desde **Archivo > Cuenta > Opciones de actualización > Actualizar ahora**.

---

### Problema 2: Las respuestas de Copilot son genéricas o no reflejan los datos del dataset

**Síntoma:** Copilot responde con información genérica sobre calidad en manufactura (ej. *"Los costos de no calidad típicamente incluyen..."*) en lugar de analizar los datos específicos de la tabla `Tabla_Calidad`. Los números en la respuesta no corresponden a los valores del dataset.

**Causa probable:** Copilot no está "viendo" la tabla correcta. Esto ocurre cuando: (a) el cursor no estaba dentro de la tabla al hacer la pregunta, (b) la tabla no tiene nombre asignado y Copilot no puede referenciarla, o (c) el prompt no especifica explícitamente que debe analizar los datos de la hoja activa.

**Solución:**
1. **Asegura el contexto de la tabla:** Antes de escribir cualquier prompt, haz clic en cualquier celda **dentro** de la tabla `Tabla_Calidad`. Verifica que en la pestaña **Diseño de tabla** aparezca el nombre `Tabla_Calidad`.
2. **Reformula el prompt con referencia explícita:** Añade al inicio de tu prompt: *"Usando los datos de la tabla activa en esta hoja de Excel..."* o *"Analiza los datos de la Tabla_Calidad que está en esta hoja..."*
3. **Cierra y reabre el panel de Copilot:** Haz clic en el botón **X** del panel de Copilot para cerrarlo, luego haz clic nuevamente en el botón **Copilot** en la cinta para reabrirlo. A veces el panel pierde el contexto del archivo y necesita reiniciarse.
4. **Verifica que el archivo tenga datos:** Confirma que la tabla `Tabla_Calidad` tiene al menos 50 filas de datos visibles (no filtradas). Si hay un filtro activo que oculta datos, Copilot puede analizar solo los datos visibles. Ve a **Datos > Borrar** para eliminar filtros activos.

---

## 9. Limpieza del Entorno

Al finalizar la práctica, realiza los siguientes pasos de limpieza para mantener tu entorno de trabajo organizado:

1. **Cierra el panel de Copilot** en Excel y Word haciendo clic en el botón **X** del panel lateral.
2. **Guarda todos los archivos** con `Ctrl + S` antes de cerrarlos.
3. **Cierra Excel y Word** correctamente (no fuerces el cierre con el administrador de tareas).
4. **Verifica la sincronización en OneDrive:** Abre el cliente de OneDrive en la bandeja del sistema (ícono de nube en la barra de tareas). Confirma que todos los archivos muestran el ícono de palomita verde (sincronizado). Si algún archivo muestra un ícono de error (X roja), haz clic derecho sobre él y selecciona **"Reintentar sincronización"**.
5. **Cierra la sesión de Copilot Chat** en el navegador si la utilizaste durante la práctica: ve a [https://copilot.microsoft.com](https://copilot.microsoft.com) y cierra la pestaña del navegador (no es necesario cerrar sesión de tu cuenta Microsoft, solo cerrar la pestaña).
6. **Archiva tu hoja de notas:** Si usaste una hoja de papel para anotar los hallazgos, escríbelos en un archivo de texto o en el propio documento Word del reporte para que queden digitalizados.

> ℹ️ **Nota:** No elimines el archivo `dataset_calidad_SKU.xlsx` ni el reporte Word de tu OneDrive. Estos archivos serán utilizados como referencia en prácticas posteriores del curso (Prácticas 3, 4 y 5 dependen de los entregables generados en esta práctica).

---

## 10. Resumen

### Lo que Aprendiste en Esta Práctica

En esta práctica aplicaste los fundamentos de **Calidad 4.0** presentados en la Lección 1.1 para transformar datos crudos de defectos en manufactura en un análisis ejecutivo accionable. Recorriste el flujo completo de trabajo que un analista o supervisor de calidad puede replicar en su entorno real:

1. **Preparación del dataset:** Formatear correctamente los datos en Excel como tabla estructurada es el paso fundamental que habilita el análisis asistido por IA. Sin esta preparación, Copilot no puede acceder al contexto correcto.

2. **Prompts progresivos:** Aprendiste que la efectividad de Copilot depende directamente de la calidad de los prompts. La secuencia de 5 prompts demostró cómo pasar de una pregunta general (*"resume los datos"*) a una solicitud estratégica (*"identifica riesgos y recomienda acciones preventivas"*), incrementando el valor de cada respuesta.

3. **Análisis de Pareto automatizado:** La gráfica de Pareto por SKU demostró visualmente el principio 80/20 aplicado a los costos de no calidad, permitiendo priorizar los esfuerzos de mejora en los SKUs del "grupo vital".

4. **Reporte ejecutivo asistido:** Copilot en Word redujo significativamente el tiempo de redacción del reporte, permitiéndote enfocarte en la validación crítica del contenido en lugar de en la escritura desde cero.

5. **Pensamiento crítico sobre IA:** Evaluaste las respuestas de Copilot con criterio profesional, reconociendo que son generativas y requieren validación antes de convertirse en decisiones de planta.

### Conexión con el Contexto de Calidad 4.0

Como se describió en la Lección 1.1, la Calidad 4.0 no reemplaza la experiencia del profesional de manufactura; la potencia. Esta práctica demostró ese principio en acción: tu conocimiento del proceso fue indispensable para evaluar si los patrones identificados por Copilot tenían sentido operativo. La herramienta aceleró el análisis; tu criterio profesional lo validó.

El flujo que practicaste hoy —datos estructurados → prompts progresivos → visualización → reporte → acción— es el mismo que aplicarás en los capítulos posteriores del curso para mantenimiento predictivo, análisis de causa raíz y gestión de riesgos operativos.

### Recursos Adicionales

| Recurso | URL |
|---|---|
| Documentación oficial de Copilot en Excel | [https://support.microsoft.com/es-es/copilot-excel](https://support.microsoft.com/es-es/topic/get-started-with-copilot-in-excel-d7110502-0334-4b4f-a175-a73abdfc118a) |
| Guía de prompts efectivos para Microsoft Copilot | [https://learn.microsoft.com/es-es/copilot/microsoft-365/prompting-tips](https://learn.microsoft.com/es-es/copilot/microsoft-365/prompting-tips-and-tricks) |
| Conceptos de Calidad 4.0 — ASQ | [https://asq.org/quality-resources/quality-4-0](https://asq.org/quality-resources/quality-4-0) |
| Análisis de Pareto en manufactura — referencia técnica | [https://asq.org/quality-resources/pareto](https://asq.org/quality-resources/pareto) |
| Microsoft Copilot para operaciones — casos de uso | [https://learn.microsoft.com/es-es/copilot/microsoft-365/microsoft-365-copilot-overview](https://learn.microsoft.com/es-es/copilot/microsoft-365/microsoft-365-copilot-overview) |

---

> 🚀 **Próxima práctica:** En la **Práctica 2** profundizarás en el análisis de causa raíz asistido por Copilot, utilizando los hallazgos del Pareto generado hoy como punto de partida para formular hipótesis de causas y planes de acción correctiva. Asegúrate de tener disponibles los archivos generados en esta práctica.

---
LAB_END---
