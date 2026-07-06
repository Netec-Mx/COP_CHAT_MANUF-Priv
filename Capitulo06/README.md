# Práctica 6 — Despliegue de "Ishikawa" y "5 Porqués" con Copilot Chat

## 1. Metadatos del Laboratorio

| Atributo | Detalle |
| :--- | :--- |
| **Duración** | 90 minutos (Enfoque de Resolución de Problemas y Diagnóstico Crítico) |
| **Complejidad** | Intermedia |
| **Audiencia** | Jefes de Planta, Supervisores de Producción, Líderes de Mantenimiento, Ingenieros de Procesos y Analistas de Calidad |
| **Tecnologías** | Microsoft Copilot Chat (M365), Copilot Image Generator (DALL-E), Microsoft Excel y Microsoft Word |
| **Enfoque** | Aplicación sistemática de metodologías de Análisis de Causa Raíz (RCA): Diagrama de Ishikawa (6M) y la técnica de los 5 Porqués estructurada con IA para eliminar fallas crónicas en la línea de producción. |

---

## 2. Descripción Corta

Este laboratorio de 90 minutos capacita a los estudiantes en el uso de Microsoft Copilot como un copiloto experto en metodologías de solución de problemas industriales. Los participantes tomarán una falla crónica real del sector cerámico (fisuras por choque térmico en la salida del horno) y guiarán a la IA para clasificar las causas potenciales bajo el esquema de las 6M (Mano de obra, Maquinaria, Métodos, Materiales, Medio ambiente y Medición) en **Microsoft Excel**. Posteriormente, desplegarán un análisis profundo de "5 Porqués" hasta aislar la causa raíz subyacente, documentarán las acciones correctivas en **Microsoft Word** y generarán una infografía visual del flujo de diagnóstico para el entrenamiento del personal técnico.

---

## 3. Objetivos del Laboratorio

Al finalizar este laboratorio, el estudiante será capaz de:
* **Estructurar un Diagrama de Ishikawa (6M)** asistido por IA, asegurando que no se omitan variables operativas ni humanas en fallas complejas.
* **Ejecutar la metodología de los 5 Porqués** de forma lógica y lineal con Copilot para evitar la confusión común entre síntomas superficiales y causas raíz físicas u organizacionales.
* **Diseñar planes de acción definitivos** usando la matriz 5W2H (Qué, Por qué, Dónde, Cuándo, Quién, Cómo, Cuánto) en entornos industriales.
* **Desarrollar prompts de imagen técnicos** para crear diagramas de flujo de diagnóstico claros y visuales para el personal operativo.

---

## 4. Prerrequisitos

* Cuenta activa de **Microsoft 365** con acceso a **Copilot Chat** y generación de imágenes.
* Aplicación de **Microsoft Excel** abierta con un libro en blanco guardado como `RCA_Ishikawa_5Porques.xlsx`.
* Aplicación de **Microsoft Word** abierta con un documento en blanco guardado como `Informe_RCA_Horno.docx`.

---

## 5. Procedimiento Paso a Paso (Análisis de Causa Raíz)

### Fase A: Despliegue del Diagrama de Ishikawa / 6M (Excel)

Cuando ocurre un defecto de calidad recurrente en el producto terminado, la planta tiende a culpar al operador o a la materia prima de inmediato. Usaremos el enfoque de las 6M para mapear todas las variables posibles de manera científica.

1. En su libro de Excel, renombre la primera hoja como `1. Ishikawa_6M`.
2. Vaya al chat de **Copilot** e introduzca el siguiente prompt de generación analítica para estructurar las causas potenciales:

```
Actúa como un Facilitador de Causa Raíz (RCA) Black Belt en Lean Six Sigma para plantas de manufactura cerámica. Estamos analizando un problema crítico: "Fisuras y roturas por estrés térmico en las piezas cerámicas a la salida del Horno de Rodillos N°2".

Necesito que diseñes una estructura de Diagrama de Ishikawa utilizando el método de las 6M. Genera una tabla limpia formateada para Microsoft Excel con las siguientes columnas exactas:
| Categoría 6M | Causa Hipotética Específica | Justificación Técnica de la Falla | Nivel de Impacto Estimado (Alto/Medio/Bajo) | Método de Validación en Piso |

Asegúrate de incluir exactamente las 6 categorías: Mano de Obra, Maquinaria (enfocado en ventiladores de enfriamiento y rodillos), Métodos (curvas de cocción), Materiales (composición del atomizado), Medición (pirómetros y termopares) y Medio Ambiente (corrientes de aire externas). Devuelve únicamente la tabla markdown lista para copiar y pegar en la celda A1 de Excel.
```

3. Seleccione la tabla generada por Copilot en el chat, cópiela (`Ctrl+C`) y péguela (`Ctrl+V`) en la celda `A1` de la hoja `1. Ishikawa_6M` en Excel.

---

### Fase B: Análisis de los 5 Porqués e Identificación de Causa Raíz (Excel)

