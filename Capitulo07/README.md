# Práctica 7 — Guías Paso a Paso con Copilot para Restauración Inmediata de Líneas

## 1. Metadatos

| Atributo | Detalle |
|---|---|
| **Duración estimada** | 90 minutos |
| **Complejidad** | Alta (Hard) |
| **Nivel Bloom** | Crear |
| **Capítulo asociado** | Capítulo 7 — Solución de Problemas y Recovery |
| **Versión de guía** | 1.0 |
| **Aplicaciones principales** | Copilot Chat · Microsoft Word · Microsoft Excel · SharePoint Online · Microsoft Teams |

---

## 2. Descripción General

Esta práctica cierra el ciclo del Capítulo 7 llevando al participante del análisis a la **creación**: construir un repositorio operativo de guías de restauración rápida basadas en 24 meses de historial de órdenes de trabajo correctivo. Usando Copilot Chat para tipificar fallas, Copilot en Word para redactar protocolos estructurados y SharePoint para organizar el repositorio, el participante experimentará el flujo completo que va desde el dato histórico hasta el documento de campo consultable en menos de 5 minutos durante un paro crítico real.

Al finalizar la práctica, el participante habrá producido un **Manual de Restauración Rápida** con al menos 5 guías de falla tipificada, publicado en SharePoint con metadatos que permiten búsqueda por equipo, tipo de falla y tiempo de restauración estimado. Este entregable es directamente transferible al entorno operativo real de la planta.

---

## 3. Objetivos de Aprendizaje

Al completar este laboratorio, el participante será capaz de:

- [ ] **Generar** guías de restauración inmediata paso a paso en Word con Copilot, basadas en históricos de mantenimiento reales, incluyendo criterios de diagnóstico, herramientas requeridas, pasos de intervención y verificación post-restauración.
- [ ] **Aplicar** estrategias de recovery ágil ante paros críticos diseñadas con Copilot, localizando y ejecutando la guía correcta en un escenario simulado de paro en menos de 5 minutos.
- [ ] **Tipificar** fallas complejas de equipos utilizando Copilot Chat para analizar el historial de OT e identificar firmas de falla recurrentes con su protocolo de atención asociado.
- [ ] **Construir** un repositorio estructurado de guías de restauración en SharePoint con metadatos generados por Copilot que faciliten la búsqueda y consulta en campo.
- [ ] **Evaluar** críticamente las respuestas generadas por Copilot, validando la coherencia técnica de cada guía antes de publicarla en el repositorio oficial.

---

## 4. Prerrequisitos

### 4.1 Conocimiento Previo

| Área | Nivel Requerido |
|---|---|
| Navegación en Microsoft 365 (Word, Excel, Teams, SharePoint) | Intermedio |
| Conceptos de mantenimiento correctivo y preventivo en manufactura | Intermedio |
| Uso básico de Copilot Chat (prompts simples, seguimiento de conversación) | Básico–Intermedio |
| Análisis de causa raíz (contenido de Práctica 6) | Completado o familiarizado |
| Interpretación de órdenes de trabajo (OT) y KPIs de mantenimiento | Básico |

### 4.2 Acceso y Archivos Requeridos

| Recurso | Estado Requerido |
|---|---|
| Cuenta corporativa Microsoft 365 con licencia **Copilot activa** | ✅ Verificado antes del lab |
| Acceso a **copilot.microsoft.com** en modo **Trabajo (Work)** | ✅ Verificado |
| Archivo `historico_OT_24meses.xlsx` cargado en OneDrive for Business | ✅ Disponible |
| Acceso al sitio SharePoint del curso (URL proporcionada por el instructor) | ✅ Verificado |
| Microsoft Word, Excel y Teams instalados (versión 2308 o posterior) | ✅ Verificado |
| Carpeta `Practica_07` creada en OneDrive personal del participante | ✅ Creada |

> **⚠️ Nota importante sobre privacidad:** Todos los datos utilizados en esta práctica son **simulados y anonimizados**. No cargue datos reales de producción o mantenimiento de su empresa en Copilot Chat sin verificar que está usando el **modo Trabajo protegido** en copilot.microsoft.com con su cuenta corporativa.

---

## 5. Entorno de Laboratorio

### 5.1 Hardware Recomendado

| Componente | Mínimo | Recomendado |
|---|---|---|
| Procesador | Intel Core i5 8va gen / AMD Ryzen 5 | Intel Core i7 / AMD Ryzen 7 |
| RAM | 8 GB | 16 GB |
| Almacenamiento libre | 5 GB | 10 GB |
| Resolución de pantalla | 1366 × 768 | 1920 × 1080 |
| Conexión a internet | 10 Mbps estable | Red corporativa cableada |

### 5.2 Software y Servicios

| Aplicación | Versión Mínima | Uso en esta Práctica |
|---|---|---|
| Microsoft Word | M365 Apps v2308+ | Redacción de guías con Copilot |
| Microsoft Excel | M365 Apps v2308+ | Revisión de historial de OT |
| Copilot Chat (Web) | copilot.microsoft.com | Tipificación de fallas y análisis |
| SharePoint Online | Incluido en M365 | Repositorio de guías |
| OneDrive for Business | Incluido en M365 | Almacenamiento de archivos de trabajo |
| Microsoft Teams | New Teams v2.0+ | Simulación de paro crítico (Paso 5) |

### 5.3 Preparación del Entorno (Antes de Comenzar)

Ejecute los siguientes pasos de configuración **antes de iniciar el Paso 1** de la práctica:

**1. Verificar acceso a Copilot en modo Trabajo:**
```
1. Abrir navegador → ir a: https://copilot.microsoft.com
2. Iniciar sesión con cuenta corporativa (@empresa.com)
3. Verificar que aparece el indicador "Trabajo" (Work) en la interfaz
4. Si aparece "Web" en lugar de "Trabajo", hacer clic en el selector y cambiar a "Trabajo"
```

**2. Verificar y abrir el archivo de historial:**
```
1. Abrir OneDrive for Business → navegar a: Documentos > Practica_07
2. Confirmar presencia del archivo: historico_OT_24meses.xlsx
3. Si el archivo no está presente, descargarlo desde el sitio SharePoint del curso:
   Ruta SharePoint: [URL del curso] > Materiales > Practica_07 > Datasets
4. Abrir el archivo en Excel (no en modo solo lectura)
```

