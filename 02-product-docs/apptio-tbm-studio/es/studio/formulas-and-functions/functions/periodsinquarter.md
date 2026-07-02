---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "PeriodsInQuarter función"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/periodsinquarter.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# PeriodsInQuarter función

**Se aplica a** : TBM Studio y posteriores

Devuelve el número de periodos del primer, segundo, tercer o cuarto trimestre.

## Dónde utilizarlo

Esta función puede utilizarse en:

- Conjuntos de datos
- Columnas de fórmulas en tablas de informes
- Texto dinámico

## Sintaxis

`PeriodsInQuarter(quarter)`

## Argumentos

*trimestre*

El número del trimestre, ya sea 1, 2, 3 o 4.

## Tipo de retorno

Serie

## Ejemplo

Dado un proyecto de 13 periodos con el tercer trimestre teniendo cuatro periodos, y el selector de calendario establecido en P10 FY2013, la siguiente función devuelve los resultados que se muestran a continuación:

| Función | Volver |
| --- | --- |
| PeriodsInQuarter(1) | 3 |
| PeriodsInQuarter(2) | 3 |
| PeriodsInQuarter(3) | 4 |
| PeriodsInQuarter(4) | 3 |
