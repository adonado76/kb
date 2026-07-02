---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Clasificación métrica"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia del estudio de modelos"
  - "Métricas de modelo"
source_path: "studio/new-uc/reference/model-studio-reference/metric-classification.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Clasificación métrica

Las métricas se clasifican en dos categorías según cómo se obtienen sus valores.

**Métricas modelizadas**

**Descripción:** Una métrica modelada recorre la estructura de asignación. Cuenta con factores que aportan valor y asignaciones que lo distribuyen. El coste, el presupuesto y las previsiones suelen ser métricas modelizadas.

**Características**

- El valor se suma al agrupar
- No se pueden realizar cálculos entre distintos periodos
- Participa en los flujos de asignación
- Se muestra en los informes de modelos

**Métricas calculadas**

**Descripción:** Una métrica calculada utiliza una fórmula para obtener su valor a partir de otras métricas o columnas. Normalmente se calculan métricas de varianza y de ratio.

**Características**

- La fórmula se vuelve a calcular cada vez que se visualiza (no se suma)
- Puede realizar cálculos a lo largo de distintos periodos de tiempo
- No participa en las asignaciones
- Se utiliza para el análisis y la elaboración de informes

**Tema principal:** [Métricas del modelo](../../../../studio/new-uc/reference/model-studio-reference/model-metrics.html)
