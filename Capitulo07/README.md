# Práctica 7 — Guías Paso a Paso con Copilot para Restauración Inmediata de Líneas

## 1. Metadatos del Laboratorio

| Atributo | Detalle |
| :--- | :--- |
| **Duración** | 90 minutos (Alta Densidad Operativa y Mitigación de Lucro Cesante) |
| **Complejidad** | Avanzada |
| **Audiencia** | Jefes de Planta, Planners de Mantenimiento, Jefes de Turno, Ingenieros de Automatización y Supervisores de Producción |
| **Tecnologías** | Microsoft Copilot Chat (M365), Copilot Image Generator (DALL-E), Microsoft Excel y Microsoft Word |
| **Enfoque** | Creación de Guías de Restauración Rápida (SOP de Contingencia) asistidas por IA para reducir el Tiempo Medio de Reparación ($MTTR$) ante paros críticos en la línea continua de manufactura cerámica. |

---

## 2. Descripción Corta

Este laboratorio de 90 minutos entrena a los estudiantes en el uso de Microsoft Copilot para diseñar e instrumentar "Guías de Recovery Inmediato" ante eventos de falla catastrófica que detienen la planta. Los participantes simularán un colapso mecánico/eléctrico en la cadena cinemática (Bloqueo de rodillos del horno con material compactado), estructurarán un árbol de decisiones lógicas en **Microsoft Excel** para el diagnóstico veloz en piso, redactarán un procedimiento de respuesta rápida paso a paso en **Microsoft Word** y generarán un flujograma conceptual visual con el motor de imágenes de Copilot para estandarizar la respuesta de contingencia bajo condiciones de alta presión.

---

## 3. Objetivos del Laboratorio

Al finalizar este laboratorio, el estudiante será capaz de:
* **Construir árboles de decisión para fallas críticas** en Excel asistido por Copilot, reduciendo el tiempo de diagnóstico inicial en piso de planta.
* **Redactar Guías de Recovery de Alta Velocidad** en Word con instrucciones claras de aislamiento de energía, mitigación de daños colaterales y rearranque seguro.
* **Diseñar flujos visuales de contingencia operativa** mediante prompts gráficos en Copilot para estandarizar la respuesta de los operadores en turnos nocturnos.
* **Calcular y proyectar el impacto de la reducción del MTTR** sobre el indicador OEE y el ahorro en costo de lucro cesante por minuto de paro.

---

## 4. Prerrequisitos

* Cuenta activa de **Microsoft 365** con acceso a **Copilot Chat** y generación de imágenes.
* Aplicación de **Microsoft Excel** abierta con un libro en blanco guardado como `Arbol_Decisiones_Recovery.xlsx`.
* Aplicación de **Microsoft Word** abierta con un documento en blanco guardado como `SOP_Recovery_Inmediato.docx`.

---

## 5. Procedimiento Paso a Paso (Solución de Problemas y Recovery)

### Fase A: Estructuración del Árbol de Decisiones de Diagnóstico Rápido (Excel)

Cuando una línea continua se detiene, el técnico de piso suele perder valiosos minutos buscando herramientas o adivinando el origen del problema. Utilizaremos Copilot para mapear un árbol lógico de descarte inmediato.

1. En su libro de Excel, renombre la primera hoja como `1. Arbol_Diagnostico`.
2. Vaya al chat de **Copilot** e introduzca el siguiente prompt de generación técnica:

```
Actúa como un Ingeniero de Mantenimiento y Automatización Senior. Estamos ante el peor escenario de la planta: "Bloqueo por rotura de material cerámico dentro de la zona de alta temperatura del Horno de Rodillos N°2", lo que amenaza con deformar los rodillos si la línea se queda estática a 1150°C.

Necesito que diseñes un Árbol de Decisiones de Diagnóstico Rápido en formato de tabla limpia para copiar y pegar en la celda A1 de Excel. La tabla debe tener exactamente las siguientes columnas:
| Código de Alerta | Síntoma Visible en Piso | Pregunta de Descarte / Validación | Si la respuesta es SÍ (Acción de Recovery) | Si la respuesta es NO (Siguiente Paso Lógico) | Nivel de Urgencia (Crítico/Alto) |

Incluye al menos 3 filas con lógica secuencial: 
1. Caída de torque en la transmisión principal (revisar cadena rota vs fusibles eléctricos).
2. Activación del embrague de seguridad mecánica.
3. Atascamiento físico por rotura de azulejos (activar rotación manual de emergencia).

Genera únicamente la tabla markdown estándar, sin introducciones ni textos adicionales.
```

3. Seleccione la tabla generada por Copilot en el chat, cópiela (`Ctrl+C`) y péguela (`Ctrl+V`) en la celda `A1` de la hoja `1. Arbol_Diagnostico` en Excel.

