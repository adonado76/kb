---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "CurrentDate función"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/currentdate.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# CurrentDate función

Devuelve la fecha de inicio del periodo de tiempo actualmente seleccionado, si el tiempo está activado. Si no, devuelve Eon 2000.

## Sintaxis

`CurrentDate([format_string])`

## Parámetros

*cadena\_de\_formato*

Especifica un formato de fecha personalizado para el valor de retorno, siguiendo las mismas convenciones que [DateFormat](dateformat.html "Convierte una expresión de fecha a un formato de fecha especificado.") función. Opcional.

## Comportamiento

- Devuelve la fecha de inicio del periodo de tiempo actualmente seleccionado.
- Si se proporciona una cadena\_de\_formato, la salida se formatea en consecuencia; de lo contrario, se utiliza un formato predeterminado.
- La función acepta cero o un argumento.

## Ejemplos

- `CurrentDate()`

  Devuelve la fecha de inicio en el formato predeterminado.
- `CurrentDate("yyyy-MM-dd")`

  Devuelve la fecha de inicio formateada como 'año-mes-día'.

## Tipo de retorno

Serie

Consulte también:

- [Horas](hours.html "Convierte un valor de fecha en el número de horas transcurridas desde el 1 de enero de 1970, como valor numérico.")
- [Ahora](now.html)
- [Minutos](minutes.html "Convierte un valor de fecha en el número de minutos transcurridos desde el 1 de enero de 1970, como valor numérico.")
- [Meses](months.html "Convierte una fecha especificada en un valor decimal que representa el número de períodos desde el 1 de enero de 1970. Útil para cálculos basados en el tiempo, como la determinación de duraciones o el prorrateo de costes.")
