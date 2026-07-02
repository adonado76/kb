---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Función de potencia"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/power.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Función de potencia

Eleva un número base especificado a la potencia de un exponente especificado, realizando un cálculo exponencial.

## Sintaxis

`Power(base, exponent)`

## Parámetros

*base* : El valor de la base numérica que se elevará a una potencia. Nota: Este parámetro acepta una expresión, lo que significa que puede proporcionar un valor literal, una referencia de columna o el resultado de otra función. Obligatorio

*exponente* : El exponente numérico al que se elevará la base. Nota: Este parámetro acepta una expresión, lo que significa que puede proporcionar un valor literal, una referencia de columna o el resultado de otra función. Obligatorio

## Comportamiento

- Eleva la base a la potencia del exponente (es decir, base^exponente).
- Maneja exponentes positivos y negativos, incluyendo valores fraccionarios.
- Devuelve un resultado decimal (doble) independientemente de si las entradas son enteros o flotantes.

## Tipo de retorno

Número

## Ejemplo

El siguiente ejemplo eleva 2 a la 3ª potencia, lo que devuelve 8.: `=Power(2,3)`

`Power(5, 0)`: Devuelve 1 porque cualquier número elevado a la potencia 0 es 1.

`Power({CPU Count}, 2)`: Eleva al cuadrado el valor de la columna {CPU Count}.

Nota: Una base de 0 con un exponente negativo no está definida y dará lugar a un error.
