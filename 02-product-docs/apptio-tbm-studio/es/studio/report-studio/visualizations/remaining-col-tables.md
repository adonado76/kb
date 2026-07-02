---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Cambiar el nombre de las columnas de una tabla"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "ApptioIBM Report Studio (Nuevo)"
  - "Visualizaciones"
  - "Tabla"
source_path: "studio/report-studio/visualizations/remaining-col-tables.html"
images:
  - "resources/images/studio_images/rename1.png"
  - "resources/images/studio_images/rename2d.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Cambiar el nombre de las columnas de una tabla

Cambia el nombre de los encabezados de las columnas directamente desde el panel de configuración de datos, lo que te permite presentar los datos de una forma más significativa o intuitiva sin modificar el nombre de la dimensión subyacente.

Instrucciones de uso

1. **Abre el panel de configuración de datos de tu tabla**
   1. Ve a la pestaña «**Datos** ».
   2. Las dimensiones añadidas en la sección **«Filas»** definen las columnas de la tabla.
2. **Cambiar el nombre de una dimensión (encabezado de columna)**
   1. En la sección **«Filas»**, haz clic en el menú desplegable situado junto al nombre de la dimensión.

      ![editar el nombre que se muestra](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/rename1.png)
   2. Selecciona «**Editar nombre para mostrar** ».
   3. En el cuadro de diálogo **«Editar nombre para mostrar»**, introduce el nuevo nombre para mostrar de la columna.
   4. A continuación se muestra **el nombre original de la dimensión,** a modo de referencia.

      ![Imagen de la edición del nombre para mostrar](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/rename2d.png)
3. **Guardar cambios**
   1. Haz clic en **«Aceptar»** para confirmar los cambios.
   2. El nombre actualizado aparece como encabezado de columna en la tabla.

Nota: El cambio de nombre solo afecta al nombre que se muestra en la vista de tabla. El nombre original de la dimensión en el conjunto de datos no cambia.

**Tema principal:** [Tabla](../../../studio/report-studio/visualizations/rs-table.html "El componente de tabla muestra los datos en un formato tabular estructurado. Es ideal para mostrar información detallada, resumir métricas y facilitar el filtrado interactivo dentro de un informe.")
