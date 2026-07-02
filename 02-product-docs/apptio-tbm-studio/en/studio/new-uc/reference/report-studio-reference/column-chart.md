---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Column Charts"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Report Studio Reference"
  - "Report Components: Charts"
source_path: "studio/new-uc/reference/report-studio-reference/column-chart.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Column Charts

Column charts display vertical bars and are particularly effective for showing changes over time
or comparing items when time periods are involved. They share the same data configuration options as
bar charts but present data vertically.

**Vertical Column Chart**

The standard column chart presents values as vertical bars. This is the most common choice for
time-series comparisons where the X-axis represents time periods such as months, quarters, or years.

**When to use:** Compare values across time periods, show period-over-period changes, or
display data where the natural reading order is left-to-right chronologically.

**Stacked Column Chart**

Stacked column charts segment each column to show the composition of totals. This enables viewers
to see both the trend in total values and how the components within each period contribute to that
total.

**When to use:** Display how cost components change over time while also showing the total
trend, such as monthly IT spend broken down by infrastructure, applications, and services.

**Creating a Column Chart**

1. On the Report tab, click Chart. The chart defaults to horizontal bar format.
2. In the Component Configuration panel, select a model object from the dropdown.
3. Drag a dimension field into the Legend area to define bar groupings.
4. Drag a metric field into the Values area to define what the columns measure.
5. Drag a time field (Months, Quarters, Years) into the Axis area.
6. Select the Ad Hoc tab and click the Column icon to switch from horizontal to vertical bars.

**Parent topic:** [Report Components: Charts](../../../../studio/new-uc/reference/report-studio-reference/report-component-charts.html)
