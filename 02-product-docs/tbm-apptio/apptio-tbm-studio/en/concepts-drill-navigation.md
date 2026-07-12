---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Drill Navigation"
breadcrumb:
  - "How-To Guides (Task-Based)"
  - "IBM Apptio Report Studio (New)"
  - "Core Concepts"
  - "Drill Navigation"
source_path: "SSWRJM/studio/report-studio/create-first/drill-navigation.html"
images:
  - "03-media/apptio-tbm-studio/drill1c.png"
  - "03-media/apptio-tbm-studio/drilld2.png"
  - "03-media/apptio-tbm-studio/disable-drillthru.png"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Drill Navigation

*Drill navigation allows users to interactively explore data by clicking on charts within a report to view a related, more detailed report in a modal overlay. This enables deeper analysis and seamless navigation between summary and detailed views – all within the same reporting experience.*

1. Add a drill-through Open the Data Configuration panel for the chart. From a dimension’s overflow menu, select Configure Drill-Through. Note: Dimensions added under the Legend section of the data panel have drill-through enabled.
1. Configure drill-through settings: The drill navigation configuration menu includes the following options: Drill-through destination Select the destination report that will open in a model overlay when a user clicks the chart. This is the detailed view linked to your current chart. Show Filter Context Bar Adds a filter context bar to the modal report. Enabled by default to give users visibility into the filters applied when exploring the drill-through view. Filters Filter on selected row: Filters the destination report using values from the clicked data point. Filter on applied slicer selection – Filters the destination report using the slicer selections from the current report. Insert current report filters – Applies all filters currently active in the source report to the drill-through report. Added Columns Add currently selected column: Includes the column associated with the clicked data point in the drill-through report. Include current report’s added columns: Carries forward any additional columns selected through the column picker into the destination report. Using drill navigation After configuration, users can click on a data point within the chart to open the linked report in a modal overlay. The applied filters and context are automatically reflected, helping users trace insights from a high-level summary to detailed data with a single click. Works in both the report studio and the report viewer. Users can disable configured drill-through interactions directly from the Data Panel without needing to remove and recreate the configuration. This provides greater flexibility and control when managing report interactions and allows drill-through behaviour to be easily enabled or disabled as reporting needs evolve.
