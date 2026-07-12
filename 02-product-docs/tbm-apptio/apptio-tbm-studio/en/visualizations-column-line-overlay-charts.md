---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Column + Line (Overlay) Charts"
breadcrumb:
  - "How-To Guides (Task-Based)"
  - "IBM Apptio Report Studio (New)"
  - "Visualizations"
  - "Column + Line (Overlay) Charts"
source_path: "SSWRJM/studio/report-studio/visualizations/col-line.html"
images:
  - "03-media/apptio-tbm-studio/col-line.png"
  - "03-media/apptio-tbm-studio/soverlay.png"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Column + Line (Overlay) Charts

The Column + Line (Overlay) chart combines column and line visualisations into a single chart. It allows you to compare absolute values (columns) alongside a related trend or metric (line) across the same categories.

This visualisation is especially useful when you want to analyse relationships between two different measures without switching between charts.

When to use a column + line chart

Use a column + Line (overlay) chart when you want to:

- Compare actual values versus a trend or target
- Visualise volume and performance together (Ex: cost versus utilization)
- Track changes over time while still seeing category-wise distribution
- Highlight how one metric behaves in relation to another

Add a column + line chart to a report

- Add a Column + Line Chart from the Visualizations pane on the toolbar
- Click on the Chart to enable the Data and Format panels.
- Data Panel Select the model object from the drop-down menu Categories – Defines the X-axis of the chart. Click here or drag to add dimensions from the Dimension Explorer Column Values – Metrics displayed as columns Line Values – Metrics displayed as a line overlay Legend – Differentiates multiple column or line series Column Filters – Apply filters that affect only the column values Line Filters – Apply filters that affect only the line values.
- Format Panel General Properties – See Component Properties Column + Line chart specific Properties Categories Show category title Show category labels Choose the Font size, style (bold, italics, underline) and color Show grid lines Values Show values title Show values labels Choose the Font size, style (bold, italics, underline) and color Show grid lines Legend Toggle to show the legend Legend title, font size and style for the legend (bold, italics, underline) Color of the legend text (with option to reset the color) Legend labels – font size, style and color Legend location – choose between center, left and right Lines Choose the line type, color and style Columns Results to display – Let's you choose the number of columns to display Padding between columns – Controls the spacing between adjacent columns in the chart, helping improve readability and visual clarity. Series color – Apply color to different series Data Labels Toggle to show the data labels Label Position – choose among the different positions

Example: Column + Line chart

Column + Line chart supports custom formulas and formula dimensions. For more details, see Custom Formulas

Stacked Column + Line Charts : Extends the column + line chart by stacking multiple column values within each category, allowing you to compare part-to-whole distributions alongside an overlaid trend or metric.

Share Axis in Overlay Charts: Overlay charts now support a share axis, enabling multiple data series to be aligned on a common scale for easier comparison and improved readability.
