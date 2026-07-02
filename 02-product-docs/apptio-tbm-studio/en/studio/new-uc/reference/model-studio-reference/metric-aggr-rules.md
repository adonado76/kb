---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Metric Aggregation Rules"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Model Studio Reference"
  - "Model Metrics"
source_path: "studio/new-uc/reference/model-studio-reference/metric-aggr-rules.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Metric Aggregation Rules

**How Modeled Metrics Aggregate**

When viewing modeled metrics at different grouping levels:

- Detail level: Shows individual row values
- Grouped level: Sums all values in the group
- Across periods: Follows Time Behavior setting

**How Calculated Metrics Aggregate**

Calculated metrics recalculate their formula at each grouping level rather than summing:

- Detail level: Formula runs per row
- Grouped level: Formula runs on grouped values
- Exception: If Can Sum is checked, values are added instead

**Parent topic:** [Model Metrics](../../../../studio/new-uc/reference/model-studio-reference/model-metrics.html)
