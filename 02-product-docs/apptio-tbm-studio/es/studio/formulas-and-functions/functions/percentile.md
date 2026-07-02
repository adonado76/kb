---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Función percentil"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/percentile.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Función percentil

Devuelve el valor de percentil especificado para una columna numérica dada. Un percentil representa el valor por debajo del cual se sitúa un determinado porcentaje de los datos.

Devuelve un percentil especificado para una columna especificada.

Para un conjunto dado de números, un percentil es el valor por debajo del cual cae un determinado porcentaje de los números. Por ejemplo, para una columna que contiene 0, 1, 2, 3, 4, 5, 6, 7, 8 y 9, el percentil 30 es 2.3, que es el valor por debajo del cual cae el 30 por ciento de los números (0,1,2). El valor decimal.3 del resultado se obtiene tomando el valor que está a un 30% de distancia entre 2 y 3.

## Sintaxis

`Percentile([rollup_operator]column,percentage)`

## Argumentos

*operador\_rollup*

@, SOURCE, ~, o TARGET. Este argumento es opcional y sólo se utiliza con métricas. Véase [Operadores Rollup](../operators.html "Se aplica a: TBM Studio 12.0 y posteriores").

*columna* : La columna numérica a partir de la cual evaluar el percentil. Nota: Este parámetro acepta una expresión, lo que significa que puede proporcionar un valor literal, una referencia de columna o el resultado de otra función. Obligatorio

*porcentaje* : Valor numérico que representa el umbral del percentil (por ejemplo, 50 para la mediana, 90 para el percentil 90). Nota: Este parámetro acepta una expresión, lo que significa que puede proporcionar un valor literal, una referencia de columna o el resultado de otra función. Obligatorio

## Comportamiento

Devuelve el valor por debajo del cual cae el porcentaje de datos especificado. Interpola entre valores cuando la posición exacta del percentil cae entre dos puntos de datos.

## Tipo de retorno

Número

## Ejemplo

El siguiente ejemplo devuelve el percentil 50 para los valores que contribuyen al rollup en la columna Servidores. Si Servidores en la tabla de origen contiene: 500, 600, 700 y 1200, este ejemplo devuelve 650.

`=Percentile(Servers,50)`: Devuelve la mediana (percentil 50) de los valores de la columna {Servers}.

`=Percentile(Sales,90)`: Devuelve el valor del percentil 90 de la columna {Sales}.

Nota: El resultado del percentil puede incluir un decimal si se requiere interpolación entre dos valores. El porcentaje debe ser un número entre 0 y 100.