**3. Crear estructura de carpetas en OneDrive:**
```
OneDrive > Documentos > Practica_07 >
    ├── 01_Analisis_Fallas/
    ├── 02_Guias_Restauracion/
    └── 03_Manual_Final/
```

**4. Abrir SharePoint del curso:**
```
1. Navegar al sitio SharePoint proporcionado por el instructor
2. Localizar la biblioteca de documentos: "Manual de Restauración Rápida"
3. Confirmar permisos de edición (debe poder crear carpetas y subir archivos)
```

> **⚠️ Nota de conectividad:** Esta práctica tiene alta carga de análisis en Copilot. Se recomienda usar red corporativa cableada o WiFi de alta velocidad para evitar latencia, especialmente en los Pasos 2, 3 y 4.

---

## 6. Procedimiento Paso a Paso

---

### Paso 1 — Exploración Inicial del Historial de OT en Excel con Copilot

**Objetivo:** Familiarizarse con la estructura del dataset de órdenes de trabajo y obtener una visión estadística inicial de los 24 meses de historial mediante Copilot en Excel, identificando las columnas clave y la distribución general de fallas.

---

**Instrucciones:**

1. Abra el archivo `historico_OT_24meses.xlsx` desde OneDrive en **Microsoft Excel**.

2. Revise la estructura del archivo. El dataset contiene las siguientes columnas clave:

   | Columna | Descripción |
   |---|---|
   | `ID_OT` | Identificador único de la orden de trabajo |
   | `Fecha_Apertura` | Fecha y hora de apertura de la OT |
   | `Equipo` | Nombre/código del equipo afectado |
   | `Linea` | Línea de producción (L1, L2, L3, L4) |
   | `Descripcion_Falla` | Texto libre con descripción del técnico |
   | `Causa_Raiz_Registrada` | Causa raíz documentada (puede estar vacía) |
   | `Acciones_Realizadas` | Pasos ejecutados para restaurar el equipo |
   | `Tiempo_Restauracion_Min` | Tiempo total en minutos hasta restauración |
   | `Tecnico_Responsable` | Nombre del técnico que atendió la OT |
   | `Estado_Final` | Restaurado / Pendiente / Escalado |
   | `Clasificacion_Falla` | Categoría (Mecánica / Eléctrica / Neumática / Software / Operacional) |

3. Haga clic en cualquier celda dentro del dataset. Luego, en la cinta de opciones, haga clic en el botón **Copilot** (ícono de estrella bicolor) en la pestaña **Inicio** o **Copilot** para abrir el panel de Copilot en Excel.

4. Ingrese el siguiente prompt en el panel de Copilot de Excel:

   ```
   Analiza este dataset de órdenes de trabajo correctivo. 
   Proporciona:
   1. Total de OT registradas en el período
   2. Distribución de OT por Clasificacion_Falla (tabla y porcentaje)
   3. Top 5 equipos con mayor número de OT
   4. Tiempo promedio de restauración por Clasificacion_Falla
   5. Porcentaje de OT con Causa_Raiz_Registrada vacía
   Presenta los resultados en formato de tabla.
   ```

5. Revise los resultados generados por Copilot. Tome nota de los **3 tipos de falla con mayor frecuencia** y los **2 equipos más críticos** — estos datos guiarán la selección de fallas a tipificar en el Paso 2.

6. Solicite a Copilot en Excel que cree una tabla dinámica resumen:

   ```
   Crea una tabla dinámica que muestre el conteo de OT y el tiempo 
   promedio de restauración agrupados por Linea y Clasificacion_Falla. 
   Ordena por tiempo promedio de restauración de mayor a menor.
   ```

7. **Guarde el archivo** con las adiciones (`Ctrl + S`) y asegúrese de que se sincronice en OneDrive.

---

**Resultado Esperado:**

- Tabla de distribución mostrando que las fallas de tipo **Mecánica** y **Eléctrica** representan típicamente el 60–70% del total de OT.
- Lista de top 5 equipos críticos con su conteo de OT y tiempo promedio de restauración.
- Tabla dinámica creada en una nueva hoja del libro Excel.
- Identificación clara de que entre el 30–45% de las OT tienen el campo `Causa_Raiz_Registrada` vacío (lo que justifica el uso de Copilot para inferir causas desde la descripción de falla).

**Verificación:**

- [ ] El panel de Copilot en Excel generó respuestas coherentes con el dataset.
- [ ] La tabla dinámica fue creada correctamente en una hoja nueva.
- [ ] Tiene identificados al menos 3 tipos de falla prioritarios para tipificar.
- [ ] El archivo fue guardado y sincronizado en OneDrive.

---

### Paso 2 — Tipificación de Fallas con Copilot Chat

**Objetivo:** Usar Copilot Chat en modo Trabajo para analizar en profundidad el historial de OT, identificar firmas de falla recurrentes y generar una taxonomía de fallas tipificadas con su protocolo de atención asociado.

---

**Instrucciones:**

1. Abra una nueva pestaña del navegador y navegue a **https://copilot.microsoft.com**. Confirme que está en **modo Trabajo (Work)**.

2. Inicie una nueva conversación. Copie y pegue el siguiente prompt inicial de contexto:

   ```
   Actúa como un experto en mantenimiento industrial con 15 años de 
   experiencia en manufactura. Voy a compartirte un resumen estadístico 
   de 24 meses de órdenes de trabajo correctivo de una planta de 
   manufactura con 4 líneas de producción. Tu tarea es ayudarme a 
   tipificar las fallas más frecuentes y complejas, identificando 
   patrones en las acciones de restauración exitosas.
   
   Contexto del dataset:
   - Total de OT: [insertar número del Paso 1]
   - Top 3 clasificaciones de falla: [insertar datos del Paso 1]
   - Top 5 equipos críticos: [insertar datos del Paso 1]
   - Tiempo promedio de restauración general: [insertar dato del Paso 1]
   
   ¿Entendiste el contexto? Confirma y espera mis instrucciones.
   ```

   > **Nota:** Reemplace los marcadores `[insertar...]` con los datos reales obtenidos en el Paso 1 antes de enviar el prompt.

