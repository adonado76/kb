---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Función trimestral"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/quarter.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Función trimestral

Devuelve el valor total de una métrica especificada en la misma tabla para un trimestre especificado, sumando los valores de todo el trimestre. Si no se especifica ningún trimestre, la función se evalúa para el trimestre actual. Esta función devuelve el total de todo el trimestre independientemente del mes en el que se visualice.

## Sintaxis

`Quarter(metric[,delta[,type]])`

## Parámetros

- *métrica* : Una métrica en la misma tabla. La función devuelve la suma de esta métrica para todo el trimestre.
- *delta* : El número de trimestres a desplazar respecto al trimestre actual. Utilice números negativos para mirar hacia atrás (por ejemplo, -2 para hace dos trimestres). Por defecto 0 (trimestre actual). Opcional (por defecto: 0)
- *tipo* : Especifica si el trimestre se basa en el año fiscal (`FY`) o en el año natural (`CY`). Por defecto `FY`. Debe proporcionarse como una cadena literal. Opcional (por defecto: "FY")

## Comportamiento

- Calcula el valor total de la métrica especificada para el trimestre completo.
- Admite los tipos de trimestre fiscal y de calendario, en función de la configuración del conjunto de datos.
- Por defecto, el trimestre fiscal actual si no se proporciona ningún delta o tipo.
- Devuelve siempre el valor del trimestre completo, independientemente del mes a partir del cual se evalúe la función.

## Tipo de retorno

Número

## Ejemplo

El siguiente ejemplo devuelve el total de {cost} para el trimestre fiscal actual:

`=Quarter(Cost)`

El siguiente ejemplo devuelve el total de {cost} para el siguiente trimestre fiscal:

`=Quarter(Cost,1)`

Devuelve el total de {Cost} de hace dos trimestres naturales.

`Quarter(Cost, -2, "CY")`

Nota: Utilice el tipo FY para calendarios fiscales (incluidos los tipos de 4-4-5 o 13 períodos) y CY para estructuras de calendario gregoriano. Si no hay datos para el trimestre especificado, la función devuelve 0 o null dependiendo de la completitud de los datos.
