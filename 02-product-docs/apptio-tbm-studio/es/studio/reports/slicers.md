---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Componente de la cortadora"
breadcrumb: []
source_path: "studio/reports/slicers.html"
images:
  - "resources/images/studio_images/studioimages/reports/rep016.png"
  - "resources/images/studio_images/studioimages/reports/rep017.png"
  - "resources/images/studio_images/studioimages/reports/rep045.png"
  - "resources/images/studio_images/studioimages/reports/rep331.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Componente de la cortadora

**Se aplica a** : TBM Studio 12.0 y posteriores

Cuando se añade una tabla o un gráfico a un informe, se toman decisiones sobre los datos que se muestran. Pero, ¿y si desea que los usuarios puedan filtrar el informe para satisfacer sus necesidades específicas? Puede darles esta capacidad añadiendo troceadores al informe. En la siguiente imagen se muestra un ejemplo de informe con dos cortadoras. Las cortadoras están a la izquierda:

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep016.png)

Puede filtrar el informe por tipo de servidor y coste. La siguiente imagen muestra el mismo informe filtrado para UNIX y Mayor que 10.000. Este tema y sus subtemas se centran en la creación de cortadoras. Las rebanadoras sólo funcionan con tablas y gráficos creados con el cuadro de diálogo Configuración de componentes ad hoc. No funcionan con tablas y gráficos heredados.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep017.png)

## Pestaña Rebanadora

Después de añadir una rebanadora a un informe, puede controlar su apariencia y funcionalidad utilizando la pestaña Rebanadora:

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep045.png)

## Puntos clave

A continuación se indican los puntos clave sobre la creación y el uso de cortadoras:

- Las rebanadoras sólo funcionan con tablas y gráficos Ad Hoc Query. No funcionan con tablas y gráficos heredados.
- Las rebanadoras deben ser añadidas a un informe por la persona que lo crea. Los usuarios finales no pueden crear rebanadoras cuando están visualizando un informe.
- Sólo los usuarios con funciones de administrador o analista pueden crear rebanadoras.
- Las rebanadoras añadidas a un informe están disponibles para todos los usuarios del informe.
- Las rebanadoras sólo muestran valores del mes en curso aunque las tablas anualizadas del informe muestren entradas de todo el año.
- `!ALL_ROWS` está activada por defecto en todos los proyectos. Cuando `!ALL_ROWS` está activado, las rebanadoras mostrarán todos los valores, incluidos aquellos que no tengan ninguna entrada en el periodo actual. Si `!ALL_ROWS` está desactivado en la Configuración del proyecto, las rebanadoras sólo mostrarán valores del mes en curso, aunque las tablas anualizadas del informe muestren entradas de todo el año.

  Ejemplo

  | Proveedor | Periodo | Gasto |
  | --- | --- | --- |
  | IBM | Ene | 100 |
  | IBM | Feb | 100 |
  | IBM | mar | 100 |
  | Cisco | Ene | 100 |
  | Cisco | Feb | 100 |

  En este ejemplo, tenemos gastos de proveedor de IBM de enero a marzo y gastos de proveedor para Cisco sólo en enero y febrero.
  - Si `ALL_ROWS` está habilitado, entonces en el Periodo Mar, tanto IBM como Cisco aparecerían en el slicer de Nombre de Proveedor.
  - Si se desactiva `ALL_ROWS` , entonces en el Periodo Mar, sólo aparecería IBM en el cortador de Nombre de Proveedor
- Los valores seleccionados en dos o más cortadoras se combinan mediante la lógica AND. Los valores seleccionados dentro de la misma rebanadora se combinan utilizando la lógica OR.
- Los cortes que no están en un cuadro de grupo se aplican a todas las tablas y gráficos del informe (incluso los que están en grupos y grupos anidados). Los cortes en un cuadro de grupo sólo se aplican a las tablas y gráficos dentro del cuadro de grupo y cualquier cuadro de grupo anidado.
- Las rebanadas de una pestaña sólo se aplican a las tablas y gráficos de la misma pestaña.
- Las rebanadoras se aplican inmediatamente al editar tablas y gráficos en los informes.
- Las cortadoras pueden ser jerárquicas.
- Un slicer sólo puede mostrar 250 valores. Si hay más valores, aparece un mensaje en la parte inferior de la cortadora.
- Si se imprime un informe, también se imprimen las rebanadoras para conservar la información sobre cómo se ha filtrado el informe.

## Combinación de cortadoras en una cortadora compacta

Si desea colocar varias rebanadoras en un informe, pero no quiere que ocupen una gran superficie del mismo, cree una rebanadora compacta. En la siguiente imagen se muestra un ejemplo. Para más información, consulte [Cortadoras compactas](compact-slicers.htm "(se abre en una pestaña o una ventana nueva)").

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep331.png)

## Detalles específicos de la cortadora

Las cortadoras se describen detalladamente en los siguientes temas:

- [Añadir cortadoras](add-slicer.htm "(se abre en una pestaña o una ventana nueva)")
- [Ordenar los valores de la cortadora](arrange-slicer-values.htm "(se abre en una pestaña o una ventana nueva)")
- [Estados y valores de la cortadora](slicer-states-and-values.htm "(se abre en una pestaña o una ventana nueva)")
- [Filtrar cortadoras](filter-slicers.htm "(se abre en una pestaña o una ventana nueva)")
- [Seleccione una opción de búsqueda](select-search-option.htm "(se abre en una pestaña o una ventana nueva)")
- [Cortadora compacta](compact-slicers.htm "(se abre en una pestaña o una ventana nueva)")
- [Cortadora jerárquica](hierarchical-slicers.htm "(se abre en una pestaña o una ventana nueva)")