Una vez mapeado el universo de causas, el equipo de planta descubrió en la validación que los pirómetros de la zona de enfriamiento rápido estaban descalibrados. Utilizaremos el método de los 5 Porqués para perforar el síntoma y encontrar la falla de gestión original.

1. En su libro de Excel, cree una segunda hoja llamada `2. Cinco_Porques`.
2. Introduzca el siguiente prompt en el chat de Copilot para desarrollar el árbol de fallas:

```
Actúa como un Ingeniero de Procesos Cerámicos y Especialista en Confiabilidad. Basado en el problema del Horno N°2 de la Fase A, la validación en piso confirmó que el origen del choque térmico es una "Caída brusca e incontrolada de la presión de soplado en los ventiladores de la zona de enfriamiento rápido".

Necesito que desarrolles el análisis lineal de los 5 Porqués para llegar a la Causa Raíz física, humana u organizacional. Devuélveme una tabla formateada para Excel con las siguientes columnas exactas:
| Nivel | Pregunta (Por qué ocurre) | Respuesta / Diagnóstico Técnico Realista | Tipo de Causa (Síntoma / Causa Intermedia / Causa Raíz) |

Haz que la secuencia parta del síntoma visible en las piezas cerámicas, pase por la falla del variador de frecuencia del ventilador debido al sobrecalentamiento por acumulación de polvo, y termine en una Causa Raíz Organizacional relacionada con la omisión de los filtros del tablero eléctrico en las rutinas de mantenimiento autónomo. Entrega únicamente la tabla markdown para copiar y pegar en la celda A1 de Excel.
```

3. Copie la tabla de los 5 Porqués generada por Copilot en el chat y péguela (`Ctrl+V`) en la celda `A1` de la hoja `2. Cinco_Porques` en Excel.

---

### Fase C: Interacción Práctica – Diagrama Visual del Flujo de Diagnóstico (Copilot)

Para entrenar a las tripulaciones de los tres turnos en la prevención de este problema, crearemos un diagrama visual que conecte el polvo del entorno con la rotura del material cerámico.

1. En el chat de Copilot, introduzca el siguiente prompt en español para activar el motor de imágenes:

```
Crea un diagrama de flujo técnico e industrial, de estilo infografía limpia y moderna, que ilustre visualmente una línea de diagnóstico "5 Porqués". 

El gráfico debe mostrar un camino lineal que conecte 3 íconos conceptuales clave de izquierda a derecha de forma secuencial:
1. **El Origen:** El ícono de un tablero eléctrico industrial con una señal de advertencia por acumulación de polvo cerámico.
2. **La Falla:** Una flecha limpia que apunta al ícono de un variador de frecuencia deteniéndose o sobrecalentándose.
3. **El Efecto Final:** Una flecha final que apunta hacia una pieza o azulejo cerámico con una fisura limpia y brillante, representando el producto defectuoso por choque térmico.

El diseño debe utilizar una paleta de colores de seguridad industrial (azul, gris, detalles en naranja de advertencia), con un fondo técnico limpio, líneas de flujo gruesas y corporativas, y sin textos confusos o caóticos en la imagen, ideal para un tablero de gestión visual en planta.
```

2. Una vez generada la imagen, haga clic en ella, seleccione **Descargar** y guárdela localmente como `Flujo_RCA_Horno.png`.

---

### Fase D: Redacción del Informe Técnico de Acción Preventiva (Word)

Consolidaremos la investigación en un reporte formal que autorice cambios en las rutinas de mantenimiento de la planta.

1. Abra su archivo de **Word** (`Informe_RCA_Horno.docx`) y escriba el título principal: `# Informe de Análisis de Causa Raíz (RCA): Fisuras por Estrés Térmico en Horno de Rodillos N°2`.
2. Use el siguiente prompt en Copilot para redactar el cuerpo del documento con una matriz de acción 5W2H:

```
Actúa como un Gerente de Aseguramiento de Calidad Industrial. Necesito redactar el informe técnico final para mi documento de Word basado en los hallazgos de las fases anteriores (Fisura cerámica -> Variador de ventilador -> Filtros obstruidos por polvo cerámico).

Por favor, genera el texto formal estructurado exactamente en 3 secciones:
1. **Resumen Ejecutivo del Hallazgo**: Un párrafo técnico corporativo que detalle cómo se vinculó el defecto de calidad en el producto terminado con una falla de gestión en el mantenimiento de los tableros del horno.
2. **Despliegue de la Causa Raíz (Los 5 Porqués)**: Redacta en texto fluido y argumentativo la cadena lógica de eventos que descubrió el equipo.
3. **Plan de Acción Preventivo (Matriz 5W2H)**: Diseña y entrégame una tabla en formato texto para Word con las columnas: `| Qué (Acción) | Por qué | Dónde | Cuándo | Quién | Cómo | Cuánto ($ USD) |`. Incluye acciones específicas como rediseñar el plan de mantenimiento autónomo para limpiar filtros semanalmente, instalar sellos de presión positiva en los tableros y capacitar al personal.
```

