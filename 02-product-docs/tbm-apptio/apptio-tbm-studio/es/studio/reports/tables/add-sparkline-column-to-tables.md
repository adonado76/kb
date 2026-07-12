---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Añadir una columna Sparkline a una tabla"
breadcrumb: []
source_path: "studio/reports/tables/add-sparkline-column-to-tables.html"
images:
  - "resources/images/studio_images/studioimages/studio/aug304.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Añadir una columna Sparkline a una tabla

**Se aplica a** : TBM Studio 12.0 y posteriores

Para mostrar datos de tendencias, añada una columna de gráfico a una tabla. En la siguiente imagen, se muestran líneas de puntos en la columna **Tendencia**. Los datos pueden evolucionar tanto hacia atrás como hacia delante. Para que funcionen los sparklines, la tabla debe tener una columna de clave primaria que persista durante todo el tiempo de la tendencia. Además, debe haber datos para cada mes.

![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/aug304.png)

Los indicadores de estado están estrechamente relacionados con los cuadros de mando. Los indicadores de estado son iconos que señalan el estado actual de los datos, como por encima o por debajo de un valor determinado. Los indicadores de estado se describen en [Añadir una columna de indicador de estado a una tabla](add-status-indicators-to-tables.htm "(se abre en una pestaña o una ventana nueva)").

Para añadir destellos a una tabla:

1. Seleccione la columna de valores de la tabla a la que desea aplicar la tendencia en el gráfico.
2. Haga clic en la pestaña **Fórmulas**.
3. En el menú del icono **Fechas**, haga clic en **Tendencia de Sparkline**. La columna se añade a la fórmula table.The es `=Sparkline(past,future,column).` Los argumentos se describen a continuación:
   - **Pasado** es el número de periodos que la línea de tendencia retrocederá en el tiempo. Debe ser un número positivo.
   - **Futuro** es el número de periodos que la línea de tendencia avanzará en el tiempo. Debe ser un número positivo.
   - **Columna** es el nombre de la columna que contiene los datos a los que se quiere aplicar la tendencia.

Por ejemplo, la fórmula siguiente mostrará la tendencia de los datos de la columna Coste hacia adelante y hacia atrás durante 4 meses.

> =SPARKLINE( 4,4,Cost )
