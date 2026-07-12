---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Common Chart Properties"
breadcrumb:
  - "Reference"
  - "Report Studio Reference"
  - "Report Components: Charts"
  - "Common Chart Properties"
source_path: "SSWRJM/studio/new-uc/reference/report-studio-reference/common-charts.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Common Chart Properties

All charts share a common set of configurable properties accessed through the Properties dialog. Select a chart and access properties via the Properties icon on the Author tab, the Actions menu (small triangle in the chart header), or by right-clicking the chart.

Chart Tab Properties

| Property | Description |
| --- | --- |
| Property | Description |
| X Axis Tag | Select the source column for X-axis values. |
| Y Value Tag | Select the source column for Y-axis values. |
| Y Axis Scale | Select Linear or Logarithmic scaling for the Y-axis. |
| Color Spec | Enter color formatting strings to customize metric colors (e.g., "Cost=blue;Budget=green"). |
| Chart Number Format | Enter a pattern to format axis numbers (e.g., "#,###" for thousands separator). |
| Chart Number Prefix | Text displayed before numbers (e.g., "$" for dollars). |
| Chart Number Suffix | Text displayed after numbers (e.g., "M" for millions). |
| Show Data Values | Display data values for each data point in the chart. |
| Legend Location | Position the legend: North, South, East, West, or Hidden. Default is South. |
| Hide Grid Lines | Remove horizontal and vertical grid lines from the chart. |
| Include zero on Y-axis | Force the Y axis to start at 0 rather than auto-scaling. |

Data Tab Properties

| Property | Description |
| --- | --- |
| Property | Description |
| Maximum Rows | Limits elements displayed. In bar charts: number of bars. In pie charts: number of slices. Excess items grouped into "Other". |
| Include Columns* | Restrict displayed columns to those selected (legacy charts only). |
| Exclude Columns* | Allow all columns except those selected (legacy charts only). |
| Show rows with all zeros* | Override default behavior to display zero-value rows (legacy charts only). |
| Pivot Data Set* | Switch X and Y axes in the chart (legacy charts only). |

General Tab Properties

| Property | Description |
| --- | --- |
| Property | Description |
| Name | The title displayed in the chart header (when Show Header is enabled). |
| Caption | Additional information displayed near the chart. HTML allowed (no links for security). |
| Caption Position | Position the caption: Top, Bottom, Left, Right, or Hide. |
| Show Border | Display a border around the chart. Hidden borders appear on hover in Edit mode. |
| Show Header | Display the chart name as a header. Default is enabled. |
| Wrap Title | Wrap long chart names to fit the chart width. |

Advanced Tab Properties

| Property | Description |
| --- | --- |
| Property | Description |
| Data Time Period | Lock the chart to a specific time period regardless of report date selection. |
| Hide Hydration Warning | Suppress warnings when a chart intentionally displays data from multiple sources. |
| Auto Refresh on Calc Finish | Automatically refresh the chart when background calculations complete. |
| Auto Shorten Column Names | Display only the portion of column names after the dot separator. |
