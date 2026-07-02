---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Función Mod"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/mod.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Función Mod

Divide un número entre otro y devuelve el resto, conservando el signo del dividendo (primer número).

## Sintaxis

`Mod(number, divisor)`

## Parámetros

*número* : El número a dividir. Es el dividendo en la operación módulo. Nota: Este parámetro acepta una expresión, lo que significa que puede proporcionar un valor literal, una referencia de columna o el resultado de otra función. Obligatorio

*divisor* : El número por el que se divide el dividendo. Nota: Este parámetro acepta una expresión, lo que significa que puede proporcionar un valor literal, una referencia de columna o el resultado de otra función. Obligatorio

## Comportamiento

- Devuelve el resto de dividir el primer número por el segundo.
- El signo del resultado siempre coincide con el signo del dividendo (el primer número), independientemente del signo del divisor.
- Admite valores decimales tanto en el dividendo como en el divisor.

## Tipo de retorno

Número

## Ejemplos

El signo del resultado siempre coincide con el signo del primer número, no con el signo del divisor.

| Función | Resultado |
| --- | --- |
| =Mod(5,3) | 2 - 5 dividido por 3 es 1 con un resto de 2. |
| =Mod(4,2) | 0 - 4 dividido a partes iguales entre 2. |
| =Mod(7,-3) | 1 - el signo del resultado sigue el dividendo (7). |
| =Mod(-7,3) | -1 - el signo del resultado sigue al dividendo (-7) |
| =Mod(-7,-3) | -1 - ambos números son negativos; el resultado mantiene el signo de -7. |
| =Mod(7, 2.25 ) | 0.25 - 7 dividido por 2.25 es 3 con un resto de 0.25. |

Nota: Mod se utiliza a menudo para recorrer valores, identificar números pares o impares, o segmentar datos. El resultado de Mod tiene el mismo signo que el primer argumento (el dividendo).
