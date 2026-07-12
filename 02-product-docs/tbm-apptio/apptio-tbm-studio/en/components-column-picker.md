---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Column Picker"
breadcrumb:
  - "How-To Guides (Task-Based)"
  - "IBM Apptio Report Studio (New)"
  - "Components"
  - "Column Picker"
source_path: "SSWRJM/studio/report-studio/components/rs-column-picker.html"
images:
  - "03-media/apptio-tbm-studio/column-picker.png"
  - "03-media/apptio-tbm-studio/bn-config.png"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Column Picker

*A Column Picker lets users control which columns are displayed in a normal table, editable table or a chart. It enables flexible exploration of tabular data without requiring changes to the report configuration.*

## When to use a Column Picker

Use a column picker when you want the users to:

- Show or hide table columns based on their needs
- Focus on specific metrics or dimensions
- Reduce visual clutter in wide tables

## Add a Column Picker to the Report

1. Add a Column Picker from the Components pane on the toolbar
1. Click on the Column Picker to enable the Data and Format panels.
1. Data Panel Select the model object from the dropdown list Drag dimensions from the Dimension Explorer to the fields section in the data panel
1. Format Panel General Properties – See Component Properties Column Picker-specific Properties Selection Multiple Selection – The columns appear as set of checkboxes. Single Selection With – The picker fields appear as radio buttons. Enable Select All Toggle to see the Select All option in the column picker component. Orientation Vertical Horizontal

Example: Column Picker

Column Picker supports custom formulas and formula dimensions. For more details, see Custom Formulas

## Configure Drill Navigation for Column Picker Dimensions

When a visualization includes dimensions that can be selected through the Column Picker , configuring drill navigation for those dimensions can be challenging because they are not explicitly listed in the Data panel.

To simplify this process, the Data panel now displays virtual (ghost) dimensions in the Rows section of the table whenever column picker selections are in scope. These virtual dimensions serve as placeholders, allowing administrators to configure drill navigation for column picker dimensions without first adding them to the visualization.

Key points

- Virtual (ghost) dimensions appear only when the visualization has column picker dimensions in scope.
- Ghost dimensions are displayed in the Rows section (in case of tables) of the Data panel for configuration purposes only.
- You can configure drill navigation for these virtual dimensions just as you would for regular dimensions.
- Ghost dimensions do not affect the visualization or displayed data - they exist solely to enable drill navigation configuration for dynamically selected column picker dimensions.
