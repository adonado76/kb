---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Crear una tabla a partir de una tabla existente"
breadcrumb: []
source_path: "studio/data_studio/create-table-from-existing-table.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Crear una tabla a partir de una tabla existente

**Se aplica a** : TBM Studio 12.0 y posteriores

Puede haber ocasiones en las que desee crear una nueva tabla a partir de una tabla existente. Por ejemplo, puede tener una tabla que contenga una gran cantidad de información en varias columnas y desee crear un conjunto de datos con sólo algunas de las columnas para la elaboración de informes.

Cuando se crea una nueva tabla a partir de una tabla existente, la nueva tabla se vincula a la tabla de origen. Puede utilizar los datos de origen o la tabla de salida. Los datos de origen utilizan los datos brutos cargados en la aplicación. La tabla de salida utiliza los datos una vez aplicados todos los pasos de la cadena de transformación.

Hay muchas razones por las que puede querer crear una transformación:

- Depuración de datos
- Crear el nivel adecuado de granularidad en los datos
- Validación de los datos
- Realizar uniones complejas
- Realización de cálculos

Hay dos formas de crear una nueva tabla a partir de una tabla existente:

- Cree una nueva tabla y utilice la opción de origen **Tabla existente**.
- Haga clic con el botón derecho en el paso **Importar** o en el paso **Tabla** en el canal de transformación de una tabla existente y haga clic en **Crear nueva tabla a partir de este paso**.

Después de crear la tabla, haga clic en el paso **Tabla existente** en el canal de transformación de la nueva tabla y haga clic en la opción **Datos de origen** o **Tabla de salida**.
