---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Añadir una columna de indicador de estado a una tabla"
breadcrumb: []
source_path: "studio/reports/tables/add-status-indicators-to-tables.html"
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
# Añadir una columna de indicador de estado a una tabla

## Acerca de esta tarea

**Se aplica a** : TBM Studio 12.0 y posteriores

En las tablas de los informes, puede añadir indicadores de estado que utilicen iconos de colores para proporcionar información sobre los valores de una columna. En la siguiente imagen, los indicadores de estado de la columna **CPU Status** proporcionan información sobre los valores de la columna **Avg CPU Util**. Los indicadores pueden introducirse en rangos de valores. Por ejemplo, una flecha verde señala hacia arriba para un servidor con una utilización de la CPU superior al 65%, una flecha amarilla señala hacia la derecha para una utilización de la CPU superior al 50% y una flecha roja señala hacia abajo para una utilización de la CPU inferior al 50%.

**Iconos generados por la función Icono**

Los iconos de estado se generan mediante la siguiente función:

`=Icon(["icon_type"],conditional_expression,conditional_expression+)`

Hay varios tipos de iconos disponibles. La siguiente tabla enumera los tipos, las expresiones y los resultados de cada expresión. Cada tipo de icono tiene un número diferente de expresiones. Las expresiones se evalúan en el orden en que aparecen en la función. Si una expresión es verdadera, el resultado de esa expresión se muestra en la tabla y el resto de expresiones se ignoran. El argumento tipo\_icono es opcional. Si omite el argumento, la función utiliza por defecto el tipo de icono de círculos rojos. Si incluye el tipo de icono, enciérrelo entre comillas. A los valores que no entran dentro de las expresiones introducidas se les asigna el último icono del conjunto.

Cuadro 1.

| Tipo de icono | Expresiones y resultados |
| --- | --- |
| círculos rojos | Expresión 1: círculo rojo imagen  Expresión 2: círculo rosa imagen |
| 3colorcircles | Expresión 1: círculo verde imagen  Expresión 2: círculo amarillo imagen  Expresión 3: círculo rojo imagen |
| 3arrows | Expresión 1: flecha hacia arriba imagen  Expresión 2: flecha derecha imagen  Expresión 3: flecha hacia abajo imagen |
| 3arrowsinv | Expresión 1: flecha hacia arriba imagen  Expresión 2: flecha derecha imagen  Expresión 3: flecha hacia abajo imagen |
| 4arrows | Expresión 1: flecha hacia arriba imagen  Expresión 2: flecha arriba-derechaimagen  Expresión 3: flecha abajo-derecha imagen  Expresión 4: flecha hacia abajo imagen |
| 4arrowsinv | Expresión 1: flecha hacia arriba imagen  Expresión 2: flecha arriba-derecha imagen  Expresión 3: flecha abajo-derecha imagen  Expresión 4: flecha hacia abajo imagen |
| 5arrows | Expresión 1: flecha hacia arriba imagen  Expresión 2: flecha arriba-derecha imagen  Expresión 3: flecha derecha imagen  Expresión 4: flecha abajo-derecha imagen  Expresión 5: flecha hacia abajo imagen |
| 5arrowsinv | Expresión 1: flecha hacia arriba imagen  Expresión 2: flecha arriba-derecha imagen  Expresión 3: flecha derecha imagen  Expresión 4: flecha abajo-derecha imagen  Expresión 5: flecha hacia abajo imagen |

## Procedimiento

1. Vaya a la página del informe que contiene la tabla y pase al modo **Edición**.
2. Selecciona la tabla.
3. En la pestaña **Datos**, haga clic en **Insertar**.
4. Si lo desea, cambie el nombre de la columna haciendo clic con el botón derecho del ratón en la cabecera de la columna, seleccionando **Cambiar nombre** e introduciendo un nuevo nombre.
5. Seleccione la columna que acaba de insertar.
6. Haz clic en la pestaña **Fórmulas**, abre las funciones **Avanzadas** y haz clic en la opción **Icono**.
7. Edite la fórmula, seleccionando el tipo de icono adecuado e introduciendo el número de expresiones que corresponda.

   A continuación se muestra un ejemplo de fórmula.

   `Icon("3arrows",Avg CPU Util<40,Avg CPU Util<50,Avg CPU Util>70 AND Disk Image
   GB=500)`
8. Guarde la fórmula haciendo clic en el icono de guardar situado a la izquierda del campo de fórmula. Si ha introducido la fórmula correctamente, los iconos de estado aparecerán en la columna. Si ha cometido un error en la fórmula, la aplicación muestra un mensaje de error en la columna que puede ayudarle a solucionar el problema.