---

### Fase B: Diseño del Procedimiento Paso a Paso para Restauración Inmediata (Excel)

Identificado el camino lógico, el operador necesita una lista de verificación secuencial de "rearranque rápido" que garantice que el horno vuelva a producir m² estables en el menor tiempo posible, protegiendo los activos.

1. En su libro de Excel, cree una segunda hoja llamada `2. Secuencia_Recovery`.
2. Introduzca el siguiente prompt en el chat de Copilot para estructurar los pasos del plan de choque:

```
Actúa como un Especialista en Operaciones de Manufactura Avanzada. Con base en la falla por atascamiento del Horno N°2 de la Fase A, necesito una guía de pasos secuenciales para la evacuación del material y el rearranque seguro de la línea.

Por favor, devuélveme una tabla formateada para copiar y pegar directamente en la celda A1 de Excel con las siguientes columnas exactas:
| Paso N° | Acción Operativa de Emergencia | Herramientas / EPP Requeridos | Tiempo Máximo Estimado (Minutos) | Riesgo Asociado a Mitigar |

Asegúrate de detallar cronológicamente los pasos críticos: desde el aislamiento LOTO (Lockout/Tagout) de la transmisión, el uso de varillas de extracción de alta temperatura con trajes aluminizados, hasta la activación del motor de respaldo para evitar la flexión de los rodillos cerámicos. Calcula el tiempo acumulado para que el MTTR total no supere los 45 minutos. Entrega únicamente la tabla markdown.
```

3. Copie la tabla generada por Copilot en el chat y péguela (`Ctrl+V`) en la celda `A1` de la hoja `2. Secuencia_Recovery` en Excel.

---

### Fase C: Interacción Práctica – Diagrama Visual del Protocolo de Recovery (Copilot)

Para garantizar que el protocolo de evacuación sea comprendido al instante bajo una situación de alta presión (alarma sonora encendida), generaremos una guía visual del protocolo de emergencia de 3 pasos.

1. En el chat de Copilot, introduzca el siguiente prompt en español para activar el motor gráfico:

```
Crea un diagrama de estilo infografía industrial o una ilustración conceptual que represente un "Protocolo de Recovery de 3 Etapas" ante una parada crítica en el piso de una planta de fabricación cerámica.

La imagen debe mostrar claramente tres fases secuenciales o apiladas de izquierda a derecha:
1. **Etapa 1: Aislamiento Seguro:** Muestra un icono nítido de un candado de seguridad industrial y tarjeta de bloqueo (LOTO) sobre un panel de control con luces de advertencia.
2. **Etapa 2: Evacuación y Extracción:** Muestra la silueta de un operador técnico con traje aluminizado de protección térmica utilizando una herramienta o varilla larga para despejar una sección de rodillos industriales.
3. **Etapa 3: Rearranque Exitoso:** Muestra una gran marca de verificación verde y una flecha limpia de flujo ascendente que apunta hacia un indicador digital que marca "Línea Operativa - OEE OK".

El estilo debe ser moderno, limpio, con colores de seguridad corporativos (gris técnico, amarillo de advertencia y verde de éxito), sin detalles caóticos y óptimo para una guía de capacitación de respuesta a emergencias.
```

2. Una vez generada la imagen, haga clic en ella, seleccione **Descargar** y guárdela localmente con el nombre `Protocolo_Recovery_Horno.png`.

---

### Fase D: Redacción de la Guía Oficial de Contingencia de Planta (Word)

Traduciremos las tablas analíticas de Excel y la imagen gráfica en un Estándar de Operación de Emergencia (SOP) formal para la biblioteca técnica de la empresa.

1. Abra su archivo de **Word** (`SOP_Recovery_Inmediato.docx`) y escriba el título: `# Procedimiento Operativo Estándar de Emergencia (SOP): Recovery ante Atascamiento Crítico en Horno de Rodillos`.
2. Use el siguiente prompt en Copilot para redactar el contenido formal:

```
Actúa como un Director de Operaciones y Excelencia Operacional. Necesito redactar el texto formal para un SOP de contingencia industrial basado en los datos de recovery que estructuramos para el Horno N°2 en Excel.

Por favor, genera el texto formal estructurado exactamente en estas 3 secciones para mi documento de Word:
1. **Política de Mitigación del MTTR**: Un párrafo técnico sólido que explique la correlación directa entre el tiempo de respuesta (MTTR) ante el atascamiento del horno, el costo por minuto de paro operativo (lucro cesante de $250 USD/min) y la preservación de la vida útil de los rodillos.
2. **Protocolo Técnico de Desbloqueo de Línea**: Redacta de forma imperativa y ultra clara los pasos detallados para los equipos de mantenimiento mecánico y eléctrico durante la emergencia.
3. **Plan de Estabilización Posteriores al Rearranque**: Define los criterios de calidad que el inspector de control de procesos debe validar (como la verificación de la planeidad del azulejo y la ausencia de grietas) antes de autorizar la velocidad nominal de producción.
```

