# Configuración de alertas tempranas y resúmenes ejecutivos. Cómo pasar de "explicar el pasado" a "gestionar el riesgo futuro". Priorización de acciones preventivas.

## 1. Metadatos del Laboratorio

| Atributo | Detalle |
| :--- | :--- |
| **Duración** | $60$ minutos (Densidad Estratégica y Prospectiva) |
| **Complejidad** | Intermedia |
| **Audiencia** | Superintendentes de Planta, Jefes de Operaciones, Directores de Confiabilidad, Líderes de Seguridad Operacional y Analistas de Riesgos |
| **Tecnologías** | Microsoft Copilot Chat (M365), Copilot Image Generator (DALL-E), Microsoft Excel y Microsoft Word |
| **Enfoque** | Transición del análisis reactivo ("explicar el pasado") al análisis proactivo ("gestionar el riesgo futuro"). Diseño de reglas de negocio para alertas tempranas, automatización de resúmenes ejecutivos de riesgos y generación visual de diagramas de contención. |

---

## 2. Descripción Corta

Este laboratorio final de $90$ minutos capacita a los líderes industriales en el uso de Microsoft Copilot para migrar de una cultura de diagnóstico reactivo a una de anticipación operativa y mitigación del riesgo futuro. Los estudiantes aprenderán a estructurar lógicas de **Alertas Tempranas (Early Warning Systems)** en **Microsoft Excel** basadas en umbrales predictivos de degradación. Posteriormente, utilizarán Copilot en **Microsoft Word** para redactar resúmenes ejecutivos de riesgos críticos para la alta dirección. Como elemento innovador, interactuarán con el motor de generación de imágenes de Copilot para crear infografías y diagramas conceptuales de los flujos de contención ante alertas, asegurando una comunicación clara, visual y unificada en toda la organización.

---

## 3. Objetivos del Laboratorio

Al finalizar este laboratorio, el estudiante será capaz de:
* **Diseñar un sistema lógico de alertas tempranas** en Excel definiendo umbrales predictivos (Pre-alerta, Alerta, Emergencia) asistido por IA.
* **Migrar del enfoque reactivo al proactivo** mediante la creación de matrices de priorización de acciones preventivas basadas en la severidad del riesgo latente.
* **Redactar resúmenes ejecutivos predictivos en Word** que traduzcan señales débiles de datos en escenarios de riesgo financiero y operativo.
* **Interactuar con Copilot para generar imágenes y diagramas** conceptuales que ilustren visualmente los protocolos de respuesta ante alarmas de procesos.
* **Automatizar la toma de decisiones críticas** mediante la estructuración de árboles de decisión claros para los operadores en el piso de planta.

---

## 4. Prerrequisitos

* Cuenta activa de **Microsoft 365** con acceso a **Copilot Chat** y capacidades de generación de imágenes habilitadas.
* Aplicación de **Microsoft Excel** abierta con un libro en blanco guardado como `Gestion_Anticipada_Alertas.xlsx`.
* Aplicación de **Microsoft Word** abierta con un documento en blanco guardado como `Plan_Gestion_Riesgo_Futuro.docx`.

---

## 5. Procedimiento Paso a Paso (Modelado Prospectivo y Comunicación Visual)

### Fase A: Matriz de Alertas Tempranas y Umbrales de Degradación (Excel)

Para gestionar el futuro, primero debemos definir qué variables operativas actúan como "señales débiles" de que una falla catastrófica se está gestando en los activos críticos de la planta cerámica (Prensas, Atomizadores, Hornos).

1. En su libro de Excel, nombre la primera hoja como `1. Configuración_Alertas`.
2. Vaya al chat de **Copilot** e introduzca el siguiente prompt avanzado de diseño prospectivo:

