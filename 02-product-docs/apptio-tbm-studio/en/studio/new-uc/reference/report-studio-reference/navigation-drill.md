---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Navigation and Drill-Through"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Report Studio Reference"
  - "Report Components: Charts"
source_path: "studio/new-uc/reference/report-studio-reference/navigation-drill.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Navigation and Drill-Through

Charts can be configured to navigate users to related reports when they click on chart elements.
This drill-through capability enables users to explore data from summary to detail.

**Enabling Chart Navigation**

1. Select the chart.
2. On the Ad Hoc tab, click Drill in the Navigation section.
3. Enable Navigation: Check this option to make chart elements clickable.
4. Navigate To: Select the target report from the dropdown.

**Navigation Options**

|  |  |
| --- | --- |
| **Option** | **Description** |
| Enable Navigation | Makes chart elements (bars, slices, etc.) active as navigation links. |
| Open as Modal | Displays the target report as a popup. Users can close it to return to the original report. |
| Navigate To | Select the destination report from any report in the project. |
| Use Per Metric Drills | Activates drill-down for values displayed within pie slices and on bar chart bars. |
| Filter on selected row | Passes the selected value as a filter to the target report. |
| Filter on applied slicer selections | Passes current slicer selections to the target report. |
| Include current report's filters | Passes the source report's filters to the target report. |

Note: For navigation to work with filters, the data in both reports must be linked through the
inference engine.

**Parent topic:** [Report Components: Charts](../../../../studio/new-uc/reference/report-studio-reference/report-component-charts.html)
