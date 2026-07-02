---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "IsNumeric función"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/isnumeric.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# IsNumeric función

Evalúa una expresión para determinar si es un número válido, devolviendo 'verdadero' o 'falso' como cadena.

## Sintaxis

*IsNumeric("value")*

o

*IsNumeric({column nombre})*

`IsNumeric(expression)`

## Parámetros

*valor*

La cadena a evaluar. Debe ir entre comillas.

*{column name}*

Nombre de una columna de una tabla.

## Comportamiento

- Comprueba si la expresión proporcionada se evalúa como un valor numérico.
- Devuelve la cadena 'true' si el valor es un número.
- Devuelve la cadena 'false' si el valor no es un número.
- Puede evaluar tanto cadenas entrecomilladas como referencias a columnas.
- Ignora caracteres no numéricos como '%' al determinar la validez numérica.

## Tipo de retorno

La función devuelve un booleano **verdadero** o **falso**.

## Observaciones

Puede utilizar la función dentro de la función IF en ambos lados de la ecuación y en la función STATUSICON.

Por ejemplo:

```
IF(IsNumeric("423"),"OK","Check for
        error.")
```

`STATUSICON(IsNumeric("123"), LEN(TRIM(" hello ")) = 5 )`

## Ejemplos

Los siguientes ejemplos se muestran con sus valores de retorno.

- `IsNumeric("95")` = verdadero
- `IsNumeric("95%")`= verdadero
- `IsNumeric("95 Percent")` = falso
- `IsNumeric({Location})` = falso
- `IsNumeric({345})`= verdadero

Nota: Utilice comillas entre las cadenas literales cuando evalúe valores constantes. Cuando utilice nombres de columnas, enciérrelos entre llaves { }.
