---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Función de icono"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/icon.html"
images:
  - "resources/images/studio_images/studioimages/icons/arrow-down-right.png"
  - "resources/images/studio_images/studioimages/icons/arrow-up-right.png"
  - "resources/images/studio_images/studioimages/icons/circle-green.png"
  - "resources/images/studio_images/studioimages/icons/circle-pink.png"
  - "resources/images/studio_images/studioimages/icons/circle-red.png"
  - "resources/images/studio_images/studioimages/icons/circle-yellow.png"
  - "resources/images/studio_images/studioimages/icons/down-arrow-green.png"
  - "resources/images/studio_images/studioimages/icons/down-arrow.png"
  - "resources/images/studio_images/studioimages/icons/right-arrow.png"
  - "resources/images/studio_images/studioimages/icons/up-arrow-red.png"
  - "resources/images/studio_images/studioimages/icons/up-arrow.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Función de icono

**Se aplica a** : TBM Studio 12.0 y posteriores

Evalúa dos o más expresiones y devuelve una de hasta cinco etiquetas HTML <img> para iconos de colores en función de los resultados.

## Dónde utilizarlo

Esta función puede utilizarse en:

- Conjuntos de datos
- Métricas calculadas e informes con columnas de métricas
- Columnas de fórmulas en tablas de informes
- Texto dinámico

## Sintaxis

`Icon(["icon-type"], expression, expression+)`

## Argumentos

*[icono-tipo]*

Hay varios tipos de iconos disponibles. La siguiente tabla enumera los tipos, expresiones y resultados de cada expresión.

Este argumento es opcional. Si omite el argumento, la función utiliza por defecto el tipo de icono "círculos rojos".

| Tipo de icono | Expresiones y resultados |
| --- | --- |
| "círculos rojos" | Expresión 1: círculo rojo círculo rojoExpresión 2: círculo rosa círculo rosa |
| "3colorcircles" | Expresión 1: círculo verde círculo verdeExpresión 2: círculo amarillo círculo amarilloExpresión 3: círculo rojo círculo rojo |
| "3arrows" | Expresión 1: flecha hacia arriba flecha verde hacia arribaExpresión 2: flecha hacia la derecha flecha amarilla hacia la derechaExpresión 3: flecha hacia abajo flecha roja hacia abajo |
| "3arrowsinv" | Expresión 1: flecha hacia arriba Expresión 2: flecha hacia la derecha flecha amarilla hacia la derechaExpresión 3: flecha hacia abajo flecha verde hacia abajo |
| "4arrows" | Expresión 1: flecha arriba flecha verde hacia arribaExpresión 2: flecha arriba a la derecha amarillo arriba flecha derechaExpresión 3: flecha abajo a la derecha Expresión 4: flecha abajo flecha roja hacia abajo |
| "4arrowsinv" | Expresión 1: flecha arriba Expresión 2: flecha arriba a la derecha amarillo arriba flecha derechaExpresión 3: flecha abajo a la derecha amarillo abajo flecha derechaExpresión 4: flecha abajo flecha verde hacia abajo |
| "5arrows" | Expresión 1: flecha arriba flecha verde hacia arribaExpresión 2: flecha arriba derecha amarillo arriba flecha derechaExpresión 3: flecha derecha flecha amarilla hacia la derechaExpresión 4: flecha abajo derecha amarillo abajo flecha derechaExpresión 5: flecha abajo flecha roja hacia abajo |
| "5arrowsinv" | Expresión 1: flecha arriba Expresión 2: flecha arriba derecha amarillo arriba flecha derechaExpresión 3: flecha derecha flecha amarilla hacia la derechaExpresión 4: flecha abajo derecha amarillo abajo flecha derechaExpresión 5: flecha abajo flecha verde hacia abajo |
| "círculos rojos" | Expresión 1: círculo rojo círculo rojoExpresión 2: círculo rosa |
| "3colorcircles" | Expresión 1: círculo verde círculo verdeExpresión 2: círculo amarillo círculo amarilloExpresión 3: círculo rojo círculo rojo |
| "3arrows" | Expresión 1: flecha hacia arriba flecha verde hacia arribaExpresión 2: flecha hacia la derecha flecha amarilla hacia la derechaExpresión 3: flecha hacia abajo flecha roja hacia abajo |
| "3arrowsinv" | Expresión 1: flecha hacia arriba Expresión 2: flecha hacia la derecha flecha amarilla hacia la derechaExpresión 3: flecha hacia abajo |
| "4arrows" | Expresión 1: flecha arriba flecha verde hacia arribaExpresión 2: flecha arriba a la derecha amarillo arriba flecha derechaExpresión 3: flecha abajo a la derecha amarillo abajo flecha derechaExpresión 4: flecha abajo flecha roja hacia abajo |
| "4arrowsinv" | Expresión 1: flecha arriba Expresión 2: flecha arriba a la derecha amarillo arriba flecha derechaExpresión 3: flecha abajo a la derecha amarillo abajo flecha derechaExpresión 4: flecha abajo |
| "5arrows" | Expresión 1: flecha arriba flecha verde hacia arribaExpresión 2: flecha arriba derecha amarillo arriba flecha derechaExpresión 3: flecha derecha flecha amarilla hacia la derechaExpresión 4: flecha abajo derecha amarillo abajo flecha derechaExpresión 5: flecha abajo flecha roja hacia abajo |
| "5arrowsinv" | Expresión 1: flecha hacia arriba  Expresión 2: flecha arriba a la derecha amarillo arriba flecha derecha  Expresión 3: flecha derecha flecha amarilla hacia la derecha  Expresión 4: flecha abajo a la derecha amarillo abajo flecha derecha  Expresión 5: flecha hacia abajo flecha verde hacia abajo |