3. Una vez que Copilot confirme el contexto, ingrese el siguiente prompt de tipificación:

   ```
   Basándote en el contexto proporcionado y en las mejores prácticas 
   de mantenimiento industrial (RCM, TPM), genera una tipificación 
   estructurada de las 6 fallas más críticas y frecuentes para una 
   planta de manufactura con estas características.
   
   Para cada falla tipificada proporciona:
   - Nombre de la falla (nomenclatura técnica estándar)
   - Equipo(s) típicamente afectado(s)
   - Firma de falla: síntomas observables antes y durante el evento
   - Causas raíz más probables (top 3)
   - Tiempo de restauración típico (minutos)
   - Nivel de criticidad: CRÍTICA / ALTA / MEDIA
   - Indicador de recurrencia: ALTA / MEDIA / BAJA
   
   Presenta en formato de tabla Markdown.
   ```

4. Revise la tabla generada por Copilot. Seleccione las **5 fallas tipificadas más relevantes** para su contexto de planta. Copie la tabla completa y péguela en un nuevo documento de Word llamado `Tipificacion_Fallas.docx`, guardado en `OneDrive > Practica_07 > 01_Analisis_Fallas`.

5. Continúe la conversación en Copilot Chat para profundizar en cada falla. Para cada una de las 5 fallas seleccionadas, use el siguiente prompt (repita para cada falla):

   ```
   Para la falla tipificada "[NOMBRE DE LA FALLA]", proporciona:
   
   1. ÁRBOL DE DIAGNÓSTICO: 5 preguntas de diagnóstico secuencial 
      que el técnico debe hacer en campo (formato de decisión Sí/No)
   2. HERRAMIENTAS REQUERIDAS: Lista completa de herramientas, 
      instrumentos de medición y EPP necesarios
   3. ACCIONES DE RESTAURACIÓN EXITOSAS: Basándote en las mejores 
      prácticas, describe los 7-10 pasos de intervención ordenados 
      cronológicamente
   4. CRITERIOS DE VERIFICACIÓN POST-RESTAURACIÓN: 3-5 pruebas 
      funcionales para confirmar que el equipo fue restaurado 
      correctamente
   5. SEÑALES DE ESCALAMIENTO: Cuándo el técnico debe escalar la 
      intervención a nivel superior o a proveedor especializado
   
   Usa lenguaje técnico preciso pero comprensible para un técnico 
   de mantenimiento de nivel intermedio.
   ```

6. Para cada falla, copie la respuesta completa de Copilot en el documento `Tipificacion_Fallas.docx`, creando una sección separada por falla.

7. **Guarde y cierre** el documento `Tipificacion_Fallas.docx`.

---

**Resultado Esperado:**

- Tabla de tipificación con 6 fallas estructuradas incluyendo todos los atributos solicitados.
- Para cada una de las 5 fallas seleccionadas: árbol de diagnóstico, lista de herramientas, pasos de restauración y criterios de verificación.
- Documento `Tipificacion_Fallas.docx` completo y guardado en OneDrive.

**Verificación:**

- [ ] Copilot Chat respondió en modo Trabajo (no en modo Web).
- [ ] La tabla de tipificación contiene al menos 5 fallas con todos los atributos.
- [ ] Cada falla tiene árbol de diagnóstico, herramientas, pasos de restauración y criterios de verificación.
- [ ] El documento `Tipificacion_Fallas.docx` fue guardado correctamente en OneDrive.
- [ ] Las respuestas de Copilot fueron revisadas críticamente — identifique al menos 1 elemento que requirió ajuste manual por parte suya.

---

### Paso 3 — Creación de Guías de Restauración en Word con Copilot

**Objetivo:** Usar Copilot en Microsoft Word para transformar la tipificación de fallas del Paso 2 en guías de restauración inmediata con formato estandarizado, listas para uso en campo por el personal técnico y operativo.

---

**Instrucciones:**

1. Abra **Microsoft Word** y cree un nuevo documento en blanco. Guárdelo inmediatamente como `Guia_Restauracion_[NOMBRE_FALLA_01].docx` en `OneDrive > Practica_07 > 02_Guias_Restauracion`.

2. Con el documento abierto, haga clic en el ícono de **Copilot** en la cinta de opciones (pestaña **Inicio** → **Copilot**) para abrir el panel de Copilot en Word.

3. En el panel de Copilot en Word, ingrese el siguiente prompt para generar la estructura base de la primera guía:

   ```
   Genera una Guía de Restauración Inmediata para la siguiente 
   falla tipificada en una planta de manufactura industrial.
   
   FALLA: [Nombre de la primera falla del Paso 2]
   EQUIPO AFECTADO: [Equipo del Paso 2]
   TIEMPO TÍPICO DE RESTAURACIÓN: [Tiempo del Paso 2]
   NIVEL DE CRITICIDAD: [Criticidad del Paso 2]
   
   La guía debe seguir EXACTAMENTE esta estructura:
   
   # GUÍA DE RESTAURACIÓN INMEDIATA
   ## [Nombre de la Falla] — Código: [Asignar código GR-XX]
   
   ### INFORMACIÓN GENERAL
   - Equipo afectado, línea, criticidad, tiempo estimado de restauración
   - Responsable de ejecución (nivel técnico requerido)
   - Fecha de última revisión
   
   ### ⚠️ ADVERTENCIAS DE SEGURIDAD
   - Mínimo 3 advertencias de seguridad específicas para esta falla
   
   ### 🔍 DIAGNÓSTICO RÁPIDO (5 minutos máximo)
   - Árbol de diagnóstico con preguntas Sí/No
   - Síntomas que confirman esta falla vs. síntomas que indican 
     otra causa
   
   ### 🛠️ HERRAMIENTAS Y MATERIALES REQUERIDOS
   - Lista de herramientas, instrumentos y refacciones típicas
   - EPP obligatorio
   
   ### 📋 PASOS DE RESTAURACIÓN
   - Numerados del 1 al N con descripción detallada de cada paso
   - Incluir tiempo estimado por paso
   - Marcar pasos CRÍTICOS con ⚡
   
   ### ✅ VERIFICACIÓN POST-RESTAURACIÓN
   - Pruebas funcionales a ejecutar antes de liberar el equipo
   - Criterios de aceptación para cada prueba
   
   ### 🚨 CRITERIOS DE ESCALAMIENTO
   - Condiciones que requieren escalar la intervención
   
   ### 📝 REGISTRO DE OT
   - Campos a completar en el sistema de OT después de la restauración
   
   Usa íconos y formato visual que facilite la lectura rápida 
   en campo. Lenguaje claro y directo.
   ```

