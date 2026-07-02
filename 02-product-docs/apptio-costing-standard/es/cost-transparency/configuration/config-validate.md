---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Validar asignaciones de modelos"
breadcrumb:
  - "Costing Standard"
  - "Configuración"
source_path: "cost-transparency/configuration/config-validate.html"
images:
  - "resources/images/studio_images/da.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Validar asignaciones de modelos

Utilice la vista de tabla del modelo para validar el flujo de valor en un modelo. Una vez que haya cargado y asignado los datos de origen a la tabla de datos maestros adecuada, las tablas modeladas asociadas deberían comenzar a mostrar tanto los impulsores unitarios como las asignaciones.

Una tabla modelada según el estándar de costes es una tabla a la que se ha añadido un paso de modelo. La tabla modelada es una transformación de una tabla de datos maestros. Por ejemplo, la tabla «Cost Source» es una transformación de la tabla «Cost Source Master Data». No se pueden añadir pasos adicionales al proceso de transformación en las tablas modeladas con Costing Standard. Los únicos pasos de transformación que se muestran para las tablas modeladas son **Origen** y **Modelo**.

**Diagrama de asignación de conductores**

Si hace clic en una tabla de modelos en **el Explorador de proyectos** y, a continuación, hace clic en el paso Modelo en el canal de transformación, se muestra un diagrama de asignación de controladores como se muestra a continuación. Utilice el diagrama para comprobar el flujo de valores hacia y desde la tabla.

![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/da.png)

El diagrama muestra el flujo de valor para la métrica del modelo seleccionada en el campo **Seleccionar una métrica** situado encima del diagrama. En la figura A anterior, la métrica es el coste. Puede seleccionar cualquiera de las métricas de modelo definidas para el proyecto.

**Realizar cambios**

Puede realizar cambios en las asignaciones del modelo de cálculo de costes estándar. Puede modificar las asignaciones existentes y añadir nuevas asignaciones. Antes de realizar cambios en un modelo, debe comprender a fondo cómo crear y modificar modelos.

Para obtener información sobre cómo trabajar con modelos, consulte [Acerca de Model Studio.](https://www.ibm.com/docs/en/apptio-commercial/tbm-studio/saas?topic=metrics-about-model-studio "(se abre en una pestaña o una ventana nueva)")