Existen varias reglas que rigen la evaluación de las expresiones:

- Las expresiones se evalúan en el orden en que aparecen en la función.
- Si una expresión es verdadera, el resultado de esa expresión se muestra en la tabla y el resto de expresiones se ignoran.
- Si se introduce un conjunto completo de expresiones para un tipo de icono y ninguna de las expresiones es verdadera, la celda se deja en blanco.
- Si se introduce un conjunto de expresiones no completo para un tipo de icono, a los valores que queden fuera de las expresiones especificadas se les asignará el icono asociado a la primera expresión que no specified.For ejemplo, suponiendo que esté utilizando el tipo de icono 3colorcircles. Se introducen expresiones para los iconos del círculo verde y del círculo amarillo, pero no para el icono rojo. A los valores que queden fuera de las expresiones de los iconos verde y amarillo se les asignará automáticamente el icono del círculo rojo.

El argumento tipo de icono es opcional. Si omite el argumento, la función utiliza por defecto el tipo de icono "círculos rojos".

*expresión*

El número de expresiones depende del tipo de icono seleccionado. Las expresiones admiten los operadores AND y OR.

Por ejemplo:

Icon(" 3arrows ",CPU media Util<40,Avg CPU Util<50,Avg CPU Util<70 E imagen de disco GB=500 )

Existen varias reglas que rigen la evaluación de las expresiones:

- Las expresiones se evalúan en el orden en que aparecen en la función.
- Si una expresión es verdadera, el resultado de esa expresión se muestra en la tabla y el resto de expresiones se ignoran.
- Si se introduce un conjunto completo de expresiones para un tipo de icono y ninguna de las expresiones es verdadera, la celda se deja en blanco.
- Si se introduce un conjunto de expresiones no completo para un tipo de icono, a los valores que queden fuera de las expresiones especificadas se les asignará el icono asociado a la primera expresión no especificada.
- Por ejemplo, supongamos que utiliza el tipo de icono 3colorcircles. Se introducen expresiones para los iconos del círculo verde y del círculo amarillo, pero no para el icono rojo. A los valores que queden fuera de las expresiones de los iconos verde y amarillo se les asignará automáticamente el icono del círculo rojo.
- El orden de evaluación es AND y luego OR. Las operaciones entre paréntesis se evalúan primero.

## Tipo de retorno

Serie

## Observaciones

Sólo se pueden utilizar expresiones simples, iguales a las utilizadas en el [IF](if.htm "(se abre en una pestaña o una ventana nueva)").

## Ejemplo

El siguiente ejemplo devuelve:

- Una flecha verde hacia arriba si la Utilización Media de la CPU es superior a 65.
- Una flecha amarilla a la derecha si la Utilización Media de la CPU es superior a 50.
- Una flecha roja hacia abajo si la Utilización Media de la CPU es superior a 0.

Si CostPerGB no existe, la función devuelve el color gris.

`Icon("3arrows",Avg CPU Util>65,Avg CPU Util>50,Avg CPU Util>0)`

**Véase también** : [StatusIcon](statusicon.htm "(se abre en una pestaña o una ventana nueva)")
