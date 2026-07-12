---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Función de recorte"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/trim.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Función de recorte

Elimina los espacios iniciales y finales de una cadena especificada. No elimina los espacios dentro de una cadena.

## Sintaxis

`Trim(expression[, trimUnicodeWhitespace][, additionalCharacters])`

## Parámetros

- *expresión* : La cadena a recortar. Se eliminarán los espacios en blanco iniciales y finales. Nota: Este parámetro acepta una expresión, lo que significa que puede proporcionar un valor literal, una referencia de columna o el resultado de otra función. Obligatorio
- *trimUnicodeWhitespace* : Opcional. Un valor booleano (verdadero o falso) que especifica si se recortan todos los caracteres Unicode de espacios en blanco. Si se omite, por defecto es false. Opcional (por defecto: false)
- *caracteresadicionales* : Opcional. Una cadena de caracteres adicionales para eliminar de ambos extremos de la entrada. Esto se añade a los espacios en blanco. Debe ir entre comillas dobles (por ejemplo, "\*"). Opcional

## Comportamiento

- Elimina los espacios en blanco estándar o Unicode del principio y el final de la cadena de entrada.
- No altera los espacios en blanco ni los caracteres situados dentro del cuerpo de la cadena.
- Si se especifican caracteres adicionales, éstos también se eliminan de ambos extremos de la cadena.

## Tipo de retorno

Serie

## Ejemplos

| Ejemplo Función | Valor de retorno |
| --- | --- |
| =Trim(" servidor" ) | servidor (sin espacios delante) |
| =Trim("servidor ") | servidor (sin espacios al final) |
| =Trim("servidor xyz") | servidor xyz |
| Trim( {Description}, true, "\*") | Elimina los espacios en blanco Unicode iniciales/finales y los asteriscos de los valores de la columna {Description}. |

Observe en el 3er ejemplo que no se eliminan los espacios entre el texto dentro de la cadena.