3. Copie el texto generado por Copilot y péguelo directamente en su documento de Word.
4. Inserte la imagen `Protocolo_Recovery_Horno.png` descargada en la Fase C justo debajo de la segunda sección para ilustrar visualmente las acciones del personal de piso.

---

### Fase E: Reto de Aplicación Autónoma – Recovery por Falla de Red en Clasificadora Láser

**Instrucciones para el estudiante:** La Línea de Clasificación y Empaque de Gran Formato N°1 se ha detenido por completo debido a una "Pérdida de Comunicación de Datos / Falla de Bus de Campo" entre las cámaras de inspección por visión artificial y el brazo robótico paletizador. Las cajas de cerámica se están acumulando al final de la línea, forzando a detener las etapas de esmaltado previas. El equipo eléctrico quiere cablear un bypass provisional que anularía los controles de calidad por 8 horas.

#### El Desafío:
Usa tu criterio e ingeniería de prompts de forma autónoma con Copilot para resolver la contingencia técnica:
1. **Árbol de Descarte de Redes (Excel):** Diseña un prompt para que Copilot te entregue una tabla estructurada para Excel (en una hoja nueva llamada `3. Reto_Network_Recovery`) que guíe al técnico a verificar de forma secuencial la fuente de alimentación del switch de red, la integridad del cable de fibra óptica y la dirección IP del controlador, evitando el bypass inseguro.
2. **Procedimiento de Desahogo de Línea (Word):** Pídele a la IA que redacte un protocolo rápido que explique cómo desviar las piezas cerámicas terminadas hacia una zona de almacenamiento temporal (mantenimiento de flujo degradado) mientras se restaura la red industrial, protegiendo el indicador OEE de la planta.

#### Pistas de Ingeniería de Prompts para el Éxito:
* **Para la Tabla de Descarte:** Pide las columnas de manera idéntica a la Fase A asegurando que el problema central definido sea `"Falla de Comunicación en Bus de Red Línea Clasificación 1"`.
* **Para el Prompt de Copilot:** Usa instrucciones claras en tu prompt autónomo: `"Actúa como un Especialista en Redes Industriales OT. Genera una tabla markdown de diagnóstico rápido paso a paso para descartar fallas de comunicación Profinet en una clasificadora de azulejos..."`

#### Cierre del Laboratorio:
1. Copie la tabla del reto e insértela en la hoja `3. Reto_Network_Recovery` en la celda `A1` de su archivo de Excel.
2. Guarde ambos archivos (`Arbol_Decisiones_Recovery.xlsx` y `SOP_Recovery_Inmediato.docx`). Su ecosistema para la solución de problemas complejos y restauración inmediata de líneas de producción está completamente operativo.

---

## 6. Conceptos Clave para Recordar

* **Recovery Speed (Velocidad de Recuperación):** En procesos continuos como la cerámica (donde los hornos nunca se apagan), el costo de una parada no se mide solo en mano de obra, sino en el daño estructural por calor y el lucro cesante acumulado por minuto de inactividad del OEE.
* **Lógica de Descarte Secuencial:** El diagnóstico estructurado bajo condiciones de estrés previene el error humano y la toma de decisiones desesperadas o inseguras (como los bypass a los sistemas de calidad o seguridad).
* **Flujos Degradados:** Un buen plan de recovery contempla cómo mantener operativas las etapas previas o posteriores de la línea de producción (por ejemplo, acumulando material en pulmones de stock intermedio) para que una falla local no paralice la planta entera.

---

## 7. Resultado Esperado

Al finalizar los 90 minutos del laboratorio, el estudiante consolidará los siguientes entregables integrados:

1. **Archivo `Arbol_Decisiones_Recovery.xlsx` (Excel):**
   * **Hoja 1 (`1. Arbol_Diagnostico`):** Matriz analítica para descartar fallas en la transmisión del horno a 1150°C.
   * **Hoja 2 (`2. Secuencia_Recovery`):** Cronograma de tareas operativas cronometradas para no superar un MTTR de 45 minutos.
   * **Hoja 3 (`3. Reto_Network_Recovery`):** Flujo de descarte técnico de la red OT de la clasificadora láser.
2. **Archivo `SOP_Recovery_Inmediato.docx` (Word):**
   * Procedimiento de emergencia estandarizado y listo para impresión en planta, detallando la matriz de aislamiento de energías, el plan de contingencia paso a paso e incorporando el gráfico explicativo `Protocolo_Recovery_Horno.png`.
