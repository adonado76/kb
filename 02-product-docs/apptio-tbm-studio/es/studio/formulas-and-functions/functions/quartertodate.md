---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "QuarterToDate función"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/quartertodate.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# QuarterToDate función

Devuelve el valor acumulado de una métrica especificada desde el comienzo del trimestre fiscal en curso hasta el período actual inclusive.

El trimestre actual es el trimestre fiscal definido en el cuadro de diálogo **Configurar periodos de tiempo**, independientemente de la selección de fecha actual en el selector de fecha. El número de trimestres sumados será 1, 2, 3 ó 4 dependiendo del trimestre actual.

## Sintaxis

`QuarterToDate(metric)`

## Parámetros

*métrica* : La columna métrica cuyos valores se sumarán desde el inicio del trimestre actual hasta el periodo actual. Debe referirse a una columna de la misma tabla. Obligatorio

## Comportamiento

- Suma los valores de la métrica especificada desde el inicio del trimestre fiscal actual hasta el período seleccionado actualmente.
- La estructura del trimestre fiscal se define en la configuración de Periodos de tiempo, no se basa en el selector de fechas del calendario.

## Tipo de retorno

Número

## Ejemplo

El siguiente ejemplo devuelve la suma de la métrica {Cost} desde el inicio del trimestre actual hasta el periodo actual.

`=QuarterToDate(Cost)`
