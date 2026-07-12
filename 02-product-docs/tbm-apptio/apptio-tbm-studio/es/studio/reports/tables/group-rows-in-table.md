---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Agrupar las filas de una tabla"
breadcrumb: []
source_path: "studio/reports/tables/group-rows-in-table.html"
images:
  - "resources/images/studio_images/studioimages/reports/rep161.png"
  - "resources/images/studio_images/studioimages/reports/rep162.png"
  - "resources/images/studio_images/studioimages/studio/stu615.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Agrupar las filas de una tabla

**Se aplica a** : TBM Studio 12.0 y posteriores

Puede que desee consolidar los datos en una tabla agrupándolos por los valores de la primera columna. Para consolidar los datos, utilice la función Agrupar. Las tablas se agrupan automáticamente por al menos un campo en el área **Filas** del panel **Configuración de componentes**.

Puede agrupar las filas de una tabla haciendo clic en **Agrupar** en la pestaña **Datos**. Las siguientes imágenes muestran una tabla antes y después de la agrupación. Las columnas con dos o más valores diferentes mostrarán tres puntos verticales. Se añade una columna **Recuento** a la tabla que muestra el número de unidades del grupo.

Un ejemplo es la columna **SubService** de la siguiente imagen.

![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep162.png)

![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu615.png)

Si hay campos vacíos en la columna **Agrupar por**, se mostrará una fila en la parte inferior de la tabla con los siguientes valores:

| En esta columna: | Se muestra este valor: |
| --- | --- |
| Columna Agrupar por | en blanco |
| contar | Número de filas en blanco |
| Columnas numéricas | Suma de todas las filas con espacios en blanco en la columna Agrupar por |

Para agrupar una tabla:

1. Seleccione la tabla y, a continuación, haga clic en el icono **Grupo** de la pestaña **Datos**.
2. Aparecerá el cuadro de diálogo **Grupo** como se muestra en la siguiente imagen:

   ![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep161.png)
3. Seleccione las columnas que se utilizarán para agrupar la tabla. En la imagen anterior, se han seleccionado el **Centro de Datos** y el **Servicio**.
4. Después de hacer sus selecciones, haga clic en **Grupo**. La aplicación agrupa la tabla.
