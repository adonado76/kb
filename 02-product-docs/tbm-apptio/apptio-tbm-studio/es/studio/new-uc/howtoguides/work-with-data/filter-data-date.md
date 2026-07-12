---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Filtrar datos por partición de fecha"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "Trabajar con datos"
  - "Transformar y enriquecer los datos"
source_path: "studio/new-uc/howtoguides/work-with-data/filter-data-date.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Filtrar datos por partición de fecha

## Objetivo

Distribuye los datos con marca de tiempo por periodos y filtra automáticamente según el periodo activo seleccionado en TBM Studio, lo que permite realizar análisis de costes por meses.

## Cuándo utilizar esto

Utiliza la partición por fecha cuando:

- Tus datos contienen fechas de transacciones y necesitas desgloses mensuales
- Trabajar con datos del libro mayor con marcas de fecha por transacción
- Los datos muestran los meses en columnas separadas (ene, feb, mar, etc.)
- Necesitas que los valores se actualicen automáticamente cuando los usuarios cambien de periodo

Nota: TBM Studio se basa en meses. Las particiones de fecha filtran los datos para mostrar únicamente los valores seleccionados de « month&#x2019;s ». La agregación de varios periodos se lleva a cabo en la capa de presentación de informes.

***Nota:***

## Requisitos previos

- Datos con información de fecha (en filas o columnas)
- Comprensión del formato de fecha de tus datos
- Columnas de fecha con el tipo de datos adecuado (para datos basados en filas)

## Estimación de tiempo

10-15 minutos

**Pasos**

## Para datos organizados en filas (fechas en filas)

*Utiliza este método cuando tus datos contengan columnas de fecha con una fecha por fila (por ejemplo, la fecha de la transacción en el libro mayor).*

1. Echa un vistazo a la tabla y añade un paso **de partición por fecha** al proceso de transformación.
2. **Las fechas** seleccionadas se muestran en filas.
3. Selecciona la columna **«Fecha de inicio»** (obligatorio).
4. (Opcional) Selecciona la columna **«Fecha de finalización»** si tus datos abarcan varios intervalos de fechas.
5. Pulse **Guardar**.

## Para datos organizados en columnas (fechas en los encabezados de columna)

*Utiliza este método cuando tus datos tengan una columna para cada mes (por ejemplo, «Presupuesto» con las columnas «Ene», «Feb» y «Mar»).*

1. Echa un vistazo a la tabla y añade un paso **de partición por fecha** al proceso de transformación.
2. **Las fechas** seleccionadas se muestran en columnas.
3. En «**Interpretar año como** », seleccione **«Año fiscal»** o «**Año natural** ».
4. En «**Prefijo de nueva columna** », introduce una etiqueta que se añadirá al principio de las columnas de fecha (por ejemplo, «Importe&» creará «Importe ene&», «Importe feb&»).
5. Selecciona qué conjuntos de columnas deseas particionar:
   - Si tienes varios conjuntos (por ejemplo, «Coste» y «Presupuesto»), selecciona cuáles quieres incluir
   - Puedes dividir por uno o por todos los conjuntos de columnas
6. Pulse **Guardar**.

## Resultados previstos

La tabla ahora se adapta al intervalo de tiempo seleccionado en TBM Studio. Cuando cambias de mes con el selector de fechas, la vista previa se actualiza para mostrar únicamente los datos de ese mes en month&#x2019;s. En el caso de las particiones basadas en columnas, se crean nuevas columnas con el prefijo especificado y las etiquetas de mes.

## Errores habituales

- **Formato de fecha no reconocido:** en el caso de los datos organizados en columnas, los nombres de los meses deben ser reconocibles (Ene, Enero, P1, etc.). Los años pueden aparecer en cualquier posición, excepto en el centro (por ejemplo, «2016 Jan&» o «Jan 2016&» son válidos, pero «Jan 2016 Cost&» no lo es).
- **No se ven datos tras la segmentación:** comprueba que el periodo seleccionado coincida con las fechas de tus datos. Si trabajas con datos históricos, asegúrate de que el selector de fechas de TBM Studio abarque el periodo correspondiente.
- **No se pueden seleccionar varios meses:** es el comportamiento esperado. El filtro de particiones de fechas se limita a un único periodo activo. Para la agregación de varios meses, utiliza funciones de la capa de informes como YTD (acumulado del año) o crea columnas basadas en fechas.

**Tareas relacionadas**

- [Tablas de versiones para datos mensuales](version-tables-monthly-data.html)
- Comprensión de los periodos de tiempo (Conceptos: Arquitectura de datos)
- Fórmulas basadas en el tiempo en los informes (Referencia: Fórmulas y funciones)

**Tema principal:** [Transformar y enriquecer datos](../../../../studio/new-uc/howtoguides/work-with-data/transform-enrich-data.html)
