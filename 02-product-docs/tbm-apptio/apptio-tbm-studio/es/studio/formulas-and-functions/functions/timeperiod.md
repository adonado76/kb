---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "TimePeriod función"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/timeperiod.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# TimePeriod función

Devuelve el valor de una métrica especificada al comienzo de un período de tiempo (por ejemplo, mes, trimestre, año) que es un número especificado de períodos antes o después del período actual. La unidad de tiempo viene determinada por la vista seleccionada o por un sufijo de granularidad explícito.

## Sintaxis

`TimePeriod(metric, offset)`

## Parámetros

- **metric** : La columna métrica de la que recuperar valores para una unidad de tiempo anterior o futura. Debe referirse a una columna de la misma tabla. Obligatorio
- **desplazamiento** : un desplazamiento numérico combinado con un sufijo de unidad de tiempo opcional (por ejemplo, «m», «q», «h», «y») que indica cuántos períodos se debe desplazar. Los valores negativos se desplazan hacia atrás; los positivos, hacia delante. Si no se proporciona ningún sufijo, la unidad utiliza por defecto meses. Obligatorio

## Comportamiento

- Devuelve el valor de la métrica al comienzo del período resuelto en el desplazamiento especificado.
- La unidad de tiempo viene determinada por el sufijo ('m' para mes, 'q' para trimestre, 'h' para semestre, 'y' para año), o por defecto el mes si se omite.

## Ejemplos

- `TimePeriod(Sales, -6)`: Devuelve el valor de un {Sales} e al comienzo del período hace 6 meses. La unidad es el mes por defecto.
- `TimePeriod(Sales, -3q)`: Devuelve el valor de un {Sales} e al comienzo del período de hace tres trimestres.
- `TimePeriod(Sales, -1y)`: Devuelve el valor de un {Sales} e al comienzo del período hace un año.

Nota: Los sufijos de granularidad válidos incluyen "m" (mes), "q" (trimestre), "h" (semestre) e "y" (año).

## Tipo de retorno

Número