3. Copie el texto generado por Copilot y péguelo directamente en su documento de Word.
4. Inserte la imagen `Flujo_RCA_Horno.png` descargada en la Fase C justo debajo de la sección de los 5 Porqués para dar soporte visual al informe.

---

### Fase E: Reto de Aplicación Autónoma – Análisis de Causa Raíz en Defectos de Esmaltado

**Instrucciones para el estudiante:** La planta está experimentando una tasa de rechazo del 4.5% en la línea de clasificación debido al defecto conocido como "Pinhole" (ojo de pescado o burbuja estallada en la superficie esmaltada) en la Línea de Esmaltado 3. El supervisor del área insiste en que el problema es la viscosidad del esmalte provisto por el proveedor químico externo. Sin embargo, el laboratorio sospecha que el verdadero problema radica en la presión de atomización de las pistolas de aplicación de aire comprimido debido a la presencia de condensación de agua en las tuberías de aire (falla en el sistema de purga del secador de aire central).

#### El Desafío:
Aplica tus conocimientos de ingeniería de prompts para interactuar de forma autónoma con Copilot y resolver este caso:
1. **Modelar las 6M del Defecto de Esmaltado (Excel):** Solicita a Copilot una tabla estructurada para Excel que evalúe las causas potenciales del "Pinhole" bajo el enfoque de Ishikawa, forzando a la IA a contrastar la hipótesis del proveedor (Materiales) contra la hipótesis de la presión y humedad del aire (Maquinaria/Medio Ambiente).
2. **Perforar hasta la Causa Raíz Organizacional (5 Porqués):** Diseña un prompt para obligar a Copilot a desarrollar un árbol de 5 Porqués donde se demuestre que el agua en las líneas de aire no es culpa del clima, sino del vencimiento del kit de mantenimiento del secador de aire comprimido industrial que no fue presupuestado a tiempo.

#### Pistas de Ingeniería de Prompts para el Éxito:
* **Para la Tabla de Ishikawa:** Pide las columnas idénticas a la Fase A asegurando que el problema central definido sea `"Defecto de Pinhole en Línea de Esmaltado 3"`.
* **Para los 5 Porqués:** Pídele a la IA: `"Despliega la técnica de los 5 porqués en formato tabla para Excel partiendo del defecto superficial en la pieza hasta llegar a la falta de presupuesto de OPEX para repuestos críticos de servicios auxiliares."`

#### Cierre del Laboratorio:
1. Copie la tabla de Ishikawa del reto en una tercera hoja de su archivo de **Excel** llamada `3. Reto_Ishikawa_Pinhole`.
2. Copie la tabla de los 5 Porqués del reto y péguela justo debajo en la misma hoja.
3. Guarde ambos archivos (`RCA_Ishikawa_5Porques.xlsx` y `Informe_RCA_Horno.docx`). Tu portafolio de control de calidad y confiabilidad basado en procesos analíticos con IA está terminado.

---

## 6. Conceptos Clave para Recordar

* **Enfoque de las 6M:** Es una disciplina visual que impide el "sesgo de confirmación" en la planta, obligando al equipo interdisciplinario a auditar todos los frentes (Mano de obra, Maquinaria, Métodos, Materiales, Medición, Medio ambiente) antes de emitir un juicio sobre una falla.
* **Cadena Lógica de los 5 Porqués:** Una buena sesión de 5 Porqués debe leerse de abajo hacia arriba utilizando el conector lógico **"por lo tanto"** (Ej: No se cambiaron los filtros, *por lo tanto* se calentó el variador, *por lo tanto* se apagó el ventilador, *por lo tanto* hubo choque térmico). Si la lógica no se sostiene a la inversa, el análisis está roto.
* **Matriz 5W2H:** Traduce las conclusiones de un análisis técnico en un plan de acción con responsables, costos y fechas límites claras, evitando que la investigación de causa raíz quede en un documento archivado sin impacto real.

---

## 7. Resultado Esperado

Al finalizar la sesión de 90 minutos, el estudiante consolidará los siguientes entregables:

1. **Archivo `RCA_Ishikawa_5Porques.xlsx` (Excel):**
   * **Hoja 1 (`1. Ishikawa_6M`):** Matriz completa de causas probables para las fisuras térmicas del horno cerámico.
   * **Hoja 2 (`2. Cinco_Porques`):** Flujo de deducción técnica y organizacional del variador del horno.
   * **Hoja 3 (`3. Reto_Ishikawa_Pinhole`):** Diagnóstico autónomo completo del defecto de pinhole por aire comprimido húmedo.
2. **Archivo `Informe_RCA_Horno.docx` (Word):**
   * Informe gerencial firmado que contiene el resumen técnico del incidente del Horno N°2, el árbol de fallas y la matriz estructurada 5W2H con presupuesto y responsables asignados, integrando la infografía técnica `Flujo_RCA_Horno.png`.
