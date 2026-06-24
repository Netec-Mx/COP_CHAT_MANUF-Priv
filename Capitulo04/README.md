# Configuración de alertas tempranas y resúmenes ejecutivos. Cómo pasar de "explicar el pasado" a "gestionar el riesgo futuro". Priorización de acciones preventivas.

## Metadatos

| Atributo | Detalle |
|---|---|
| **Duración estimada** | 60 minutos |
| **Complejidad** | Media |
| **Nivel Bloom** | Aplicar |
| **Módulo** | Capítulo 4 — Gestión Anticipada con Microsoft 365 Copilot |
| **Práctica número** | 4 de 7 |
| **Última revisión** | 2024 |

---

## Descripción General

En esta práctica, los participantes darán un paso decisivo en la transición del enfoque reactivo al enfoque preventivo: configurarán un sistema de alertas tempranas en Excel con asistencia de Copilot, definirán umbrales críticos para indicadores clave de manufactura (OEE, tasa de defectos, frecuencia de paros y consumo de refacciones), y generarán resúmenes ejecutivos de riesgo operativo en Word de forma automatizada. La práctica culmina con la simulación de un escenario de riesgo emergente donde el participante debe construir un reporte ejecutivo completo y una matriz de priorización de acciones preventivas en menos de 15 minutos utilizando Copilot como aliado estratégico. El hilo conductor de todo el laboratorio es el principio central del Capítulo 4: **la anticipación es más valiosa que la reacción**.

---

## Objetivos de Aprendizaje

Al completar esta práctica, el participante será capaz de:

- [ ] Configurar reglas de formato condicional y alertas tempranas en Excel con asistencia de Copilot para detectar desviaciones de KPIs antes de que escalen a crisis operativas.
- [ ] Generar resúmenes ejecutivos de riesgo operativo automatizados con Copilot en Word que comuniquen el estado actual y las proyecciones de riesgo futuro.
- [ ] Aplicar Copilot Chat para construir una matriz de priorización de acciones preventivas con criterios de impacto, urgencia y viabilidad basada en datos integrados de producción, calidad y mantenimiento.
- [ ] Diseñar y ejecutar una rutina de gestión del riesgo futuro que reemplace la narrativa retrospectiva por un enfoque prospectivo, utilizando Copilot como intérprete inteligente de los datos de planta.

---

## Prerrequisitos

### Conocimientos Previos

| Área | Nivel requerido |
|---|---|
| Microsoft Excel (tablas, fórmulas básicas, formato condicional) | Básico-Intermedio |
| Microsoft Word (edición de documentos, uso de Copilot en Word) | Básico |
| Copilot Chat en copilot.microsoft.com | Básico (completado en prácticas anteriores) |
| KPIs de manufactura: OEE, tasa de defectos, MTBF, frecuencia de paros | Comprensión conceptual |
| Gestión de riesgos operativos (impacto, urgencia, probabilidad) | Comprensión conceptual |

### Acceso y Archivos Necesarios

| Recurso | Estado requerido |
|---|---|
| Cuenta corporativa Microsoft 365 con licencia Copilot activa | ✅ Verificado antes del inicio |
| Dashboard integrado de OEE de la Práctica 3 (archivo Excel) | Disponible en OneDrive |
| Archivo de respaldo `Practica3_Dashboard_Completado.xlsx` | Proporcionado por el instructor |
| Acceso a Microsoft Word con Copilot habilitado | ✅ Verificado |
| Acceso a copilot.microsoft.com con cuenta corporativa (modo Trabajo) | ✅ Verificado |
| OneDrive for Business con al menos 5 GB disponibles | ✅ Verificado |

> ⚠️ **Nota importante:** Si no completaste la Práctica 3, solicita al instructor el archivo `Practica3_Dashboard_Completado.xlsx` antes de iniciar. Este archivo es el punto de partida de los Pasos 1 y 2.

---

## Entorno de Laboratorio

### Hardware Mínimo Recomendado

| Componente | Especificación mínima | Recomendado |
|---|---|---|
| Procesador | Intel Core i5 8va Gen / AMD Ryzen 5 | Intel Core i7 / AMD Ryzen 7 |
| RAM | 8 GB | 16 GB |
| Almacenamiento disponible | 5 GB libres | 10 GB libres |
| Resolución de pantalla | 1366×768 | 1920×1080 |
| Conexión a internet | 10 Mbps estable | Red corporativa cableada |

### Software Requerido

| Aplicación | Versión mínima | Verificación |
|---|---|---|
| Microsoft Excel | Microsoft 365 Apps v2308+ | Abrir Excel → Archivo → Cuenta → Ver versión |
| Microsoft Word | Microsoft 365 Apps v2308+ | Abrir Word → Archivo → Cuenta → Ver versión |
| Microsoft Teams | New Teams v2.0+ | Ícono de Teams → Configuración → Acerca de |
| Copilot Chat (Web) | copilot.microsoft.com | Navegar al sitio con cuenta corporativa |
| OneDrive for Business | Incluido en M365 | Verificar sincronización activa en la barra de tareas |

### Configuración Inicial del Entorno

Antes de comenzar los pasos del laboratorio, ejecuta la siguiente lista de verificación:

