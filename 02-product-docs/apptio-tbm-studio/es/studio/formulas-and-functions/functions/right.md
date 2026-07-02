---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Función derecha"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/right.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Función derecha

Devuelve el número especificado de caracteres desde el final (lado derecho) de una cadena, incluidos los espacios en blanco.

## Sintaxis

`Right(string[, count])`

## Argumentos

*cadena* : La cadena de la que extraer caracteres de la derecha. Nota: Este parámetro acepta una expresión, lo que significa que puede proporcionar un valor literal, una referencia de columna o el resultado de otra función. Obligatorio

*count* : El número de caracteres a devolver desde la izquierda. Si el valor es una cadena, se convertirá en un número. Si la conversión falla, el valor por defecto es 0. Opcional (por defecto: 1). Un número entero que especifica el número de caracteres que se devolverán. Si no se especifica este argumento, por defecto es 1. Si este argumento se evalúa como una etiqueta o cadena, el sistema intentará convertirlo en un número. Si no puede, el valor será cero.

## Comportamiento

- Extrae los caracteres empezando por la derecha de la cadena de entrada.
- Devuelve exactamente el número de caracteres especificado por el parámetro count.
- Si el recuento es mayor que la longitud de la cadena, se devuelve la cadena completa.
- Si se omite count, se devuelve 1 carácter por defecto.

## Tipo de retorno

Serie

## Ejemplos

| Función de ejemplo | Valor de retorno |
| --- | --- |
| =Derecha("123456", 3) | 456 |
| =Derecha("123456", 1) | 6 |
| =Derecha("123456") | 6 |
| =Derecha("Me gusta la tarta", 3) | tarta |
| Derecha( {Hostname}, 5) | Devuelve los 5 últimos caracteres del valor de la columna {Hostname}. |
| Derecha("red") | Devuelve "k" ya que el recuento por defecto es 1. |
| Derecha("servidor", 3) | ver |
|  |  |

Nota: Los espacios en blanco se tratan como caracteres y se incluyen en el resultado.
