---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Create Blank Editable Tables"
breadcrumb:
  - "TBM Studio"
  - "How-To Guides (Task-Based)"
  - "Work with Data"
  - "Manual Data Entry"
source_path: "studio/new-uc/howtoguides/work-with-data/create-blank-et.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Create Blank Editable Tables

## Objective

Create a fully manual table where all rows, columns, and data are entered by users.

## When to Use

- Small reference data that doesn't exist in source systems (e.g., vendor categories,
  custom mapping tables)
- Lookup tables with fewer than 500 rows
- Data that changes infrequently and requires manual curation
- Classification schemes maintained by business users
- One-off mappings or enrichment data

## When NOT to Use

- Large datasets (>500 rows) that should come from source systems
- Data available through automated feeds
- Data that needs enrichment from existing system-generated tables (use enriched editable
  tables instead)

## Prerequisites

- Data Studio access with table creation permissions
- Understanding of required columns and data types
- Plan for who will maintain the data

**Time estimate:** 10-15 minutes

## Steps

1. **Create the editable table**
   - Navigate to **Data Studio**
   - On the **Home** tab in the **Document** group, select **New > Editable
     Table**
   - In the **New Manually Entered Table** dialog, select **Blank Table**
   - Enter a descriptive name for the editable table (e.g., "Vendor Categories," "Cost
     Center Attributes")
   - Click **OK**
2. **Configure the table schema**
   - The editable table opens with a default primary key column (.PK)
   - Navigate to **Steps > Configure Columns** in the pipeline
   - The system displays your column configuration workspace
3. **Add columns to your table**
   - Click **Add a new column**
   - For each column you need, configure:
     - **Column Name:** Enter a descriptive name (e.g., "Vendor Name,"
       "Category")
     - **Description:** Provide context for users who will enter data
     - **Data Type:** Select from Label (text), Numeric, Date, or Boolean
     - **Display Name:** How the column appears in reports (optional)
4. **Set column properties** (optional but recommended)
   - **Default Value:** Automatically populate new rows with a starting value
   - **Value Required:** Check this box to prevent saving rows without a value
   - **Allow Unique Values Only:** Enforce that each row has a distinct value
5. **Configure dropdowns** (if needed for data quality)
   - See section 3.1.3.3 "Configure dropdowns and validation" for detailed guidance
   - Dropdowns prevent free-text entry and ensure consistent values
6. **Review your schema**
   - Verify column names, types, and requirements match your data needs
   - Ensure the primary key (.PK) column remains configured
7. **Save and check in**
   - Click **Save** on the **Home** tab
   - Click **Check In** to make the table available
   - Add a check-in comment describing the table's purpose

## Expected Results

You now have an empty editable table with a defined schema. The table appears in the
**Tables** section of **Project Explorer** under the folder where you created it.
Users can add data through reports with editable table components or direct editing in Data
Studio (for administrators). The table is ready to be incorporated into transform tables and
your cost model.

## Common Pitfalls

|  |  |
| --- | --- |
| **Issue** | **Solution** |
| **Too many columns defined upfront** | Start with essential columns only. You can add more columns later as needs emerge. Unused columns confuse data entry users. |
| **Unclear column purposes** | Always add descriptions to columns. Users entering data need context about what each field represents. |
| **No data validation** | Without validation or dropdowns, users can enter inconsistent data (e.g., "IT Services," "IT Svcs," "Information Technology"). Add dropdowns for any column used in allocations or reporting dimensions. |
| **Wrong data type selected** | If you select "Numeric" but users need to enter values like "N/A" or mixed text/numbers, the column will reject valid entries. Use "Label" type when data might include non-numeric values. |

## What's Next

After creating your blank editable table:

- [Create a transform table from the editable table](data-security.html)
- [Set Up Editable Table Publishing](setup-et-publish.html)
- [Add Tables to Reports](../create-reports/add-tables-report.html)
- [Configure row-level security](htg-arls.html)

**Parent topic:** [Manual Data Entry](../../../../studio/new-uc/howtoguides/work-with-data/manual-data-entry.html)
