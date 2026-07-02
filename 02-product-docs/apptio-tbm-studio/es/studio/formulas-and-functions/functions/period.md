---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Función de periodo"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/period.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Función de periodo

**Se aplica a** : TBM Studio 12.0 y posteriores

Devuelve una cadena que representa un período de tiempo seleccionado basado en un formato de ejemplo especificado.

Esta función puede ser útil dentro de una región HTML, donde se utilizan scripts de texto dinámicos. Puede especificar una cadena de formato de ejemplo, como **mensual**, para utilizarla como sufijo con un valor de datos dependiente del tiempo. Luego, cuando visualice ese valor de datos para distintos periodos de tiempo, el sufijo reflejará el periodo de tiempo apropiado. En este ejemplo, si visualiza los datos de un año, el sufijo es **anual**, para un trimestre, es **trimestral**, y así sucesivamente.

## Dónde utilizarlo

Esta función puede utilizarse en:

- Conjuntos de datos
- Columnas de fórmulas en tablas de informes
- Texto dinámico

## Sintaxis

`Period(["time_period"][1])`

## Argumentos

Introduzca uno de los dos argumentos, pero no los dos.

`time_period`

Una cadena que proporciona un ejemplo del formato, como **mes**, **mensual**, **GB/mes**, **$ al mes** o **$/m**. La cadena debe contener un elemento que represente el mes. Formatos incluidos:

- "mes" (no distingue mayúsculas de minúsculas)
- "mensual" (no distingue mayúsculas de minúsculas)
- que termina en "mes "que termina en "Mes"
- que terminan en "/m"
- que terminan en "/M"
- "punto" (distingue mayúsculas de minúsculas)
- termina en "punto
- que termina en "Punto"
- que terminan en "/p"
- que terminan en "/P"

`1`

Devuelve un número que representa el periodo de tiempo actual: 1 para el período o mes, 3 para el trimestre y 12 ó 13 para el año, dependiendo del tipo de calendario (gregoriano, variante 445 o período 13). Este argumento se puede utilizar si desea utilizar el valor de retorno en los cálculos.

Por ejemplo, =Coste/Periodo(1) daría como resultado el coste medio por periodo o mes.

## Tipo de retorno

Serie

## Ejemplo

En el siguiente ejemplo, el uso de la función Período permite que el Coste se muestre con un sufijo que cambia dinámicamente con el período de tiempo seleccionado. Si se consultan los datos de un año y Cost=$503,122, la producción es de **503.122 dólares al año**, pero si se consultan los datos de un trimestre, la producción es de **503.122 dólares al trimestre**.

```
Total Cost: <%=Cost%> <%=Period("per
      month")%>
```
