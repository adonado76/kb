---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Función Abs"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/abs-function.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Función Abs

Devuelve el valor absoluto de un número o expresión, eliminando cualquier signo negativo.

## Sintaxis

`Abs(expression)`

## Parámetros

**expresión** : Un valor numérico o una fórmula que se evalúa a un número. Puede incluir variables, constantes u otras funciones. Opcional

## Tipo de retorno

Número

Si el resultado de la expresión es negativo, Abs lo convierte en un número positivo. Si el resultado es positivo, no se modifica.

## Ejemplos

**Abs(-5)**

Devoluciones 5

**Abs(Suma(Presupuesto) - Suma(Coste))**

Devuelve la diferencia absoluta entre el presupuesto total y el coste

**Abs(Precio \* Cantidad)**

Devuelve el valor absoluto del producto de precio y cantidad

Nota: Puede pasar un simple número, una referencia de columna o una fórmula completa como argumento.
