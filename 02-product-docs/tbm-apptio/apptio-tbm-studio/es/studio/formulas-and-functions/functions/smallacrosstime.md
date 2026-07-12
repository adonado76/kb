---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "SmallAcrossTime función"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/smallacrosstime.html"
images:
  - "resources/images/studio_images/studioimages/studio/stu015.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# SmallAcrossTime función

**Se aplica a** : TBM Studio 12.0 y posteriores

Devuelve el valor más pequeño de una columna especificada en uno o más periodos de tiempo.

Si no se especifica ningún periodo de tiempo, se comportará como la función Pequeño. La excepción es si hay un trend\_append[timeperiods] más adelante en la ruta, en cuyo caso trend\_append inyectará sus periodos de tiempo en la función SmallAcrossTime en algún punto de la ruta cuando vaya a buscar las tablas que se incluirán en la tendencia.

## Dónde utilizarlo

Esta función puede utilizarse en:

- Conjuntos de datos (con argumentos de columna y rollup)
- Métricas calculadas e informes con columnas de métricas (con argumento de rollup)
- Columnas de fórmulas en tablas de informes (con argumentos de columna y rollup)

En cualquier controlador de unidad de objeto modelado o en cualquier tabla agrupada.

## Sintaxis

`Small(column, period, period, etc.)`

## Argumentos

*columna*

La columna de la que devolver el número más pequeño.

*periodo*

El periodo o periodos en los que buscar. El formato debe ser MMM AAAA. Por ejemplo: Enero de 2013. No hay límite en el número de periodos que puede incluir.

## Tipo de retorno

Igual que el tipo de columna.

## Ejemplos

En el ejemplo siguiente, el valor de la columna Pequeño se extrae de un período distinto del que se muestra actualmente:

![Ejemplos](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu015.png)

Consulte también:

- [Promedio](average.htm "(se abre en una pestaña o una ventana nueva)")
- [Percentil](percentile.htm "(se abre en una pestaña o una ventana nueva)")
- [Grande](large.htm "(se abre en una pestaña o una ventana nueva)")
- [Mín](min.htm "(se abre en una pestaña o una ventana nueva)")
- [Máx](max.htm "(se abre en una pestaña o una ventana nueva)")
