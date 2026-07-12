---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Table"
breadcrumb:
  - "How-To Guides (Task-Based)"
  - "IBM Apptio Report Studio (New)"
  - "Visualizations"
  - "Table"
source_path: "SSWRJM/studio/report-studio/visualizations/rs-table.html"
images:
  - "03-media/apptio-tbm-studio/zerofilter.png"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Table

*The table component displays data in a structured, tabular format. It is ideal for showing detailed information, summarizing metrics, and supporting interactive filtering within a report.*

## When to use a Table

- Present rows and columns of data (structured data)
- Show multiple metrics or dimensions together
- Enable sorting, filtering, or drilling down into details

## Add a Table to the Report

1. Add a Table from the Visualizations pane on the toolbar
1. Click on the Table to enable the Data and Format panels.
1. Data Panel Select Model Object Rows - Provides entries for the first column in the table. If there are duplicate entries in the source, the entries are grouped and a single entry for each unique value is displayed. If you add more than one field to the area, sub-groups are created in the first column of the table. Columns - Provides column headers for the table. Only one field can be put in the Columns area. Values - Provides the data displayed in the body of the table Filters - Filters the entries in a column in the table.
1. Format Panel General Properties – See Component Properties Total & Subtotals Show Total Column – Displays a summary column to the right that calculates totals for each of the numeric rows. Show Total Row – Displays a summary row at the bottom of the table that calculates totals for each of the numeric columns. Show Other Row - If there are many rows in a table, and you want to limit the number of rows displayed, you can add an other row. The Other Row is displayed at the bottom of the table. It shows the total for the entire table minus the values displayed on the current page of the table. Show Subtotal – Displays subtotal rows for grouped data. You can choose where to show subtotal labels and which items to subtotal. Row limit per page Sets the maximum number of rows displayed per page in the table, enabling pagination for large datasets. Zero filter The Zero Filters feature helps you focus on meaningful data by quickly hiding rows where selected numeric columns contain zero values. This makes it easier to analyse relevant data without manual filtering. Select Numeric Columns All numeric columns in the table are listed with checkboxes. Select one or more columns you want the zero filter to apply to. Apply the Zero Filter After selecting the numeric columns, the table instantly updates to display non-zero data. Rows where the selected columns contain zero values are hidden from view. Clear the Filter To revert to the original view by clearing the zero filter. All rows, including those with zero values, will be restored.
