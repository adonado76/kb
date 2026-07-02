---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Create Enriched Editable Tables"
breadcrumb:
  - "TBM Studio"
  - "How-To Guides (Task-Based)"
  - "Work with Data"
  - "Manual Data Entry"
source_path: "studio/new-uc/howtoguides/work-with-data/create-eet.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Create Enriched Editable Tables

**Objective:** Create an editable table whose rows are automatically generated from an
existing transform table, allowing users to enrich the data with additional classifications
or annotations.

**When to Use**

- You have system-generated data that requires human classification (e.g., tagging cloud
  instances with responsible projects)
- Mapping general ledger accounts to IT cost categories
- Adding business context to automated data feeds
- Labor mapping (associating employees with IT towers and services)
- Scenarios where rows should match a source system but need additional user-entered
  fields

**When NOT to Use**

- For small lookup tables with no upstream source (use blank editable tables)
- When users need to add or delete rows freely (enriched tables inherit rows from the
  source)
- For data that's fully automated without human enrichment needs

Attention: In enriched editable tables, rows come from the source transform table
and cannot be deleted by users. Users can only add columns and populate values for those
columns. If the source table adds a row, that row automatically appears in the enriched table.
If the source table removes a row, it disappears from the enriched table.

## Prerequisites

- An existing transform table that will serve as the data source
- Understanding of which columns from the source table users need to see
- Plan for what additional columns users will populate
- Data Studio access with table creation permissions

**Time estimate:** 15-20 minutes

**Steps**

1. **Create the enriched editable table**
   - Navigate to **Data Studio**
   - On the **Home** tab, select **New > Editable Table**
   - In the **New Manually Entered Table** dialog, select **Enriched Table**
   - Enter a descriptive name (e.g., "GL Account Mapping," "Labor Enrichment")
   - Click **OK**
2. **Select the source transform table**
   - Navigate to **Steps > Generated** in the pipeline
   - Click **Configure Source Table**
   - In the **Source Table** dropdown, select the transform table whose data will
     populate this editable table
   - The system loads all columns and rows from the source table
3. **Choose source columns to include**
   - Review the list of available columns from the source table
   - Select which columns users need to see when entering data
   - **Best practice:** Include identifying columns (names, IDs, descriptions) but
     exclude calculated fields
   - **Note:** These source columns are read-only; users cannot edit them
4. **Add editable columns**
   - Navigate to **Steps > Configure Columns**
   - Click **Add a new column** for each field users will populate
   - Common editable columns: Classification fields, Mapping targets, User-entered metrics,
     Comments
5. **Configure each editable column**
   - **Column Name:** Use clear, business-friendly names
   - **Description:** Explain what users should enter and why
   - **Possible Values:** Define dropdowns to control data quality (highly
     recommended)
   - **Value Required:** Check if users must provide a value before publishing
6. **Set up column dependencies** (if needed)
   - For cascading dropdowns (e.g., Tower → Service → Subservice), configure "Possible
     Values" formulas
   - Set **Possible Values Context** to "Current row" for dependent dropdown
     scenarios
7. **Review the data preview**
   - Click the **Table** step to see how the enriched table looks
   - Verify source columns appear correctly and editable columns are present
8. **Save and check in**
   - Click **Save** on the **Home** tab
   - Click **Check In** with a descriptive comment

## Expected Results

Your enriched editable table now contains all rows from the source transform table
(automatically synced), read-only columns from the source table for user reference, and
empty editable columns ready for user input. When the source transform table updates, the
enriched editable table automatically reflects those changes while preserving user-entered
data in the editable columns.

**Common Pitfalls**

|  |  |
| --- | --- |
| **Issue** | **Solution** |
| **Users confused about which columns they can edit** | In reports, clearly label or group editable vs. read-only columns. Consider using the "Display Name" property to add "(Read-Only)" to source columns. |
| **Source table rows deleted, user enrichment lost** | This is expected behavior. If source data is removed, enrichment for those rows disappears. Maintain source table stability or document that enrichment may be lost. |
| **Users expect to add new rows manually** | Enriched tables cannot have manually added rows. If users need this capability, ensure all needed rows exist in the source transform table first, or use a blank editable table instead. |
| **Editable columns lack dropdowns** | For any column used in allocations or reporting, add dropdown constraints. Free-text entries lead to inconsistent classifications. |

## What's Next

After creating your enriched editable table:

- [Configure Dropdowns and Validation](config-dd-valid.html)
- [Set Up Editable Table Publishing](setup-et-publish.html)
- [Create reports for user data
  entry](../create-reports/create-basic-report.html)
- [How-To Guide 1: Apply Row-Level Security to Tables](htg-arls.html)

**Parent topic:** [Manual Data Entry](../../../../studio/new-uc/howtoguides/work-with-data/manual-data-entry.html)
