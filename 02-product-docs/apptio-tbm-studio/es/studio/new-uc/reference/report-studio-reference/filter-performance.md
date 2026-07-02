---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Consideraciones sobre el rendimiento de los filtros"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia de Report Studio"
  - "Componentes del informe: filtros y segmentadores"
source_path: "studio/new-uc/reference/report-studio-reference/filter-performance.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Consideraciones sobre el rendimiento de los filtros

**Listas de valores de gran tamaño**

**Límites y umbrales:**

|  |  |  |
| --- | --- | --- |
| **Componente** | **Límite** | **Manipulación** |
| Valores del cortador | 250 valores como máximo | Mensaje que aparece cuando se supera el límite |
| Diálogo de filtro | Se muestran 1.000 valores | Utiliza el cuadro de búsqueda para ver más valores |
| Editar selecciones de filtro | Sin límite estricto | Utiliza la opción «Valores no mostrados actualmente» |

**Buenas prácticas de rendimiento:**

1. Filtrar los segmentadores para reducir el número de valores antes de mostrarlos
2. Utilice cortadoras compactas cuando se necesiten múltiples dimensiones
3. Aplica filtros a nivel de componente para filtrar previamente los datos antes de que el segmentador los evalúe
4. Considera el uso de filtros jerárquicos para dimensiones categóricas de gran tamaño

**Tema principal:** [Componentes de los informes: Filtros y segmentadores](../../../../studio/new-uc/reference/report-studio-reference/report-component-filters-slicers.html)
