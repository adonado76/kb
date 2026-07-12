---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Búsqueda de datos"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/data-lookup.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Búsqueda de datos

La búsqueda de datos es una función que permite que una celda haga referencia a un valor de una o más celdas. En función de la ubicación de las celdas, existen dos variantes de búsqueda de datos:

- [Búsqueda interna de datos](#Datalookup__Internaldatalookup)

Búsqueda de datos que hace referencia a un valor de la misma tabla.

- [Búsqueda de datos externos](#Datalookup__Externaldatalookup)

Búsqueda de datos que hace referencia a un valor en otra tabla, pero en el mismo proyecto.

## Búsqueda interna de datos

La búsqueda interna de datos permite que una celda haga referencia a un valor de una o más celdas de la misma fila.

Sintaxis interna de búsqueda de datos

`=column`

La fórmula devuelve los valores de todas las celdas que se encuentran en la misma fila y están en la **columna** columna, donde **columna** es cualquier nombre de columna de la misma tabla.

## Ejemplos

Creamos una nueva columna llamada **Porcentaje de uso de espacio** y le asignamos la siguiente fórmula:

`=(Used Space/Total Space)*100`

Cada celda de la nueva columna **Porcentaje de uso de espacio** :

1. Hace referencia a las celdas de las columnas **Espacio utilizado** y **Espacio total** de la misma fila.
2. Realiza el cálculo de la fórmula.
3. Asigna el valor final a la celda que contiene la fórmula.

Nota: No puede hacer referencia a una celda de otra fila de la misma tabla. Por ejemplo, no puede asignar la fórmula =B1 a la celda A2 de una hoja de cálculo de Excel, ni buscar una celda en una fila diferente basándose en criterios u orden de búsqueda.

## Búsqueda de datos externos

La búsqueda externa de datos permite que una celda haga referencia a un valor de una o varias celdas de una columna de otra tabla.

[Más información sobre casos de uso y rendimiento](#Datalookup__Use)

[Más información sobre métodos alternativos de búsqueda de datos externos](#Datalookup__Alternat)

Sintaxis de búsqueda de datos externos

```
={table}:{column1}

or

={table}:{column1}[selector]
```

La fórmula devuelve el valor de todas las celdas de **column1** de la **tabla**. También puede añadir **[selector]** para añadir criterios adicionales que deben cumplir las celdas.

- **{table}** - nombre de otra tabla que contenga las celdas a las que queremos hacer referencia.
- **{column1}** - cualquier nombre de columna de la **tabla**
- **[selector]** - criterios adicionales de las celdas.
  - En el selector, puede utilizar operadores relacionales, por ejemplo **=**, **!=**, **IN**, **NOT IN**, **>** y **<.**
  - El selector puede hacer referencia a una o varias columnas de la **tabla** y de la tabla en la que se define esta fórmula.

Nota: Sólo se devolverá un valor, incluso si varias celdas cumplen los criterios del selector. Si la columna es numérica, se devolverá el valor sumado de todas las celdas coincidentes. Si la columna no es numérica y hay más de una coincidencia, se devolverá ":" o " {Various} ".

## Ejemplos

`=GL:Cost[ID="95847"]`

Devuelve la suma de todas las celdas de la columna **Coste** de la tabla **GL**, donde el valor **del ID** en esas celdas es igual a **95847**.

`=GL:Cost[ID="95847"]*PercentColumn`

Devuelve la suma de todas las celdas de la columna **Coste** de la tabla **GL**, donde el valor de la columna **ID** de dicha tabla es igual a **95847**.

A continuación, utiliza una búsqueda interna de datos para multiplicar el valor devuelto por el valor de la celda de la columna **PercentColumn** columna. La dirección **PercentColumn** debe estar en la misma fila que esta fórmula.

Esta fórmula utiliza tanto una búsqueda de datos externos como una búsqueda de datos internos.

`=GL:Cost[Type=Expense Type]`

Devuelve la suma de todas las celdas de la columna **Coste** de la tabla **GL**, donde el valor de la columna **Tipo** y en las mismas filas es igual al valor de la columna **Tipo de Gasto** en la celda donde se define esta fórmula.

Al utilizar este tipo de nombres de columna:

- La parte izquierda de cada comparación busca una columna con ese nombre en la tabla de destino.
- El lado derecho busca una columna en la tabla, donde se define la fórmula.

En este ejemplo, **GL**.

Esta fórmula utiliza una búsqueda de datos interna dentro de una búsqueda de datos externa.

`=GL:Cost[Type="ServerType"]`

Devuelve la suma de todas las celdas de la columna **Coste** de la tabla **GL**, donde el valor de la columna **Tipo** de dicha tabla es igual a la etiqueta: **ServerType**.

`=Labor:Amount[Equipment IN ("server","router","desktop") ]`

Devuelve la suma de todas las celdas de la columna **Importe** de la tabla **Mano de obra**, donde el valor de la columna **Equipo** de dicha tabla es igual a **servidor**, **enrutador** o **escritorio**.

`=Labor:Amount[Equipment NOT IN ("server","router","desktop")]`

Devuelve la suma de todas las celdas de la columna **Importe** de la tabla **Mano de obra**, en las que el valor de la columna **Equipo** de dicha tabla no sea igual a **servidor**, **enrutador** o **escritorio**.

`=Storage:Amount[Amount>Threshold]`

Devuelve la suma de todas las celdas en la columna **Cantidad** de la tabla **Almacenamiento**, donde el valor en la columna **Cantidad** de esa tabla es mayor que el valor en la celda en la columna **Umbral** en la misma fila (en la tabla donde está definida la fórmula, no en la tabla **Almacenamiento** ).

## Casos prácticos y rendimiento

Dado que la búsqueda externa de datos realiza el equivalente de un SumIf en la tabla de destino (encontrando todas las celdas que cumplen los criterios y sumándolas después), es una operación potencialmente costosa que puede tener un impacto negativo en el rendimiento.

Siempre que sea posible, utilice la función de búsqueda que admita el caso de uso requerido. La función de búsqueda sólo devuelve la primera coincidencia que encuentra, lo que reduce el impacto en el rendimiento. La búsqueda externa de datos encuentra todas las filas que coinciden con los criterios del selector.

Si es necesario ejecutar los mismos criterios de selección de búsqueda de datos externos en la misma tabla más de una vez, sugerimos crear una nueva columna en la tabla que sería el equivalente de los criterios de selección (y potencialmente incluiría un SumIf, si es necesario), y luego usarla como la columna que se busca en múltiples funciones de búsqueda en otras tablas. De este modo, la operación más costosa de encontrar las filas coincidentes sólo se realiza una vez, y la operación menos costosa de referenciar las columnas entre tablas se realiza varias veces.

## Métodos alternativos de búsqueda de datos externos

Hay otras formas de buscar datos en otras tablas, cada una adecuada para casos de uso distintos, y cada una tiene consideraciones diferentes que hay que tener en cuenta.

- [Búsqueda](functions/lookupandlookup_wild.htm "(se abre en una pestaña o una ventana nueva)")
- [LookupEx](functions/lookupexandlookupex_wild.htm "(se abre en una pestaña o una ventana nueva)")
- [TableMatch](functions/tablematch.htm "(se abre en una pestaña o una ventana nueva)")
- [Paso de unión](../data%20studio/join-data.htm "(se abre en una pestaña o una ventana nueva)") en el proceso de transformación
