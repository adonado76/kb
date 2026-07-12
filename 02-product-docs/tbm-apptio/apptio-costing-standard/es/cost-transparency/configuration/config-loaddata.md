---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Cargar datos"
breadcrumb:
  - "Costing Standard"
  - "Configuración"
source_path: "cost-transparency/configuration/config-loaddata.html"
images:
  - "resources/images/studio_images/load4a.png"
  - "resources/images/studio_images/load6.png"
  - "resources/images/studio_images/load7.png"
  - "resources/images/studio_images/load9.png"
  - "resources/images/studio_images/lod2a.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Cargar datos

Las tablas de datos maestros proporcionan una forma de asignar sus datos a los datos requeridos por la aplicación CT.

Cada componente de Costing Standard (CT) tiene una tabla de datos maestros. La tabla de datos maestros proporciona estructura a los datos relacionados. Los informes, las asignaciones y otros elementos de configuración están vinculados a la estructura de la tabla de datos maestros. No se cargan datos directamente en las tablas de datos maestros. En su lugar, se añaden o se asignan datos (utilizando el paso Map en el canal de datos) a las tablas. Esto garantiza que no se modifique la estructura de las tablas de datos maestros.

Debe cargar sus datos de origen en la aplicación. Después de cargar los datos, puede asignarlos a la tabla de datos maestros de un componente. Las tablas de datos que suba deben contener campos que puedan asignarse a los campos obligatorios de las tablas de datos maestros. Las tablas de datos no necesitan contener todos los campos de las tablas de datos maestros.

Para obtener más información sobre los tipos de datos que se pueden cargar y los diferentes métodos disponibles para cargar datos, haga clic [aquí.](https://www.ibm.com/docs/en/apptio-commercial/tbm-studio/saas?topic=data-upload "(se abre en una pestaña o una ventana nueva)")

A continuación se describe el procedimiento general para cargar una tabla de origen:

1. Haga clic en la pestaña **Inicio** de la cinta de opciones.
2. Haga clic en el menú **Nuevo** y, a continuación, haga clic en **Tabla**.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/lod2a.png)
3. En el cuadro de diálogo Crear tabla, introduzca un nombre para la tabla.
4. Introduzca una categoría. A medida que empieces a escribir, se mostrarán los nombres de las categorías que ya existen y que coincidan con lo que escribas. Además, puede introducir un nuevo nombre de categoría. Las categorías se utilizan para organizar las tablas en el Explorador de proyectos.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/load4a.png)
5. Pulse **Aceptar**. La aplicación crea la tabla y muestra el paso Fuente en el canal de transformación, tal y como se muestra a continuación.
6. Haga clic en la opción «**Subir archivo** ». Para obtener más información sobre otras opciones, haga clic [aquí](https://www.ibm.com/docs/en/apptio-commercial/tbm-studio/saas?topic=data-upload "(se abre en una pestaña o una ventana nueva)").

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/load6.png)
7. Se creará un paso de carga en el que el usuario podrá hacer clic/arrastrar el archivo o hacer clic con el botón derecho para pegarlo.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/load7.png)
8. Se añade un paso de importación al proceso.
9. Haga clic en el paso **Importar** en el proceso y revise la configuración:
   - Iniciar importación en la fila: indique la primera fila de la tabla que se incluirá en la importación.
   - Columnas que se deben excluir: indique si hay columnas que desea excluir.
   - Codificación de texto: si el archivo de datos utiliza una codificación de caracteres concreta, seleccione el esquema de codificación de la lista. Si no está seguro del tipo de codificación, seleccione la opción Detectar automáticamente la codificación.
   - Delimitado: seleccione el carácter que separa los campos de datos en el archivo. En la mayoría de los casos, será una coma.
   - Calificador de texto: si hay caracteres de texto especiales en los datos, indique el calificador de texto que se utiliza para rodear esos caracteres.
   - Columnas: revise las columnas que aparecen a la derecha y, si lo desea, cambie los tipos de columna. Para filtrar por tipo de columna (clave, texto, número, fecha), haga clic en el icono de tipo en el campo de búsqueda de la columna Tipo.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/load9.png)
10. Para revisar la tabla cargada, haga clic en el paso **Tabla** en el proceso.
11. Si la tabla es aceptable, haga clic en **Guardar** en la cinta.
12. Si ha terminado de realizar las modificaciones, haga clic en **«Check In»** (Registrar) en la cinta de opciones. Para obtener más información sobre el registro de entrada y salida, haga clic [aquí.](https://www.ibm.com/docs/en/apptio-commercial/tbm-studio/saas?topic=administration-best-practices-check-out-check-in "(se abre en una pestaña o una ventana nueva)")

Para obtener más información sobre funciones adicionales relacionadas con la carga de tablas, haga clic [aquí.](https://www.ibm.com/docs/en/apptio-commercial/tbm-studio/saas?topic=data-upload-file "(se abre en una pestaña o una ventana nueva)")

**Eliminar una tabla**

1. Echa un vistazo a la tabla.
2. En la pestaña **Inicio**, en el grupo **Documento**, haga clic en **Eliminar**.
3. Consulte la tabla.
