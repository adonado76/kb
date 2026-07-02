---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Line Charts"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Report Studio Reference"
  - "Report Components: Charts"
source_path: "studio/new-uc/reference/report-studio-reference/line-chart.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Line Charts

Line charts connect data points with continuous lines, making them ideal for displaying trends
and patterns over time. They excel at showing rate of change and can display multiple series
simultaneously for comparison.

**Standard Line Chart**

The standard line chart plots data points and connects them with straight line segments. Each
series appears as a separate line, allowing viewers to compare trends across multiple categories.

**When to use:** Track cost trends over time, compare multiple metrics or business units
across the same time periods, or identify patterns and anomalies in time-series data.

**Line Chart Interactivity**

**Zoom Feature:** In line charts, you can zoom in to specific time periods by holding down the
mouse button and dragging horizontally across the chart. A "Reset Zoom" option appears in the
upper-right corner to return to the full view. Zooms are reset when navigating away from the report.

**Legend Filtering:** Click any item in the legend to hide that series. The item appears
grayed out. Click again to restore visibility. This allows users to focus on specific data series
without modifying the chart configuration.

**Line Chart-Specific Properties**

- Include zero on the y-axis: Forces the Y axis to start at 0. When cleared, the Y axis may start
  at a higher value to better display small variations.
- Strip Leading and Trailing Zero Values: Removes any zero values at the start or end of the chart
  to prevent the line from dropping to the X axis at the beginning and end.

**Parent topic:** [Report Components: Charts](../../../../studio/new-uc/reference/report-studio-reference/report-component-charts.html)
