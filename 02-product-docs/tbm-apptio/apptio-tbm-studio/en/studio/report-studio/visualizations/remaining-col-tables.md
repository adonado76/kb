---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Renaming Columns in Table"
breadcrumb:
  - "TBM Studio"
  - "How-To Guides (Task-Based)"
  - "IBM Apptio Report Studio (New)"
  - "Visualizations"
  - "Table"
source_path: "studio/report-studio/visualizations/remaining-col-tables.html"
images:
  - "resources/images/studio_images/rename1.png"
  - "resources/images/studio_images/rename2d.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Renaming Columns in Table

Rename column headers directly from the data configuration panel, allowing you to present
data in a more meaningful or user-friendly way without changing the underlying dimension
name.

Steps to use

1. **Open the Data Configuration Panel of your table**
   1. Go to the **Data** tab.
   2. Dimensions added under the **Rows** section define the table’s columns.
2. **Rename a Dimension (Column Header)**
   1. In the **Rows** section, click the overflow menu next to the dimension
      name.

      ![edit displayed name](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/rename1.png)
   2. Select **Edit Display Name**.
   3. In the **Edit Display Name** dialog, enter the new display name for the column.
   4. The **original dimension name** is shown below for reference.

      ![image of editing display name](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/rename2d.png)
3. **Save Changes**
   1. Click **Ok** to confirm your changes.
   2. The updated name appears as the column header in the table.

Note: Renaming affects only the display name in the table view. The original dimension name in
the dataset remains unchanged.

**Parent topic:** [Table](../../../studio/report-studio/visualizations/rs-table.html "The table component displays data in a structured, tabular format. It is ideal for showing detailed information, summarizing metrics, and supporting interactive filtering within a report.")
