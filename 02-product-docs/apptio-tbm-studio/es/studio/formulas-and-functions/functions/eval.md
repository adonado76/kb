---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Función de evaluación"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/eval.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Función de evaluación

**Se aplica a** : TBM Studio 12.0 y posteriores

Toma una cadena que parece una expresión y la evalúa como si fuera una expresión.

## Dónde utilizarlo

Esta función puede utilizarse en:

- Columnas de fórmulas en tablas de informes
- Texto dinámico

## Dónde NO utilizar:

- Transformaciones - utilice la función [DynamicColumn](dynamic-column.htm "(se abre en una pestaña o una ventana nueva)") en su lugar.

## Sintaxis

`Eval(string)`

## Argumentos

*serie*

Una cadena parecida a una expresión.

## Ejemplo

El siguiente ejemplo devuelve 12.

`Eval("=24/2")`

Para maximizar las mejoras en el rendimiento de calc de la nueva función "cálculos de precisión", la funcionalidad de la función Eval() se sustituye por DynamicColumn( ) u otros cambios en el código. Los clientes que aún tengan Eval() en la configuración de su proyecto, pueden realizar los cambios necesarios utilizando el documento de [código de sustitución de OOTB Eval(](../updated-eval-formulas.htm "(se abre en una pestaña o una ventana nueva)") ) que contiene información de todos los informes y cambios métricos.

Nota: Si ha modificado los informes OOTB, no se eliminará Eval() de los informes de plantillas anteriores (por ejemplo, v104, v105, v106. v107 ). Véase también, [DynamicColumn](dynamic-column.htm "(se abre en una pestaña o una ventana nueva)")
