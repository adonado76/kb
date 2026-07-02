---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Paleta de colores personalizada"
breadcrumb: []
source_path: "studio/admin/color-enhancement.html"
images:
  - "resources/images/studio_images/blank-palette.png"
  - "resources/images/studio_images/ccp-applycp_991x445.png"
  - "resources/images/studio_images/ccp-colorpalette.png"
  - "resources/images/studio_images/ccp-defaultccp.png"
  - "resources/images/studio_images/ccp-menu_179x417.png"
  - "resources/images/studio_images/ccp-popup.png"
  - "resources/images/studio_images/ccp-rcpopup.png"
  - "resources/images/studio_images/ccp-reportcollection.png"
  - "resources/images/studio_images/enable-dcp.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Paleta de colores personalizada

El Apptio Admin, Admin, y el Partner Admin tienen la flexibilidad de definir, gestionar y aplicar colores corporativos a las colecciones de informes y a los informes en TBM Reports Studio. Permite a los administradores alinear la estética visual de sus informes con las directrices de marca de su organización y les ofrece una mejor experiencia de usuario. La paleta de colores sólo puede definirse a nivel de entorno, y no a nivel de instancia.

Para activar la función Paleta de colores personalizada desde la interfaz de usuario, vaya a la pestaña **Proyecto** > **Activar funciones** > y seleccione la opción **Activar mejora del color**.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/enable-dcp.png)`

## Crear una paleta de colores personalizada

En la esquina superior derecha, seleccione **Configuración** > **Paleta de colores personalizada**. Esta opción sólo está disponible para las funciones Apptio Admin, Admin y Partner Admin.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ccp-menu_179x417.png)

Aparecerá la paleta de colores personalizada. Para un usuario novato, la paleta de colores personalizada estará en blanco, sin ningún color.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/blank-palette.png)

Elija la paleta de colores de uno en uno, empezando de izquierda a derecha. Al seleccionar el primer color, el sistema aplicará automáticamente degradados de ese color al resto de los 11 colores. El administrador tiene la opción de actualizar los colores manualmente.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ccp-popup.png)

Después de seleccionar los 12 colores, seleccione el botón **Guardar**. Los colores seleccionados aquí estarán disponibles para aplicarlos a los informes y colecciones de informes en el entorno de todos los proyectos. Si el código HEX es incorrecto, aparecerá un mensaje de error apropiado.

Nota: Si un cliente no tiene varios colores en su guía de estilo, se generarán automáticamente variaciones del color aplicado.

## Paleta de colores personalizada

Cada paleta de colores tiene 12 colores, y hay 10 paletas que se pueden crear y personalizar. Si hay más de 12 dimensiones, las variaciones de los 12 colores se aplicarán a las dimensiones adicionales del gráfico.

## Nombrar la paleta de colores

El nombre de la paleta de colores debe ser alfanumérico, puede contener "espacio", "-" y "\_", y no debe superar los 30 caracteres.

Hay dos tipos de paletas disponibles:

**Paleta personalizada** : Pueden ser creadas y gestionadas por los Administradores, según los estilos de color de su organización.

**Paleta de preajustes** : Estos son Apptio colores estándar que no se pueden personalizar. Están disponibles en la colección de informes y a nivel de informe, y no al crear las paletas personalizadas.

## Actualización de la paleta de colores personalizada

Si desea cambiar cualquier color de una paleta de colores existente, el degradado automático no estará activo. El resto de los colores seguirán siendo los mismos.

## Aplicar paleta de colores

## Nivel del informe

Vaya a **TBM Studio** > **Proyectos** > **Informes** y seleccione cualquier informe. Por defecto, se tendrán en cuenta los colores de Apptio para el informe.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ccp-defaultccp.png)

En la pestaña **Inicio**, **compruebe** el informe. Vaya a la pestaña **Informe** y seleccione la opción **Paleta de colores**.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ccp-colorpalette.png)

El menú Aplicar paleta de colores se abre en el panel derecho, con la lista de paletas de colores Personalizadas y Preconfiguradas.

Seleccione la paleta de colores personalizada o los preajustes de su elección, que se aplicarán al informe.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ccp-applycp_991x445.png)

Aparece un mensaje de confirmación y el color personalizado se aplica al informe. La paleta de colores seleccionada se resaltará para facilitar su identificación.

La paleta de colores también se aplicará a todos los tipos de Gráfico, excepto Waterfall y Treemap. La paleta de colores no es aplicable a Tablas, Colores de fuentes/etiquetas, Cortadoras, Fondo y KPI. Para saber más, consulte [Definir colores por defecto en los gráficos](../reports/set-default-colors-charts.htm "(se abre en una pestaña o una ventana nueva)").

## Informe Nivel de cobros

En la pestaña **Proyecto**, seleccione **Colecciones de informes**

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ccp-reportcollection.png)

Aparecerá la ventana emergente Gestionar colección de informes

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ccp-rcpopup.png)

Al seleccionar la paleta de colores, todos los informes de la colección de informes tendrán automáticamente la misma paleta de colores que se aplica a la colección de informes.

Nota: Si se añade un nuevo informe a la colección de informes, la paleta de colores del informe no cambiará automáticamente a la de la colección de informes. El administrador debe cambiarlo manualmente a nivel de informe.
