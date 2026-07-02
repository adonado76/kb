---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Asignar datos a una tabla de datos maestros"
breadcrumb: []
source_path: "cost-transparency/configuration/maptomaster.html"
images:
  - "resources/images/ct_images/6875_1.png"
  - "resources/images/ct_images/6875_2.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Asignar datos a una tabla de datos maestros

Después de cargar una tabla de datos de origen y transformarla si es necesario, puede asignarla a una tabla de datos maestros. Siga las siguientes instrucciones para asignar datos a una tabla de datos maestros.

Se aplica a: Costing Standard en TBM Studio 12.0 y posteriores

## Acerca de esta tarea

El método principal (y preferido) para asignar datos es utilizar Columnas de mapa en lugar de las instrucciones de la información siguiente. La función Asignar columnas está pensada para transformar el conjunto de datos de origen. Si los datos se reutilizan para varios conjuntos de datos maestros, cree una nueva tabla utilizando Origen de tabla existente para cada conjunto de datos maestros y, a continuación, añada Columnas de asignación. Para obtener instrucciones completas, consulte [Columnas del mapa](https://community.apptio.com/docs/DOC-11750 "(se abre en una pestaña o una ventana nueva)").

La siguiente información explica el método menos preferido para asignar datos utilizando el paso Añadir en el conjunto de datos maestros. Este método es menos preferido porque personaliza el conjunto de datos maestros, lo que aumenta el tiempo de las actualizaciones para recibir nuevos contenidos. Para más información, consulte [Añadir datos](https://community.apptio.com/docs/DOC-4980 "(se abre en una pestaña o una ventana nueva)").

## Procedimiento

1. En el **Explorador de proyectos**, haga clic en la tabla de datos maestros que desee.
2. Echa un vistazo a la tabla.
3. En el canal de transformación, haga clic en el paso **Añadir**.
4. Haga clic en **Añadir tabla** en el área de detalles.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6875_1.png)
5. Seleccione una tabla de datos de origen y haga clic en **Siguiente.**
6. Asigne las columnas de origen a las columnas del conjunto de datos maestro utilizando el siguiente método **Anexar a...** Imagen de datos maestros.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6875_2.png)

   Nota: Un asterisco (\*) en la columna Datos maestros indica que el campo es necesario para completar los informes relacionados con ese conjunto de datos. Se permite la asignación parcial. Si no dispone de todos los datos necesarios, puede asignar un subconjunto de los campos obligatorios, aunque al hacerlo podrían faltar datos en uno o más informes.
7. Haga clic en la opción para guardar.