```
Actúa como un Especialista Senior en Sistemas de Alertas Tempranas y Confiabilidad Operacional. Necesito diseñar una estructura de datos para Excel que establezca los umbrales de tolerancia de variables críticas antes de que ocurra una falla en la planta.

Por favor, devuélveme una tabla limpia diseñada para Excel con 4 registros realistas que definan los parámetros de control predictivo para:
1. Temperatura de cojinetes del extractor de gases del Horno.
2. Nivel de vibración global (mm/s) en los rodamientos del Atomizador.
3. Caída de presión ($\Delta P$) en los filtros de mangas de la línea de molienda.
4. Temperatura del aceite hidráulico en el grupo motriz de la Prensa.

La tabla debe incluir exactamente las siguientes columnas:
`| Variable de Proceso | Activo Asociado | Valor Operativo Nominal | Umbral Pre-Alerta (Verde a Amarillo) | Umbral Alerta Crítica (Amarillo a Rojo) | Acción Preventiva Automatizada Inmediata |`

Asegúrate de que las acciones preventivas propongan tareas proactivas (ej: "Reducir velocidad nominal un $10\%$ y programar termografía en el siguiente cambio de turno" o "Activar sistema secundario de enfriamiento y verificar viscosidad").
```

3. Copie la tabla generada por Copilot (`Ctrl+C`) y péguela (`Ctrl+V`) en la hoja `1. Configuración_Alertas` a partir de la celda `A1`.

---

### Fase B: Matriz de Priorización de Riesgos Futuros (Excel)

Pasaremos de explicar por qué falló un equipo a calcular la probabilidad de que falle en los próximos 15 días, permitiendo a los planificadores priorizar las órdenes de trabajo preventivas según el nivel de riesgo financiero expuesto.

1. En su libro de Excel, cree una segunda hoja llamada `2. Priorización_Preventiva`.
2. Vaya a Copilot e introduzca el siguiente prompt enfocado en la gestión del riesgo futuro:

```
Actúa como un Gestor de Riesgos Industriales y Asset Manager. Necesito crear una matriz en Excel que evalúe y priorice las acciones preventivas de la planta para las próximas dos semanas basándome en el concepto de "Gestión del Riesgo Futuro".

Por favor, devuélveme una tabla para Excel estructurada con las siguientes columnas exactas:
`| Activo bajo Monitoreo | Síntoma / Alerta Detectada | Probabilidad de Falla en 15 Días (Porcentaje %) | Costo Estimado del Impacto si Falla ($ USD) | Valor del Riesgo Expuesto (Fórmula: Probabilidad * Costo) | Prioridad de Intervención (Crítica / Alta / Media) | Ventana Máxima de Acción Preventiva (Horas) |`

Desarrolla 4 escenarios realistas para la industria cerámica donde un activo en estado de Pre-Alerta tenga un alto valor de riesgo expuesto debido al costo de su parada, obligando a que su prioridad sea más alta que la de un equipo que ya está fallando pero cuyo impacto económico es bajo.
```

3. Seleccione la matriz de priorización prospectiva generada por Copilot, cópiela y péguela en la hoja `2. Priorización_Preventiva` en la celda `A1`.

---

### Fase C: Interacción Práctica – Generación de Imágenes de Protocolos con Copilot

La comunicación visual en el piso de planta es vital. Los operadores necesitan entender de un vistazo qué hacer cuando una luz amarilla o roja de pre-alerta se enciende en las pantallas de control. Interactuaremos con el motor gráfico de Copilot para diseñar este concepto visual.

1. En el mismo chat de Copilot, ingrese el siguiente prompt detallado para activar la generación de imágenes (DALL-E):

```
Crea un diagrama de estilo infografía industrial o una ilustración conceptual que represente un "Protocolo de Alerta Temprana de 3 Etapas" para el piso de una planta de fabricación cerámica.

La imagen debe mostrar claramente tres fases secuenciales o apiladas:

Etapa Verde/Amarilla (Pre-Alerta): Muestra el icono de un panel de control digital parpadeando en amarillo, con un operador humano revisando una tableta o dispositivo inteligente (mantenimiento predictivo).

Etapa Amarilla/Rojo (Alerta Crítica): Muestra a un técnico de mantenimiento con herramientas corriendo hacia una maquinaria de prensa hidráulica pesada que tiene una luz de advertencia ámbar encendida.

Etapa de Acción y Mitigación: Muestra una flecha limpia de diagrama de flujo que apunta hacia un símbolo de "Escudo OEE" o una marca de verificación verde, representando el riesgo evitado y la producción protegida.

El estilo debe ser moderno, profesional, con un diseño de seguridad industrial corporativo, símbolos claros, sin detalles caóticos y con una disposición técnica limpia y brillante adecuada para una guía de capacitación.
```

