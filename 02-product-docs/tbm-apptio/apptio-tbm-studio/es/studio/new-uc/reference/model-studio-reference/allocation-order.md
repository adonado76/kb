---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Orden y prioridad de asignación"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia del estudio de modelos"
  - "Asignaciones"
source_path: "studio/new-uc/reference/model-studio-reference/allocation-order.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Orden y prioridad de asignación

Las asignaciones se ejecutan en un orden determinista basado en la estructura del gráfico del modelo.

**Normas de ejecución**

- Las asignaciones se ejecutan de nivel más bajo a nivel más alto (de abajo hacia arriba)
- Dentro de un nivel, las asignaciones se ejecutan en el orden en que se crearon
- Los controladores de unidad se ejecutan antes de las asignaciones de cada objeto
- Todas las entradas de un objeto deben completarse antes de que se ejecuten sus salidas. Las asignaciones recursivas se ejecutan después de las asignaciones estándar

**Tema principal:** [Asignaciones](../../../../studio/new-uc/reference/model-studio-reference/allocations.html)
