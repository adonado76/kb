---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Solucionar errores de eliminación de datos de referencia"
breadcrumb:
  - "Planning"
  - "Solución de problemas y preguntas frecuentes"
source_path: "it-planning/planning/ts-reference-data.html"
images:
  - "resources/images/it_planning_images/publish_dialog.jpg"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Solucionar errores de eliminación de datos de referencia

## Acerca de esta tarea

Las siguientes tareas sólo pueden ser realizadas por usuarios asignados a los roles de Administrador o Propietario de Proceso Presupuestario.

Si elimina un atributo e intenta publicar una dimensión en los datos de referencia, puede recibir el siguiente error:![icono engranaje](../../../../../03-media/apptio-planning/resources/images/it_planning_images/publish_dialog.jpg)

## Procedimiento

Muchas dimensiones integradas dependen de otras dimensiones. Para obtener más información, consulte [Relación de atributos y dimensiones de los datos de referencia](manage-reference-data.html).

Por ejemplo, una dimensión Departamento puede contener un Centro de Coste. La eliminación de esa dimensión de Centro de Coste daría lugar a un error. Para evitar recibir este error, primero debe eliminar la cota relacionada antes de poder eliminar la cota original.

1. Exporte las tablas de datos de referencia afectadas. Para más información, consulte [Descargar y rellenar tablas o plantillas de datos de referencia](manage-reference-data.html).
2. Edite la plantilla según sea necesario para eliminar los datos afectados.
3. Importe y publique la tabla de datos de referencia actualizada. Para más información, consulte [Importar y publicar datos de referencia](manage-reference-data.html).

Nota: Si sigue teniendo problemas, puede eliminar el contenido de ambas dimensiones y volver a importarlo.
