---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Bar Charts"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Report Studio Reference"
  - "Report Components: Charts"
source_path: "studio/new-uc/reference/report-studio-reference/bar-charts.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Bar Charts

Bar charts display horizontal bars to compare values across categories. They are the default
chart type when you add a new chart to a report and are ideal when category labels are long or when
comparing many items.

**Horizontal Bar Chart**

The standard horizontal bar chart displays a single series of values with bars extending from
left to right. Each bar represents a category value, making it easy to compare magnitudes across
different items such as cost centers, applications, or business units.

**When to use:** Compare values across categories with long labels, rank items by value, or
display data where the category axis needs more space than the value axis.

**Stacked Horizontal Bar Chart**

Stacked horizontal bar charts divide each bar into segments representing different series. This
shows both the total value and the composition of that total. Use this when you need to show how
different components contribute to an overall figure.

**When to use:** Show partial-to-whole total costs relationships while maintaining the ability
to compare totals across categories, such as showing cost breakdown by expense type for each
department.

**Bar Chart Data Configuration**

|  |  |
| --- | --- |
| **Configuration Area** | **Description** |
| Legend | Drag dimension fields to define the categories displayed as separate bars or bar segments (for stacked charts). The Legend determines how data is grouped. |
| Values | Drag metric fields to specify the values represented by bar length. Multiple metrics create grouped bars or additional stack segments. |
| Axis | Drag dimension or time fields to define the Y-axis labels (for horizontal bars). Time fields enable trend-style presentation. |
| Filters | Drag fields and configure filter criteria to limit the data displayed in the chart. |

**Bar Chart-Specific Properties**

- Maximum Rows: Controls the number of bars displayed. Excess items are grouped into an "Other"
  bar.
- Multicolor Single Series Charts: When enabled, each bar in a single-series chart displays a
  different color.
- Reverse Order: Reverses the order of bars on the axis.
- Hide X Axis / Hide Y Axis: Removes axis labels from the chart.
- Hide Grid Lines: Removes horizontal and vertical grid lines for a cleaner appearance.

**Parent topic:** [Report Components: Charts](../../../../studio/new-uc/reference/report-studio-reference/report-component-charts.html)
