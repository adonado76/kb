---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Funciones de la mesa"
breadcrumb: []
source_path: "studio/data_studio/table-functions.html"
images:
  - "resources/images/icons/dropdown.png"
  - "resources/images/studio_images/datapath-databases.png"
  - "resources/images/studio_images/studioimages/datapath-1.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Funciones de la mesa

**Se aplica a** : TBM Studio 12.0 y posteriores

## ¿Cómo se utilizan las funciones de tabla en una ruta?

1. En la vista **del explorador de proyectos** TBM Studio , seleccione **Tablas**.
2. Seleccione una tabla (Por ejemplo, nombre de la tabla: XYZ) **>** Comprobar XYZ).
3. Añadir un paso de modelo **>** seleccionar **Modelo** **>** seleccionar XYZ **>** seleccionar **Usar identificador de objeto**.
4. Seleccione el menú desplegable **>** seleccione **Familia de aplicaciones** y **Función de la aplicación** **>** seleccione **Guardar**.
5. Ahora, necesita crear un nuevo informe. Seleccione **Nuevo** **>Informe** **>** Escriba un nombre para el informe **>** **Ok****.Nota:** Debe comenzar el nombre del informe con Texto, y no con números.
6. Seleccione la tabla XYZ en la **sección Configuración de componentes ad hoc**.
7. En el **Explorador de proyectos**, expanda ![](../../../../../03-media/apptio-tbm-studio/resources/images/icons/dropdown.png) junto a la tabla XYZ y arrastre **Familia de aplicaciones** a **Filas**. Los componentes de la tabla se cargan con agrupación automática.
8. Haga clic con el botón derecho del ratón dentro de la tabla **>** seleccione Mostrar ruta de datos completa. Puede ver las funciones de tabla GROUPBY, SORT y LIMIT\_COLUMNS.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/datapath-1.png)
9. ¡Para aplicar el!FILTRO en esta tabla, pulse **OK** para salir de esta ventana.
10. Supongamos ahora que no desea utilizar bases de datos. ¡Ponlo!Bases de datos aquí:

    ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/datapath-databases.png)
11. Las bases de datos ya no existen. Ahora, haga clic con el botón derecho del ratón dentro de la tabla **>** seleccione **Mostrar ruta de datos completa**. ¡Ahora puedes ver el!Función de filtro

## ¿Cómo utilizar estas funciones de tabla para obtener sus valores en una tabla editable?

1. Consulta una tabla editable.
2. Seleccione **Configurar columnas >** seleccione **Añadir una nueva columna >** seleccione **Valores posibles >**.
3. Puede poner la sintaxis de su función de tabla en los **Valores posibles >** seleccione **Guardar >** seleccione **Tabla editable** en el pipeline.
4. Una vez cargada la tabla, aparecerá una nueva columna. Puede hacer clic en las celdas de la nueva columna para seleccionarlas en el desplegable con las funciones de tabla.

Obtenga más información sobre las distintas funciones de tabla para obtener sus valores en la tabla editable:

- [!GROUPBY[]](groupby.html)
- [!LIMITAR\_COLUMNAS[]](limit-columns.html "Determina las columnas que se muestran en una tabla. Puede limitar las columnas mediante la cinta de opciones.")
- [!SORT[]](sort.html "Ordena una tabla en una o más columnas especificadas de la tabla. Puede ordenar una tabla utilizando la cinta de opciones. ¡El!La función SORT puede aplicarse utilizando una, dos o más columnas de una tabla.")

**Tema principal:** [Tablas editables: Adaptación a las entradas del usuario](../../studio/data_studio/editabletables.html "Se aplica a: TBM Studio 12.6 y posteriores")
