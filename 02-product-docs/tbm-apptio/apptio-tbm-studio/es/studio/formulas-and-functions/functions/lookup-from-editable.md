---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Función Lookup_From_Editable"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/lookup-from-editable.html"
images:
  - "resources/images/studio_images/lookupeditable.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Función Lookup_From_Editable

Esta función trae columnas de una tabla editable a través de una búsqueda para incluirlas en tablas de informes que muestran datos de una tabla editable diferente o datos de una transformación/modelo.

## Dónde utilizarlo

Esta función puede utilizarse en:

- Conjuntos de datos
- Columnas con fórmulas en tablas editables

## Dónde NO utilizar

Canal de transformación, controlador de modelo o fórmula de asignación avanzada.

## Sintaxis

=Lookup\_From\_Editable(columna\_de\_origen,tabla\_de\_busqueda,columna\_comparativa,columna\_de\_valor\_de\_busqueda, [leave\_original\_value], (replace\_nulls], [ignore\_case])

**Argumentos**

- *columna\_fuente* es la columna del conjunto de datos actual que coincidirá con una columna del otro conjunto de datos.
- *lookup\_table* es el nombre editable desde donde necesita traducir los datos.
- *columna\_coincidente* es la columna de la tabla de consulta que coincide con los datos de la columna especificada en columna\_fuente.
- *columna\_valor\_de\_consulta* es la columna de la tabla de consulta que debe traducirse al conjunto de datos actual.
- *leave\_original\_value* es un booleano que no actualiza el resultado si la búsqueda no tiene éxito
- *replace\_nulls* es un booleano que sustituye null por un valor por defecto definido
- *ignore\_case* es booleano para ignorar mayúsculas y minúsculas en otros parámetros

## Tipo de retorno

Tipo de columna de consulta.

**Notas** :

- Si la función LookUp\_From\_Editable encuentra varias filas coincidentes, devuelve {Various} en lugar de un null.
- Si utiliza los argumentos opcionales replace\_nulls o ignore\_case, deberá especificar también los argumentos opcionales que les preceden.
- Utilice las llaves estándar { } para escapar de caracteres especiales u operadores que puedan aparecer en los nombres de columna a los que se hace referencia. Por ejemplo, {P&L Rate}.
- La inferencia que vincula varias tablas es preferible a realizar búsquedas y puede utilizarse siempre que la columna resultante no sea necesaria en un conjunto de datos.

## Ejemplos

Esta fórmula se puede utilizar para crear una columna de consulta en una tabla editable a partir de otra tabla editable.

Nota: Esta columna de búsqueda no añadirá datos a las tablas editables en el backend, es sólo una columna visible en la superficie de informes.

![Ejemplos](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/lookupeditable.png)

Ejemplo de sintaxis

`=Lookup_From_Editable(Product Family ID, L1 Product Family, Product Family ID, Product
Family)`
