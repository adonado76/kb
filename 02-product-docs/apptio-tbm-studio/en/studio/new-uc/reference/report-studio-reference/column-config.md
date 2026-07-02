---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Column Configuration"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Report Studio Reference"
  - "Report Components: Tables"
source_path: "studio/new-uc/reference/report-studio-reference/column-config.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Column Configuration

Each column in a table can be individually configured for display, formatting, and behavior.

**Column Types**

|  |  |  |
| --- | --- | --- |
| **Column Type** | **Description** | **Source** |
| Dimension | Label/text columns from tables. Used in the Rows area for grouping. | Tables section in Project Explorer |
| Metric | Numeric columns with pre-defined formatting. Includes model and calculated metrics. | Metrics section in Project Explorer |
| Formula | Custom calculated columns using formulas. Can reference other columns and functions. | Created via Data tab > New Column |
| Calculated | Derived columns: Count, Percent, Variance, Comparison, Threshold Icons. | Created via Value Field Settings |
| Calendar-Based | Time-aggregated values: YTD, QTD, FY, LFY, ANN, LTM, etc. | Created via Formulas tab > Dates |
| Sparkline | Small trend line showing historical data. | Created via Formulas tab > Dates > Sparkline |
| Status Indicator | Icons indicating value status (red/yellow/green, arrows, etc.). | Created via Icon function |
| Total | Row totals across multiple value columns. | Created via Data tab > Sum |
| Spacer | Blank column for visual separation. | Created via Data tab > Insert > Spacer Column |
| Editable | User-editable column in editable tables. | Editable table configuration |

**Adding Formula Columns**

Formula columns allow custom calculations using data from the table.

**To add a formula column:**

1. Select the table and click the Data tab.
2. Click New Column.
3. Enter a Name for the column.

1. Select Enter Formula and enter the formula using table.column format.
2. Select the Format, Type, and optionally enable Summable.
3. Click OK.

**Column Properties Reference**

|  |  |  |
| --- | --- | --- |
| **Property** | **Description** | **Values** |
| Name | Display name for the column. Accepts alphanumeric characters. | Any text |
| Type | Data type of the column values. | Automatic, Numeric, Label, Date |
| Format | Display format for the values. | Number, Currency, Percent, Date, Advanced (formula) |
| Summable | Whether the column can be safely summed when grouped. Disable for calculated ratio columns. | Yes/No (default: No) |
| Decimal Places | Number of decimal places for numeric values. | 0-10 (varies by format) |
| Use Grouping Separator | Adds thousands separator based on project locale. | Yes/No |

**Column Width**

**To resize a column:**

- Position the mouse pointer over the right boundary of the column header. When the pointer
  changes to a resize arrow, click and drag.
- Right-click the column header > Formatting > Set Width and enter the width in pixels.

**Column Visibility**

Columns can be hidden while configuring the table. Hidden columns still participate in
calculations but are not displayed.

**To hide a column:**

- Right-click the column name in the Values area of the Component Configuration pane and select
  Hide. The column name is grayed.

**To show a hidden column:**

- Right-click the grayed column name in the Component Configuration pane and select Show.

**Parent topic:** [Report Components: Tables](../../../../studio/new-uc/reference/report-studio-reference/report-component-table.html)