4. Revise el documento generado por Copilot. Realice los siguientes ajustes manuales:
   - Verifique que las advertencias de seguridad sean técnicamente correctas para el equipo específico.
   - Ajuste los tiempos estimados por paso basándose en los datos reales del historial de OT.
   - Agregue o corrija cualquier paso de restauración que Copilot haya omitido o descrito incorrectamente.

5. Use Copilot nuevamente para mejorar la guía con el siguiente prompt de refinamiento:

   ```
   Revisa la guía que acabas de generar y:
   1. Agrega una sección de "ERRORES COMUNES A EVITAR" con los 
      3 errores más frecuentes que cometen los técnicos al 
      atender esta falla (basado en mejores prácticas de 
      mantenimiento industrial)
   2. Agrega un "DIAGRAMA DE FLUJO DE DECISIÓN" en formato 
      ASCII art que muestre el árbol de diagnóstico de forma visual
   3. Agrega al final una "TABLA DE HISTORIAL DE APLICACIÓN" 
      con columnas: Fecha | Técnico | Tiempo Real | Observaciones 
      (dejar vacía para registro futuro)
   ```

6. **Repita los pasos 1 al 5 para las 4 fallas restantes**, creando un documento Word independiente por cada falla. Nombre los archivos:
   ```
   Guia_Restauracion_GR-01_[NombreFalla].docx
   Guia_Restauracion_GR-02_[NombreFalla].docx
   Guia_Restauracion_GR-03_[NombreFalla].docx
   Guia_Restauracion_GR-04_[NombreFalla].docx
   Guia_Restauracion_GR-05_[NombreFalla].docx
   ```

7. Para acelerar la creación de las guías 2 a 5, use este prompt optimizado que referencia la guía anterior:

   ```
   Usando el mismo formato y estructura de la guía anterior, 
   genera ahora la Guía de Restauración Inmediata para:
   
   FALLA: [Nombre de la falla N]
   EQUIPO AFECTADO: [Equipo]
   TIEMPO TÍPICO: [Tiempo]
   CRITICIDAD: [Nivel]
   
   Datos adicionales de restauración exitosa del historial:
   [Pegar aquí el contenido relevante del documento 
   Tipificacion_Fallas.docx para esta falla]
   ```

8. Guarde todos los documentos en OneDrive y confirme la sincronización.

---

**Resultado Esperado:**

- 5 documentos Word independientes, uno por falla tipificada, con formato estandarizado y completo.
- Cada guía incluye: información general, advertencias de seguridad, diagnóstico rápido, herramientas, pasos de restauración numerados con tiempos, verificación post-restauración, criterios de escalamiento, errores comunes, diagrama de flujo ASCII y tabla de historial.
- Todos los documentos guardados y sincronizados en `OneDrive > Practica_07 > 02_Guias_Restauracion`.

**Verificación:**

- [ ] Los 5 documentos Word existen en la carpeta correcta de OneDrive.
- [ ] Cada guía tiene todos los elementos de la estructura estandarizada.
- [ ] Se realizaron al menos 2 ajustes manuales por guía para validar la precisión técnica.
- [ ] Los tiempos estimados en las guías son coherentes con los datos del historial de OT.
- [ ] Los códigos GR-01 a GR-05 están asignados y son únicos.

---

### Paso 4 — Construcción del Manual de Restauración Rápida

**Objetivo:** Consolidar las 5 guías individuales en un Manual de Restauración Rápida unificado con portada, índice navegable, sección de uso del manual y metadatos, usando Copilot en Word para generar los elementos de encuadre del documento.

---

**Instrucciones:**

1. Abra **Microsoft Word** y cree un nuevo documento en blanco. Guárdelo como `Manual_Restauracion_Rapida_v1.docx` en `OneDrive > Practica_07 > 03_Manual_Final`.

2. Abra el panel de Copilot en Word y use el siguiente prompt para generar la portada y sección introductoria:

   ```
   Genera el contenido de apertura para un Manual de Restauración 
   Rápida de Líneas de Producción de una planta de manufactura 
   industrial. El manual contiene 5 guías de restauración inmediata 
   para las fallas más críticas y frecuentes identificadas en 24 
   meses de historial de mantenimiento.
   
   Genera los siguientes elementos:
   
   1. PORTADA con:
      - Título: "Manual de Restauración Rápida de Líneas — MRR-2025"
      - Subtítulo descriptivo
      - Campos: Versión, Fecha de emisión, Área responsable, 
        Aprobado por, Próxima revisión
      - Declaración de uso: para quién es el manual y cómo usarlo
   
   2. INSTRUCCIONES DE USO DEL MANUAL (1 página):
      - Cómo navegar el manual durante un paro crítico
      - Protocolo de consulta en campo (máximo 3 pasos para 
        encontrar la guía correcta)
      - Qué hacer si la falla no está tipificada en el manual
      - Cómo reportar actualizaciones o correcciones al manual
   
   3. TABLA DE CONTENIDO con las 5 guías (usar los nombres 
      de falla que yo definiré a continuación):
      [Insertar aquí los nombres de las 5 fallas tipificadas]
   
   4. RESUMEN EJECUTIVO DE FALLAS CRÍTICAS: tabla de una página 
      con las 5 fallas, su código GR, equipo afectado, tiempo 
      típico de restauración y nivel de criticidad. Esta tabla 
      es la primera hoja que el técnico debe consultar durante 
      un paro.
   ```

3. Copie y pegue el contenido de cada una de las 5 guías individuales al final del documento `Manual_Restauracion_Rapida_v1.docx`, asegurando que cada guía comience en una nueva página (inserte saltos de página entre guías).

