---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Cortadoras compactas"
breadcrumb: []
source_path: "studio/reports/compact-slicers.html"
images:
  - "resources/images/studio_images/studioimages/reports/rep331.png"
  - "resources/images/studio_images/studioimages/reports/rep332.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Cortadoras compactas

**Se aplica a** : TBM Studio 12.0 y posteriores

Si desea colocar varias rebanadoras en un informe, pero no quiere que ocupen una gran superficie del mismo, cree una rebanadora compacta. Las cortadoras compactas pueden ser locales o globales. El ejemplo de la imagen siguiente incluye un cortador compacto local y un cortador compacto global:

![segmentaciones](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep331.png)

## Tipos de cortadoras compactas

Existen dos tipos de cortadoras compactas: locales y globales.

- **Local** - Un slicer compacto local tiene las mismas propiedades que un slicer individual. Puede utilizar tanto campos bloqueados como desbloqueados. Las selecciones realizadas en las cortadoras por los usuarios no se guardan.
- **Global** - Un slicer compacto global tiene las mismas propiedades que un filtro global.
  - Aplicar a todas las tablas y gráficos basados en objetos de un informe.
  - Sólo los campos bloqueados a un objeto pueden incluirse en un rebanador compacto global.
  - Las cortadoras compactas globales pueden incluir varios campos. Los campos deben ser de perspectivas personalizadas o de aplicación. No puede utilizar campos de las perspectivas Datos, Cálculos o Tiempo.
  - Los usuarios individuales pueden guardar sus propios ajustes globales del filtro de corte compacto.
  - Los ajustes guardados se mantienen cuando el usuario sale de la aplicación y vuelve a entrar.
  - Los cambios realizados en un corte compacto global en un informe se aplican a todos los informes que incluyen el corte.
  - Se pueden añadir diferentes rebanadoras compactas globales a diferentes conjuntos de informes.
  - Si envía un informe por correo electrónico, los ajustes globales del cortador compacto se guardan con el informe.

Las cortadoras compactas globales están pensadas para sustituir a los filtros globales. Siempre que sea posible, utilice cortadoras compactas globales en lugar de filtros globales.

## Crear una cortadora compacta

Para crear una cortadora compacta:

1. En la pestaña **Informe**, haga clic en **Compact Slicer**.
2. Decida si la cortadora será local o global y seleccione la opción adecuada en la pestaña **Compactar cortadora****.AVISO**

   Si crea un cortador compacto local y luego lo cambia a un cortador compacto global, los campos desbloqueados se eliminarán del panel de configuración y sus correspondientes cortadores se eliminarán del cortador compacto.
3. En el panel **Configuración de la rebanadora** compacta, arrastre los campos a la rebanadora Mediante area.When. Si añade un campo, se añadirá la rebanadora correspondiente a la rebanadora compacta.

## Filtrar una cortadora compacta

Puede aplicar filtros a cada una de las cortadoras de una cortadora compacta seleccionando una cortadora y creando los filtros en el cuadro de diálogo **Configuración de cortadoras**. Los usuarios no podrán modificar los filtros. Para más información, consulte [Filtrar cortadoras](filter-slicers.htm "(se abre en una pestaña o una ventana nueva)").

## Seleccionar valores de corte

Puede seleccionar valores de corte en un corte compacto expandiendo el corte. Los valores seleccionados aparecen en la línea situada bajo el nombre de la cortadora, como se muestra en la imagen siguiente. Si hay más valores de los que se pueden mostrar en la línea, puede pasar el puntero del ratón por encima de la línea y aparecerá una ventana emergente con una lista de todos los valores. Los usuarios pueden modificar los filtros creados de esta forma.

![Cortadoras compactas](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep332.png)

## Formatear una cortadora compacta

Al igual que con las cortadoras estándar, puede formatear una cortadora compacta utilizando las opciones de la pestaña **Cortadora compacta**.

Para formatear una cortadora:

1. Haga clic en la rebanadora en la rebanadora compacta.
2. Haga clic en la pestaña **Compact Slicer**.
3. Seleccione las opciones de formato.
   - Para obtener información sobre las opciones de búsqueda, consulte [Seleccionar una opción de búsqueda](select-search-option.htm "(se abre en una pestaña o una ventana nueva)")
   - Para más información sobre las opciones de ordenación, véase [Ordenar valores de la cortadora](slicer-states-and-values.htm "(se abre en una pestaña o una ventana nueva)")
