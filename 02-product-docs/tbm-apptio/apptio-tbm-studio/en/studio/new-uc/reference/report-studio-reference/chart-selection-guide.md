---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Chart Selection Guide"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Report Studio Reference"
  - "Report Components: Charts"
source_path: "studio/new-uc/reference/report-studio-reference/chart-selection-guide.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Chart Selection Guide

Use the following decision matrix to select the most appropriate chart type for your data and
analytical purpose:

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| **Purpose** | **Few Categories** | **Many Categories** | **Time-Based** | **Hierarchical** |
| Compare Values | Column | Bar | Column, Line | Tree Map |
| Show Trend | Line | Line | Trend | N/A |
| Part of Whole | Pie, Donut | Stacked Bar | Stacked Column | Tree Map |
| Explain Variance | Waterfall | Waterfall | Waterfall | N/A |
| Multi-Metric Compare | Radar | Overlay | Overlay | N/A |
| KPI Progress | Gauge | N/A | KPI Component | N/A |

**Best Practices for Chart Selection**

- Use pie charts only when showing parts of a whole and when you have 6 or fewer categories.
- Prefer bar charts over pie charts when precise comparisons are important.
- Use line charts for time-series data where the trend is more important than individual values.
- Use waterfall charts to explain variances or changes between two values.
- Use tree maps when you have hierarchical data and want to show relative size and proportions.
- Use overlay charts when comparing two related metrics that may have different scales.
- Use radar charts sparingly and only when comparing multiple attributes across a few items.

**Parent topic:** [Report Components: Charts](../../../../studio/new-uc/reference/report-studio-reference/report-component-charts.html)