4. Use Copilot en Word para generar una sección de cierre del manual:

   ```
   Genera la sección final del manual con:
   
   1. GLOSARIO TÉCNICO: Define los 15 términos técnicos más 
      importantes que aparecen en las guías de restauración 
      (términos de mantenimiento industrial, diagnóstico de 
      fallas y seguridad industrial)
   
   2. REGISTRO DE CAMBIOS: Tabla con columnas: Versión | Fecha | 
      Descripción del cambio | Autor | Aprobado por
      (incluir la versión 1.0 como entrada inicial)
   
   3. CONTACTOS DE ESCALAMIENTO: Plantilla de tabla con roles: 
      Supervisor de Turno, Jefe de Mantenimiento, Técnico 
      Especialista Externo, Soporte del Fabricante — con 
      columnas para nombre y teléfono (dejar en blanco para 
      completar con datos reales)
   ```

5. Revise el documento completo. Use Copilot para generar metadatos del manual:

   ```
   Para este Manual de Restauración Rápida, genera una lista 
   de metadatos en formato de tabla que se usarán para catalogar 
   el documento en SharePoint. Incluye los siguientes campos de 
   metadatos:
   - Tipo de documento
   - Área de aplicación
   - Equipos cubiertos (lista)
   - Tipos de falla cubiertos (lista)
   - Nivel técnico requerido
   - Tiempo de consulta estimado en campo
   - Palabras clave de búsqueda (mínimo 10)
   - Idioma
   - Estado del documento (Borrador / Revisión / Aprobado)
   - Clasificación de seguridad de la información
   ```

6. Copie la tabla de metadatos generada por Copilot en un documento separado llamado `Metadatos_MRR.txt` guardado en la misma carpeta. Este archivo se usará en el Paso siguiente para configurar los metadatos en SharePoint.

7. **Guarde el manual completo** y verifique que el documento tenga una estructura coherente de principio a fin.

---

**Resultado Esperado:**

- Documento `Manual_Restauracion_Rapida_v1.docx` completo con: portada, instrucciones de uso, tabla de contenido, resumen ejecutivo de fallas, 5 guías completas, glosario, registro de cambios y contactos de escalamiento.
- Archivo `Metadatos_MRR.txt` con todos los campos de metadatos para SharePoint.
- El manual tiene una extensión estimada de 25–40 páginas dependiendo del detalle de las guías.

**Verificación:**

- [ ] El documento tiene portada, índice y todas las secciones requeridas.
- [ ] Las 5 guías están integradas con saltos de página entre ellas.
- [ ] El glosario contiene al menos 15 términos relevantes.
- [ ] Los metadatos cubren todos los campos especificados.
- [ ] El documento fue guardado y sincronizado en OneDrive.

---

### Paso 5 — Simulación de Paro Crítico: Prueba de Uso del Manual

**Objetivo:** Validar la utilidad práctica del manual de restauración creado mediante una simulación de paro crítico cronometrada, donde el participante debe localizar y aplicar la guía correcta en menos de 5 minutos, replicando las condiciones de presión de un paro real de planta.

---

**Instrucciones:**

1. El instructor enviará por **Microsoft Teams** un mensaje de alerta de paro simulado al canal del curso. El mensaje tendrá el siguiente formato:

   ```
   🚨 ALERTA DE PARO CRÍTICO — SIMULACIÓN
   
   Hora de paro: [Hora actual]
   Línea afectada: [L1 / L2 / L3 / L4 — el instructor asignará 
   una línea diferente a cada participante o grupo]
   Equipo: [Nombre del equipo — corresponde a uno de los equipos 
   en las guías del manual]
   Síntomas reportados por operador:
   - [Síntoma 1 — relacionado con una de las fallas tipificadas]
   - [Síntoma 2 — puede ser un síntoma adicional o distractor]
   - [Síntoma 3]
   
   OBJETIVO: Identificar la guía de restauración correcta y 
   ejecutar los primeros 3 pasos de intervención.
   TIEMPO LÍMITE: 5 minutos desde este mensaje.
   ```

2. **Inicie el cronómetro** en su dispositivo en el momento que reciba el mensaje de Teams.

3. Abra el `Manual_Restauracion_Rapida_v1.docx` desde OneDrive. Navegue a la **Tabla Resumen Ejecutivo de Fallas Críticas** (primera hoja de consulta del manual).

4. Identifique la guía correcta basándose en los síntomas del mensaje de Teams. Use el árbol de diagnóstico de la guía identificada para confirmar que es la falla correcta.

5. Navegue a la guía correspondiente y ejecute mentalmente (o documente) los primeros 3 pasos de intervención.

6. **Detenga el cronómetro** cuando haya completado la identificación y los primeros 3 pasos. Registre su tiempo.

7. Responda al mensaje de Teams del instructor con:
   ```
   ✅ RESPUESTA A ALERTA DE PARO
   
   Tiempo de localización de guía: [X minutos Y segundos]
   Guía identificada: [Código GR-XX — Nombre de la falla]
   Criterio de diagnóstico aplicado: [Síntoma que confirmó la falla]
   Primeros 3 pasos de intervención:
   1. [Paso]
   2. [Paso]
   3. [Paso]
   Herramienta crítica requerida: [Herramienta principal]
   ¿Requiere escalamiento? [Sí/No — justificación]
   ```

8. Si su tiempo fue **mayor a 5 minutos**, use Copilot Chat para analizar qué mejorar en el manual:

   ```
   Durante una simulación de paro crítico, tardé [X minutos] en 
   localizar la guía correcta en mi Manual de Restauración Rápida. 
   El manual tiene 5 guías con la siguiente estructura: [describir 
   brevemente la estructura].
   
   ¿Qué mejoras de navegación, estructura o elementos visuales 
   puedo implementar en el manual para reducir el tiempo de 
   localización a menos de 3 minutos? Proporciona 5 recomendaciones 
   concretas y accionables.
   ```

9. Implemente al menos **2 de las mejoras sugeridas** en el manual y guarde como `Manual_Restauracion_Rapida_v1.1.docx`.

---

**Resultado Esperado:**

- Tiempo de localización de guía registrado (objetivo: < 5 minutos).
- Respuesta documentada en Teams con identificación correcta de la falla y primeros 3 pasos.
- Si el tiempo fue > 5 minutos: al menos 2 mejoras de navegación implementadas en la versión v1.1 del manual.

**Verificación:**