**1. Verificar acceso a Copilot en modo Trabajo:**
```
1. Navegar a: https://copilot.microsoft.com
2. Iniciar sesión con cuenta corporativa (no cuenta personal)
3. Verificar que aparezca el indicador "Trabajo" (Work) en la interfaz
4. Confirmar que el ícono de escudo/protección esté visible (indica modo protegido)
```

**2. Abrir y verificar el archivo de la Práctica 3:**
```
1. Acceder a OneDrive for Business
2. Localizar: Practica3_Dashboard_Completado.xlsx
3. Abrir en Excel (versión escritorio, NO en Excel Online)
4. Verificar que el archivo contiene las hojas:
   - "Dashboard_OEE"
   - "Datos_Produccion"
   - "Datos_Calidad"
   - "Datos_Mantenimiento"
5. Guardar una copia con el nombre: Practica4_Alertas_[TuNombre].xlsx
```

**3. Verificar Copilot en Excel:**
```
1. En Excel, hacer clic en la pestaña "Inicio" o "Home"
2. Verificar que aparece el botón "Copilot" en la cinta de opciones
3. Si no aparece: Archivo → Opciones → Complementos → verificar habilitación
```

> 🔒 **Aviso de privacidad:** Todos los datos utilizados en esta práctica son simulados y anonimizados. No cargues datos reales de producción de tu empresa en Copilot Chat sin verificar que estás en modo "Trabajo" protegido con tu cuenta corporativa.

---

## Pasos del Laboratorio

---

### Paso 1: Definición de Umbrales Críticos con Copilot en Excel

**Objetivo del paso:** Utilizar Copilot en Excel para identificar y documentar los umbrales críticos de los KPIs de manufactura que servirán como base del sistema de alertas tempranas.

**Duración estimada:** 12 minutos

#### Instrucciones

1. Abre el archivo `Practica4_Alertas_[TuNombre].xlsx` que preparaste en la configuración inicial.

2. Navega a la hoja **"Dashboard_OEE"** y localiza los datos de los indicadores clave. Deberías ver columnas con valores de OEE, Tasa de Defectos, Frecuencia de Paros y Consumo de Refacciones por línea de producción.

3. Haz clic en el botón **Copilot** en la cinta de opciones de Excel para abrir el panel lateral de Copilot.

4. Escribe el siguiente prompt en el panel de Copilot:

```
Analiza los datos de esta hoja de cálculo y ayúdame a identificar los umbrales 
críticos para los siguientes KPIs de manufactura:
- OEE (Overall Equipment Effectiveness) por línea
- Tasa de defectos (%)
- Frecuencia de paros no planificados (paros/semana)
- Consumo de refacciones (unidades/mes)

Para cada KPI, sugiere tres niveles de umbral:
1. VERDE: Operación normal (sin intervención requerida)
2. AMARILLO: Alerta temprana (intervención preventiva recomendada)
3. ROJO: Riesgo crítico (intervención inmediata requerida)

Basa los umbrales en el comportamiento histórico visible en los datos y en 
estándares de manufactura de clase mundial. Presenta los resultados en formato 
de tabla.
```

5. Revisa la respuesta de Copilot. Evalúa críticamente si los umbrales propuestos son coherentes con los datos históricos del dashboard. Recuerda: las respuestas de Copilot son referenciales y requieren validación.

6. Crea una nueva hoja en el archivo llamada **"Umbrales_Alertas"**.

7. En la celda **A1**, escribe el título: `TABLA DE UMBRALES CRÍTICOS - SISTEMA DE ALERTAS TEMPRANAS`

8. A partir de la celda **A3**, crea manualmente (o pide a Copilot que genere la fórmula para insertar) la siguiente estructura de tabla basada en los umbrales que Copilot te sugirió:

```
Columnas: KPI | Línea | Umbral Verde (≥) | Umbral Amarillo | Umbral Rojo (≤) | Unidad | Frecuencia de revisión
```

9. Completa la tabla con al menos los siguientes KPIs para las 3 líneas de producción del dashboard:

| KPI | Línea | Verde (≥) | Amarillo | Rojo (≤) | Unidad |
|---|---|---|---|---|---|
| OEE | L1, L2, L3 | 85% | 75-84% | <75% | % |
| Tasa de Defectos | L1, L2, L3 | <2% | 2-4% | >4% | % |
| Frecuencia de Paros | L1, L2, L3 | <2 | 2-4 | >4 | paros/semana |
| Consumo Refacciones | L1, L2, L3 | <80% del presupuesto | 80-95% | >95% | % presupuesto |

> 📝 **Nota pedagógica:** Los valores de la tabla anterior son de referencia. Ajusta los umbrales según lo que Copilot haya sugerido basándose en los datos reales del dashboard de la Práctica 3. Este ajuste basado en datos históricos propios es precisamente el valor de usar Copilot como intérprete inteligente.

10. Guarda el archivo (`Ctrl+S`).

#### Resultado Esperado

Una hoja **"Umbrales_Alertas"** completa con una tabla estructurada de umbrales para 4 KPIs × 3 líneas de producción, con niveles Verde/Amarillo/Rojo claramente definidos y justificados por el análisis de Copilot sobre los datos históricos del dashboard.

#### Verificación

