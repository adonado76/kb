---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Umbral limitado: Fila Expansión"
breadcrumb: []
source_path: "studio/troubleshooting/studio-troubleshooting-row-expanding.html"
images:
  - "resources/images/studio_images/troubleshooting/row-expanding-1.png"
  - "resources/images/studio_images/troubleshooting/row-expanding-solution.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Umbral limitado: Fila Expansión

El limitador de expansión de filas evita la generación de tablas muy grandes en los productos de Apptio. Algunas funciones, como *LookupEx*, *SplitEx* y *Unpivot*, pueden dar lugar a tablas involuntariamente grandes.

Si se alcanza el límite de Ampliación de filas, se debe a que una de estas funciones ha superado el límite establecido en Apptio.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/troubleshooting/row-expanding-1.png)

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/troubleshooting/row-expanding-solution.png)

## Recomendación de configuración para el umbral Limitado: Error de expansión de filas

Para resolver el error de la función LookupEx :

- Analiza la relación entre las dos tablas para determinar por qué hay un gran número de coincidencias *uno a muchos*, y reduce su variabilidad.
- [LookupEx función](../formulas-and-functions/functions/lookupexandlookupex_wild.htm "(se abre en una pestaña o una ventana nueva)")

El mayor número posible de coincidencias para LookupEx es el producto de las dos tablas.

Para resolver el error de la función SplitEx :

- Revise los datos subyacentes que se dividen y reduzca el tamaño de los datos para limitar la expansión.
- [SplitEx función](../formulas-and-functions/functions/splitex.htm "(se abre en una pestaña o una ventana nueva)")

Para resolver el error de la función Unpivot, realice una de las siguientes acciones:

- Reduzca el número de columnas contraídas.
- Reduce el número de filas de la tabla actual.
