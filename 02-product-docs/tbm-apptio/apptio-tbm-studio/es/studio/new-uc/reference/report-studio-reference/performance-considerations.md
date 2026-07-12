---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Consideraciones sobre el rendimiento"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia de Report Studio"
  - "Componentes del informe: Tablas"
source_path: "studio/new-uc/reference/report-studio-reference/performance-considerations.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Consideraciones sobre el rendimiento

El rendimiento de la tabla depende del volumen de datos, los cálculos y la complejidad de la configuración.

|  |  |
| --- | --- |
| **Factor** | **Recomendación** |
| Recuento de filas | Utiliza la paginación para conjuntos de datos de gran tamaño. Considera la posibilidad de utilizar filtros para reducir el número de filas que se muestran. |
| Fórmulas complejas | Siempre que sea posible, traslada los cálculos complejos a transformaciones de « Data Studio ». |
| Varias columnas de hora | Cada columna basada en el calendario requiere cálculos independientes. Úsalo con moderación. |
| Gráficos de tendencia | Se necesitan datos para cada periodo analizado. Asegúrate de que los datos subyacentes existan. |
| Indicadores de estado | Los cálculos de iconos son ligeros, pero añaden una carga de procesamiento. |
| Profundidad de agrupación | Las jerarquías profundas (4 o más niveles) afectan al tiempo de renderizado. |
| Cortadoras interactivas | Utiliza la actualización manual para los informes en los que se interactúa mucho con los filtros. |

**Tema principal:** [Componentes del informe: Tablas](../../../../studio/new-uc/reference/report-studio-reference/report-component-table.html)
