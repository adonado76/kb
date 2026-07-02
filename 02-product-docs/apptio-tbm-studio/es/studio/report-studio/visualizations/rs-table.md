---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Tabla"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "ApptioIBM Report Studio (Nuevo)"
  - "Visualizaciones"
source_path: "studio/report-studio/visualizations/rs-table.html"
images:
  - "resources/images/studio_images/zerofilter.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Tabla

El componente de tabla muestra los datos en un formato tabular estructurado. Es ideal para mostrar información detallada, resumir métricas y admitir el filtrado interactivo dentro de un informe.

## Cuándo utilizar una tabla

Utiliza un componente Tabla cuando desees:

- Presentar filas y columnas de datos (datos estructurados)
- Mostrar varias métricas o dimensiones juntas
- Habilitar la clasificación, el filtrado o la exploración detallada

## Añadir una tabla al informe

1. Añadir una tabla desde el panel Visualizaciones de la barra de herramientas
2. Haga clic en la tabla para habilitar los paneles Datos y Formato.
3. **Panel de datos**
   - Seleccionar objeto modelo
   - **Filas** : proporciona entradas para la primera columna de la tabla. Si hay entradas duplicadas en la fuente, las entradas se agrupan y se muestra una sola entrada para cada valor único. Si añades más de un campo al área, se crean subgrupos en la primera columna de la tabla.
   - **Columnas** : proporciona encabezados de columna para la tabla. Solo se puede introducir un campo en el área Columnas.
   - **Valores** : proporciona los datos que se muestran en el cuerpo de la tabla
   - **Filtros** : filtra las entradas de una columna de la tabla.
4. **Panel de formato**
   1. Propiedades generales: consulte [Propiedades de los componentes.](../components/components.html#abt-comp__comprop)
   2. **Total y subtotales**
      1. Mostrar columna total: muestra una columna de resumen a la derecha que calcula los totales de cada una de las filas numéricas.
      2. Mostrar fila total: muestra una fila de resumen en la parte inferior de la tabla que calcula los totales de cada una de las columnas numéricas.
      3. Mostrar otra fila: si hay muchas filas en una tabla y desea limitar el número de filas que se muestran, puede añadir otra fila. La otra fila se muestra en la parte inferior de la tabla. Muestra el total de toda la tabla menos los valores que se muestran en la página actual de la tabla.
      4. Mostrar subtotal: muestra las filas de subtotal para los datos agrupados. Puede elegir dónde mostrar las etiquetas de subtotal y qué elementos incluir en el subtotal.
   3. **Límite de filas por página**
      1. Establece el número máximo de filas que se muestran por página en la tabla, lo que permite la paginación para conjuntos de datos grandes.
   4. **Filtro cero**
      1. La función Filtros Cero le ayuda a centrarse en los datos significativos ocultando rápidamente las filas en las que las columnas numéricas seleccionadas contienen valores cero. Esto facilita el análisis de los datos pertinentes sin necesidad de filtrarlos manualmente.
      2. **Seleccionar columnas numéricas**
         1. Todas las columnas numéricas de la tabla aparecen con casillas de verificación.
         2. Seleccione una o varias columnas a las que desee aplicar el filtro cero.

            ![filtros cero](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/zerofilter.png)
      3. **Aplicar el filtro cero**
         1. Tras seleccionar las columnas numéricas, la tabla se actualiza instantáneamente para mostrar datos distintos de cero.
         2. Las filas en las que las columnas seleccionadas contienen valores cero se ocultan de la vista.
      4. **Borrar el filtro**
         1. Para volver a la vista original borrando el filtro cero.
         2. Se restaurarán todas las filas, incluidas las que tengan valores cero.

- **[Menú de desbordamiento de columnas de tabla](../../../studio/report-studio/visualizations/table-col-overflow.html)**
- **[Cambiar el nombre de las columnas de una tabla](../../../studio/report-studio/visualizations/remaining-col-tables.html)**
- **[Ocultar dimensiones intermedias](../../../studio/report-studio/visualizations/hiding-intermediate-dimensions.html)**
- **[Mostrar valores](../../../studio/report-studio/visualizations/show-values.html)**
- **[Vista en árbol](../../../studio/report-studio/visualizations/tree-view.html)**
- **[Exportar una tabla a Excel](../../../studio/report-studio/visualizations/export-table.html)**
