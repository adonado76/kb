---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Sparklines and Status Indicators"
breadcrumb:
  - "Reference"
  - "Report Studio Reference"
  - "Report Components: Tables"
  - "Sparklines and Status Indicators"
source_path: "SSWRJM/studio/new-uc/reference/report-studio-reference/sparklines-status-indi.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Sparklines and Status Indicators

Sparkline Columns

Sparklines display small trend lines showing historical and future data in a single cell.

Sparkline function syntax:

=SPARKLINE(past, future, column)

| Parameter | Description |
| --- | --- |
| Parameter | Description |
| past | Number of periods to trend backward. Must be a positive number. |
| future | Number of periods to trend forward. Must be a positive number. |
| column | Name of the column containing the data to trend. |

Example: =SPARKLINE(4,4,Cost) displays a trend line spanning 4 months back and 4 months forward for the Cost column.

Status Indicator Columns

Status indicators use colored icons to communicate value states at a glance.

Icon function syntax:

=Icon(["icon_type"], condition1, condition2, ...)

| Icon Type | Description |
| --- | --- |
| Icon Type | Description |
| redcircles | 2-state: Red circle (expression 1 true), Pink circle (expression 2 true) |
| 3colorcircles | 3-state: Green, Yellow, Red circles based on conditions |
| (default) | If no icon_type specified, defaults to “redcircles” |

Values not matching any expression receive the last icon in the set. To see all available icon types, hover over the calculation name in the Value Field Settings dialog.

Quick Calculated Indicators

Access these through Value Field Settings (right-click a value in Component Configuration):

| Indicator | Description |
| --- | --- |
| Indicator | Description |
| Threshold Icons | Red icon below threshold, green icon above threshold. |
| Zero Arrows | Up arrow (>0), sideways arrow (=0), down arrow (<0). |
| Sparkline Trend | Small trend graph of the last six months. |
