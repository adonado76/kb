---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Drill Navigation"
breadcrumb:
  - "TBM Studio"
  - "How-To Guides (Task-Based)"
  - "IBM Apptio Report Studio (New)"
  - "Core Concepts"
source_path: "studio/report-studio/create-first/drill-navigation.html"
images:
  - "resources/images/studio_images/disable-drillthru.png"
  - "resources/images/studio_images/drill1c.png"
  - "resources/images/studio_images/drilld2.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Drill Navigation

Drill navigation allows users to interactively explore data by clicking on charts within
a report to view a related, more detailed report in a modal overlay. This enables deeper
analysis and seamless navigation between summary and detailed views – all within the same
reporting experience.

1. Add a drill-through
   1. Open the Data Configuration panel for the chart.
   2. From a dimension’s overflow menu, select Configure Drill-Through.
   3. Note: Dimensions added under the Legend section of the data panel have drill-through
      enabled.

   ![image of drill through navigation](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/drill1c.png)
2. Configure drill-through settings: The drill navigation configuration menu includes the
   following options:
   1. Drill-through destination
      1. Select the destination report that will open in a model overlay when a user clicks the chart.
      2. This is the detailed view linked to your current chart.
   2. Show Filter Context Bar
      1. Adds a filter context bar to the modal report.
      2. Enabled by default to give users visibility into the filters applied when exploring the
         drill-through view.
   3. Filters
      1. Filter on selected row: Filters the destination report using values from the clicked data point.
      2. Filter on applied slicer selection – Filters the destination report using the slicer selections
         from the current report.
      3. Insert current report filters – Applies all filters currently active in the source report to the
         drill-through report.
   4. Added Columns
      1. Add currently selected column: Includes the column associated with the clicked data point in the
         drill-through report.
      2. Include current report’s added columns: Carries forward any additional columns selected through
         the column picker into the destination report.

      ![image of the drill through navigation for the selected column](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/drilld2.png)
   5. Using drill navigation
      1. After configuration, users can click on a data point within the chart to open the linked report
         in a modal overlay.
      2. The applied filters and context are automatically reflected, helping users trace insights from a
         high-level summary to detailed data with a single click.
      3. Works in both the report studio and the report viewer.
   6. Users can disable configured drill-through interactions directly from the Data Panel without needing to remove and recreate the configuration. This provides greater flexibility and control when managing report interactions and allows drill-through behaviour to be easily enabled or disabled as reporting needs evolve.

   ![image to show disable drill through option](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/disable-drillthru.png)
