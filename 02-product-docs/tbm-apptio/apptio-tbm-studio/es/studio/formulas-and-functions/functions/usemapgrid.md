---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Función Use_Map_Grid"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/usemapgrid.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Función Use_Map_Grid

**Se aplica a** : TBM Studio 12.0 y posteriores

Para las asignaciones basadas en tablas, especifica asignaciones de unidades una a una y un porcentaje del valor de la unidad de origen. Esta función sustituye a [Use\_Map\_Table](usemaptable.htm "(se abre en una pestaña o una ventana nueva)").

## Dónde utilizarlo

En una fórmula de asignación **avanzada** en un modelo.

Nota: No es necesario ni aconsejable utilizar directamente esta función. La interfaz de usuario para la asignación basada en tablas permite especificar una tabla de asignación gráficamente y crea la función automáticamente.

## Sintaxis

`Use_Map_Grid(table:source_column[,notation])`

## Argumentos

*tabla*

Hace referencia a una tabla de asignación.

*columna\_fuente*

Especifica el nombre de la columna de la unidad fuente.

*notación*

Una de las dos cadenas literales que indican cómo se expresa la asignación:

- porcentaje = Un número entero que especifica una ponderación porcentual (puede ser *n* o *n%* ).
- ratio = Un número entero, dividido por el total para obtener un valor decimal.

Si no se especifica la *notación*, se supone que los números ya son un valor decimal (por ejemplo, 0.25 = 25%).

## Tipo de retorno

Tipo de las columnas de la tabla de correspondencia.

## Observaciones

La tabla tendrá una única columna (que se especifica en la función). El resto de columnas son columnas de unidades objetivo.
