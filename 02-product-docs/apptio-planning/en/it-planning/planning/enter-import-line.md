---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Bulk Upload Line-Item Values"
breadcrumb:
  - "Planning"
  - "Working with Plans"
source_path: "it-planning/planning/enter-import-line.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Bulk Upload Line-Item Values

Bulk upload data by uploading a CSV to your financial plan.

## Permissions

- **Admins** and **Budget Process Owners** can upload line item data across the
  organization.
- **Cost Center Owners** can upload for the departments they have edit access to.
- **Project Managers** can upload for the projects they have edit access to.

## Import Modes

When performing a bulk upload, you’ll choose between following import modes:

|  |  |
| --- | --- |
| **Mode** | **Behavior** |
| Replace All Data | Clears existing values and replaces them entirely with the values in the import file. Each line imported will have a new Line Item Code. |
| Replace All Data with Dimension Filter | Enables line item importing to selectively replace the data only for the specific dimensions. Users can select one or more dimensions for selectively replacing the data. Each line imported will have a new Line Item Code.  Filtering by following dimensions is supported   1. Account 2. Cost Center 3. Cost Object 4. Project 5. Vendor 6. Location 7. Custom Dimensions 8. Custom Columns of List data type |
| Update Data | Updates existing rows by matching on Line Item Code. If External Code is enabled, the system will match on Line Item Code and External Code during the update process. Any rows in the import file that do not match an existing Line Item Code or External Code will be added as new line items, and a new Line Item Code will be automatically generated. |
| Append Data | Adds all line items from the file to Plan without modifying or deleting existing data. Use this option to import new records only. Each new row will be assigned a unique Line Item Code. |

## Steps to Bulk Upload Line Item Values

1. Open the plan and navigate to the appropriate Expense tab (e.g., **Labor**, **Labor
   Activity**, **Contracts**, **Assets**, or **Other**).
2. Select the **Department** you want to import data into from the Department menu.
3. Open the **Actions** menu in the upper-right corner and choose **Import...**
4. Upload your **CSV file** and select the desired **Import Mode**(Replace All Data,
   Update Data, Append Data, or Replace All Data with Dimension Filter).
   1. **Using Replace All Data with Dimension Filter**
      1. In the Import dialog, click on **Add** **Dimension** **Filter** button
      2. Select a **D****imension**.
      3. Select one or more values for the selected dimension.
      4. *(Optional)***Add additional dimensions** and specify values for each
         one.
      5. When multiple filters are applied, data will be replaced only for rows that meet
         *all* filter criteria.
   2. **To use any other import modes** (Replace All Data, Update Data or Append Data)
      select the desired import option.
5. *(Optional)* Adjust import settings such ascolumn delimiter, date format, decimal
   symbol, percent display, and character encoding.
6. Click **Import** to generate a preview.
7. Review the preview to confirm that the data is mapped and formatted correctly.
8. If correct, click **Import** to finalize — or **Import with Issues** if you want
   to proceed despite warnings. You may also **Export Help File** to review any import
   errors in detail.
9. Once completed, the data is successfully added to the plan and becomes visible in the
   **Expenses** table.

Note: The Period/Month columns are automatically populated based on the **Start Date**, **End
Date**, and **Quantity** entered. The system distributes the specified quantity across the
months within the selected date range. Users may modify these auto-generated values if
needed.

## Export a Template for Import

1. Open the plan and navigate to the appropriate Expense tab (e.g., **Labor**, **Labor
   Activity**, **Contracts**, **Assets**, or **Other**).
2. Click the **Actions** menu in the upper-right and select **Export Template...**
3. Click **OK** to download the generated template file. **Do not change the column
   headers or structure** — they are required for import consistency.
4. Populate the template with your line-item data.
5. Save your file in .csv format and import it back into Apptio Planning when ready.
