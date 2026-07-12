---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "El espacio de trabajo de transformación de datos"
breadcrumb: []
source_path: "studio/data_studio/transform-workspace.html"
images:
  - "resources/images/studio_images/blue-ind.png"
  - "resources/images/studio_images/en-feat.jpg"
  - "resources/images/studio_images/pe-expand-filter.png"
  - "resources/images/studio_images/pe-filter.png"
  - "resources/images/studio_images/studioimages/studio_data_studio_transform_workspace_sui.png"
  - "resources/images/studio_images/studioimages/studio_data_studio_transform_workspace_tables_sui.png"
  - "resources/images/studio_images/studioimages/studio_data_trans_add_step_sui.png"
  - "resources/images/studio_images/studioimages/studio_project_explorer_errors_sui.png"
  - "resources/images/studio_images/studioimages/studio_project_explorer_servers_master_data.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# El espacio de trabajo de transformación de datos

**Se aplica a** : TBM Studio 12.0 y posteriores. Utilice el área de trabajo de transformación de datos para importar datos y modificarlos para que se ajusten a sus necesidades.

El espacio de trabajo de transformación de datos se divide en tres paneles.

- Panel **Explorador de proyectos** : Utilícelo para seleccionar una tabla que desee transformar.
- Panel **Pasos de transformación** : Se utiliza para añadir pasos de transformación.
- Panel **Detalles del paso de transformación/Previsualización de datos** : Muestra detalles sobre un paso de transformación o muestra la tabla después de aplicar el paso actual. Las pestañas que aparecen en la parte inferior de los paneles Pasos de transformación y Detalles de los pasos de transformación son los documentos que ha seleccionado en el **Explorador de proyectos**.

  ![Explorador de proyectos](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio_data_studio_transform_workspace_sui.png)

## Explorador de proyectos

El panel **Explorador de proyectos** muestra los documentos disponibles. Los tipos de documentos son:

- Tablas
- Tablas editables
- Métricas
- Perspectivas
- Tablas publicadas
- Informes
- Hora

Cuando trabaje con datos, se centrará en la sección **Tablas**.

Para mostrar el panel **Explorador de proyectos** :

- En TBM Studio v12.1 y versiones anteriores, haga clic en el icono de modo TBM
  Studio ![Icono de modo](../../resources/images/studio_images/studioimages/icons/studio%20mode.png) situado a la derecha de la cabecera global.
- En TBM Studio v12.2+, abra el menú Aplicaciones/Proyectos y haga clic en **TBM Studio**.

Para cambiar la anchura del panel **Explorador**, arrastre el tirador del borde derecho. Para minimizar el panel **del Explorador**, haga clic en la flecha de minimización situada en la esquina superior derecha del panel.

## Expansión de carpetas filtradas - Explorador de proyectos

**Se aplica a** : 12.11.2 y posteriores

Esta función permite filtrar y ver a qué carpeta pertenece una tabla, una tabla editable, una perspectiva o un informe. Para activar esta función, vaya a la pestaña **Proyectos** > **Activar funciones** y seleccione la casilla **Mostrar resultados agrupados en el explorador de proyectos**.

![Activar funciones](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/en-feat.jpg)

Para encontrar un documento en el **Project** Explorer, introduzca el término de búsqueda en la barra de búsqueda del Project Explorer, o seleccione un filtro predefinido en el desplegable. Los resultados de la búsqueda se mostrarán dentro de su carpeta asociada en una vista ampliada. La vista ampliada de carpetas no es aplicable a las secciones Métricas y Tiempo.

![vista ampliada](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/pe-expand-filter.png)

![Informes](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/pe-filter.png)

Si borra el término de búsqueda en la barra de búsqueda, volverá automáticamente a la vista "Todos" en el desplegable.

Nota: El triángulo azul ![Icono de](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/blue-ind.png)indica que el sistema está consultando el back-end y aún no se han devuelto los resultados.

## Sección de tablas

Los cuadros están agrupados por categorías. Por defecto, existe una categoría **General**. También habrá otras categorías basadas en la aplicación que estés utilizando, y categorías personalizadas creadas por otros usuarios. Puede crear nuevas categorías al crear una nueva tabla.

Para limitar las tablas mostradas, utilice el filtro que se muestra a continuación:

![Sección de tablas](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio_data_studio_transform_workspace_tables_sui.png)

## Columnas de tabla

Para visualizar las columnas de una tabla, haga clic en la flecha situada a la izquierda del nombre de la tabla. En el ejemplo siguiente, la tabla es **Datos maestros de servidores**.

Las columnas son Unidades reales, Edad, etc.

![Columnas de tabla](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio_project_explorer_servers_master_data.png)

El símbolo delante del nombre de una columna indica el tipo de columna:

- (![Icono clave](../../resources/images/studio_images/studioimages/icons/column%20type%20key.png)) Tecla
- (![Icono de etiqueta](../../resources/images/studio_images/studioimages/icons/column%20type%20label.png)) Etiqueta
- (![Icono del número](../../resources/images/studio_images/studioimages/icons/column%20type%20numeric.png)) Numérico
- (![Icono del selector de fechas](../../resources/images/studio_images/studioimages/icons/column%20type%20date.png)) Fecha

El estado de un documento se indica mediante la fuente:

- Llano: Registrado
- *Cursiva* : Comprobado por otra persona
- **Orange Bold** : Comprobado por usted

## Errores de tabla

(Se aplica a: TBM Studio v12.1, v12.2+.4 )

Cuando se trabaja con tablas y con el proceso de transformación, pueden producirse una gran variedad de errores. A continuación se enumeran algunos de los errores típicos.

- Falta una tabla anexa
- Un paso de transformación hace referencia a una columna que falta en una tabla

Si una tabla tiene uno o más errores, en el Explorador de proyectos aparece un número a la derecha del nombre de la tabla que indica el número de errores. En el siguiente ejemplo, la tabla All Business Services tiene un error y la tabla Cloud Service Provider tiene cuatro errores. Cuando se visualiza el pipeline de la tabla, a la derecha del nombre del paso aparece un número que indica el número de errores. Cuando señale el número con el cursor del ratón, una información sobre herramientas mostrará el mensaje de error:

![Mensaje de error](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio_project_explorer_errors_sui.png)

## Transformación de pasos

Añada pasos a la cadena de Transformación de Pasos según sea necesario.

- Para mostrar el panel **Pasos de transformación**, seleccione una tabla de la sección **Tablas** del **Explorador de proyectos**.
- Para añadir un paso, desplace el cursor hasta la línea que divide dos pasos existentes y, a continuación, haga clic en el signo más situado en el borde derecho del panel **Transformar pasos**. Haga clic en el tipo de paso que desea añadir. Algunos tipos de pasos sólo pueden utilizarse una vez en una canalización, por ejemplo **la Partición de datos**. Si el paso ya se ha añadido al pipeline, aparecerá un banner en la esquina inferior izquierda de la opción del paso.

  ![Partición de datos](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio_data_trans_add_step_sui.png)
- Para cambiar el lugar donde se produce un paso en una canalización, arrastre el paso a una nueva posición en la canalización. Los siguientes pasos no se pueden reordenar: Origen, Cargar, Importar, Tabla, Modelo.
- Para minimizar el panel **Pasos**, haga clic en la flecha situada en la esquina superior derecha del panel.
- Para ajustar la anchura del panel **Explorador de proyectos**, arrastre el tirador divisor del borde derecho.
- Para guardar los pasos de transformación, haga clic en la pestaña **Inicio** y, a continuación, en **Guardar**.
