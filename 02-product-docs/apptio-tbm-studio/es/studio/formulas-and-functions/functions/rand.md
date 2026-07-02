---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Función Rand"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/rand.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Función Rand

Genera un número decimal aleatorio entre 0.0 (inclusive) y 1.0 (exclusive).

## Sintaxis

```
Rand()
```

## Parámetros

Ninguna

## Comportamiento

Cada vez que se evalúa la función, produce un nuevo número pseudoaleatorio. Devuelve un número en coma flotante mayor o igual que 0.0 y menor que 1.0.

## Tipo de retorno

Número

## Ejemplo

`Rand()`

Algunos posibles valores de retorno son:

- 0.354
- 0.515
- 0.034

`Rand() * 100`: Genera un porcentaje aleatorio entre 0 y 100.

Nota:

Dado que esta función devuelve un resultado diferente cada vez que se recalcula, los resultados pueden variar entre evaluaciones.
