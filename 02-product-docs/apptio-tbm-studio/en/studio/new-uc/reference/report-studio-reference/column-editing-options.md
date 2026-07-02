---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Column Editing Options"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Report Studio Reference"
  - "Report Components: Editable Tables in Reports"
source_path: "studio/new-uc/reference/report-studio-reference/column-editing-options.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Column Editing Options

Each column in an editable table can be configured with specific editing behaviors. These
settings are defined in Data Studio but affect how the column behaves in the report component.

**Editable vs. Read-Only Setting**

Columns can be set as editable or read-only at the report level:

- **Uneditable Columns:** Access the Editable Tables ribbon and expand Uneditable Columns to
  select columns that should be read-only
- **Source columns:** In enriched editable tables, columns from the source transform are
  read-only by default
- **Allow editing in included columns:** A checkbox in the configuration enables editing of
  included source columns

**Input Types**

Column data types determine the input experience:

|  |  |  |
| --- | --- | --- |
| **Input Type** | **Description** | **Data Studio Setting** |
| Text (Label) | Free-form text entry | Type: Label |
| Number (Numeric) | Numeric values with locale formatting | Type: Numeric |
| Dropdown | Selection from predefined values | Possible Values configured |
| Date | Date picker with format control | Type: Date with Date Format |
| Boolean | True/False checkbox selection | Type: Boolean |

**Dropdown Value Sources**

Dropdowns can be configured with static or dynamic values:

- **Static list:** Comma-separated values entered directly (e.g., "OpEx, CapEx, Transfer")
- **Dynamic from table:** Formula referencing another table:
  %TableName/!LIMIT\_COLUMNS[ColumnName]
- **Cascading dropdowns:** Filter values based on another column using:
  %Table/!FILTER[Column="<%=OtherColumn%>"]/!LIMIT\_COLUMNS[Column]

The Possible Values Context setting determines how dynamic text is evaluated: Current Row
evaluates formulas in the context of the row being edited, while Report evaluates in the overall
report context.

**Default Values**

When users add new rows, default values can be pre-populated:

- Set in the Default Value field in Data Studio column configuration
- Can be static values or formulas
- Helpful for setting default dates, status values, or owner assignments

**Parent topic:** [Report Components: Editable Tables in Reports](../../../../studio/new-uc/reference/report-studio-reference/report-component-editable-components.html)
