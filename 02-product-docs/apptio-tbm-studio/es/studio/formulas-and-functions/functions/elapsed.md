---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Función transcurrido"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/elapsed.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Función transcurrido

Calcula el tiempo transcurrido entre dos fechas en segundos, teniendo en cuenta opcionalmente los periodos excluidos y ofreciendo una salida formateada.

## Sintaxis

`Elapsed(startDate, endDate [, "format" [, exclusionTable [, startCol,
endCol]]])`

## Parámetros

- **fechaInicio** : Una expresión que se evalúa a la fecha y hora de inicio. Debe estar en un formato fecha-hora reconocido (por ejemplo, 'MM/DD/AAAA HH:MM'). Nota: Este parámetro acepta una expresión, lo que significa que puede proporcionar un valor literal, una referencia de columna o el resultado de otra función. Obligatorio
- **endDate** : Una expresión que se evalúa a la fecha y hora de finalización. Debe estar en un formato fecha-hora reconocido. Nota: Este parámetro acepta una expresión, lo que significa que puede proporcionar un valor literal, una referencia de columna o el resultado de otra función. Obligatorio
- **formato** : Opcional. Si se proporciona la cadena "formato", la función devuelve el tiempo transcurrido dividido en Años, Días, Horas, Minutos y Segundos en lugar de segundos totales. Debe ser exactamente "formato" (distingue mayúsculas de minúsculas). Opcional (por defecto: devuelve el total de segundos transcurridos)
- **exclusionTable** : Opcional. Una referencia de tabla que enumera los periodos de tiempo que deben excluirse del cálculo del tiempo transcurrido. Opcional (por defecto: no se aplican exclusiones)
- **startCol** : Opcional. El nombre de la columna de la tabla de exclusión que representa el inicio del período excluido. Por defecto es "De". Opcional (por defecto: columna "De")
- **endCol** : Opcional. El nombre de la columna de la tabla de exclusión que representa el final del período excluido. Por defecto es "A". Opcional (por defecto: columna "Para")

## Comportamiento

- Calcula la diferencia entre startDate y endDate en segundos.
- Si 'format' se proporciona como una cadena literal, devuelve la salida dividida en Años, Días, Horas, Minutos y Segundos.
- Admite la exclusión de periodos de tiempo mediante una tabla de exclusión y columnas especificadas.
- Si no se indican startCol y endCol, se utilizarán por defecto las columnas "De" y "A" de la tabla de exclusión.

## Tipo de retorno

Número

## Cuadro de exclusiones

Para calcular tramos de tiempo que excluyan las horas no laborables, las vacaciones, etc, la función se basa en una tabla de exclusiones definida como conjunto de datos en su proyecto Apptio. A continuación figura un ejemplo de cuadro de exclusiones. La columna Descripción es ignorada por la función.

| De | Para | Descripción |
| --- | --- | --- |
| 00:00 Sábado | 00:00 Lunes | No incluye fines de semana |
| 16:00 | 08:00 | El horario laboral estándar es de 8:00 A.M. a 4:00 P.M. |
| 1/1/2009 00:00 | 1/2/2009 00:00 | Año Nuevo |
| 18/01/2009 00:00 | 19/01/2009 00:00 | Día de MLK |
| 15/02/2009 00:00 | 16/02/2009 00:00 | Día de los Presidentes |
| 4/6/2009 00:00 | 5 de junio de 2009, 00:00 | 4 de julio |
| 25/12/2009 00:00 | 26/12/2009 00:00 | Navidad |

## Ejemplos

- `Elapsed("04/23/2010 08:00", "04/23/2010 10:00")`

  Devuelve el número de segundos transcurridos entre las 8:00 AM y las 10:00 AM del 23 de abril de 2010.
- `Elapsed(DateSubmitted, DateFirstResponse)`

  Calcula el tiempo transcurrido entre la fecha de envío y la fecha de la primera respuesta.
- `Elapsed("04/23/2010 18:00", "04/26/2010 11:00", Exclusions, From,
  To)`

  Calcula el tiempo transcurrido excluyendo los periodos definidos en la tabla "Exclusiones".
- `Elapsed("04/23/2010 18:00", "04/26/2010 11:00", "format")`

  Devuelve el tiempo transcurrido formateado como Años, Días, Horas, Minutos y Segundos.
- `Elapsed("04/23/2010 18:00", "04/26/2010 11:00", "format", Exclusions, From,
  To)`

  Devuelve el tiempo transcurrido formateado, excluyendo los periodos definidos en la tabla "Exclusiones".

Nota:

- Todos los valores de fecha y hora deben proporcionarse en formatos reconocidos.
- El argumento "formato" debe introducirse exactamente como la cadena "formato".
- Al especificar una tabla de exclusión, se pueden personalizar opcionalmente las columnas inicial y final.
- Si se utiliza la tabla de exclusión pero no se especifica startCol y endCol, se asume "De" y "A".
