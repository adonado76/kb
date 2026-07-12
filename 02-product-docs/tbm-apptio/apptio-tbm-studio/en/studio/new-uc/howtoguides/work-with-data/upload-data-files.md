---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Upload Data from Files (Excel, CSV)"
breadcrumb:
  - "TBM Studio"
  - "How-To Guides (Task-Based)"
  - "Work with Data"
  - "Data Import & Management"
source_path: "studio/new-uc/howtoguides/work-with-data/upload-data-files.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Upload Data from Files (Excel, CSV)

**Objective:** Import data from Excel or CSV files into TBM Studio tables to make it
available for cost modeling and reporting.

**When to use this procedure:** Use file upload when you need to:

- Import one-time or ad-hoc datasets
- Load monthly cost data from financial systems
- Bring in external data that isn’t available through automated connectors
- Test data structures before setting up automated feeds

**Prerequisites:**

- Permissions to check out and edit tables (AccessDev role)
- Data file in a supported format (Excel .xlsx/.xls, CSV, TSV, or other delimited
  formats)
- File name contains only one period before the extension (e.g., cost\_data.xlsx not
  cost.data.xlsx)
- Understanding of which table to upload data into (or permission to create a new
  table)

**Time estimate:** 10-15 minutes for first upload; 5 minutes for subsequent uploads

## Steps

**Create a Table and Upload Your First File**

1. **Create a new table** (if one doesn’t already exist):
   - In the **Project Explorer**, click **New** → **Table**
   - Enter a **Name** for the table (e.g., “General Ledger”, “Server Costs”)
   - Enter or select a **Category** to organize the table in the Project
     Explorer
   - Click **OK**
2. **Configure the table source:**
   - The application displays the **Source** step in the transform pipeline
   - In the **Table Description** field, enter a brief description of the table’s
     purpose
   - Click **File Upload**
   - An **Upload** step is added to the pipeline
3. **Upload your data file:**
   - Either click in the **Details** pane and browse to your file, or drag the
     file from Windows Explorer into the **Details** pane
   - The system adds an **Import** step to the pipeline and begins parsing the
     file
4. **Configure import settings:**

   Click the **Import** step in the pipeline to
   review settings:

   **Basic Settings:**

   - **Start import at row:** Specify which row contains the first data record
     (default is row 1, assuming row 0 is the header)
   - **Columns to Exclude:** Select any columns you don’t want to import
   - **Text Encoding:** Choose character encoding (select “Autodetect encoding” if
     unsure)
   - **Delimited:** Select the delimiter character (comma, tab, pipe, etc.)
   - **Text qualifier:** Specify the character used to surround text with special
     characters (default is double quotes)

   **Column Configuration:**

   - Review the **Columns** section
   - Verify that column types are correctly detected (Key, Text, Number, Date)
   - Change column types as needed by clicking on the type
   - To filter columns by type, click a type icon in the **Type** column search
     field
5. **Configure data validation** (optional, TBM Studio v12.1+):
   - **Data validation** checks for schema changes when uploading to existing
     tables: column added, column deleted, column type changed, column cardinality
     changed
   - **Cardinality validation** checks column content:
     - **Any:** No cardinality validation (default)
     - **One:** Ensures all values are unique (no duplicates)
     - **Many:** Ensures every entry is duplicated
6. **Select a refresh cycle:**

   At the top of the screen, select how often the data
   will be updated:

   - **Ad-Hoc updates:** No schedule; upload as needed
   - **1 version; No scheduled updates:** Single version, replace on upload
   - **1 version; Update every month:** Monthly refresh, replaces existing
     data
   - **1 version; Update every year:** Annual refresh
   - **Monthly versions; Update every month:** New version each month (see
     “Version tables for monthly data”)
   - **Yearly versions** (various options): Annual datasets with different update
     patterns
7. **Review and save:**
   - Click the **Table** step in the pipeline to preview the imported data
   - Verify that data appears correctly
   - Click **Save** on the Home tab
   - Click **Check In** to make the table available to the project

**Upload Additional Data to an Existing Table**

When you need to add more
data to an existing table (e.g., loading the next month’s costs):

1. **Check out the table:** Navigate to the table in the **Project Explorer**,
   right-click and select **Check Out**
2. **Select the target time period** (for monthly/yearly versioned tables): Use the
   date picker at the top of the screen to select the period where data should be added. A
   placeholder appears in the Upload step.
3. **Upload the new file:** Click the placeholder and browse your file or drag it into
   the placeholder.
4. **Save and check in:** Click **Save** on the Home tab, then click **Check
   In**.

## Expected Results

- Your data file is successfully imported into TBM Studio
- Column types are correctly identified (or manually corrected)
- Data appears in the table preview with proper formatting
- The table is available for use in transforms, models, and reports
- For versioned tables, each time period contains its own dataset

## Common Pitfalls and Troubleshooting

**Problem:** “Unsupported file extension” error

- **Cause:** File name contains multiple periods (e.g., cost.data.xlsx)
- **Solution:** Rename the file to have only one period before the extension (e.g.,
  cost\_data.xlsx)

**Problem:** Data appears in wrong columns or with incorrect formatting

- **Cause:** Delimiter or text qualifier settings are incorrect
- **Solution:** Review the Import step settings and adjust the delimiter and text
  qualifier to match your file format

**Problem:** Numeric data appears as text

- **Cause:** Column type was incorrectly detected, or the data contains non-numeric
  characters
- **Solution:** In the Import step, change the column type to Number. If the issue
  persists, check for special characters in your source data.

**Problem:** File upload fails or data looks corrupted

- **Cause:** Excel file contains macros, special formatting, or formulas
- **Solution:** With the enhanced Excel parser (v12.11.16+), the system reads raw
  values directly. Save Excel as CSV, remove special formatting or macros, or apply
  formatting in TBM Studio using transform steps.

## What’s Next

After successfully uploading data, you can:

- [Transform the data](transform-enrich-data.html): Add transform steps to
  clean, map, filter, or join data.
- [Add to a model](../build-cost-model/model-basics.html): Incorporate the
  table into a cost model (see Section 3.2)
- Set up data freshness monitoring: Configure alerts for missing or stale data (see Section
  6.4)
- [Automate uploads](connect-external-dl.html): Transition to DataLink or
  API-based uploads for regular data feeds

**Parent topic:** [Data Import & Management](../../../../studio/new-uc/howtoguides/work-with-data/data-import-mgmt.html)
