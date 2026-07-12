---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Table Properties"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Report Studio Reference"
  - "Report Components: Tables"
source_path: "studio/new-uc/reference/report-studio-reference/table-properties.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Table Properties

Access the Properties dialog by right-clicking the table's Total bar and selecting Properties.
Properties are organized into Data, General, and Advanced tabs.

**Data Properties**

|  |  |  |
| --- | --- | --- |
| **Property** | **Description** | **Default** |
| Maximum Rows | Number of rows per page. Controls pagination. | System default |
| Hide Paging Bar | Hides pagination controls. Only Maximum Rows are displayed. | Disabled |
| Include Columns | Restrict displayed columns to those selected. | All columns |
| Exclude Columns | Hide specified columns from display. | None |
| Auto Search | Adds search fields below column headers. | Disabled |

**General Properties**

|  |  |  |
| --- | --- | --- |
| **Property** | **Description** | **Default** |
| Name | Display name shown in the table header. | Table name |
| Caption | Additional descriptive text. Supports HTML (no links). | Empty |
| Caption Position | Location of caption relative to table: Top, Bottom, Left, Right, Hide. | Hide |
| Show Header | Display the table header with Name. | Enabled |
| Show Border | Display a border around the table. | Enabled |
| Wrap Title | Wrap long title text to fit the table width. | Disabled |

**Advanced Properties**

|  |  |  |
| --- | --- | --- |
| **Property** | **Description** | **Default** |
| Auto Refresh when Calculations Finish | Updates table when background calculations complete. Available only with Dynamic Publishing calculation policy. | Disabled |
| Auto Shorten New Dotted Column Names | Displays only the portion after the period. E.g., "Data.Cost" shows as "Cost". | Disabled |
| Lines Per Row | For tables with text wrapping. Leave blank for default. | Blank |
| Max. Columns to Display | Maximum columns processed from source table. | All |
| Include PK Column | Includes the default primary key column. | Auto |
| Use Column Aliases | Enables correct configuration when two objects share column names. Recommended: Leave selected. | Enabled |
| Hide Hydration Warning | Suppresses warnings when components display data from different contexts (e.g., comparing business units). | Disabled |

**Pivot Table Properties (Legacy)**

|  |  |
| --- | --- |
| **Property** | **Description** |
| Pivot Row Col | Column providing values for the first column in the pivoted table. |
| Pivot Col Col | Column providing headings for data columns in the pivoted table. |
| Pivot Val Col | Column providing cell values in the pivoted table. |

**Parent topic:** [Report Components: Tables](../../../../studio/new-uc/reference/report-studio-reference/report-component-table.html)
