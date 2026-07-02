---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "SumIf función"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/sumif.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# SumIf función

Devuelve la suma de los valores de una columna, incluyendo sólo las filas que coinciden con los criterios especificados. Útil para calcular totales agrupados basados en lógica condicional.

## Sintaxis

`SumIf(key_column, criteria, sum_range)`

## Parámetros

*columna\_clave* : La columna utilizada para asignar valores para la suma. Agrupa los datos y determina cómo se estructuran los resultados. Obligatorio

*criterios* : El valor o columna utilizado para filtrar las filas para la suma. Determina qué filas del rango\_suma se incluyen. Nota: Este parámetro acepta una expresión, lo que significa que puede proporcionar un valor literal, una referencia de columna o el resultado de otra función. Obligatorio

*rango\_suma* : La columna que contiene los valores a sumar. Nota: Este parámetro acepta una expresión, lo que significa que puede proporcionar un valor literal, una referencia de columna o el resultado de otra función. Obligatorio

## Tipo de retorno

Número

**Notas** :

Al utilizar la función SumIf en una transformación filtrada, ésta incluirá los valores filtrados en su suma. La solución consiste en filtrar la tabla, crear una transformación a partir de ella y, a continuación, crear la función SumIf en la nueva tabla.

## Ejemplos

SumIf(Region, Región, Peso): Suma los valores de Peso de cada región y los muestra en una tercera columna.

Suponga que tiene la siguiente tabla:

| Región | peso |
| --- | --- |
| Continente americano | 10 |
| Continente americano | 20 |
| Europa | 30 |
| Continente americano | 40 |
| Australia | 50 |
| Australia | 60 |

Desea sumar los valores de cada una de las regiones y mostrarlos en una tercera columna como se muestra a continuación:

Para ello, añada la columna Suma a la transformación de la tabla e introduzca la siguiente ecuación en el campo Valor:

SumIf(Region, Región, Peso)

Si introduce "Región" como criterio, la aplicación evaluará todas las entradas de la columna Región.

| Región | peso | Suma |
| --- | --- | --- |
| Continente americano | 10 | 70 |
| Continente americano | 20 | 70 |
| Europa | 30 | 30 |
| Continente americano | 40 | 70 |
| Australia | 50 | 110 |
| Australia | 60 | 110 |

`SumIf(Region, "Americas", Weight)`

Añade sólo los valores de las Américas.

Supongamos ahora que desea añadir sólo los valores de las Américas. Se utilizaría la siguiente ecuación:

SumIf(Region, "Américas", Peso)

El resultado:

| Región | peso | Suma |
| --- | --- | --- |
| Continente americano | 10 | 70 |
| Continente americano | 20 | 70 |
| Europa | 30 | 70 |
| Continente americano | 40 | 70 |
| Australia | 50 | 70 |
| Australia | 60 | 70 |
