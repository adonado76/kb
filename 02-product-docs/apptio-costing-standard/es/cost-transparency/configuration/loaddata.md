---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Cargar datos en la aplicación Costing Standard"
breadcrumb: []
source_path: "cost-transparency/configuration/loaddata.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Cargar datos en la aplicación Costing Standard

Las tablas de datos maestros proporcionan una forma de asignar sus datos a los datos requeridos por la aplicación CT. La siguiente información describe cómo cargar datos en la aplicación.

## Introducción

Cada componente de Costing Standard (CT) tiene una tabla de datos maestros. La tabla de datos maestros proporciona estructura a los datos relacionados. Los informes, las asignaciones y otros elementos de configuración están vinculados a la estructura de la tabla de datos maestros. No se editan directamente las tablas de datos maestros. En su lugar, se añaden y asignan datos a las tablas. Esto garantiza que no se modifique la estructura de las tablas de datos maestros.

La siguiente información describe cómo cargar datos en la aplicación. Consulte este tema cuando tenga que cargar una tabla de datos. El procedimiento de carga no se describe en ninguna otra parte de la Guía de Configuración.

## Cargue sus datos de origen

Debe cargar sus datos de origen en la aplicación. Después de cargar los datos, puede asignarlos a la tabla de datos maestros de un componente. Las tablas de datos que cargue deben contener campos que puedan asignarse a los campos requeridos en las tablas de datos maestros. No es necesario que las tablas de datos contengan todos los campos de las tablas de datos maestros.

A continuación se indica el procedimiento general para cargar una tabla de origen:

1. Haga clic en la pestaña **Inicio** de la cinta de opciones.
2. Haga clic en el menú **Nuevo** y, a continuación, en **Tabla**.
3. En el cuadro de diálogo Crear tabla, introduzca un nombre para la tabla.
4. Introduzca una categoría. Cuando empiece a escribir, se mostrarán los nombres coincidentes de las categorías que ya existen. También puede introducir un nuevo nombre de categoría. Las categorías se utilizan para organizar las tablas en el Explorador de proyectos.
5. Pulse **Aceptar**. La aplicación crea la tabla y muestra el paso Fuente en el canal de transformación como se muestra a continuación.
6. Haga clic en la opción **Cargar archivo**.
7. Realice una de las siguientes acciones para añadir un paso de Importación a la canalización:
   - Haga clic en el panel **Detalles** y busque el archivo que desea cargar.
   - Arrastre un archivo al panel **Detalles**.Se añade un paso de Importación al proceso.
8. Haga clic en el paso **Importar** de la canalización y revise la configuración:
   - Iniciar la importación en la fila - Indique la primera fila de la tabla que se incluirá en la importación.
   - Columnas a excluir - Indique si hay columnas que desea excluir.
   - Codificación de texto: si el archivo de datos utiliza una codificación de caracteres determinada, seleccione el esquema de codificación de la lista. Si no está seguro de la codificación, seleccione la opción Autodetectar codificación.
   - Delimitado -Seleccione el carácter que separa los campos de datos en el archivo. En la mayoría de los casos se trata de una coma.
   - Calificador de texto -Si hay caracteres de texto especiales en los datos, indique el calificador de texto que se utiliza para rodear esos caracteres.
   - Columnas - Revise las columnas que aparecen a la derecha y, si lo desea, cambie los tipos de columna. Para filtrar por tipo de columna (clave, texto, número, fecha), haga clic en un icono de tipo en el campo de búsqueda de la columna Tipo.
9. Para revisar la tabla cargada, haga clic en el paso **Tabla** del pipeline.
10. Si la tabla es aceptable, haga clic en **Guardar** en la cinta de opciones.
11. Cuando haya terminado de editar, haga clic en **Comprobar** en la cinta de opciones.

## Información relacionada

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentarios sobre el Centro de ayuda](productfeedback@apptio.com "(se abre en una pestaña o una ventana nueva)")
