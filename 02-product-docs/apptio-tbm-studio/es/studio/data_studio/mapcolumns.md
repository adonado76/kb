---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Columnas del mapa"
breadcrumb: []
source_path: "studio/data_studio/mapcolumns.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Columnas del mapa

**Se aplica a** : TBM Studio 12.7 y posteriores. Las aplicaciones disponibles en TBM Studio requieren alinear los datos con los conjuntos de datos maestros. Con la versión 12.7, todos los clientes disponen de un nuevo paso de canalización: **Map Columns**.

**Las columnas de mapa** se pueden añadir a una tabla de salida aparte de los propios conjuntos de datos maestros. Tras añadir el paso, se solicita un destino. Cualquier información mapeada se añade a la tabla de destino en un nuevo paso de "Tablas mapeadas" en los conjuntos de datos maestros. Los conjuntos de datos maestros son los únicos destinos válidos.

Consejo: Después de cargar una tabla de datos de origen y transformarla, si es necesario, puede asignarla a una tabla de datos maestros. Si está ejecutando TBM Studio 12.7 o posterior, Apptio le recomienda que utilice la función Mapear columnas, descrita aquí, para mapear datos (excepto para Nube). Si Mapear columnas no es una opción para usted, consulte los métodos alternativos descritos aquí: [Asignar datos a una tabla de datos maestros](../../cost-transparency/configuration/maptomaster.html "(se abre en una pestaña o una ventana nueva)") y [Asignación de nubes](../../cost-transparency/configuration/cloudmapping.html "(se abre en una pestaña o una ventana nueva)").

**Requisitos previos**

- Los componentes deben estar instalados para poder asignarse a sus conjuntos de datos maestros.
- Los conjuntos de datos maestros deben estar en las versiones de contenido 104 o posteriores.

## Añada el paso Map Columns pipeline y elija un destino

1. Crear o consultar una tabla y añadir datos en ella. Además, puede aplicar pasos de transformación, como la Partición de fechas.
2. Pase el ratón por encima de los pasos de la canalización y haga clic en **+** para añadir un nuevo paso. **Columnas del Mapa** está disponible a menos que se haya añadido un paso Modelo.![](../../resources/images/studio_images/studioimages/studio_add%20step_map%20columns.png)

   Nota: Si la tabla fue revertida y la carga de datos no, el paso no estará disponible hasta que usted agregue cualquier otro paso y luego agregue Columnas de Mapa.
3. Haga clic en **Asignar columnas** y, a continuación, seleccione un destino. Si no ve el conjunto de datos maestros que esperaba, vaya a **Componentes** e instale el componente necesario.![](../../resources/images/studio_images/studioimages/studio_map%20columns_destination.png)

## Asignar a una columna del conjunto de datos maestros

1. Revise las columnas de destino. Son las columnas de los conjuntos de datos maestros a las que se puede asignar. Es posible que algunos ya estén asignados porque un encabezado de columna de su tabla coincide con un valor esperado en el destino.
2. Seleccione **Elegir fuente** en la columna Fuente, o para cambiar una asignación, seleccione uno de los otros valores de esa columna.![](../../resources/images/studio_images/studioimages/studio_map%20columns_cost%20center.png)
3. Elija uno de los nombres de columna de la lista desplegable. Esta lista muestra todas las columnas de la tabla con un tipo de columna coincidente con el destino.

   Nota: La siguiente tabla de vista previa no se actualizará hasta que se guarde el cambio.

   Consejo: Si no ve las columnas que desea en la lista desplegable, es posible que no sean del tipo de correspondencia adecuado para el destino. Vaya al paso Importar y cambie la opción Anular tipo según sea necesario. Si la columna esperada se creó en el canal de transformación, utilice o modifique el paso Fórmulas.
4. Para introducir una cadena o un número para todas las líneas, seleccione **Introducir un valor fijo para todas las líneas**. Como resultado, cada fila de la tabla muestra el mismo valor para esa columna. Esta opción no evalúa las fórmulas. Para utilizar una fórmula, añada el paso **Fórmulas** y, a continuación, asigne la columna adicional resultante.
5. Ingrese el valor y luego haga clic en **Aceptar**. Ahora ha asignado dos columnas adicionales al conjunto de datos maestros eligiendo una columna de su tabla e ingresando un valor.

## Añadir una columna personalizada al conjunto de datos maestros