- [ ] El tiempo de respuesta fue registrado y comunicado en Teams.
- [ ] La guía identificada corresponde correctamente a los síntomas del escenario simulado.
- [ ] Los 3 pasos de intervención son técnicamente correctos según la guía.
- [ ] Si hubo mejoras, la versión v1.1 fue guardada en OneDrive.

---

### Paso 6 — Publicación del Repositorio en SharePoint con Metadatos

**Objetivo:** Publicar el Manual de Restauración Rápida y las guías individuales en el sitio SharePoint del curso, configurando metadatos generados por Copilot para habilitar búsqueda y consulta eficiente en campo.

---

**Instrucciones:**

1. Abra el sitio **SharePoint del curso** en el navegador (URL proporcionada por el instructor).

2. Navegue a la biblioteca de documentos **"Manual de Restauración Rápida"**. Si no existe, cree una nueva biblioteca con ese nombre:
   ```
   SharePoint > Inicio > + Nueva > Biblioteca de documentos
   Nombre: Manual de Restauración Rápida
   Descripción: Repositorio de guías de restauración inmediata 
   para fallas críticas de líneas de producción
   ```

3. Cree la siguiente estructura de carpetas dentro de la biblioteca:
   ```
   Manual de Restauración Rápida/
   ├── 00_Manual_Completo/
   ├── 01_Guias_Individuales/
   │   ├── GR-01_[NombreFalla]/
   │   ├── GR-02_[NombreFalla]/
   │   ├── GR-03_[NombreFalla]/
   │   ├── GR-04_[NombreFalla]/
   │   └── GR-05_[NombreFalla]/
   └── 02_Analisis_Base/
   ```

4. Suba los archivos a las carpetas correspondientes:
   - `Manual_Restauracion_Rapida_v1.1.docx` → carpeta `00_Manual_Completo`
   - Cada `Guia_Restauracion_GR-0X_*.docx` → su carpeta `GR-0X` correspondiente
   - `Tipificacion_Fallas.docx` y `historico_OT_24meses.xlsx` → carpeta `02_Analisis_Base`

5. Configure las **columnas de metadatos** en la biblioteca de SharePoint. Para agregar columnas:
   ```
   En la biblioteca SharePoint:
   1. Clic en el ícono de engranaje (Configuración) → Configuración de biblioteca
   2. Sección "Columnas" → Crear columna
   3. Agregar las siguientes columnas personalizadas:
   ```

   | Nombre de Columna | Tipo | Opciones / Descripción |
   |---|---|---|
   | `Tipo_Falla` | Elección | Mecánica; Eléctrica; Neumática; Software; Operacional |
   | `Equipo_Afectado` | Texto de una línea | Nombre del equipo cubierto |
   | `Codigo_Guia` | Texto de una línea | GR-01 a GR-05 |
   | `Criticidad` | Elección | CRÍTICA; ALTA; MEDIA |
   | `Tiempo_Restauracion_Min` | Número | Tiempo típico en minutos |
   | `Nivel_Tecnico` | Elección | Técnico Junior; Técnico Senior; Especialista |
   | `Estado_Documento` | Elección | Borrador; En Revisión; Aprobado |
   | `Palabras_Clave` | Texto de varias líneas | Etiquetas para búsqueda |

6. Una vez creadas las columnas, seleccione cada archivo subido y complete sus metadatos haciendo clic en el archivo → **Detalles** (panel lateral) → complete cada campo.

7. Use Copilot Chat para generar las palabras clave de búsqueda para cada guía:

   ```
   Para una Guía de Restauración Inmediata titulada 
   "[Nombre de la guía GR-0X]" que cubre la falla 
   "[Nombre de la falla]" en el equipo "[Nombre del equipo]" 
   de una planta de manufactura, genera:
   
   1. Lista de 10 palabras clave en español para búsqueda en 
      SharePoint (términos que un técnico en campo usaría para 
      buscar esta guía)
   2. Lista de 5 palabras clave en inglés (terminología técnica 
      estándar internacional)
   3. 3 frases de búsqueda completas que el técnico podría usar
   
   Formato: lista separada por punto y coma para copiar 
   directamente en el campo de metadatos.
   ```

8. Copie las palabras clave generadas por Copilot en el campo `Palabras_Clave` de cada archivo en SharePoint.

9. Verifique que la búsqueda funciona correctamente:
   ```
   En la biblioteca SharePoint:
   1. Use la barra de búsqueda → escriba una palabra clave 
      (ej: "motor", "variador", "fuga")
   2. Confirme que aparece el archivo correspondiente
   3. Use el filtro de columna "Criticidad" → filtre por "CRÍTICA"
   4. Confirme que solo aparecen las guías de criticidad crítica
   ```

10. Comparta el enlace de la biblioteca con sus compañeros de curso en Teams:
    ```
    En Teams → Canal del curso → Nueva conversación:
    "✅ Repositorio publicado: [pegar URL de la biblioteca SharePoint]
    Contiene 5 guías de restauración + manual completo.
    Metadatos configurados para búsqueda por tipo de falla, 
    equipo y criticidad."
    ```

---

**Resultado Esperado:**

- Biblioteca SharePoint con estructura de carpetas creada y todos los archivos subidos.
- 8 columnas de metadatos configuradas en la biblioteca.
- Cada archivo tiene sus metadatos completos, incluyendo palabras clave generadas por Copilot.
- La búsqueda por palabras clave y el filtrado por columnas funciona correctamente.
- El enlace fue compartido en Teams.

**Verificación:**

- [ ] La biblioteca SharePoint existe y tiene la estructura de carpetas correcta.
- [ ] Los 7 archivos (1 manual + 5 guías + 1 tipificación) están subidos.
- [ ] Las 8 columnas de metadatos están configuradas.
- [ ] Cada archivo tiene metadatos completos.
- [ ] La búsqueda por palabras clave devuelve resultados correctos.
- [ ] El enlace fue compartido en el canal de Teams del curso.

---

## 7. Validación y Pruebas Finales

Al completar todos los pasos, ejecute la siguiente lista de validación integral del entregable:

### 7.1 Checklist de Validación del Manual

