---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "YearToDate función"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/yeartodate.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# YearToDate función

Devuelve el valor acumulado de una métrica especificada desde el comienzo del ejercicio en curso hasta el período actual inclusive. Esto difiere de la función Anual, que siempre devuelve el total de todo el año, independientemente del periodo actual.

YearToDate es diferente de la función [Anual](annual.html "Devuelve un valor para la métrica especificada ajustado hacia delante o hacia atrás en un número de años, en función del tipo de calendario seleccionado."), que devuelve el total de todo el año independientemente del periodo en el que se visualice.

El año en curso es el año fiscal definido en el cuadro de diálogo **Configurar periodos de tiempo**, independientemente de la selección de la fecha actual en el selector de fechas.

## Sintaxis

`YearToDate(metric)`

## Parámetros

*métrica* : La columna métrica cuyos valores se sumarán desde el inicio del ejercicio hasta el período actual. Debe referirse a una columna de la misma tabla. Obligatorio

## Comportamiento

Suma los valores de la métrica especificada desde el comienzo del ejercicio hasta el período seleccionado actualmente. La estructura del año fiscal se define en la configuración de Periodos de tiempo y no se ve afectada por el selector de fechas.

## Tipo de retorno

Número

## Ejemplo

El siguiente ejemplo devuelve la suma del año hasta la fecha de la métrica {Cost}.

`=YearToDate(Cost)`
