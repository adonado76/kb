---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Line Item Filters (Dependent Picklists)"
breadcrumb:
  - "Planning"
  - "Configuration and Administration"
source_path: "it-planning/planning/itp-dependent-picklists.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Line Item Filters (Dependent Picklists)

Note: *Admin or Budget Process Owner roles are required to manage line item filters.*

**Line Item Filters** allow you to control which values appear in a drop-down field based
on selections made in another column. This improves data entry accuracy by preventing users
from seeing irrelevant or invalid options.

For example:

- When a user selects a **Cost Center**, you can restrict the **Account** dropdown
  to only show accounts associated with that Cost Center.
- Filters can be chained to create multi-level dependencies (e.g., Cost Center → Account →
  Vendor).

**Important:**

Line Item Filters only affect what is displayed in the drop-down. They do not modify data
already entered.

**Example**

Given the following mapping:

|  |  |
| --- | --- |
| **Account** | **Cost Center** |
| ACCT\_6000 | **CC-200** |
| ACCT\_6100 | **CC-200** |
| ACCT\_6200 | **CC-200** |
| ACCT\_3001 | **CC-200** |
| ACCT\_3002 | CC-210 |
| ACCT\_3011 | CC-210 |
| ACCT\_2006 | CC-220 |
| ACCT\_4021 | CC-220 |

If a user selects **Cost Center = CC-200**, the **Account** dropdown will display only:

- ACCT\_6000
- ACCT\_6100
- ACCT\_6200
- ACCT\_3001

## Create a Line Item Filter

1. Navigate to **Configuration** → **Line Item Filters**.
2. Select **Add** (➕) in the top-right corner. The **Add Line Item Filter** dialog
   opens.
3. Enter the following details:
   1. **Name** – A unique filter name
   2. **Column** – The dimension you want to filter
   3. **Filter By** – The attribute whose value determines the filtered options
4. Select **Add** to create the filter.
5. Select the filter from the table.
6. Export the filter template:
   1. Select the **Ellipsis menu** → **Export To File**, or right-click the filter
      and choose **Export To File**.
   2. You can also export a blank template via **Ellipsis menu** → **Export
      Template**
7. Populate the CSV file:
   1. Add rows that map **Column** values to **Filter By** values
   2. For dimensions that use **Code** as the unique identifier, you must use the code
      (not the name).
   3. Each row can only have one value per column.
8. Import the mapping:
   1. Select **Ellipsis menu** → **Import From File**, or right-click the filter and
      choose **Import From File.**
   2. Upload the CSV.

## Update a Line Item Filter

1. Navigate to **Configuration** → **Line Item Filters** and select the filter to
   update.
2. Export the current mapping using **Ellipsis menu** → **Export To File**.
3. Edit the CSV to add, modify, or delete rows.
4. Import the updated CSV using **Ellipsis menu** → **Import From File**.

   The
   updated mappings take effect immediately.

## Delete a Line Item Filter

1. Navigate to **Configuration** → **Line Item Filters**.
2. Right-click the filter you want to delete and select **Delete**.

Once deleted, the filter is no longer applied to dropdowns in any line-item table.