- [ ] La hoja "Umbrales_Alertas" existe en el archivo y contiene la tabla completa.
- [ ] Los umbrales están definidos para los 4 KPIs en las 3 líneas de producción.
- [ ] Los valores de umbral son coherentes con los datos históricos visibles en el dashboard (no son valores arbitrarios).
- [ ] El archivo ha sido guardado correctamente.

---

### Paso 2: Configuración de Formato Condicional con Asistencia de Copilot

**Objetivo del paso:** Configurar reglas de formato condicional en Excel, asistido por Copilot, para que el dashboard muestre visualmente el estado de alerta de cada KPI en tiempo real usando el código de colores Verde/Amarillo/Rojo definido en el Paso 1.

**Duración estimada:** 15 minutos

#### Instrucciones

1. Regresa a la hoja **"Dashboard_OEE"** en tu archivo.

2. Identifica el rango de celdas que contiene los valores actuales de OEE por línea. Típicamente será un rango como `C5:C7` o similar dependiendo de cómo esté estructurado tu dashboard.

3. En el panel de Copilot (si está cerrado, vuelve a abrirlo desde la cinta), escribe el siguiente prompt:

```
Necesito configurar formato condicional en las celdas que contienen los valores 
de OEE de las líneas L1, L2 y L3 de este dashboard. 

Las reglas deben ser:
- VERDE (relleno verde claro, texto verde oscuro): cuando el valor sea ≥ 85%
- AMARILLO (relleno amarillo, texto naranja oscuro): cuando el valor esté entre 75% y 84%
- ROJO (relleno rojo claro, texto rojo oscuro): cuando el valor sea < 75%

¿Puedes guiarme paso a paso para configurar estas tres reglas de formato 
condicional en Excel? Incluye las fórmulas exactas que debo usar.
```

4. Sigue las instrucciones que Copilot te proporcione. El flujo estándar en Excel para formato condicional es:
   ```
   Seleccionar rango de celdas con valores OEE
   → Inicio → Formato Condicional → Nueva Regla
   → "Aplicar formato únicamente a las celdas que contengan"
   → Configurar condición y formato de color
   → Repetir para cada nivel (Verde, Amarillo, Rojo)
   ```

5. Aplica el mismo proceso de formato condicional para los otros 3 KPIs (Tasa de Defectos, Frecuencia de Paros, Consumo de Refacciones). Puedes usar el siguiente prompt adaptado:

```
Ahora necesito el mismo tipo de formato condicional para la Tasa de Defectos.
Los umbrales son:
- VERDE: valor < 2%
- AMARILLO: valor entre 2% y 4%  
- ROJO: valor > 4%

Dame las instrucciones específicas y las fórmulas para configurarlo en Excel.
```

6. Una vez configurado el formato condicional para todos los KPIs, crea una **leyenda visual** en una sección libre del dashboard. Puedes pedirle a Copilot:

```
Ayúdame a redactar el texto para una leyenda de colores de alerta que explique 
en 3 líneas breves qué significa cada color (Verde, Amarillo, Rojo) en el 
contexto de este dashboard de manufactura. El lenguaje debe ser claro para 
operadores de planta y para directivos.
```

7. Inserta la leyenda en el dashboard usando un cuadro de texto o celdas formateadas.

8. **Prueba el sistema de alertas:** Modifica temporalmente un valor de OEE en el dashboard (por ejemplo, cambia el OEE de L1 de 87% a 72%) y verifica que el color de la celda cambia automáticamente a ROJO. Luego restaura el valor original.

9. Guarda el archivo (`Ctrl+S`).

#### Resultado Esperado

El dashboard de OEE muestra ahora un sistema visual de semáforo completamente funcional: cada celda de KPI cambia automáticamente de color (Verde/Amarillo/Rojo) según el valor que contiene, comparado con los umbrales definidos en el Paso 1. La leyenda explica claramente el significado de cada color.

#### Verificación

- [ ] Las celdas de OEE cambian de color automáticamente al modificar los valores.
- [ ] El formato condicional está configurado para los 4 KPIs (OEE, Tasa de Defectos, Frecuencia de Paros, Consumo de Refacciones).
- [ ] La leyenda de colores está visible en el dashboard.
- [ ] Al restaurar los valores originales, los colores regresan al estado correcto.
- [ ] El archivo está guardado.

---

### Paso 3: Construcción de la Matriz de Priorización de Acciones Preventivas con Copilot Chat

**Objetivo del paso:** Utilizar Copilot Chat en copilot.microsoft.com para construir una matriz de priorización de acciones preventivas con criterios de impacto, urgencia y viabilidad, basada en el estado actual de los indicadores del dashboard.

**Duración estimada:** 12 minutos

#### Instrucciones

1. Abre un navegador web y navega a **https://copilot.microsoft.com**

2. Inicia sesión con tu **cuenta corporativa** y verifica que estás en modo **"Trabajo"** (Work). Debes ver el indicador de protección en la interfaz.

3. Antes de escribir el prompt principal, proporciona contexto a Copilot con el siguiente mensaje inicial:

```
Actúa como un consultor experto en gestión de riesgos operativos para plantas 
de manufactura. Voy a proporcionarte el estado actual de los KPIs de tres 
líneas de producción y necesito que me ayudes a construir una matriz de 
priorización de acciones preventivas.

El contexto es: planta de manufactura con 3 líneas de producción (L1, L2, L3), 
operando con indicadores de OEE, tasa de defectos, frecuencia de paros y 
consumo de refacciones.
```