2. Analice la imagen generada por Copilot. 
3. **Instrucciones para guardar:** Haga clic en la imagen dentro del chat, seleccione la opción **Descargar** o **Copiar**, y guárdela localmente con el nombre `Protocolo_Visual_Alertas.png`. Esta imagen será utilizada en la documentación de la Fase D.

---

### Fase D: Redacción del Resumen Ejecutivo de Riesgos y Directrices Directivas (Word)

Con los datos prospectivos de Excel y el soporte visual generado, estructuraremos el informe formal para el comité de gerencia que justifica cambiar el enfoque del mantenimiento calendario a la gestión del riesgo.

1. Abra su archivo de **Word** (`Plan_Gestion_Riesgo_Futuro.docx`) y configure el título principal: `# Plan de Gestión Anticipada: Transformación de la Toma de Decisiones Basada en Riesgo Futuro Operacional`.
2. Introduzca el siguiente prompt en el chat de Copilot para redactar el cuerpo del informe:

```
Actúa como un Gerente de Planta y Confiabilidad Corporativa. Necesito redactar un informe ejecutivo de alta densidad directiva para la Vicepresidencia de Operaciones que sustente la migración hacia el modelo de Gestión Anticipada diseñado en las fases previas.

Por favor, redacta el texto formal listo para mi documento de Word con la siguiente estructura analítica:
1. **Resumen Ejecutivo de Señales Débiles y Riesgo Financiero**: Un párrafo persuasivo y técnico que describa cómo la planta está utilizando el valor del riesgo expuesto (calculado en la Fase B) para intervenir los activos antes de que se destruya el valor del negocio, en lugar de redactar informes post-mortem después de los paros.
2. **Gobernanza y Protocolo Operativo ante Alertas Tempranas**: Un texto que formalice los tiempos de respuesta y las responsabilidades del personal de operaciones y mantenimiento cuando se violan los umbrales definidos en la Fase A.
3. **Justificación de la Cultura Predictiva**: Explicación de los beneficios de entrenar al personal usando herramientas visuales e infografías de flujo (como el mapa visual de control generado) para estandarizar la toma de decisiones rápidas en el piso de planta.
```

3. Copie el texto generado por Copilot y péguelo en su documento de Word bajo el título principal.
4. Inserte la imagen `Protocolo_Visual_Alertas.png` (descargada en la Fase C) en la sección correspondiente a la gobernanza del protocolo para enriquecer visualmente el material didáctico.

---

### Fase E: Reto de Aplicación Autónoma – Simulación Predictiva de Pérdida de Vacío en el Atomizador

**Instrucciones para el estudiante:** Es momento de evaluar tu capacidad de toma de decisiones directivas sin supervisión ante un escenario de riesgo inminente. El sistema de telemetría reporta una "señal débil" crítica: la bomba de vacío del Atomizador principal (Línea 2) muestra micro-caídas de presión de vacío de un $3.2\%$ cada 8 horas, y el análisis de vibraciones por ultrasonido detecta un armónico anómalo en la frecuencia de paso de álabes. Si la bomba de vacío colapsa por completo, el polvo cerámico perderá su humedad óptima ($5.5\%$), suspendiendo el prensado de toda la planta y generando un costo por lucro cesante estimado en $\$45,000$ USD por día. Mantenimiento quiere esperar al paro programado dentro de 10 días; tú debes decidir si intervienes de manera anticipada.

#### El Desafío:
Debes interactuar de forma autónoma con Copilot utilizando ingeniería de prompts avanzada para realizar dos tareas fundamentales:
1. **Modelar el Riesgo de la Crisis (Excel):** Generar una matriz de decisión predictiva que demuestre que la probabilidad acumulada de falla de la bomba en los próximos 3 días es del $78\%$, calculando el valor del riesgo expuesto frente al costo de una parada controlada de 2 horas.
2. **Generar el Diagrama de Mitigación Visual (Imagen):** Solicitar a Copilot la creación de una segunda imagen o gráfico conceptual que funcione como un *Árbol de Decisión Rápida para el Operador del Atomizador*, ilustrando el camino lógico: `Si Vibración > Umbral Crítico Y Vacío Cae -> Detención Controlada Automática -> Desvío de Barbotina al Tanque de Reserva`.

