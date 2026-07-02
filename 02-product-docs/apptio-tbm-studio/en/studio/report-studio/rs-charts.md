---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Charts"
breadcrumb: []
source_path: "studio/report-studio/rs-charts.html"
images:
  - "resources/images/studio_images/cv-2b.png"
  - "resources/images/studio_images/drill-1c.png"
  - "resources/images/studio_images/srill-2d.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Charts

Charts, when used correctly, can convey valuable information quickly.

The application offers a wide range of chart types, including:

1. Bar (bar and stacked bar)
2. Column (column and stacked column)
3. Line
4. Pie
5. KPI

## Compatible Visualizations

Compatible Visualizations feature allows you to quickly switch between compatible chart
types without rebuilding your visualization. This helps you experiment with different visual
formats and find the one that best represents your data.

**Steps to use** 

1. Select a chart
2. Click on a chart (for example, a Bar chart) in your report.
3. Use the conversion option
4. On the widget header, locate the Compatible Visualizations icon.
5. Select the icon to view a list of compatible visualizations for the selected chart
   type.

   ![image of compatible visualizations](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/cv-2b.png)
6. Select a visualization type
7. Select from options such as:
8. Column chart
9. Stacked Bar chart
10. Stacked Column chart
11. The chart updates instantly to the chosen visual type, retaining existing data,
    formatting, and configuration.

## Drill Navigation for Charts

Drill navigation allows users to interactively explore data by clicking on charts within a
report to view a related, more detailed report in a modal overlay. This enables deeper
analysis and seamless navigation between summary and detailed views – all within the same
reporting experience.

Steps to use

1. Add a drill-through
   1. Open the Data Configuration panel for the chart.
   2. From a dimension’s overflow menu, select Configure Drill-Through.
   3. Note: Dimensions added under the Legend section of the data panel have
      drill-through enabled.

      ![configure drill through](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/drill-1c.png)
2. Configure drill-through settings: The drill navigation configuration menu includes the
   following options:
   1. Drill-through destination
      1. Select the destination report that will open in a model overlay when a user
         clicks the chart.
      2. This is the detailed view linked to your current chart.
   2. Show Filter Context Bar
      1. Adds a filter context bar to the modal report.
      2. Enabled by default to give users visibility into the filters applied when
         exploring the drill-through view.
   3. Filters
      1. Filter on selected row: Filters the destination report using values from the
         clicked data point.
      2. Filter on applied slicer selection – Filters the destination report using the
         slicer selections from the current report.
      3. Insert current report filters – Applies all filters currently active in the
         source report to the drill-through report.
   4. Added Columns
      1. Add currently selected column: Includes the column associated with the clicked
         data point in the drill-through report.
      2. Include current report’s added columns: Carries forward any additional columns
         selected through the column picker into the destination report.

         ![drill through added column](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/srill-2d.png)
   5. Using drill navigation
      1. After configuration, users can click on a data point within the chart to open
         the linked report in a modal overlay.
      2. The applied filters and context are automatically reflected, helping users
         trace insights from a high-level summary to detailed data with a single click.
      3. Works in both the report studio and the report viewer.
