---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Función de sustitución"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/substitute.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Función de sustitución

Busca en una cadena de destino especificada la presencia de una cadena de búsqueda especificada. Si se encuentra la cadena buscada, la sustituye por una cadena de sustitución especificada.

## Sintaxis

`Substitute(target_string, search_string, replacement_string)`

## Parámetros

*cadena\_objetivo* : La cadena en la que buscar y realizar el reemplazo. Nota: Este parámetro acepta una expresión, lo que significa que puede proporcionar un valor literal, una referencia de columna o el resultado de otra función. Obligatorio

*cadena\_buscada* : La subcadena a buscar dentro de la cadena de destino. Nota: Este parámetro acepta una expresión, lo que significa que puede proporcionar un valor literal, una referencia de columna o el resultado de otra función. Obligatorio

*cadena\_de\_sustitución* : La cadena a utilizar como reemplazo para cada ocurrencia de la cadena de búsqueda. Nota: Este parámetro acepta una expresión, lo que significa que puede proporcionar un valor literal, una referencia de columna o el resultado de otra función. Obligatorio

## Comportamiento

- Sustituye todas las apariciones de la cadena de búsqueda dentro de la cadena de destino por la cadena de sustitución.
- Se distingue entre mayúsculas y minúsculas.
- Si no se encuentra la cadena buscada, se devuelve la cadena original sin cambios.

## Tipo de retorno

Serie

## Ejemplo

El siguiente ejemplo busca todas las apariciones de **servidor virtual** y sustituye **virtual** por **físico**.

`=Substitute("virtual server", "virtual", "physical")`

El siguiente ejemplo busca comillas simples y las sustituye por nada, eliminando esencialmente las comillas simples de la cadena. Esto puede ser útil si está importando datos de Excel y algunas de las entradas, pero no todas, tienen una comilla simple inicial.

`=Substitute(Billing
ID,"'","")`

`Substitute({Server Type}, "legacy", "modern")`: Sustituye "legacy" por "modern" en todos los valores de la columna {Server Type}.

Nota: Utilice Sustituir para normalizar texto o reemplazar subcadenas no deseadas en tareas de preparación o formateo de datos. La sustitución afecta a todas las coincidencias, no sólo a la primera.
