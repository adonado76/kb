---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Sin identificador en el objeto modelo grande"
breadcrumb: []
source_path: "studio/troubleshooting/studio-troubleshooting-large-identifier.html"
images:
  - "resources/images/studio_images/troubleshooting/large-identifier-solution.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Sin identificador en el objeto modelo grande

Para mejorar el rendimiento, los objetos modelo con un gran número de filas deben tener un identificador.

[Crear un identificador de tabla personalizado](../model_studio/create-custom-table-identifier.html "Se aplica a: TBM Studio 12.0 y posteriores. El entorno de modelización Apptio proporciona un marco flexible para manipular los datos en agrupaciones que constituyen la base de las asignaciones y los informes. A continuación, se explicarán las mejores prácticas para elegir el identificador adecuado para una tabla modelo determinada.")

## Recomendación de configuración para el error No identifier on large model object

Para resolver este error:

1. Comprueba el objeto afectado.
2. En el desplegable Filas, seleccione Utilizar identificador de objeto y, a continuación, seleccione las columnas necesarias para el identificador.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/troubleshooting/large-identifier-solution.png)

Consejo: Las siguientes columnas suelen ser necesarias en el identificador:

- Tendencias
- Asignar por
- Cortar por
- Pivotar sobre
- Agrupación por
- Presentación de informes

A menos que se utilicen para las columnas anteriores, los identificadores no tienen que ser únicos.
