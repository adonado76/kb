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
source_path: "studio/formulas-and-functions/functions/lookup.html"
images:
  - "resources/images/studio_images/studioimages/studio/aug036.png"
  - "resources/images/studio_images/studioimages/studio/aug037.png"
  - "resources/images/studio_images/studioimages/studio/aug039.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Función de búsqueda

Busca un valor en una tabla de consulta basándose en una coincidencia entre una columna de la tabla actual y una columna de la tabla de consulta, y devuelve el valor correspondiente de una columna de sustitución.

Busca el valor en una columna de origen especificada en la tabla actual y en una columna especificada de una tabla de consulta. Lookup y Lookup\_Wild devuelven el valor de la columna de sustitución especificada correspondiente de la tabla lookup. Si se encuentran dos o más valores en la tabla de búsqueda, se devuelve el valor {Various}. La única diferencia entre las dos funciones es que Lookup\_Wild admite expresiones regulares en la columna de coincidencia y Lookup no.

Para aumentar el número de filas creando una nueva fila por cada valor devuelto en lugar de {Various}, utilice [LookupEx](lookupexandlookupex_wild.html "Realiza una búsqueda en las tablas y devuelve todos los valores coincidentes, creando nuevas filas para cada coincidencia. Esta función permite establecer una relación de uno a muchos uniendo cada fila coincidente de la tabla de búsqueda en la tabla transformada.").

Si utiliza Lookup para introducir un valor numérico y desea sumar los valores en lugar de devolver varios, utilice la sintaxis de [búsqueda de datos](../data-lookup.html).

## Sintaxis

```
Lookup(source_column, lookup_table, matching_column, replacement_column, leave_original_value, replace_nulls, ignore_case, default_value)
```

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

`Lookup({Product ID}, ProductTable, ProductCode, Description)`: Devuelve la descripción de ProductTable que coincide con el ID de producto de la fila actual.

`Lookup(ProductType, LookupTable, Type, Label, true)`: Devuelve la Etiqueta para la coincidencia ProductType; si no se encuentra ninguna coincidencia, devuelve el original ProductType.

`Lookup(Region & SubRegion, GeographyTable, Region & SubRegion, Code, false,
false, true)`: Realiza una búsqueda sin distinción entre mayúsculas y minúsculas utilizando dos columnas combinadas.

Suponga que tiene la siguiente tabla llamada Centros de Datos que enumera los centros de datos y su ubicación:

![buscar imagen](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/aug036.png)

En función de la ubicación, debe rellenar la columna Zona horaria. Dispone de la siguiente tabla llamada Zona Horaria que puede suministrar el desfase GMT.

![buscar imagen](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/aug037.png)

Introduzca lo siguiente en el campo Sustitución de valor de la columna Ubicación de la tabla Centros de datos:

```
=Lookup(Location,Time Zone,City,Time
      Zone)
```

El resultado es:

![buscar imagen](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/aug039.png)

Nota:

- Si utiliza replace\_nulls o ignore\_case, debe incluir también todos los parámetros opcionales anteriores.
- Cuando no se encuentra ninguna coincidencia y leave\_original\_value es false, la función devuelve blank a menos que se especifique un default\_value.
- Utilice Lookup\_Wild si necesita la concordancia de patrones mediante expresiones regulares en la columna de concordancia.
- Si se encuentran varias filas coincidentes, Lookup devuelve ' {Various} '. Si esto no es aceptable, utilice LookupEx en su lugar.
