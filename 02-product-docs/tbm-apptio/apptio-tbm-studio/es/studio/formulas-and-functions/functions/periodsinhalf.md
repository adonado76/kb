---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "PeriodsInHalf función"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/periodsinhalf.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# PeriodsInHalf función

**Se aplica a** : TBM Studio y posteriores

Devuelve el número de periodos en la primera o segunda mitad del año.

## Dónde utilizarlo

Esta función puede utilizarse en:

- Conjuntos de datos
- Columnas de fórmulas en tablas de informes
- Texto dinámico

## Sintaxis

`PeriodsInHalf(half)`

## Argumentos

*Medio*

El número de la mitad, 1 ó 2 para la primera o la segunda mitad.

## Tipo de retorno

Serie

## Ejemplo

Dado un proyecto de 13 periodos, y el periodo fijado en P10 FY2013, la siguiente función devuelve los resultados que se muestran a continuación.

| Función | Volver |
| --- | --- |
| PeriodsInHalf(1) | 6 |
| PeriodsInHalf(2) | 7 |