#### Pistas de Ingeniería de Prompts para el Éxito:
* **Para el Prompt Analítico:** Configura a la IA como un *Ingeniero de Confiabilidad Predictiva y Analista Financiero de Riesgos*. Pídele que te entregue una tabla con las columnas: `| Activo | Escenario de Espera (10 Días) | Escenario de Acción Anticipada (Hoy) | Probabilidad de Colapso (%) | Pérdida Financiera Proyectada ($ USD) | Decisión Recomendada |`.
* **Para el Prompt de Imagen:** Diseña un prompt descriptivo en inglés para el motor de imágenes de Copilot: `"A clean, professional flowchart diagram for an industrial decision tree. It shows two main branches: path A (Wait 10 days, leading to a red breaking gear icon and financial loss text) and path B (Immediate 2-hour controlled stop, leading to a green shield icon and optimal OEE text). Modern tech style, suitable for a manufacturing plant operating manual."`

#### Cierre del Laboratorio:
1. Copie la tabla del modelo de riesgo del atomizador. Vaya a su archivo de **Excel** (`Gestion_Anticipada_Alertas.xlsx`), cree una tercera hoja llamada `3. Reto_Decisión_Bomba` y pegue la información en la celda `A1`.
2. Descargue la imagen del árbol de decisión lógica generada por la IA, nómbrela `Arbol_Decision_Bomba.png`. Vaya al final de su archivo de **Word** (`Plan_Gestion_Riesgo_Futuro.docx`), cree un título llamado `## Anexo de Decisión Anticipada: Mitigación Proactiva Bomba de Vacío - Atomizador` y pegue la justificación de tu decisión junto a la imagen del árbol lógico.
3. Guarde y cierre todos los archivos. ¡Tu sistema integral de gobernanza analítica y gestión de riesgo futuro está completado con éxito!

---

## 6. Conceptos Clave para Recordar

* **Señales Débiles (Weak Signals):** Son pequeñas desviaciones o tendencias en las variables de los equipos (pequeños aumentos de temperatura o micro-oscilaciones de vibración) que, analizadas de forma aislada, parecen normales, pero que unidas indican la gestación de una falla catastrófica futura.
* **Valor del Riesgo Expuesto:** Es la métrica financiera clave de la gestión anticipada. Multiplicar la probabilidad matemática de falla por el costo total de la indisponibilidad permite a la gerencia de operaciones tomar decisiones de parada basadas en dólares y rentabilidad, no en corazonadas técnicas.
* **Estandarización Visual (Visual Management):** Integrar tablas de datos con diagramas visuales y árboles de decisión generados por IA acelera la velocidad de reacción del personal operativo. Disminuir el tiempo entre la detección de una alerta y la ejecución de la acción preventiva es el factor crítico para proteger el $OEE$ global de la organización.

---

## 7. Resultado Esperado

Al finalizar los $90$ minutos de la sesión práctica, el estudiante entregará un portafolio digital interdisciplinario listo para implementar en planta:

1. **Archivo `Gestion_Anticipada_Alertas.xlsx` (Excel):**
   * **Hoja 1 (`1. Configuración_Alertas`):** Matriz técnica con la lógica de variables, rangos operativos, umbrales de alerta y acciones de contención por activo.
   * **Hoja 2 (`2. Priorización_Preventiva`):** Tabla de gestión prospectiva con el cálculo de la probabilidad de falla y la priorización de órdenes preventivas basadas en el valor del riesgo expuesto en USD.
   * **Hoja 3 (`3. Reto_Decisión_Bomba`):** Matriz financiera comparativa del **Reto Autónomo** que justifica la intervención inmediata de la bomba de vacío.
2. **Archivo `Plan_Gestion_Riesgo_Futuro.docx` (Word):**
   * Un documento maestro de gobernanza operativa que detalla el nuevo modelo predictivo, los tiempos de respuesta exigidos y la justificación del cambio cultural ante el comité directivo.
   * **Sección de Gobernanza Visual:** Contiene incrustada la imagen `Protocolo_Visual_Alertas.png` generada en la Fase C.
   * **Anexo del Reto Autónomo:** La justificación estratégica de la parada del atomizador acompañada por el diagrama técnico `Arbol_Decision_Bomba.png` generado interactivamente con la IA.