1. Para añadir una columna que no existe en el conjunto de datos maestros, haga clic en **Añadir columna personalizada**. Estos añadidos se mantendrán entre actualizaciones sin necesidad de acciones especiales.
2. Introduzca el nombre de la columna que desea añadir y elija el tipo. Seleccione una fuente para esa columna, ya sea eligiendo otra columna de la tabla o un valor fijo.
3. Pulse **Aceptar**. Las columnas añadidas son siempre opcionales. Guarde la tabla para ver la columna en la vista previa.

## Utilizar Join para asignar columnas

1. Utilice el paso **Unir** para asignar columnas en las que otro conjunto de datos tenga información adicional que pueda compararse con los datos de la tabla asignada. Para utilizar esta función, haga clic en **Unirse**.
2. Haga clic en **Añadir enlace** y, a continuación, seleccione la tabla a la que desea unirse o arrastre la tabla desde la sección **Tablas** del **Explorador de proyectos** y trace una línea hasta ella. **De columna** y **A columna** representan una relación clave en la que se espera que los valores coincidan.![](../../resources/images/studio_images/studioimages/studio_map%20columns_add%20link.png)
3. Seleccione las columnas adecuadas y haga clic en **Aceptar**.

   Nota: La vista previa no se actualizará hasta que haga clic en **Guardar**.
4. Haga clic en **Asignar columnas** y, a continuación, seleccione la columna que desee asignar. Las columnas recién asignadas aparecen en la lista desplegable con el nombre de la tabla, "." y, a continuación, el nombre de la columna. Las columnas también aparecen en la pestaña **Columnas no mapeadas** :![](../../resources/images/studio_images/studioimages/studio_map%20columns_chart%20of%20accounts%20master%20data.png)
5. Seleccione la columna deseada y, a continuación, guarde para actualizar la tabla de vista previa.

## Navegar por las columnas del mapa

1. En la parte superior derecha, utilice **Buscar en todos los campos** para buscar en las columnas Destino, Origen y Descripción.
2. Haga clic en cada encabezado de columna para ordenar cada columna o invertir el orden de cada columna.
3. La tabla de vista previa muestra los resultados de la asignación de columnas cuando se asigna al menos una columna o la tabla sin asignar si no se asigna nada. Cuando algunas columnas pero no todas están mapeadas, la pestaña por defecto muestra lo que ha sido mapeado, y "Columnas no mapeadas" está disponible en las pestañas.

## Ver tablas asignadas en conjuntos de datos maestros

- Para ver todas las tablas que envían datos al conjunto de datos maestros, vaya al conjunto de datos maestros correspondiente y seleccione **Tablas asignadas**.![](../../resources/images/studio_images/studioimages/studio_cost%20source%20master%20data_mapped%20tables.png)
- En la tabla Vista previa, la columna **Tabla de origen** identifica de qué tabla procede la fila. Utilice el **filtro de búsqueda automática** para ver todas las filas de una misma fuente.![](../../resources/images/studio_images/studioimages/studio_mapped%20tables_source%20table.png)
- Utilice la tabla en Tablas mapeadas para navegar hasta la tabla de origen y mostrar la siguiente información:
  - Nombre de la tabla que contiene el paso Map Columns coincidente.
  - La última vez que se cambió la mesa.
  - El recuento de filas de la tabla asignada.
  - Número de columnas marcadas como Obligatorias que se han añadido.
  - Número de columnas del conjunto de datos maestros que se han asignado en total.
  - Número de columnas que se han añadido al conjunto de datos maestros.
  - Descripción de la tabla añadida al conjunto de datos maestros. La adición de una descripción a las tablas facilitará su mantenimiento y es muy recomendable para cualquier tabla que se vaya a asignar a un conjunto de datos maestros con más de una tabla asignada.

## Actualizaciones de la aplicación y columnas del mapa

Cuando se publique nuevo contenido de la aplicación, puede actualizar los proyectos para que reciban los cambios. Para más información, consulte [Acerca de la mejora de la transparencia de los costes](../../cost-transparency/configuration%20-%20additional/aboutupgradingct.htm "(se abre en una pestaña o una ventana nueva)").

Map Columns siempre muestra información para la misma versión de contenido de la aplicación que el conjunto de datos maestros. Si se ha actualizado el componente pero el conjunto de datos maestros está personalizado, no se producirá ningún cambio. Las actualizaciones menores, como las descripciones de las columnas, pueden producirse en cualquier momento.

Para actualizar un conjunto de datos maestros, vaya a Componentes y seleccione el Componente que contiene ese conjunto de datos maestros. Desplácese hasta **Elementos personalizados**. En la lista, busque el nombre del conjunto de datos maestros y haga clic en la **flecha de** la izquierda.

![](../../resources/images/studio_images/studioimages/studio_comp_app%20dev.png)
