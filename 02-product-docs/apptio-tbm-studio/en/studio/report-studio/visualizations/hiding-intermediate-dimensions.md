---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Hiding Intermediate Dimensions"
breadcrumb:
  - "TBM Studio"
  - "How-To Guides (Task-Based)"
  - "IBM Apptio Report Studio (New)"
  - "Visualizations"
  - "Table"
source_path: "studio/report-studio/visualizations/hiding-intermediate-dimensions.html"
images:
  - "resources/images/studio_images/hide-1e.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Hiding Intermediate Dimensions

The Hiding Intermediate Dimensions feature allows you to hide dimensions that are used as
intermediate steps in formulas or calculations, helping you present cleaner and more
relevant data to end users. This ensures that only meaningful dimensions are displayed in
report components, while intermediate or supporting fields remain hidden from view.

1. Hide dimensions in tables
   1. Open the **Data Configuration** panel of the table.
   2. In the **Rows** or **Values** section, locate the dimension you want to hide.
   3. Open the **overflow menu** next to the dimension name and select **Hide**.
   4. After hiding, a **hidden icon** appears next to the dimension name.
   5. The dimension is no longer visible in the table view.

      ![image of hidden dimension](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/hide-1e.png)
2. Show hidden dimensions
   1. To unhide a dimension, open the **overflow menu** again and select **Show**.
   2. The dimension reappears in the table.
3. Hide dimensions in charts
   1. Open the **Data Configuration** panel for a chart.
   2. Similar to tables, click the **overflow menu** next to the dimension you want to
      hide and select **Hide**.
   3. The chart refreshes to display only the visible dimensions.

Table supports custom formulas and formula dimensions. For more details, see [Custom Formulas](../create-first/custom-formula.html "Custom formulas (also referred to as formula dimensions) allow you to define new calculated dimensions using existing fields in your data model. This enables deeper analysis and richer insights without requiring any changes to the underlying dataset or schema.")

**Parent topic:** [Table](../../../studio/report-studio/visualizations/rs-table.html "The table component displays data in a structured, tabular format. It is ideal for showing detailed information, summarizing metrics, and supporting interactive filtering within a report.")