| Elemento | Criterio de Aceptación | ✅ / ❌ |
|---|---|---|
| Número de guías | Exactamente 5 guías de restauración completas | |
| Estructura de cada guía | Todos los 9 elementos de la estructura estandarizada presentes | |
| Códigos únicos | GR-01 a GR-05 asignados sin duplicados | |
| Tiempos de restauración | Coherentes con los datos del historial de OT (±20%) | |
| Advertencias de seguridad | Al menos 3 por guía, específicas para cada falla | |
| Árbol de diagnóstico | Formato Sí/No, mínimo 5 preguntas por guía | |
| Pasos de restauración | Entre 7 y 10 pasos numerados con tiempos estimados | |
| Verificación post-restauración | Mínimo 3 pruebas funcionales con criterios de aceptación | |
| Glosario | Al menos 15 términos definidos | |
| Metadatos SharePoint | 8 columnas configuradas y completas para todos los archivos | |

### 7.2 Prueba de Usabilidad en Campo

Pida a un compañero que **nunca haya visto su manual** que realice la siguiente prueba:

```
PRUEBA DE USABILIDAD:
1. Dar al compañero solo el Manual_Restauracion_Rapida_v1.1.docx
2. Describir verbalmente un escenario de falla (uno de los 5 tipificados)
3. Medir el tiempo que tarda en:
   a. Identificar la guía correcta
   b. Leer las advertencias de seguridad
   c. Listar las herramientas necesarias
   d. Describir los primeros 3 pasos de intervención

CRITERIO DE ÉXITO: Todo el proceso en menos de 5 minutos.
```

Documente el resultado en el campo `Observaciones` de la sección **Registro de Cambios** del manual.

### 7.3 Validación del Repositorio SharePoint

```
Prueba 1 — Búsqueda por síntoma:
  Buscar: "vibración excesiva" → debe encontrar guía correspondiente

Prueba 2 — Filtro por criticidad:
  Filtrar Criticidad = "CRÍTICA" → debe mostrar solo guías críticas

Prueba 3 — Filtro por equipo:
  Filtrar Equipo_Afectado = [nombre de un equipo] → debe mostrar 
  solo guías de ese equipo

Prueba 4 — Acceso desde móvil (opcional):
  Acceder al SharePoint desde el navegador del teléfono y verificar 
  que el manual es legible y navegable
```

---

## 8. Resolución de Problemas

### Problema 1 — Copilot en Word Genera Guías con Estructura Incompleta o Genérica

**Síntoma:** Al usar Copilot en Word para generar las guías de restauración, el contenido generado es demasiado genérico, omite secciones completas de la estructura solicitada (por ejemplo, no genera el diagrama de flujo ASCII o el árbol de diagnóstico), o las instrucciones son tan abstractas que no son útiles para un técnico en campo.

**Causa:** Este comportamiento ocurre cuando el prompt no provee suficiente contexto específico sobre el equipo y la falla, o cuando el prompt es demasiado extenso y Copilot prioriza las primeras instrucciones sobre las últimas. También puede ocurrir cuando Copilot no tiene suficiente "memoria" del contexto de la falla porque la información de tipificación del Paso 2 no fue incluida en el prompt.

**Solución:**
```
Estrategia 1 — Prompts segmentados:
En lugar de pedir toda la guía en un solo prompt, divida la 
solicitud en prompts separados por sección:
  Prompt A: "Genera solo la sección de DIAGNÓSTICO RÁPIDO para..."
  Prompt B: "Ahora genera solo la sección de PASOS DE RESTAURACIÓN..."
  Prompt C: "Ahora genera el DIAGRAMA DE FLUJO ASCII del diagnóstico..."

Estrategia 2 — Proveer datos del historial:
Antes de pedir la guía, pegue en el prompt el contenido 
relevante del documento Tipificacion_Fallas.docx para esa falla:
  "Basándote en estos datos del historial real de la planta: 
  [pegar sección de Tipificacion_Fallas.docx], genera..."

Estrategia 3 — Iteración con corrección:
Si una sección quedó incompleta, use:
  "La sección [nombre] no está completa. Específicamente falta 
  [elemento]. Regenera solo esa sección con más detalle."

Estrategia 4 — Verificación técnica manual:
Recuerde que las respuestas de Copilot son referenciales. 
Siempre valide los pasos de restauración con el técnico de 
mayor experiencia del equipo antes de publicar la guía.
```

---

### Problema 2 — Los Metadatos de SharePoint No Permiten Búsqueda Efectiva

**Síntoma:** Al buscar en la biblioteca SharePoint usando palabras clave o al filtrar por columnas de metadatos (como `Tipo_Falla` o `Criticidad`), los archivos no aparecen en los resultados o el filtrado no funciona correctamente. Los archivos existen en la biblioteca pero no son encontrados por la búsqueda.

**Causa:** Existen tres causas posibles: (a) Las columnas de metadatos fueron creadas después de subir los archivos y los valores no fueron completados retroactivamente para cada archivo; (b) SharePoint Online requiere un tiempo de indexación de hasta 15–30 minutos después de que se agregan o modifican metadatos antes de que sean buscables; (c) Las columnas de tipo "Elección" tienen valores que no coinciden exactamente con los ingresados (diferencia en mayúsculas/minúsculas o espacios adicionales).

**Solución:**
```
Verificación 1 — Confirmar que los metadatos están guardados:
  1. Clic en el archivo → panel Detalles (lateral derecho)
  2. Verificar que todos los campos de columnas personalizadas 
     muestran valores (no vacíos)
  3. Si están vacíos, completarlos y hacer clic en "Guardar"

Verificación 2 — Esperar indexación:
  Si los metadatos fueron recién completados, espere 15-30 minutos 
  y vuelva a intentar la búsqueda. SharePoint Online indexa 
  periódicamente, no en tiempo real.

Verificación 3 — Revisar consistencia de valores en columnas Elección:
  1. Ir a Configuración de biblioteca → Columna [nombre]
  2. Verificar que los valores de elección están escritos 
     exactamente igual que los ingresados en los archivos
  3. Si hay discrepancias, editar los valores de los archivos 
     para que coincidan con las opciones definidas

Verificación 4 — Usar búsqueda por nombre de archivo como alternativa:
  Mientras se resuelve el problema de metadatos, use la 
  nomenclatura estandarizada de nombres de archivo 
  (GR-01, GR-02, etc.) para búsqueda directa por nombre.
  
Verificación 5 — Permisos de búsqueda:
  Confirme con el administrador del sitio SharePoint que el 
  índice de búsqueda está habilitado para la biblioteca.
```

