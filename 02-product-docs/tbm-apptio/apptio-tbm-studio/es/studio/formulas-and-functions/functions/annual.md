---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Función anual"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/annual.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Función anual

Devuelve un valor para la métrica especificada ajustado hacia delante o hacia atrás en un número de años, en función del tipo de calendario seleccionado.

## Sintaxis

`Annual(metric, delta, calendarType)`

## Parámetros

*métrica* : El nombre de la métrica que desea ajustar. Opcional.

*delta* : Opcional. El número de años que hay que mirar hacia delante (valor positivo) o hacia atrás (valor negativo). Si no se especifica, el valor por defecto es 0.

*calendarType* : Opcional. El sistema de calendario a utilizar. Los valores admitidos son "FY" para Año Fiscal (por defecto) y "CY" para Año Natural. Si no se especifica, el valor por defecto es "FY".

## Comportamiento

- Requiere una métrica como entrada.
- Opcionalmente, ajusta el valor en función del número de años especificado por delta.
- Utiliza el tipo de calendario especificado para determinar cómo se calculan los años.
- Si no se especifica delta, por defecto es 0 (sin ajuste).
- Si no se especifica calendarType, el valor por defecto es "FY" (año fiscal).

## Tipo de retorno

Número

## Ejemplo

El siguiente ejemplo devuelve el Coste total del año en curso.

`=Annual(Cost)`

`=Annual(Budget,0,"CY`

`Annual(Budget)`: Devuelve la métrica "Presupuesto" del ejercicio en curso.

`Annual(Budget, -1)`: Devuelve la métrica "Presupuesto" de hace un ejercicio.

`Annual(Budget, 1, "CY")`: Devuelve la métrica "Presupuesto" para el próximo año natural.

Nota:

- El parámetro delta debe ser un valor numérico como 0, 1 o -1.
- Utilice "FY" (año fiscal) para los calendarios fiscales de 445 variantes y 13 períodos.
- Utilice "CY" (año civil) para los calendarios gregorianos estándar.