4. Espera la confirmación de Copilot y luego escribe el siguiente prompt con los datos del estado actual de tu dashboard (ajusta los valores según lo que realmente muestre tu dashboard):

```
El estado actual de los KPIs es el siguiente:

LÍNEA 1 (L1):
- OEE: 78% (Alerta AMARILLA - umbral crítico: 75%)
- Tasa de defectos: 3.2% (Alerta AMARILLA)
- Frecuencia de paros: 3 paros/semana (Alerta AMARILLA)
- Consumo de refacciones: 88% del presupuesto mensual (Alerta AMARILLA)

LÍNEA 2 (L2):
- OEE: 71% (Alerta ROJA - por debajo del umbral crítico)
- Tasa de defectos: 5.1% (Alerta ROJA)
- Frecuencia de paros: 6 paros/semana (Alerta ROJA)
- Consumo de refacciones: 97% del presupuesto mensual (Alerta ROJA)

LÍNEA 3 (L3):
- OEE: 89% (Estado VERDE - operación normal)
- Tasa de defectos: 1.8% (Estado VERDE)
- Frecuencia de paros: 1 paro/semana (Estado VERDE)
- Consumo de refacciones: 72% del presupuesto mensual (Estado VERDE)

Con base en este estado, genera una Matriz de Priorización de Acciones 
Preventivas con los siguientes criterios para cada acción recomendada:
1. Descripción de la acción preventiva
2. Línea afectada
3. KPI que mejora
4. Impacto en producción (Alto/Medio/Bajo)
5. Urgencia (Inmediata/Esta semana/Este mes)
6. Viabilidad operativa (Alta/Media/Baja)
7. Índice de prioridad (calculado como: Impacto × Urgencia)
8. Responsable sugerido (Mantenimiento/Calidad/Producción/Dirección)

Ordena las acciones de mayor a menor prioridad. Incluye mínimo 8 acciones.
```

5. Revisa la matriz generada por Copilot. Evalúa críticamente cada acción recomendada. Si alguna acción no te parece realista o aplicable, escribe un prompt de refinamiento:

```
La acción número [X] no es aplicable en nuestro contexto porque [razón]. 
¿Puedes reemplazarla por una alternativa más viable considerando que [contexto 
adicional]?
```

6. Una vez que tengas una matriz satisfactoria, pide a Copilot que la reformatee para Excel:

```
Reformatea la matriz anterior en formato de tabla con separadores de columna 
claramente definidos, lista para copiar y pegar en Excel. Usa el formato:
Prioridad | Acción | Línea | KPI | Impacto | Urgencia | Viabilidad | Responsable
```

7. Copia la tabla generada por Copilot.

8. Regresa a tu archivo Excel `Practica4_Alertas_[TuNombre].xlsx` y crea una nueva hoja llamada **"Matriz_Priorización"**.

9. Pega la tabla en la celda **A1** de la hoja "Matriz_Priorización". Ajusta el formato (anchos de columna, encabezados en negrita, bordes de tabla).

10. Aplica formato condicional a la columna "Urgencia" para resaltar en ROJO las acciones con urgencia "Inmediata", en AMARILLO las de "Esta semana" y en VERDE las de "Este mes".

11. Guarda el archivo (`Ctrl+S`).

#### Resultado Esperado

Una hoja "Matriz_Priorización" en Excel con al menos 8 acciones preventivas ordenadas por prioridad, con criterios de impacto, urgencia y viabilidad claramente definidos, y con formato condicional aplicado para facilitar la lectura visual. La matriz refleja el estado real de los KPIs del dashboard.

#### Verificación

- [ ] La hoja "Matriz_Priorización" contiene al menos 8 acciones preventivas.
- [ ] Las acciones están ordenadas de mayor a menor prioridad.
- [ ] Todas las columnas requeridas están presentes (Prioridad, Acción, Línea, KPI, Impacto, Urgencia, Viabilidad, Responsable).
- [ ] El formato condicional en la columna "Urgencia" funciona correctamente.
- [ ] Las acciones priorizadas para L2 (estado ROJO) aparecen en los primeros lugares.

---

### Paso 4: Generación del Resumen Ejecutivo de Riesgo Operativo en Word con Copilot

**Objetivo del paso:** Generar un resumen ejecutivo de riesgo operativo automatizado en Microsoft Word utilizando Copilot, que comunique de forma clara y accionable el estado actual y las proyecciones de riesgo futuro para la dirección.

**Duración estimada:** 12 minutos

#### Instrucciones

1. Abre **Microsoft Word** (versión escritorio, no Word Online).

2. Crea un nuevo documento en blanco y guárdalo inmediatamente en OneDrive con el nombre: `Practica4_Reporte_Riesgo_[TuNombre].docx`

3. Haz clic en el botón **Copilot** en la cinta de opciones de Word (aparece en la pestaña "Inicio" o "Inicio de página").

4. En el panel de Copilot de Word, escribe el siguiente prompt para generar el borrador del resumen ejecutivo:

```
Redacta un Resumen Ejecutivo de Riesgo Operativo para una planta de manufactura 
con el siguiente contexto y datos:

TÍTULO: Reporte Ejecutivo de Gestión de Riesgo Operativo — [Fecha actual]

SITUACIÓN ACTUAL:
- La planta opera 3 líneas de producción (L1, L2, L3)
- Línea 2 (L2) se encuentra en estado CRÍTICO (ROJO): OEE 71%, tasa de 
  defectos 5.1%, 6 paros no planificados esta semana
- Línea 1 (L1) se encuentra en estado de ALERTA (AMARILLO): OEE 78%, 
  tendencia descendente en las últimas 2 semanas
- Línea 3 (L3) opera en estado NORMAL (VERDE): OEE 89%

PROYECCIÓN DE RIESGO (próximas 48-72 horas):
- Sin intervención en L2: riesgo de paro total estimado en 85% de probabilidad
- Sin intervención en L1: riesgo de degradación a estado ROJO en 72 horas
- Impacto económico estimado de paro en L2: pérdida de 120 unidades/hora × 
  costo unitario de producción

ACCIONES PREVENTIVAS PRIORIZADAS (Top 3):
1. Inspección y mantenimiento correctivo urgente en L2 — Responsable: 
   Mantenimiento — Urgencia: Inmediata
2. Revisión de parámetros de calidad y ajuste de proceso en L2 — 
   Responsable: Calidad — Urgencia: Inmediata  
3. Mantenimiento preventivo programado en L1 para esta semana — 
   Responsable: Mantenimiento — Urgencia: Esta semana

El resumen debe:
- Tener máximo 1 página (400-500 palabras)
- Usar lenguaje ejecutivo claro, sin tecnicismos excesivos
- Incluir secciones: Situación Actual, Riesgos Identificados, Proyección, 
  Acciones Recomendadas y Decisión Requerida
- Terminar con una llamada a la acción clara para la dirección
- Tono: profesional, urgente pero objetivo
```

5. Revisa el borrador generado por Copilot. Evalúa:
   - ¿El lenguaje es apropiado para una audiencia directiva?
   - ¿Las secciones están claramente diferenciadas?
   - ¿La llamada a la acción es específica y accionable?

6. Si necesitas ajustes, usa el botón **"Refinar"** o escribe un prompt de refinamiento directamente en Copilot:

```
El resumen está bien, pero necesito que:
- La sección "Decisión Requerida" sea más específica e incluya las dos 
  opciones de decisión con sus implicaciones
- El tono sea más urgente en la descripción del riesgo de L2
- Agregues una línea de indicadores clave en formato visual (tabla pequeña)
  al inicio del documento
```

7. Una vez satisfecho con el contenido, aplica el siguiente formato manual al documento:
   - Título principal en **negrita**, tamaño 16, color azul corporativo
   - Encabezados de sección en **negrita**, tamaño 12
   - Texto normal en tamaño 11, fuente Calibri o Arial
   - Inserta una tabla de "Indicadores de Semáforo" al inicio con los 4 KPIs de las 3 líneas y sus colores de estado (puedes usar sombreado de celda en Word)

8. Agrega un encabezado al documento con: `CONFIDENCIAL — USO INTERNO — [Nombre de la Planta]`

9. Guarda el documento (`Ctrl+S`).

#### Resultado Esperado

Un documento Word profesional de 1 página que contiene un resumen ejecutivo de riesgo operativo completo, con tabla de indicadores de semáforo, análisis de situación actual, proyección de riesgo, acciones preventivas priorizadas y una llamada a la acción clara para la dirección. El documento es generado en menos de 5 minutos con asistencia de Copilot.

#### Verificación

- [ ] El documento tiene máximo 1 página de contenido sustantivo.
- [ ] Contiene todas las secciones requeridas: Situación Actual, Riesgos, Proyección, Acciones, Decisión Requerida.
- [ ] La tabla de indicadores de semáforo está presente y es visualmente clara.
- [ ] El lenguaje es ejecutivo y apropiado para audiencia directiva.
- [ ] El documento está guardado en OneDrive.

---

### Paso 5: Simulación de Escenario de Riesgo Emergente — Reto de 15 Minutos

**Objetivo del paso:** Aplicar de forma integrada todas las herramientas configuradas en los pasos anteriores para responder a un escenario de riesgo emergente simulado, generando un reporte ejecutivo completo en menos de 15 minutos. Este paso evalúa la capacidad del participante para operar bajo presión con Copilot como aliado.

**Duración estimada:** 15 minutos

#### Instrucciones

> 🚨 **ESCENARIO DE RIESGO EMERGENTE — SIMULACIÓN**
>
> Son las 06:45 del turno matutino. El supervisor de planta te notifica que durante la noche ocurrieron los siguientes eventos en la planta:
> - **L2:** Paro no planificado de 3.5 horas por falla en motor principal del ensamble. OEE cayó a **58%**. Se consumieron refacciones de emergencia por valor del **110% del presupuesto mensual**.
> - **L1:** La tasa de defectos subió a **4.8%** (ahora en ROJO). Se detectaron 47 unidades no conformes en el último lote.
> - **L3:** Continúa en estado VERDE, OEE 91%.
> - El director de operaciones llegará a planta en **45 minutos** y necesita un reporte ejecutivo de la situación.
>
> **Tu misión:** Actualizar el sistema de alertas, actualizar la matriz de priorización y generar el reporte ejecutivo en 15 minutos.

**Parte A — Actualizar el Dashboard de Alertas (3 minutos)**