---

## 9. Limpieza del Entorno

Al finalizar la práctica, ejecute los siguientes pasos de limpieza para mantener el entorno ordenado:

### 9.1 Archivos Locales

```
1. Verificar que todos los archivos de trabajo estén sincronizados 
   en OneDrive (ícono de nube sin indicador de error en la barra 
   de tareas)

2. Eliminar archivos temporales o versiones de borrador que no 
   sean necesarias conservar:
   - Cualquier documento Word con nombre "Sin título" o temporal
   - Copias duplicadas accidentales en la carpeta Practica_07

3. Estructura final esperada en OneDrive > Practica_07:
   ├── 01_Analisis_Fallas/
   │   ├── historico_OT_24meses.xlsx (con tabla dinámica del Paso 1)
   │   └── Tipificacion_Fallas.docx
   ├── 02_Guias_Restauracion/
   │   ├── Guia_Restauracion_GR-01_[Falla].docx
   │   ├── Guia_Restauracion_GR-02_[Falla].docx
   │   ├── Guia_Restauracion_GR-03_[Falla].docx
   │   ├── Guia_Restauracion_GR-04_[Falla].docx
   │   └── Guia_Restauracion_GR-05_[Falla].docx
   └── 03_Manual_Final/
       ├── Manual_Restauracion_Rapida_v1.docx
       ├── Manual_Restauracion_Rapida_v1.1.docx
       └── Metadatos_MRR.txt
```

### 9.2 Copilot Chat

```
1. Cerrar la sesión de Copilot Chat activa en el navegador
   (no es necesario eliminar el historial, pero es buena práctica 
   cerrar conversaciones con datos operativos al terminar)
2. Si usó el modo Trabajo, confirmar que no quedaron archivos 
   adjuntos en la sesión de Copilot Chat
```

### 9.3 SharePoint

```
1. Confirmar que la biblioteca "Manual de Restauración Rápida" 
   tiene los permisos correctos:
   - Acceso de lectura para todos los participantes del curso
   - Acceso de edición solo para el participante propietario 
     y el instructor
2. No eliminar ningún archivo del repositorio SharePoint — 
   estos son los entregables finales de la práctica
```

### 9.4 Microsoft Teams

```
1. Revisar que su respuesta a la simulación de paro crítico 
   (Paso 5) fue publicada correctamente en el canal del curso
2. Guardar el enlace al repositorio SharePoint que publicó 
   en Teams — lo necesitará para la presentación final del curso
```

---

## 10. Resumen

### Logros de la Práctica

En esta práctica de 90 minutos recorrió el ciclo completo que va desde el dato histórico hasta el documento operativo listo para uso en campo:

| Paso | Actividad | Herramienta | Entregable |
|---|---|---|---|
| 1 | Exploración estadística del historial de OT | Excel + Copilot | Tabla dinámica y análisis estadístico |
| 2 | Tipificación de fallas con análisis de patrones | Copilot Chat | `Tipificacion_Fallas.docx` |
| 3 | Creación de guías de restauración estructuradas | Word + Copilot | 5 guías individuales GR-01 a GR-05 |
| 4 | Consolidación del manual de restauración rápida | Word + Copilot | `Manual_Restauracion_Rapida_v1.1.docx` |
| 5 | Simulación de paro crítico cronometrada | Teams + Manual | Respuesta documentada en Teams |
| 6 | Publicación del repositorio con metadatos | SharePoint + Copilot | Biblioteca SharePoint con búsqueda funcional |

### Conexión con el Capítulo 7

Esta práctica materializa los dos pilares del Capítulo 7:

- **Lección 7.2 — Estrategias de recovery ágil:** La simulación del Paso 5 demostró en condiciones controladas que un manual bien estructurado, construido con Copilot, permite reducir el tiempo de localización de la guía correcta a menos de 5 minutos — transformando la respuesta ante paros de reactiva e improvisada a estructurada y basada en datos históricos.

- **Lección 7.3 — Tipificación de fallas con históricos de IA:** El Paso 2 demostró cómo Copilot puede convertir 24 meses de registros de texto libre en inteligencia accionable: firmas de falla, árboles de diagnóstico y protocolos de atención que de otra forma requerirían semanas de análisis manual.

### Reflexión Crítica

> **Recuerde:** Las guías generadas por Copilot son un punto de partida de alta calidad, no un producto final certificado. Antes de publicar cualquier guía en un entorno productivo real, debe ser revisada y validada por el técnico de mayor experiencia del equipo y, en el caso de fallas que involucren seguridad eléctrica, neumática o de presión, por el responsable de seguridad industrial de la planta.

### Recursos Adicionales

| Recurso | Descripción | Enlace |
|---|---|---|
| Documentación de Copilot en Word | Guía oficial de Microsoft para usar Copilot en Word | [learn.microsoft.com/es-es/microsoft-365-copilot](https://learn.microsoft.com/es-es/microsoft-365-copilot/microsoft-365-copilot-overview) |
| Mejores prácticas de mantenimiento — SMRP | Body of Knowledge para gestión de mantenimiento | [smrp.org/resources/body-of-knowledge](https://www.smrp.org/resources/body-of-knowledge) |
| SharePoint — Gestión de metadatos y columnas | Documentación oficial de columnas en bibliotecas | [support.microsoft.com/sharepoint](https://support.microsoft.com/es-es/office/introducción-a-las-columnas-de-lista-y-biblioteca-de-sharepoint-0d8ddb7b-7dc7-414d-a283-ee9dca891df7) |
| RCM — Reliability Centered Maintenance | Marco de referencia para tipificación de fallas | [SAE JA1011 Standard](https://www.sae.org/standards/content/ja1011/) |
| Diseño de documentos técnicos de campo | Principios de usabilidad para documentos de mantenimiento | [Deloitte Manufacturing Insights](https://www2.deloitte.com/us/en/insights/industry/manufacturing.html) |

---

> **🏁 Práctica completada.** Ha construido un repositorio operativo de guías de restauración inmediata que integra inteligencia artificial, datos históricos de mantenimiento y buenas prácticas de la industria. Este entregable es directamente transferible a su entorno de planta real, con las validaciones técnicas correspondientes.
