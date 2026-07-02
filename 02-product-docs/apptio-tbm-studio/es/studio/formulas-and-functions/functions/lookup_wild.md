---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Función Lookup_Wild"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/lookup_wild.html"
images:
  - "resources/images/studio_images/studioimages/studio/aug036.png"
  - "resources/images/studio_images/studioimages/studio/aug037.png"
  - "resources/images/studio_images/studioimages/studio/aug039.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Función Lookup_Wild

Busca un valor en una tabla de búsqueda utilizando la coincidencia de patrones (expresiones regulares) en la columna coincidente y devuelve el valor correspondiente de una columna de sustitución.

## Sintaxis

```
Lookup_Wild(source_column, lookup_table, matching_column, replacement_column, leave_original_value, replace_nulls, ignore_case, default_value)
```

`Lookup_Wild(source_column,lookup_table,matching_column,replacement_column[,leave_original_value][,replace_nulls][,ignore_case])`

## Parámetros

- *columna\_fuente* : La columna de la tabla actual utilizada para buscar coincidencias. Admite varias columnas unidas con & o &&. Obligatorio
- *tabla\_de\_busqueda* : El nombre de la tabla de consulta que contiene los valores de coincidencia y sustitución. Debe ser una constante. Obligatorio
- *columna\_coincidente* : La columna de la tabla de búsqueda que se comparará con la columna de origen. Admite expresiones regulares sólo en Lookup\_Wild. Obligatorio
- *columna\_de\_sustitución* : La columna de la tabla de consulta de la que devolver el valor. Prefiérelo con '=' para seleccionar dinámicamente una columna utilizando la tabla de origen. Obligatorio
- *dejar\_valor\_original* : Devuelve el valor original de la fuente si no se encuentra ninguna coincidencia. Si es false, se devuelve en blanco. Opcional (por defecto: False)
- *replace\_nulls* : Determina el comportamiento cuando el valor de origen es nulo. Si es verdadero, intenta hacer coincidir un valor nulo en la columna de búsqueda. Opcional (por defecto: False)
- *ignorar\_casos* : Si es true, realiza una coincidencia sin distinguir mayúsculas de minúsculas. Si es false, se distingue entre mayúsculas y minúsculas. Opcional (por defecto: False)
- *default\_value* : Valor predeterminado opcional que se devuelve cuando no se encuentra ninguna coincidencia y leave\_original\_value es false. Opcional

## Comportamiento

- Encuentra una coincidencia entre la columna de origen y la columna coincidente en la tabla de búsqueda.
- Devuelve el valor de la columna de sustitución de la última coincidencia encontrada.
- Si coinciden varias filas, devuelve ' {Various} '.
- Admite indicadores booleanos opcionales para personalizar el comportamiento: leave\_original\_value, replace\_nulls e ignore\_case.
- Sólo funciona con columnas de tipo etiqueta en origen y columnas coincidentes (no admite tipos numéricos).

## Tipo de retorno

Coincide con el tipo de datos de la columna de sustitución

## Ejemplos

`Lookup_Wild(ProductCode, ProductTable, CodePattern, Description)`: Devuelve la descripción en la que ProductCode coincide con una expresión regular de la columna CodePattern.

`Lookup_Wild(Name, PatternsTable, RegexPattern, Category, false, true,
true)`: Realiza una búsqueda de "Nombre" basada en un patrón de sustitución de nulos que no distingue mayúsculas de minúsculas.

Suponga que tiene la siguiente tabla llamada Centros de Datos que enumera los centros de datos y su ubicación:

![función de búsqueda](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/aug036.png)

En función de la ubicación, debe rellenar la columna Zona horaria. Dispone de la siguiente tabla llamada Zona Horaria que puede suministrar el desfase GMT.

![función de búsqueda](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/aug037.png)

Introduzca lo siguiente en el campo Sustitución de valor de la columna Ubicación de la tabla Centros de datos:

```
=Lookup(Location,Time Zone,City,Time
      Zone)
```

El resultado es:

![función de búsqueda](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/aug039.png)

- Si utiliza replace\_nulls o ignore\_case, debe incluir también todos los parámetros opcionales anteriores.
- Cuando no se encuentra ninguna coincidencia y leave\_original\_value es false, la función devuelve blank a menos que se especifique un default\_value.
- Admite la coincidencia de patrones mediante expresiones regulares en la columna matching\_column.
- Si se encuentran varias filas coincidentes, Lookup\_Wild devuelve ' {Various} '. Si esto no es aceptable, utilice LookupEx en su lugar.
- La vinculación por inferencia es preferible a Lookup\_Wild siempre que sea posible, especialmente si no es necesario que el resultado persista en el conjunto de datos.
