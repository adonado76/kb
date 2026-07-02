---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Custom Metric Creation"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Model Studio Reference"
  - "Model Metrics"
source_path: "studio/new-uc/reference/model-studio-reference/custom-metric-creation.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Custom Metric Creation

**Creating a Modeled Metric**

1. On the Home tab, click New > Metric
2. Enter a name and click OK
3. Set Model Type to Model
4. Configure Metric Type (Costing, Pricing, or Numeric)
5. Set Table Format and Chart Format as needed
6. Click Save

**Creating a Calculated Metric**

1. On the Home tab, click New > Metric
2. Enter a name and click OK
3. Set Model Type to Calculated
4. Enter the Value Calculation formula
5. Set Time Behavior (Sum, Average, or Recalculate)
6. Configure display formatting
7. Click Save

**Note:** After a calculated metric is created, the Model Type and Value Calculation fields
become read-only.

**Example: Budget Variance Metric**

Create a calculated metric showing the difference between Budget and Cost:

- Name: Budget\_Variance
- Model Type: Calculated
- Value Calculation: =Budget - Cost
- Time Behavior: Recalculate
- Table Format: =Currency($\_)

See Section 3.2.8: Create custom metrics for detailed procedures

See Section 5.4: Formulas & Functions for calculation syntax

**Parent topic:** [Model Metrics](../../../../studio/new-uc/reference/model-studio-reference/model-metrics.html)
