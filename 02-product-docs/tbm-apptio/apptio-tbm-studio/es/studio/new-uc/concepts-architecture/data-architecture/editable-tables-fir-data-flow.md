---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Cómo encajan las tablas editables en el flujo de datos"
breadcrumb:
  - "TBM Studio"
  - "Conceptos y arquitectura"
  - "Arquitectura de datos"
  - "Tablas y tipos de tablas"
source_path: "studio/new-uc/concepts-architecture/data-architecture/editable-tables-fir-data-flow.html"
images:
  - "resources/images/studio_images/editable-data-flow.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Cómo encajan las tablas editables en el flujo de datos

Las tablas editables participan en el flujo de datos a través de un mecanismo de publicación:

![Flujo de datos de tabla editable](../../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/editable-data-flow.png)

La publicación sobrescribe todo el conjunto de datos de la tabla editable en la tabla de transformación asociada. Esto puede hacerse manualmente o según una programación periódica (cada hora, cada día, cada semana o cada mes). Opcionalmente, la publicación puede activar una promoción automática al entorno de producción.

Nota:

**Importante**

Las tablas editables son específicas de cada rama. Al crear una rama, esta obtiene su propia copia de las tablas editables, y los cambios realizados en el tronco no se reflejan en la rama (y viceversa).

**Tema principal:** [Tablas y tipos de tablas](../../../../studio/new-uc/concepts-architecture/data-architecture/table-types.html)
