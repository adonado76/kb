---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Chart Interactivity Features"
breadcrumb:
  - "Reference"
  - "Report Studio Reference"
  - "Report Components: Charts"
  - "Chart Interactivity Features"
source_path: "SSWRJM/studio/new-uc/reference/report-studio-reference/chart-interactivity.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Chart Interactivity Features

Tooltips

When users hover over chart elements, tooltips display contextual information:

- Bar charts: The tooltip displays the bar's value.
- Stacked bar charts: The tooltip shows both the value and percentage of the segment.
- Pie charts: The tooltip displays the slice value and percentage of total.
- Waterfall charts: When "Explanation in Tooltips" is enabled, the tooltip includes the explanation text.

Legend Interaction

In all charts with legends, users can click legend items to show or hide specific data series. Hidden items appear grayed out. This allows users to focus on specific data without modifying the chart configuration. When elements are hidden, percentage calculations (such as in stacked charts) are adjusted to reflect only the visible elements.

Zoom (Line Charts)

Line charts support interactive zooming. Click and drag horizontally across the chart to zoom in to a specific time period. A "Reset Zoom" link appears in the upper-right corner to return to the full view. Zooms are automatically reset when navigating away from the report.

Slicer Integration

Charts created with the Ad Hoc Component Configuration respond to slicers on the same report. When users select values in a slicer, the chart automatically filters to display only the matching data. This applies to all chart types except waterfall charts (which respond to slicers but with special behavior for intermediate steps).
