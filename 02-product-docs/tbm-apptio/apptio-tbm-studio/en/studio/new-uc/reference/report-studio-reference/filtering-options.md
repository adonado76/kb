---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Filtering Options"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Report Studio Reference"
  - "Report Components: Tables"
source_path: "studio/new-uc/reference/report-studio-reference/filtering-options.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Filtering Options

Tables can be filtered to display only rows matching specific criteria. Filters are configured in
the Filters area of the Component Configuration panel.

**Adding Filters**

1. Drag a field from the Project Explorer to the Filters area.
2. Right-click the filter and select Edit Filter.
3. Select values or configure filter criteria.

**Filter Operators**

|  |  |  |
| --- | --- | --- |
| **Operator** | **Description** | **Example** |
| Equals | Exact match. | Expense Type Equals OpEx |
| Not Equals | Excludes matching rows. | Expense Type Not Equals CapEx |
| Contains | Value includes the specified text. | Account Contains 2111 |
| Does Not Contain | Value excludes the specified text. | Description Does Not Contain Test |
| Starts With | Value begins with the specified text. | Account Starts With ACCT |
| Ends With | Value ends with the specified text. | Description Ends With Services |
| Is In | Value matches any in the comma-separated list. | Account Is In 2111,2112,2113 |
| Is Not In | Value does not match any in the list. | Type Is Not In Test,Demo |
| Is Null | Value is empty. | Category Is Null |
| Is Not Null | Value is not empty. | Category Is Not Null |
| > (Greater Than) | Numeric value greater than specified (numeric only). | Cost > 10000 |
| < (Less Than) | Numeric value less than specified (numeric only). | FTE < 5 |

**Auto Search Feature**

Enable search fields below each column header for user-driven filtering.

**To enable Auto Search:**

1. Right-click the table and select Properties.
2. On the Data tab, enable the Auto Search option.
3. Click OK. Search fields appear below column headers.

**Parent topic:** [Report Components: Tables](../../../../studio/new-uc/reference/report-studio-reference/report-component-table.html)
