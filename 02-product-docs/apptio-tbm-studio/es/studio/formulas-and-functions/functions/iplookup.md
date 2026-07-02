---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Función IPLookup"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/iplookup.html"
images:
  - "resources/images/studio_images/studioimages/studio/aug032.png"
  - "resources/images/studio_images/studioimages/studio/aug033.png"
  - "resources/images/studio_images/studioimages/studio/aug035.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Función IPLookup

**Se aplica a** : TBM Studio 12.0 y posteriores

Busca una dirección IP en una columna de origen especificada en la tabla actual y busca una dirección IP en una columna especificada de una tabla de búsqueda. IPLookup devuelve el valor de la columna de sustitución especificada correspondiente de la tabla de búsqueda para la última coincidencia que encuentra. Las direcciones IP pueden introducirse individualmente o utilizar máscaras y rangos.

## Dónde utilizarlo

Esta función puede utilizarse en:

- Conjuntos de datos
- Columnas de fórmulas en tablas de informes

## Sintaxis

`IPLookup(source_column,lookup_table,matching_column,replacement_column,"default_value")`

## Argumentos

*columna\_fuente*

La columna de la tabla actual que contiene la dirección IP que desea buscar. Nota: introduzca sólo el nombre de la columna, no el de la tabla name.column.

*tabla\_de\_busqueda*

El nombre de la tabla que contiene los valores de retorno.

*columna\_compartida*

La columna de la *tabla de búsqueda* en la que buscar una coincidencia. Los valores pueden estar en uno de varios formatos:

- Direcciones IP específicas como 99.9.1.4.
- Máscaras de dirección IP como 99.1.0.0 donde 0.0 coincidirá con cualquier conjunto de números. Por ejemplo, 99.1.0.0 incluiría direcciones IP como 99.1.5.6, 99.1.9.234 y 99.1.43.144.
- Rangos de direcciones IP como 99.1-99.6 que coincidirá con cualquier rango IP entre los dos valores. Por ejemplo, el rango 99.1-99.6 incluiría direcciones IP como 99.1.1.4, 99.3.1.54 y 99.6.6.6.

*columna\_de\_sustitución*

La columna de la *tabla de consulta* que proporciona el valor de retorno.

*valor\_por\_defecto*

El valor a devolver si no se encuentra ninguna coincidencia. El valor debe ir entre comillas.

## Tipo de retorno

El tipo de *columna\_de\_sustitución* o *valor\_por\_defecto*, según corresponda.

## Ejemplo

Suponga que tiene la siguiente tabla llamada Máquinas que enumera las máquinas y sus direcciones IP:

![Ejemplo](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/aug032.png)

A partir de la dirección IP, rellene la columna Ubicación. Dispone de la siguiente tabla llamada Ubicaciones que puede suministrar las ubicaciones:

![Ubicaciones](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/aug033.png)

Introduzca lo siguiente en el campo Anulación de valor para la columna Ubicación de la tabla Máquinas:

```
=IPLookup(IP Address,Location,IP
          Address,Location,"Unknown")
```

El resultado es:

![Resultado](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/aug035.png)

Nota:

- Las dos primeras máquinas tienen una dirección IP de 99.9.1.4 y están asignadas a Altanta, no a Nueva York. Esto se debe a que en la tabla de Ubicaciones, la última referencia para la dirección IP 99.9.1.4 es Atlanta.
- 77.1.2.3 no aparece en la tabla Ubicaciones, por lo que se devuelve el valor **Desconocido**.

Consulte también:

- [Lookup y Lookup\_Wild](lookupandlookup_wild.htm "(se abre en una pestaña o una ventana nueva)")
- [LookupEx](lookupexandlookupex_wild.htm "(se abre en una pestaña o una ventana nueva)")
- [LookupFromPath](lookupfrompath.htm "(se abre en una pestaña o una ventana nueva)")
- [LookupMetric](lookupmetric.htm "(se abre en una pestaña o una ventana nueva)")
- [LookupObjectTotalAllocated](lookupobjecttotalallocated.htm "(se abre en una pestaña o una ventana nueva)")
- [LookupObjectTotalValue](lookupobjecttotalvalue.htm "(se abre en una pestaña o una ventana nueva)")
- [LookupObjectUnitAllocated](lookupobjectunitallocated.htm "(se abre en una pestaña o una ventana nueva)")
- [LookupObjectUnitValue](lookupobjectunitvalue.htm "(se abre en una pestaña o una ventana nueva)")
