---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Versión de una tabla"
breadcrumb: []
source_path: "studio/data_studio/version_table.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Versión de una tabla

**Se aplica a** : TBM Studio 12.0 y posteriores

Puede haber ocasiones en las que los datos de una tabla cambien. Por ejemplo, las cuentas asignadas a los departamentos pueden modificarse al comienzo de un nuevo año natural fiscal. Esto puede afectar a los cálculos de un modelo. Desea conservar las asignaciones anteriores para que los cálculos históricos sigan siendo correctos, pero quiere que los nuevos datos se apliquen en el nuevo ejercicio. Para conservar los datos antiguos y facilitar la introducción de los nuevos, versiona la tabla.

Las siguientes reglas se aplican a las versiones:

- Debe consultar una tabla para versionarlo.
- El tiempo debe configurarse para el proyecto.
- No puede eliminar una versión si sólo existe una.
- Sólo puede eliminar una versión si la hora está fijada en el primer período de la versión y existe una versión anterior.
- No se puede crear una versión si la hora está fijada en el primer período de la versión.

Para versionar una tabla, en la pestaña **Inicio**, haz clic en **Crear versión**.

Para eliminar una versión, en la pestaña **Inicio**, haga clic en **Eliminar versión**.
