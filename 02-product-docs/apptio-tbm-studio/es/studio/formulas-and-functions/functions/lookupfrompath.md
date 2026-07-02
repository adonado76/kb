---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "LookupFromPath función"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/lookupfrompath.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# LookupFromPath función

**Se aplica a** : TBM Studio 12.0 y posteriores

Recupera valores de cualquier tabla en cualquier dominio y proyecto. Si hay varias coincidencias, la función devuelve {VARIOUS} para las columnas de texto y una suma para las columnas numéricas.

Nota: Esta función no funcionará en conjuntos de datos si la función hace referencia a un componente de informe en el mismo proyecto.

## Dónde utilizarlo

Esta función puede utilizarse en columnas de fórmulas en tablas de informes.

Nota: Esta función no puede utilizarse en conjuntos de datos.

## Sintaxis

`LookupFromPath("lookup_table_path",source_column,matching_column,lookup_value_column)`

## Argumentos

*ruta\_tabla\_de\_busqueda*

Ruta completa a la tabla de origen. Tenga en cuenta que debe entrecomillar la ruta si es una cadena literal.

Por ejemplo:

`"abccompany.com:test/Data/September:2010/line items"`

Puede construir la ruta a partir de otras funciones como DomainName, ProjectName, y CurrentDate. Consulte la sección Ejemplos más abajo.

*columna\_fuente*

La columna de la tabla actual que enlaza con la columna de otra tabla.

*columna\_compartida*

La columna de la otra tabla que enlaza con la tabla actual.

*columna\_valor\_buscado*

La columna de la otra tabla que suministrará los valores.

## Tipo de retorno

El valor de la columna de búsqueda. Si hay varias coincidencias, la función devuelve {VARIOUS} para las columnas de texto y una suma para las columnas numéricas.

## Ejemplos

- A continuación se muestra un ejemplo de una ruta simple introducida directamente, y una ruta equivalente introducida utilizando funciones. Las cadenas literales introducidas en la ruta deben ir entre comillas. El signo & se utiliza como operador de concatenación.

  ```
  “apptio.com:BankDemo/Data/January:2010/GL Actuals”
                DomainName()& “:” & ProjectName() & “/Data/” & CurrentDate(“MMMM:yyyy”) &
                “/<some table name here>”
  ```
- A continuación se muestra un ejemplo de trayectoria compleja utilizando las funciones DomainName, ProjectName, y CurrentDate.

  ```
  DOMAINNAME() & “:” & PROJECTNAME() &
                “/Reports/” &
  CURRENTDATE(“MMMM:yyyy”) &
                  “/
  CostModels/
  Default/
  .View:Product Capacity Owner/
  Business
                  Domains/
  .WithDefaultMetric-Planned Price/
  .DrillTo/
  <%/.DrillTo/<%=ObjectName%>/
  !FILTER[All IT
                  Products.ProductID=<%=ProductID%>]/
  !FILTER[All
                IT Products.Is Adjustment=%22No%22]/
  .LineItemsTable"
  ```

Consulte también:

- [Búsqueda de IP](iplookup.htm "(se abre en una pestaña o una ventana nueva)")
- [Lookup y Lookup\_Wild](lookupandlookup_wild.htm "(se abre en una pestaña o una ventana nueva)")
- [LookupEx](lookupexandlookupex_wild.htm "(se abre en una pestaña o una ventana nueva)")
- [LookupMetric](lookupmetric.htm "(se abre en una pestaña o una ventana nueva)")
- [LookupObjectTotalAllocated](lookupobjecttotalallocated.htm "(se abre en una pestaña o una ventana nueva)")
- [LookupObjectTotalValue](lookupobjecttotalvalue.htm "(se abre en una pestaña o una ventana nueva)")
- [LookupObjectUnitAllocated](lookupobjectunitallocated.htm "(se abre en una pestaña o una ventana nueva)")
- [LookupObjectUnitValue](lookupobjectunitvalue.htm "(se abre en una pestaña o una ventana nueva)")
