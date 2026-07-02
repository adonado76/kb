---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Metric Properties"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Model Studio Reference"
  - "Model Metrics"
source_path: "studio/new-uc/reference/model-studio-reference/metric-properties.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Metric Properties

Each metric has configurable properties that control its behavior. Properties marked with (\*)
apply to calculated metrics only.

**Complete Property Reference**

|  |  |  |
| --- | --- | --- |
| **Property** | **Values** | **Description** |
| Default View | Report name | Report displayed when metric link is clicked |
| Model Type | Model, Calculated | Whether metric flows through allocations (Model) or uses formula (Calculated) |
| Metric Type | Costing, Pricing, Numeric | Costing = monetary; Pricing = price x quantity; Numeric = other |
| Hidden | Boolean | Hides metric in model object unit tables |
| Table Format | Formula | Display format in tables (e.g., =Currency($\_)) |
| Chart Format | Pattern | Number format on chart axis (e.g., $#,###) |
| Chart Prefix | Text | Prefix added to metric in charts (e.g., $) |
| Chart Suffix | Text | Suffix added to metric in charts |
| Time Behavior | Sum, Average, Recalculate | How metric aggregates across time periods |
| Value Calculation\* | Formula | Formula defining calculated metric value |
| Can Sum\* | Boolean | Whether values can be added vs. recalculated |
| Include in Virtual Models\* | Boolean | Include in filtered and recursive models |
| Ignore for Internal Filtering\* | Boolean | Exclude from zero-row filtering evaluation |
| Time Interval\* | None, Quarterly, Yearly | Pull value from first period of interval |

**Time Behavior Options**

|  |  |
| --- | --- |
| **Option** | **Behavior** |
| Sum | Calculates each period separately, then adds periods together. Use for additive metrics like Cost. |
| Average | Calculates each period, adds together, divides by period count. Use for rate metrics. |
| Recalculate | Computes aggregated values in all columns, then reruns formula. Use for ratios. |

**Parent topic:** [Model Metrics](../../../../studio/new-uc/reference/model-studio-reference/model-metrics.html)
