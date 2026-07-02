---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Función horas"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/hours.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Función horas

Convierte un valor de fecha en el número de horas transcurridas desde el 1 de enero de 1970, como valor numérico.

## Sintaxis

`Hours(date_expression, date_format)`

## Argumentos

- *expresión\_fecha* : La fecha a convertir. El formato debe ser un formato de fecha compatible. Nota: Este parámetro acepta una expresión, lo que significa que puede proporcionar un valor literal, una referencia de columna o el resultado de otra función. Obligatorio.
- *formato\_fecha* : El formato de la cadena de fecha. Obligatorio sólo si la expresión\_fecha no está en un formato estándar admitido. Opcional

## Tipo de retorno

Número

## Ejemplo

Suponga que tiene la siguiente tabla:

| Fuente del billete | Fecha de Envío |
| --- | --- |
| Preventa | 2/2/2010 17:38 |
| CS | 10/3/2010 9:41 |
| Productos | 9/3/2010 13:14 |

Se crea una tercera columna llamada Horas utilizando la siguiente función:

`=Hours(Date Submitted)`

El resultado es la siguiente tabla:

| Fuente del billete | Fecha de Envío | Horas |
| --- | --- | --- |
| Preventa | 2/2/2010 17:38 | 351425.633 |
| CS | 10/3/2010 9:41 | 352281.683 |
| Productos | 9/3/2010 13:14 | 352261.233 |

`Hours("2/2/2010 17:38")`

Devuelve el número de horas transcurridas desde el 1 de enero de 1970 para la fecha y hora dadas.

Nota: Si la fecha de entrada tiene un formato no estándar, utilice el parámetro date\_format para especificar el formato correcto. Consulte las reglas de formato en la función DateFormat.

## Comportamiento

- Toma una entrada de fecha y la convierte en un valor numérico que representa las horas transcurridas desde la época (1 de enero de 1970).
- Si no se proporciona date\_format, la aplicación asume que la entrada está en un formato estándar compatible.
- El resultado es útil para realizar operaciones aritméticas o comparaciones con otros valores temporales.
