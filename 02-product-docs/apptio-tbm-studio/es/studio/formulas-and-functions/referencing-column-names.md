---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Referencia a nombres de columnas"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/referencing-column-names.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Referencia a nombres de columnas

**Se aplica a** : TBM Studio 12.0 y posteriores

Los nombres de columna distinguen entre mayúsculas y minúsculas y pueden incluir espacios. Cuando se hace referencia a nombres de columnas, la mejor práctica es encerrar los nombres de columnas entre llaves, y esto es necesario cuando los nombres de columnas contienen caracteres especiales. Al hacer referencia a columnas agrupadas utilizando operadores rollup, puede hacer que una función evalúe los valores que contribuyeron al rollup, en lugar del valor rollup.

## Normas generales

A continuación se indican las reglas generales para referenciar columnas en conjuntos de datos.

| Para hacer referencia a una columna en: | Utilice este formato: |
| --- | --- |
| el mismo conjunto de datos o tabla | {column name} |
| un conjunto de datos o una tabla diferentes | {data set name}:{column name} |
| un conjunto de datos de otro proyecto del mismo ámbito | nombre del proyecto! {data set name} : {column name} |
| un conjunto de datos en un proyecto diferente en un dominio diferente | nombre de dominio:nombre del proyecto! {data set name} : {column name} |

## Referencia a nombres de columnas: caracteres especiales

En las funciones, si hace referencia a un nombre de columna que contiene caracteres especiales, debe encerrar el nombre de la columna entre llaves: { }.

La siguiente tabla enumera los caracteres especiales.

| Carácter | Nombre |
| --- | --- |
| & | Y |
| \* | Asterisco |
| @ | A la señal |
| ) | Cerrar paréntesis |
| : | Colón |
| , | Coma |
| = | Signo de igualdad |
| ! | Signo de exclamación |
| / | Barra oblicua |
| - | Guión |
| [ | Soporte izquierdo |
| ( | Paréntesis abierto |
| . | Periodo |
| + | Signo más |
| ] | Soporte derecho |
| " | Comillas dobles rectas |
| ~ | Tilde |

## Ejemplo de nombre de columna con un carácter especial

Para hacer referencia a un nombre de columna que contenga un asterisco (\*), como Horas\*Tarifa, encierre el nombre de la columna entre corchetes { } para diferenciarlo de la fórmula Horas\*Tarifa, como se muestra en el siguiente ejemplo:

`Round({Hours*Rate},2)`

También debe utilizar llaves alrededor del nombre de una columna si contiene una palabra clave (nombre de función). Por ejemplo, el nombre de columna **Diff** contiene **if**, que es el nombre de una función, por lo que debe hacer referencia a ese nombre de columna entre llaves: {Diff}.

**Práctica recomendada:** Encierre siempre los nombres de las columnas entre llaves.

## Referencia a columnas agrupadas

Cuando se hace referencia a una columna agrupada, una función evalúa el valor agregado de la agrupación. Sin embargo, anteponer una @ (arroba) al nombre de la columna, como en (@columna), hace que algunas funciones evalúen los valores que contribuyeron al rollup. La @ puede utilizarse así con las siguientes funciones: [Media](functions/average.html "Devuelve el valor medio de una columna o métrica especificada."), [Grande](functions/large.html "Devuelve el mayor valor de una columna especificada."), [Percentil](functions/percentile.html "Devuelve el valor de percentil especificado para una columna numérica dada. Un percentil representa el valor por debajo del cual se sitúa un determinado porcentaje de los datos.") y [Pequeño](functions/small.html "Devuelve el valor más pequeño de una columna especificada.").

Por ejemplo, considere las siguientes tablas. A continuación se muestra una tabla antes de la agrupación.

| c | c1 |
| --- | --- |
| a | 1 |
| a | 2 |
| a | 3 |
| b | 4 |
| b | 5 |
| b | 6 |
| c | 7 |
| c | 8 |
| c | 9 |

Agrupando los datos de la tabla anterior por la columna c se obtienen los resultados que se muestran en la tabla siguiente. La columna c1 contiene ahora las sumas de las unidades distintas de la columna c. La tabla también contiene una nueva columna llamada.Count, que contiene el número de filas de cada grupo.

| **c** | **c1** | **contar** |
| --- | --- | --- |
| a | 6 | 3 |
| b | 19 | 3 |
| c | 24 | 3 |

Si se antepone una arroba ( @ ) al nombre de la columna, determinadas funciones evaluarán los valores que han contribuido al rollup (Tabla 1) para cada agrupación. Si se llama a la función =Pequeño( @c1 ) contra la tabla agrupada (Tabla 2), se obtiene el valor más pequeño de los datos previos al rollup (Tabla 1) para cada grupo.

La siguiente tabla muestra los resultados cuando la columna c2 contiene la función =Pequeño( @c1 ).

| c | c1 | c2 | contar |
| --- | --- | --- | --- |
| a | 6 | 1 | 3 |
| b | 19 | 4 | 3 |
| c | 24 | 7 | 3 |

## Palabras reservadas

Si un nombre de columna utilizado en una fórmula coincide exactamente con las siguientes palabras, o empieza con una de las palabras seguida de un espacio, debe encerrar el nombre de columna entre paréntesis.

- si
- Entonces
- else
- final
- sub
- verdadero
- falso
- EXCLUDE

Por ejemplo:

| **Anterior** | **Nuevo** |
| --- | --- |
| sub | {sub} |
| sub A | {sub A} |
| SUB b | {SUB b} |
| fin x | {end x} |
