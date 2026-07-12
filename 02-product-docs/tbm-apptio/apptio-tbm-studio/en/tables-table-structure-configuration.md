---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Table Structure Configuration"
breadcrumb:
  - "Reference"
  - "Report Studio Reference"
  - "Report Components: Tables"
  - "Table Structure Configuration"
source_path: "SSWRJM/studio/new-uc/reference/report-studio-reference/table-structure-config.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Table Structure Configuration

Table structure is configured using the Component Configuration panel, which appears when you add or select a table in a report.

Component Configuration Areas

The Component Configuration panel includes four primary areas for building tables:

| Area | Description | Constraints |
| --- | --- | --- |
| Area | Description | Constraints |
| Rows | Provides entries for the first column in the table. Duplicate entries are grouped automatically. Multiple fields create sub-groups. | Accepts dimensions (label fields). Multiple fields allowed. |
| Columns | Provides column headers for the table. Used primarily for time-based pivoting. | Only ONE field can be added. Typically used for time dimensions. |
| Values | Provides the data displayed in the body of the table. These become the numeric columns. | Accepts metrics and numeric fields. Multiple fields allowed. |
| Filters | Filters the entries displayed in the table. Restricts data to matching criteria. | Accepts dimensions and metrics. Multiple filters allowed. |

Adding and Removing Columns

To add columns:

1. Select the table in the report.
1. Drag fields from Project Explorer into the appropriate area (Rows or Values) in the Component Configuration panel.
1. The table will updates automatically to display the new column.

To remove columns:

- Drag the field out of the Component Configuration area, OR
- Right-click on the field and select Remove.

Column Ordering

To reorder columns:

- Click and drag the column header to a new position in the table.
- Reorder fields in the Values area to change column order.

Note: During Excel export, columns maintain the order configured in the report component. Any columns that are not explicitly configured are automatically appended at the end.

Column Grouping

You can group two or more columns under a common header. This is useful for organizing related metrics such as grouping Cost and Budget columns under a Financials header.

To group columns:

1. Hold down Ctrl (Windows) or Alt (Mac) and click each column header to include in the group.
1. Right-click and select Group Columns.
1. Enter the header text for the group and click OK.

Tip: You can use dynamic text in group headers. For example, <%=CurrentDate()%> displays the current period.

To ungroup columns, right-click the column header and select Ungroup Columns.

Row Grouping

Tables are automatically grouped by at least one field in the Rows area. Additional grouping consolidates data and displays aggregated values.

To configure row grouping:

1. Select the table and click Group on the Data tab.
1. In the Group dialog, select the columns to use for grouping.
1. Click Group to apply.

When grouped, columns with multiple different values display three vertical dots (various), and a Count column is added showing the number of grouped entries.

Subtotals and Grand Totals

When multiple fields are in the Rows area, TBM Studio automatically groups values and can display subtotals. Configure subtotals using the Subtotals dialog on the Data tab.

| Option | Description | Default |
| --- | --- | --- |
| Option | Description | Default |
| Show Total Row | Displays a Total row at the bottom of the table with aggregated values. | Enabled |
| Show Total Column | Displays a Totals column showing row totals. | Disabled |
| Show Other Row | When rows are limited, shows an Other row with remaining totals. | Disabled |
| Put subtotal labels in | Controls which column displays subtotal labels. | First grouped column |
| Subtotal levels (1-4) | Number of grouping levels to show subtotals for. | 1 |

Tip: The Total row intelligently handles different column types: it sums numeric columns, and for calculated columns (like Cost per Server), it recalculates using the totals rather than summing individual values.

Subtotal Tree Structure

For hierarchical data, create expandable tree tables that allow users to drill down through levels.

To create a subtotal tree:

1. Drag two or more fields into the Rows area.
1. Add one or more fields to the Values area.
1. On the Data tab, in the Structure group, click As Tree.
1. Optionally, set Max Children to limit displayed rows with an Other link for remaining items.
