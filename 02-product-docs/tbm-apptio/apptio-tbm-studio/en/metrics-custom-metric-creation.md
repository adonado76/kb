---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Custom Metric Creation"
breadcrumb:
  - "Reference"
  - "Model Studio Reference"
  - "Model Metrics"
  - "Custom Metric Creation"
source_path: "SSWRJM/studio/new-uc/reference/model-studio-reference/custom-metric-creation.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Custom Metric Creation

Creating a Modeled Metric

1. On the Home tab, click New > Metric
1. Enter a name and click OK
1. Set Model Type to Model
1. Configure Metric Type (Costing, Pricing, or Numeric)
1. Set Table Format and Chart Format as needed
1. Click Save

Creating a Calculated Metric

1. On the Home tab, click New > Metric
1. Enter a name and click OK
1. Set Model Type to Calculated
1. Enter the Value Calculation formula
1. Set Time Behavior (Sum, Average, or Recalculate)
1. Configure display formatting
1. Click Save

Note: After a calculated metric is created, the Model Type and Value Calculation fields become read-only.

Example: Budget Variance Metric

Create a calculated metric showing the difference between Budget and Cost:

- Name: Budget_Variance
- Model Type: Calculated
- Value Calculation: =Budget - Cost
- Time Behavior: Recalculate
- Table Format: =Currency($_)

See Section 3.2.8: Create custom metrics for detailed procedures

See Section 5.4: Formulas & Functions for calculation syntax
