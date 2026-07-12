---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Función de búsqueda"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/find.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Función de búsqueda

Devuelve la posición de la primera aparición de una cadena de búsqueda dentro de otra cadena, comenzando en una posición opcional. Esta función distingue entre mayúsculas y minúsculas.

Buscar es lo mismo que [Buscar](search.html), con la diferencia de que distingue entre mayúsculas y minúsculas.

## Sintaxis

`Find(search_string, in_string, [starting_position])`

## Parámetros

- *cadena\_buscada* : La subcadena a buscar. Nota: Este parámetro acepta una expresión, lo que significa que puede proporcionar un valor literal, una referencia de columna o el resultado de otra función. Obligatorio
- *cadena\_in* : La cadena en la que buscar. También puede indicar el nombre de una columna. Nota: Este parámetro acepta una expresión, lo que significa que puede proporcionar un valor literal, una referencia de columna o el resultado de otra función. Obligatorio
- *posición\_inicial* : La posición desde la que empezar a buscar (índice basado en 1). Nota: Este parámetro acepta una expresión, lo que significa que puede proporcionar un valor literal, una referencia de columna o el resultado de otra función. Opcional (por defecto: 1)

## Comportamiento

- Realiza una búsqueda de una subcadena dentro de otra cadena distinguiendo entre mayúsculas y minúsculas.
- Devuelve la posición (empezando por 1) de la primera coincidencia encontrada.
- Devuelve 0 si no se encuentra la subcadena.
- Si no se proporciona starting\_position, la búsqueda comienza desde el principio de la cadena.
- La función se comporta como Buscar, pero distingue entre mayúsculas y minúsculas.

## Ejemplos

- Buscar("Funcional", "58762 Reales Funcionales"): Devuelve 7, la posición de la subcadena "Funcional".
- Buscar("c", "58762 Reales Funcionales", 12): Devuelve 19, comenzando la búsqueda después del 12º carácter.
- Buscar("99", "58762 Reales Funcionales"): Devuelve 0, ya que "99" no se encuentra.
- LEFT(IP, Buscar(".", IP, Buscar(".", IP) + 1)): Devuelve los dos primeros octetos de una dirección IP. Por ejemplo, para ' 10.10.1.113 ' el resultado es ' 10.10 '.

Nota: La función Buscar distingue entre mayúsculas y minúsculas. Si necesita una búsqueda que no distinga entre mayúsculas y minúsculas, utilice la función Buscar. Todos los parámetros aceptan expresiones (por ejemplo, literales, columnas o funciones anidadas).

## Tipo de retorno

Número