1. Abre `Practica4_Alertas_[TuNombre].xlsx`
2. Actualiza los valores del dashboard con los nuevos datos del escenario:
   - L2: OEE = 58%, Consumo Refacciones = 110%
   - L1: Tasa de Defectos = 4.8%
3. Verifica que el formato condicional se actualiza automáticamente y muestra el estado correcto (L1 y L2 en ROJO).

**Parte B — Actualizar la Matriz de Priorización (5 minutos)**

4. Ve a Copilot Chat (https://copilot.microsoft.com) y escribe:

```
ACTUALIZACIÓN URGENTE DE ESCENARIO:

Los datos han cambiado. Actualiza la matriz de priorización con la siguiente 
nueva situación:

L2 (CRÍTICO SEVERO): OEE cayó a 58% tras paro de 3.5 horas. Consumo de 
refacciones al 110% del presupuesto. Motor principal reemplazado pero requiere 
verificación de alineación y calibración.

L1 (AHORA EN ROJO): Tasa de defectos subió a 4.8%. Se detectaron 47 unidades 
no conformes. Posible causa: desviación en parámetro de temperatura del proceso.

L3: Sin cambios, OEE 91%, estado VERDE.

El director de operaciones llega en 45 minutos. Dame las TOP 5 acciones 
inmediatas ordenadas por prioridad con responsable, tiempo estimado de 
ejecución y recursos necesarios. Sé específico y accionable.
```

5. Copia las 5 acciones prioritarias y actualiza la hoja "Matriz_Priorización" en Excel.

**Parte C — Generar el Reporte Ejecutivo Actualizado (7 minutos)**

6. Abre `Practica4_Reporte_Riesgo_[TuNombre].docx` en Word.

7. Posiciona el cursor al inicio del documento y usa Copilot en Word con el siguiente prompt:

```
Reemplaza el contenido actual con una versión actualizada del reporte 
ejecutivo de riesgo operativo con los siguientes cambios críticos:

NUEVOS DATOS:
- L2: OEE cayó a 58% (paro de 3.5 horas por falla en motor principal)
  Consumo de refacciones: 110% del presupuesto mensual (excedido)
- L1: Tasa de defectos: 4.8% (estado ROJO), 47 unidades no conformes
- L3: Sin cambios, estado VERDE, OEE 91%

El reporte debe:
- Reflejar la gravedad aumentada de la situación
- Incluir las 5 acciones inmediatas con responsable y tiempo de ejecución
- Agregar una sección de "Impacto Económico Estimado" (usa estimaciones 
  razonables para una planta de manufactura mediana)
- Terminar con las decisiones específicas que el director debe tomar hoy
- Mantener el formato de 1 página, lenguaje ejecutivo
```

8. Revisa el documento actualizado. Ajusta cualquier detalle que requiera corrección.

9. Guarda ambos archivos (Excel y Word).

10. **Reflexión final (2 minutos):** Abre Copilot Chat y escribe:

```
Acabas de ayudarme a generar un reporte ejecutivo de riesgo operativo en 
menos de 15 minutos en respuesta a un escenario de emergencia en planta.

¿Qué elementos de este proceso de gestión anticipada con Copilot son los 
más valiosos para un equipo de manufactura? ¿Qué limitaciones debo 
considerar al usar Copilot en situaciones de riesgo real? Dame 3 fortalezas 
y 2 limitaciones importantes.
```

11. Lee y reflexiona sobre la respuesta. Esta perspectiva crítica es fundamental para usar Copilot de manera responsable en entornos industriales reales.

#### Resultado Esperado

Al finalizar los 15 minutos del reto, el participante tiene:
- Dashboard actualizado con formato condicional reflejando el nuevo estado de emergencia (L1 y L2 en ROJO).
- Matriz de priorización actualizada con las 5 acciones inmediatas.
- Reporte ejecutivo Word actualizado, listo para presentar al director de operaciones.
- Comprensión crítica de las fortalezas y limitaciones de Copilot en situaciones de riesgo real.

#### Verificación

- [ ] El dashboard muestra L1 y L2 en ROJO con los nuevos valores del escenario.
- [ ] La matriz de priorización contiene las 5 acciones inmediatas con responsable y tiempo.
- [ ] El reporte Word refleja la situación actualizada con sección de impacto económico.
- [ ] El reporte fue completado en ≤15 minutos (el instructor puede verificar la marca de tiempo de guardado).
- [ ] El participante puede articular al menos 2 limitaciones del uso de Copilot en situaciones de riesgo real.

---

## Validación y Pruebas

Al finalizar todos los pasos del laboratorio, realiza la siguiente validación integral para confirmar que el sistema de gestión anticipada está funcionando correctamente.

### Lista de Verificación Final

| Componente | Criterio de éxito | Estado |
|---|---|---|
| Hoja "Umbrales_Alertas" | Tabla completa con 4 KPIs × 3 líneas × 3 niveles de umbral | ☐ |
| Formato condicional en Dashboard | Cambio automático de color al modificar valores de KPIs | ☐ |
| Leyenda de colores | Visible y comprensible en el dashboard | ☐ |
| Hoja "Matriz_Priorización" | ≥8 acciones ordenadas con todos los criterios requeridos | ☐ |
| Reporte Word — versión inicial | 1 página, 5 secciones, tabla de semáforo, llamada a la acción | ☐ |
| Reporte Word — versión escenario | Actualizado con nuevos datos, impacto económico, 5 acciones | ☐ |
| Tiempo del reto | Reto de 15 minutos completado | ☐ |

### Prueba Funcional del Sistema de Alertas

Ejecuta la siguiente prueba para confirmar que el sistema de alertas funciona de extremo a extremo:

```
PRUEBA DE EXTREMO A EXTREMO:

1. En el Dashboard_OEE, cambia el OEE de L3 de 89% a 68%
   → Resultado esperado: celda cambia a ROJO inmediatamente

2. Cambia el OEE de L3 a 80%
   → Resultado esperado: celda cambia a AMARILLO

3. Restaura el OEE de L3 a 89%
   → Resultado esperado: celda regresa a VERDE

4. Verifica que los cambios de color son instantáneos (sin necesidad de 
   guardar o recalcular manualmente)

Si los tres cambios producen el color correcto, el sistema de alertas 
está configurado correctamente.
```

---

## Solución de Problemas

### Problema 1: El botón de Copilot no aparece en la cinta de Excel o Word

**Síntoma:** Al abrir Excel o Word, el botón "Copilot" no es visible en la cinta de opciones (ribbon), incluso después de buscar en todas las pestañas.

**Causa probable:** La licencia de Microsoft 365 Copilot puede no estar correctamente asignada al usuario, la aplicación puede no estar actualizada a la versión requerida (v2308+), o el complemento de Copilot puede estar deshabilitado en las opciones de la aplicación.

**Solución paso a paso:**
```
PASO 1 — Verificar versión de la aplicación:
   Excel/Word → Archivo → Cuenta → Acerca de Excel/Word
   Verificar que el número de versión sea 2308 o superior
   Si no: Archivo → Cuenta → Opciones de actualización → Actualizar ahora

PASO 2 — Verificar licencia de Copilot:
   Navegar a: https://portal.office.com
   Hacer clic en el ícono de usuario (esquina superior derecha)
   → Ver cuenta → Suscripciones
   Verificar que "Microsoft 365 Copilot" aparece en la lista de licencias activas
   Si no aparece: contactar al administrador de TI corporativo

PASO 3 — Habilitar el complemento manualmente:
   Excel → Archivo → Opciones → Complementos
   En "Administrar" seleccionar "Complementos COM" → Ir
   Buscar "Microsoft Copilot" en la lista
   Marcar la casilla si está desmarcada → Aceptar
   Reiniciar Excel/Word

PASO 4 — Si el problema persiste:
   Cerrar todas las aplicaciones de Microsoft 365
   Abrir el Panel de Control → Programas → Microsoft 365 Apps
   Seleccionar "Reparación en línea" (Online Repair)
   Esperar 10-15 minutos y reiniciar el equipo
```

---

### Problema 2: El formato condicional no cambia de color al actualizar los valores del dashboard

**Síntoma:** Se modifican los valores de OEE u otros KPIs en el dashboard, pero las celdas no cambian de color. El formato condicional parece estar configurado pero no responde a los cambios de valor.

**Causa probable:** Las reglas de formato condicional fueron configuradas con referencias de celda incorrectas (por ejemplo, referencias absolutas que apuntan a celdas fijas en lugar de las celdas que contienen los valores actuales), o las reglas están en conflicto entre sí por el orden de aplicación, o el cálculo automático de la hoja está desactivado.

**Solución paso a paso:**
```
PASO 1 — Verificar que el cálculo automático está activo:
   Excel → Fórmulas → Opciones de cálculo → Automático
   Si estaba en "Manual": cambiar a "Automático" y presionar F9 para 
   recalcular inmediatamente

PASO 2 — Revisar las reglas de formato condicional configuradas:
   Seleccionar las celdas problemáticas
   → Inicio → Formato Condicional → Administrar reglas
   Verificar que las reglas muestran el rango correcto en "Se aplica a"
   Verificar que los valores de umbral en las condiciones son correctos
   (ej: para OEE, la condición ROJA debe ser "<0.75" si los valores 
   están en formato decimal, o "<75" si están en porcentaje entero)

PASO 3 — Corregir referencias incorrectas:
   Si las reglas usan fórmulas, verificar que las referencias sean 
   relativas (sin $ innecesarios) para que apliquen a cada celda 
   individualmente
   Ejemplo correcto: =C5<0.75 (para la celda C5)
   Ejemplo incorrecto: =$C$5<0.75 (apunta siempre a C5 aunque se 
   aplique a otras celdas)

PASO 4 — Eliminar y reconfigurar si el problema persiste:
   Inicio → Formato Condicional → Borrar reglas → 
   "Borrar reglas de las celdas seleccionadas"
   Volver a configurar las reglas desde cero siguiendo las 
   instrucciones del Paso 2 del laboratorio
   Usar Copilot nuevamente para obtener las fórmulas exactas si 
   es necesario
```

---

## Limpieza del Entorno

Al finalizar la práctica, realiza las siguientes acciones de limpieza y organización para dejar el entorno listo para la siguiente práctica:

### Organización de Archivos en OneDrive

```
1. Verificar que los siguientes archivos están guardados en OneDrive:
   ✅ Practica4_Alertas_[TuNombre].xlsx
      (con hojas: Dashboard_OEE, Umbrales_Alertas, Matriz_Priorización)
   ✅ Practica4_Reporte_Riesgo_[TuNombre].docx
      (versión final con escenario de emergencia)

2. Crear una carpeta en OneDrive llamada "Practica4_Entregables" y 
   mover ambos archivos a esa carpeta

3. Compartir la carpeta con el instructor (si así lo indica):
   OneDrive → Clic derecho en carpeta → Compartir → 
   Ingresar correo del instructor → Puede ver → Enviar
```

### Cierre de Sesiones

```
1. Cerrar la sesión de Copilot Chat en el navegador:
   copilot.microsoft.com → Ícono de usuario → Cerrar sesión
   (Esto asegura que el historial de conversación no quede expuesto)

2. Cerrar Excel y Word guardando todos los cambios pendientes

3. Si se abrieron pestañas adicionales del navegador durante la práctica,
   cerrarlas para liberar memoria
```

### Verificación de Entregables para la Práctica 5

```
La Práctica 5 utilizará los archivos de esta práctica. Antes de cerrar, 
verifica que:

✅ El archivo Excel contiene datos actualizados con el escenario de 
   emergencia (OEE L2 = 58%, Tasa Defectos L1 = 4.8%)
   
✅ La hoja "Matriz_Priorización" contiene las 5 acciones del escenario 
   de emergencia (estas serán la base del plan de acción en la Práctica 5)
   
✅ El reporte Word está en su versión final (post-escenario de emergencia)

Si alguno de estos archivos no está completo, solicita al instructor 
el archivo de respaldo correspondiente: 
"Practica4_Completado_Respaldo.xlsx" y "Practica4_Reporte_Respaldo.docx"
```

---

## Resumen

### Logros de la Práctica

En esta práctica completaste la transición conceptual y técnica del enfoque reactivo al enfoque preventivo y predictivo en la gestión de planta. Los logros concretos incluyen:

| Competencia desarrollada | Herramienta utilizada | Entregable generado |
|---|---|---|
| Definición de umbrales críticos con IA | Copilot en Excel | Hoja "Umbrales_Alertas" |
| Configuración de alertas visuales automáticas | Excel + Copilot | Dashboard con semáforo dinámico |
| Priorización de acciones preventivas | Copilot Chat | Hoja "Matriz_Priorización" |
| Generación de reporte ejecutivo de riesgo | Copilot en Word | Documento ejecutivo de 1 página |
| Respuesta a escenario de emergencia con IA | Copilot integrado | Reporte actualizado en <15 min |

### Conceptos Clave Reforzados

- **Gestión anticipada vs. gestión reactiva:** La diferencia operativa entre "explicar el pasado" (reportes post-mortem) y "gestionar el riesgo futuro" (alertas tempranas + proyecciones) se vuelve tangible cuando se tiene un sistema configurado y funcionando.

- **Copilot como intérprete inteligente:** Copilot no genera datos nuevos; conecta, sintetiza y comunica la información existente de forma ágil. Su valor reside en la velocidad de síntesis y en la calidad del prompt que lo guía.

- **Evaluación crítica de las respuestas de Copilot:** Las respuestas de Copilot son generativas y referenciales. La validación humana es siempre necesaria antes de actuar sobre las recomendaciones, especialmente en contextos de riesgo operativo.

- **Formato condicional como sistema de alerta pasiva:** Una vez configurado correctamente, el formato condicional funciona sin intervención humana constante, alertando automáticamente cuando los valores cruzan los umbrales definidos.

### Conexión con el Siguiente Laboratorio

La **Práctica 5** utilizará la Matriz de Priorización y el Reporte Ejecutivo generados en esta práctica como insumos para construir un **Plan de Acción Preventivo detallado**, donde Copilot asistirá en la asignación de recursos, la estimación de tiempos y la generación de instrucciones de trabajo para el equipo de mantenimiento.

### Recursos Adicionales

| Recurso | Descripción | Enlace |
|---|---|---|
| Microsoft Learn — Copilot en Excel | Documentación oficial de Copilot en Excel | https://learn.microsoft.com/es-es/copilot/microsoft-365/use-copilot-in-excel |
| Microsoft Learn — Copilot en Word | Guía de uso de Copilot en Word | https://learn.microsoft.com/es-es/copilot/microsoft-365/use-copilot-in-word |
| Formato Condicional en Excel | Tutorial completo de Microsoft Support | https://support.microsoft.com/es-es/office/usar-formato-condicional |
| Gestión de Riesgos en Manufactura | Plant Engineering — Predictive Maintenance | https://www.plantengineering.com/articles/predictive-maintenance-strategies/ |
| Microsoft 365 Copilot — Manufactura | Casos de uso industriales | https://www.microsoft.com/en-us/industry/manufacturing/microsoft-cloud-for-manufacturing |

---

> 💡 **Reflexión final del instructor:** Esta práctica marca el punto de inflexión en el curso. Los participantes que completan el reto de 15 minutos con éxito han internalizado no solo el uso técnico de Copilot, sino el cambio de mentalidad que define la manufactura avanzada: anticipar es más valioso que reaccionar. Enfatiza en el cierre que la velocidad lograda con Copilot no reemplaza el juicio experto del equipo de planta — lo potencia.
