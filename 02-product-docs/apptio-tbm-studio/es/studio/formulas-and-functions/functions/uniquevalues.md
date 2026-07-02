---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "UniqueValues función"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/uniquevalues.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# UniqueValues función

Devuelve una lista de valores únicos en una columna.

## Dónde utilizarlo

Esta función puede utilizarse en:

- Conjuntos de datos
- Columnas de fórmulas en tablas de informes
- Texto dinámico
- Cualquier lugar donde pueda añadir una cláusula de filtrado de condiciones.

Nota: Esta función no puede colocarse en una columna de la misma tabla a la que se hace referencia en la función. Si intenta hacerlo, recibirá un mensaje de error.

## Sintaxis

`UniqueValues(table:column1,true)`

`UniqueValues(table:column1[column2=columnA],true)`

## Argumentos

*tabla:columna*

La tabla y la columna que se examinarán en busca de valores distintos. La *tabla* no puede ser la misma que la tabla actual.

*tabla:columna[ column2=columnA ]*

Si se añade un criterio de coincidencia entre corchetes [] después de la especificación tabla:columna, los valores de retorno se limitan a los valores que coinciden entre dos tablas.

*column2* es una columna de la *tabla* externa

*columnA* es una columna de la tabla actual

*verdadero*

Si se incluye este parámetro, los valores en blanco y nulos se excluirán de la lista.

Por ejemplo, supongamos que tiene los siguientes datos:

| **Coronel A** | **Coronel B** |
| --- | --- |
| F1 | A |
| F2 | B |
| F3 |  |

Si especifica =UniqueValues(ColB ), obtendrá: "null", "A", "B".

Si especifica =UniqueValues(ColB,true ), obtendrá: "A", "B".

## Tipo de retorno

Lista separada por comas de valores únicos en la columna designada.

## Ejemplo

Suponga que tiene la tabla siguiente:

| Servidor | Ubicación |
| --- | --- |
| EXCH006 | Seattle |
| EXCH010 | Boston |
| NET207 | Boston |
| STOR124 | Seattle |
| STOR250 | Boston |
| STOR350 | Denver |

La siguiente función, si se ejecuta contra la tabla Servidores anterior, devuelve tres valores: Seattle, Boston, Denver.

`=UniqueValues(Servers:Location)`

Otra aplicación de esta función es devolver una lista de direcciones de correo electrónico concatenadas a partir de una columna de una tabla para utilizarla con la API SendMail Apptio Script.
