---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Table"
breadcrumb:
  - "TBM Studio"
  - "How-To Guides (Task-Based)"
  - "IBM Apptio Report Studio (New)"
  - "Visualizations"
source_path: "studio/report-studio/visualizations/rs-table.html"
images:
  - "resources/images/studio_images/zerofilter.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Table

The table component displays data in a structured, tabular format. It is ideal for
showing detailed information, summarizing metrics, and supporting interactive filtering within a
report.

## When to use a Table

Use a Table component when you want to:

- Present rows and columns of data (structured data)
- Show multiple metrics or dimensions together
- Enable sorting, filtering, or drilling down into details

## Add a Table to the Report

1. Add a Table from the Visualizations pane on the toolbar
2. Click on the Table to enable the Data and Format panels.
3. **Data Panel**
   - Select Model Object
   - **Rows**- Provides entries for the first column in the table. If there are
     duplicate entries in the source, the entries are grouped and a single entry for each
     unique value is displayed. If you add more than one field to the area, sub-groups are
     created in the first column of the table.
   - **Columns** - Provides column headers for the table. Only one field can be put in
     the Columns area.
   - **Values** - Provides the data displayed in the body of the table
   - **Filters** - Filters the entries in a column in the table.
4. **Format Panel**
   1. General Properties – See [Component Properties](../components/components.html#abt-comp__comprop)
   2. **Total & Subtotals**
      1. Show Total Column – Displays a summary column to the right that calculates
         totals for each of the numeric rows.
      2. Show Total Row – Displays a summary row at the bottom of the table that
         calculates totals for each of the numeric columns.
      3. Show Other Row - If there are many rows in a table, and you want to limit the
         number of rows displayed, you can add an other row. The Other Row is displayed at
         the bottom of the table. It shows the total for the entire table minus the values
         displayed on the current page of the table.
      4. Show Subtotal – Displays subtotal rows for grouped data. You can choose where to
         show subtotal labels and which items to subtotal.
   3. **Row limit per page**
      1. Sets the maximum number of rows displayed per page in the table, enabling
         pagination for large datasets.
   4. **Zero filter**
      1. The Zero Filters feature helps you focus on meaningful data by quickly hiding
         rows where selected numeric columns contain zero values. This makes it easier to
         analyse relevant data without manual filtering.
      2. **Select Numeric Columns**
         1. All numeric columns in the table are listed with checkboxes.
         2. Select one or more columns you want the zero filter to apply to.

            ![zero filters](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/zerofilter.png)
      3. **Apply the Zero Filter**
         1. After selecting the numeric columns, the table instantly updates to display
            non-zero data.
         2. Rows where the selected columns contain zero values are hidden from view.
      4. **Clear the Filter**
         1. To revert to the original view by clearing the zero filter.
         2. All rows, including those with zero values, will be restored.

- **[Table Column Overflow Menu](../../../studio/report-studio/visualizations/table-col-overflow.html)**
- **[Renaming Columns in Table](../../../studio/report-studio/visualizations/remaining-col-tables.html)**
- **[Hiding Intermediate Dimensions](../../../studio/report-studio/visualizations/hiding-intermediate-dimensions.html)**
- **[Show Values](../../../studio/report-studio/visualizations/show-values.html)**
- **[Tree View](../../../studio/report-studio/visualizations/tree-view.html)**
- **[Export a Table to Excel](../../../studio/report-studio/visualizations/export-table.html)**
