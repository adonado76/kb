---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Metric Classification"
breadcrumb:
  - "Reference"
  - "Model Studio Reference"
  - "Model Metrics"
  - "Metric Classification"
source_path: "SSWRJM/studio/new-uc/reference/model-studio-reference/metric-classification.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Metric Classification

Metrics are classified into two categories based on how they derive their values.

Modeled Metrics

Description: A modeled metric flows through the allocation structure. It has drivers that bring value in and allocations that distribute value out. Cost, Budget, and Forecast are typically modeled metrics.

Characteristics

- Value is summed when grouping
- Cannot calculate across time periods
- Participates in allocation flows
- Displayed in model reports

Calculated Metrics

Description: A calculated metric uses a formula to derive its value from other metrics or columns. Variance and ratio metrics are typically calculated.

Characteristics

- Formula recalculates on every view (not summed)
- Can calculate across time periods
- Does not participate in allocations
- Used for analysis and reporting
