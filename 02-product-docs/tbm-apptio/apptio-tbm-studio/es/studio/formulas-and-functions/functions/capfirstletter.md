---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "CapFirstLetter función"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/capfirstletter.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# CapFirstLetter función

Pone en mayúsculas la primera letra de cada palabra del argumento de cadena y en minúsculas todas las demás letras.

## Sintaxis

`CapFirstLetter(text)`

## Parámetros

*texto* : Un valor de cadena o una expresión que se evalúa a una cadena. Puede incluir texto estático, referencias a columnas u otras fórmulas que produzcan cadenas. Opcional

## Comportamiento

- Cada palabra de la cadena de entrada tendrá su primer carácter convertido a mayúsculas.
- Todos los demás caracteres de cada palabra se convertirán a minúsculas.
- Las palabras suelen ir separadas por espacios o signos de puntuación.

## Tipo de retorno

Serie

## Ejemplo

- `CapFirstLetter("hello world")`: Devuelve "Hola Mundo"
- `CapFirstLetter(User Name)`: Pone en mayúsculas la primera letra de cada palabra en el campo UserName.
- `CapFirstLetter("tHiS is a tEsT")`: Devuelve "Esto es una prueba".

Nota: útil para dar formato a nombres, títulos u otros campos de texto para que sigan las convenciones de mayúsculas y minúsculas. Si la entrada ya sigue la mayúscula deseada, el resultado no cambia.
