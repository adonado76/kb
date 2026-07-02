---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Funciones Lookup y Lookup_Wild"
breadcrumb: []
source_path: "studio/formulas-and-functions/functions/lookupandlookup_wild.html"
images:
  - "resources/images/studio_images/studioimages/studio/aug036.png"
  - "resources/images/studio_images/studioimages/studio/aug037.png"
  - "resources/images/studio_images/studioimages/studio/aug039.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Funciones Lookup y Lookup_Wild

**Se aplica a** : TBM Studio 12.0 y posteriores

Busca el valor en una columna de origen especificada en la tabla actual y en una columna especificada de una tabla de consulta. Lookup y Lookup\_Wild devuelven el valor de la columna de sustitución especificada correspondiente de la tabla lookup. Si se encuentran dos o más valores en la tabla de búsqueda, se devuelve el valor {Various}. La única diferencia entre las dos funciones es que Lookup\_Wild admite expresiones regulares en la columna de coincidencia y Lookup no.

Para aumentar el número de filas creando una nueva fila por cada valor devuelto en lugar de {Various}, utilice [LookupEx](lookupexandlookupex_wild.htm "(se abre en una pestaña o una ventana nueva)").

Si utiliza Lookup para introducir un valor numérico y desea sumar los valores en lugar de devolver varios, utilice la sintaxis de [búsqueda de datos](../data-lookup.htm "(se abre en una pestaña o una ventana nueva)").

## Dónde utilizarlo

Esta función puede utilizarse en:

- Conjuntos de datos
- Columnas de fórmulas en tablas de informes (aunque no se recomienda. En su lugar, utilice la inferencia)
- Mapeador de datos
- Texto dinámico

## Sustituye a

Hay nuevas versiones de las funciones Lookup y Lookup\_Wild que sustituyen a las antiguas. Si hay versiones antiguas que haya utilizado, la aplicación las renombra como Lookup\_Old y Lookup\_Wild\_Old. NO EDITE ESTAS VERSIONES ANTIGUAS. Si necesita realizar cambios en estas funciones, elimínelas e introduzca nuevas funciones Lookup y Lookup\_Wild.

## Sintaxis

`Lookup(source_column,lookup_table,matching_column,replacement_column[,leave_original_value][,replace_nulls][,ignore_case])`

`Lookup_Wild(source_column,lookup_table,matching_column,replacement_column[,leave_original_value][,replace_nulls][,ignore_case])`

## Argumentos

*columna\_fuente*

La columna de la tabla actual que contiene el valor a buscar. Este valor puede ser el nombre de una columna de tipo etiqueta. La búsqueda no admite valores numéricos en la columna de origen. Puede incluir dos o más columnas de origen coincidentes utilizando el operador "&" (realiza ambas pruebas) o "&&" (realiza la segunda prueba sólo si la primera es verdadera). Debe incluir el mismo número de columnas en el parámetro matching\_column.

**AVISO**

La columna no puede ser de tipo "Numérico".

*tabla\_de\_busqueda*

El nombre de la tabla que contiene los valores de retorno. Debe ser una constante y no puede hacer referencia a otras columnas o fórmulas.

*columna\_compartida*

La columna de la *tabla de búsqueda* en la que buscar una coincidencia. Si utiliza Lookup\_Wild, puede introducir expresiones regulares en la columna. Para obtener información sobre expresiones regulares, busque en la Web.

Puede incluir dos o más columnas coincidentes utilizando el operador "&" (realiza ambas pruebas) o "&&" (realiza la segunda prueba sólo si la primera es verdadera).

**AVISO**

La columna no puede ser de tipo "Numérico".

*columna\_de\_sustitución*

La columna de la tabla de consulta que proporciona el valor de retorno.

Si coloca un signo igual (=) delante del nombre de la columna, la función comprobará el valor de la columna en la tabla de origen. El valor que encuentre se utilizará como nombre de la columna que se utilizará en la tabla de consulta. Esto permite que la columna de sustitución sea dinámica en cada fila.

*dejar\_valor\_original*

Un valor booleano (verdadero o falso) que controla el valor que se devuelve si no se encuentra el valor buscado. Si leave\_original\_value = true, Lookup devuelve el valor buscado; si false, Lookup devuelve una celda en blanco. Si no se especifica este argumento, por defecto es false.

*reemplazar\_nulos*

Valor booleano (verdadero o falso) que controla el valor que se devuelve cuando el valor buscado está vacío o es nulo. Si introduce true, buscará un valor en la columna\_de\_reemplazo cuyo valor correspondiente en la columna\_de\_coincidencia sea null. Si introduce false, un valor NULL en la columna\_fuente permanecerá nulo. Si la columna\_coincidente no contiene NULL o un valor vacío, el valor de retorno será NULL. Este valor es falso por defecto.

*ignorar\_caso*

Valor booleano (verdadero o falso) que controla si la búsqueda ignora mayúsculas y minúsculas al comparar los valores de la columna\_fuente con los de la columna\_coincidente. Si ignore\_case = true, Lookup ignora mayúsculas y minúsculas; si false, Lookup distingue entre mayúsculas y minúsculas. Si no se especifica este argumento, por defecto es false. La operación Lookup será más rápida cuando ignore\_case sea false, así que sólo cambie esto cuando sea necesario.

## Tipo de retorno

Tipo de columna de consulta.

**Notas** :

- Si la función LookUp encuentra varias filas coincidentes, devuelve {Various} en lugar de un null.
- Si utiliza los argumentos opcionales *replace\_nulls* o *ignore\_case*, deberá especificar también los argumentos opcionales que les preceden.
- Utilice las llaves estándar { } para escapar de caracteres especiales u operadores que puedan aparecer en los nombres de columna a los que se hace referencia. Por ejemplo, {P&L Rate}.
- La inferencia que vincula varias tablas es preferible a realizar búsquedas y puede utilizarse siempre que la columna resultante no sea necesaria en un conjunto de datos.

## Ejemplo de búsqueda

Suponga que tiene la siguiente tabla llamada Centros de Datos que enumera los centros de datos y su ubicación:

![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/aug036.png)

En función de la ubicación, debe rellenar la columna Zona horaria. Dispone de la siguiente tabla llamada Zona Horaria que puede suministrar el desfase GMT.

![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/aug037.png)

Introduzca lo siguiente en el campo Sustitución de valor de la columna Ubicación de la tabla Centros de datos:

```
=Lookup(Location,Time Zone,City,Time
      Zone)
```

El resultado es:

![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/aug039.png)

Consulte también:

- [IPLookup](iplookup.htm "(se abre en una pestaña o una ventana nueva)")
- [LookupEx](lookupexandlookupex_wild.htm "(se abre en una pestaña o una ventana nueva)")
- [LookupFromPath](lookupfrompath.htm "(se abre en una pestaña o una ventana nueva)")
- [LookupMetric](lookupmetric.htm "(se abre en una pestaña o una ventana nueva)")
- [LookupObjectTotalAllocated](lookupobjecttotalallocated.htm "(se abre en una pestaña o una ventana nueva)")
- [LookupObjectTotalValue](lookupobjecttotalvalue.htm "(se abre en una pestaña o una ventana nueva)")
- [LookupObjectUnitAllocated](lookupobjectunitallocated.htm "(se abre en una pestaña o una ventana nueva)")
- [LookupObjectUnitValue](lookupobjectunitvalue.htm "(se abre en una pestaña o una ventana nueva)")
