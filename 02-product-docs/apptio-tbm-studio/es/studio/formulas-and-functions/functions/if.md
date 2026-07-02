---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Si la función"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/if.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Si la función

Evalúa una expresión de filtro y devuelve un valor si es verdadero y otro si es falso. Admite operaciones AND y OR en la condición.

## Sintaxis

`If(filter_expression, true_expression, false_expression)`

## Argumentos

*expresión\_filtro* : La condición a evaluar. Admite operadores lógicos como AND, OR y operadores de comparación (=,!=, <, >, <=, >=, IN, NOT IN). Nota: Este parámetro acepta una expresión, lo que significa que puede proporcionar un valor literal, una referencia de columna o el resultado de otra función. Obligatorio

*expresión\_verdadera* : El valor a devolver si la expresión\_filtro evalúa a true. Nota: Este parámetro acepta una expresión, lo que significa que puede proporcionar un valor literal, una referencia de columna o el resultado de otra función. Obligatorio

*expresión\_falsa* : El valor a devolver si la expresión\_filtro se evalúa como falsa. Nota: Este parámetro acepta una expresión, lo que significa que puede proporcionar un valor literal, una referencia de columna o el resultado de otra función. Obligatorio

## Comportamiento

- Evalúa la condición dada (expresión\_filtro).
- Si la condición se evalúa como verdadera, devuelve el resultado de la expresión\_verdadera.
- Si la condición se evalúa como falsa, devuelve el resultado de la expresión\_falsa.
- Se admiten operaciones lógicas como AND y OR, con AND evaluado antes que OR a menos que se anule mediante paréntesis.
- Admite el anidamiento de funciones If unas dentro de otras para una lógica más compleja.
- Soporta la mayoría de las funciones dentro de la sentencia If, pero no soporta las funciones LookupEx, TableMatch, o External Data Lookup.

## Tipo de retorno

Depende del tipo de retorno de expresión\_verdadera o expresión\_falsa (cadena, número o fecha).

## Ejemplos

- El siguiente ejemplo devuelve 1 si la columna Tipo contiene la cadena Int, en caso contrario devuelve el valor de la columna NumCPU :`=If(Type="Int",1,NumCPU)`
- El siguiente ejemplo devuelve "sí" si la Columna B es igual a 100 y la Columna C es igual a "hola", o la Columna A es mayor que cero. En caso contrario, devuelve "no"

  ```
  If(colA > 0 OR colB = 100 AND colC = “hello”,
                “yes”, “no”)
  ```
- El siguiente ejemplo examina el campo Tipo de la tabla Horas de Consultoría para determinar si las horas son facturables. Si lo son, devuelve el número de horas introducidas en la columna Horas. Si las horas no son facturables, devuelve un cero.

  ```
  =If({Consulting
                Hours.Type}="Billable",{Consulting Hours.Hours},0)
  ```
- El siguiente ejemplo realiza un simple cálculo de pago de horas extras:

  ```
  =If(Hours>40,Rate*40+Overtime
                Rate*(Hours-40),Rate*Hours)
  ```
- El siguiente ejemplo selecciona un programa navegador en función del sistema operativo:`=If(OS_Type="Windows","Internet Explorer","Firefox")`
- El siguiente ejemplo devuelve 0 cuando es nulo y 1 en caso contrario:`=If(IsDataPresentHere="",0,1)`
- El siguiente ejemplo muestra un If anidado:`=If(a=b,If(c=d,q,p),z)`
- El siguiente ejemplo calcula el valor absoluto:`=If(x<0,x*(-1),x)`
- El siguiente ejemplo devolvería un valor de 1:

  ```
  =If(Trim("Baskets ") = Pluralize("Basket"), 1, 0
                )
  ```
- El siguiente ejemplo devolvería "true" si un número de teléfono móvil no es uno de los especificados:

  ```
  =IF(Wireless Number NOT IN
                ("202-321-4143","310-697-9064"),"true","false")
  ```

Nota:

- Si se encuentra escribiendo una sentencia If anidada muy compleja, considere utilizar la función TableMatch en su lugar.
- Las funciones pueden utilizarse dentro de las condiciones If y los resultados, excepto para LookupEx, TableMatch, y External Data Lookup.
- Para las comparaciones en blanco, utilice "" en lugar de la palabra clave EN BLANCO.
