---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Ámbito del filtro"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia de Report Studio"
  - "Componentes del informe: filtros y segmentadores"
source_path: "studio/new-uc/reference/report-studio-reference/filter-scope.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Ámbito del filtro

**Ámbito de aplicación a nivel de informe**

Los filtros que se colocan directamente en el lienzo del informe (y no en un cuadro de grupo) se aplican a todas las tablas y gráficos del informe.

**Comportamiento:**

- Todos los componentes de consultas ad hoc responden a las selecciones del filtro
- Los filtros de las distintas pestañas solo afectan a los componentes de la misma pestaña
- Varios divisores se combinan mediante la lógica «Y»

**Ámbito a nivel de grupo**

Los segmentadores situados dentro de un cuadro de grupo se aplican únicamente a los componentes de ese grupo (y a los grupos anidados).

**Para crear filtros de ámbito de grupo:**

1. Añade un cuadro de grupo al informe
2. Coloca el cortador dentro del cuadro de grupo
3. Coloca las tablas o gráficos que deban filtrarse dentro del mismo grupo

Esto permite crear varios contextos de filtro independientes dentro de un mismo informe, vistas comparativas con diferentes configuraciones de filtro y filtrado específico por sección.

**Tema principal:** [Componentes de los informes: Filtros y segmentadores](../../../../studio/new-uc/reference/report-studio-reference/report-component-filters-slicers.html)
