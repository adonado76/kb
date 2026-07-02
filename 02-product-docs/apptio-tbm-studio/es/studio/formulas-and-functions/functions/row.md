---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Función fila"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/row.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Función fila

Devuelve el índice de la fila actual de la tabla, empezando por cero para la primera fila.

## Sintaxis

```
Row()
```

## Parámetros

Ninguna

## Comportamiento

Evalúa al índice basado en cero de la fila actual dentro de la tabla. La primera fila tiene el número 0, la segunda el 1, y así sucesivamente.

## Tipo de retorno

Número

**Observaciones**

Esta función sólo puede hacer referencia a la tabla actual, no a tablas externas.

Tenga en cuenta que **no** se recomienda utilizar la función Fila como parte de una fórmula que genere una columna de clave primaria en una tabla. Si se cargan nuevos datos en la tabla, las filas, y por tanto las claves primarias, pueden cambiar y dar lugar a asignaciones inexactas basadas en la clave.

## Ejemplo

`=Row()`: Devuelve 0 para la primera fila, 1 para la segunda y así sucesivamente.
