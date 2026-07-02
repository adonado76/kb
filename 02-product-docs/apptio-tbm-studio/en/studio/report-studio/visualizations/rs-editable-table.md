---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Editable Table"
breadcrumb:
  - "TBM Studio"
  - "How-To Guides (Task-Based)"
  - "IBM Apptio Report Studio (New)"
  - "Visualizations"
source_path: "studio/report-studio/visualizations/rs-editable-table.html"
images:
  - "resources/images/studio_images/apptio-script.png"
  - "resources/images/studio_images/cust-form-et.png"
  - "resources/images/studio_images/dd-1.png"
  - "resources/images/studio_images/et-sh-1.png"
  - "resources/images/studio_images/et-sh-2.png"
  - "resources/images/studio_images/et-uploaddata.png"
  - "resources/images/studio_images/etcf.png"
  - "resources/images/studio_images/etrefdate.png"
  - "resources/images/studio_images/etspacer.png"
  - "resources/images/studio_images/row-limit-et.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Editable Table

An editable table allows you to edit the data directly within the table, such as
updating values, adding new rows, or deleting existing rows, without having to leave the table
or navigate to a separate editing interface.

## When to use an Editable Table

Use Editable Tables when you want to:

- Update values inline
- Collaborate on structured data

## Add an Editable Table to the Report

1. Add an Editable Table from the Visualizations pane on the toolbar
2. Click on the Editable Table to enable the Data and Format panels.
3. Data Panel
   1. Drag one or more fields into the **Columns** area from the Dimension Explorer.
4. Format Panel
   1. General Properties – See [Component Properties](../components/components.html#abt-comp__comprop)
   2. Editable Table specific properties
      1. Uneditable columns - Select/unselect specific columns in the Editable Tables as
         non-editable.
      2. Permissions - Give/remove permissions to table properties (like add row, delete row,
         change history, etc) to selected roles or the entire organization.
      3. Script - Edit the scripts to enable actions like table edits, emails, workflows, and
         button logic.
      4. Totals - Displays the total of numeric values in the rows and/or columns.
      5. Disable Edits - Enter the conditions to disable edits to the table.

Editable Table supports custom formulas and formula dimensions. For more details, see [Custom Formulas](../create-first/custom-formula.html "Custom formulas (also referred to as formula dimensions) allow you to define new calculated dimensions using existing fields in your data model. This enables deeper analysis and richer insights without requiring any changes to the underlying dataset or schema.")

## Upload Data to Editable Table

The **Upload Data** feature allows you to quickly populate Editable Tables with data
from files. This makes it easy to add or update information in bulk without manually
entering each value.

**Steps to use** 

1. Navigate to the **Editable Table** section within the application.
2. Click the **Upload** button located at the top-right corner of the table interface.
3. In the **file selection dialog**, choose the file you wish to upload
   1. Supported formats: .csv, .xlsx
4. Click **Open** to start the upload.
5. After upload completes, the table will **refresh** and display the **newly added
   data.**

![image of uploading data](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/et-uploaddata.png)

## Show/Hide Columns in Editable Table

The **Show/Hide Columns**
feature enhances data traceability and usability by allowing users to customize the columns
displayed in an editable table. It also helps streamline your view by auditing and analysis
by keeping sensitive or system-generated values (.pk,.Username, and .EditDate) hidden by
default.

**Steps to use** 

1. Open **Column Settings**(usually represented by a gear or column icon).
2. A list of available columns will appear with checkboxes.
3. Check the boxes for columns you want to display; uncheck those you want to hide.
4. The table view will update instantly to reflect your selections.

![image of show hide column](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/et-sh-1.png)

![image of hidden column](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/et-sh-2.png)

## Apptio Script

The Apptio script feature enables **dynamic interactions and validations** within
editable tables through backend scripting.

**Steps to use** 

1. The script runs automatically in the background – no user action is required.
2. It ensures that table behaviours such as conditional formatting, data validation, or
   auto-calculations are executed correctly as users interact with the table.

![image of apptio script](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/apptio-script.png)

## Publish to Transform Table

The Publish to Transform Table feature enables users to publish changes made in an editable
table to a linked transform table. This ensures that any updates or edits made at the
date-entry level are reflected downstream for further processing and analysis.

**Steps to use** 

1. After making edits in the editable table, click the **Publish** button.
2. A modal window will appear showing the associated transform table.
3. Review the details and click **Confirm** to proceed.
4. A notification will appear confirming that the changes have been appended to the
   transform table.
5. The **Check-In** modal will open, allowing you to finalize and submit the changes.

   Note: This functionality is currently available only to **admin users**.

## Disable Edits

This field takes a dynamic text expression. If the expression evaluates to true, editing
will be disabled for the table. In the example below, user ddavis will not be able to edit
the table.

```
“ {$CurrentUser:Users.ID}=ddavis@ABCCompany.com ”
```

## Spacer Column

Spacer Column adds visual separation between columns for better readability. To add a spacer
column to an editable table, right-click on the table and then select **Insert column to
the right** > **Spacer column**. A new column appears at the top of the editable
table.

![image of spacer column](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/etspacer.png)

## Enable/Disable Carry Forward

This function allows you to carry forward the numeric values in a editable table (ET)
report. From the editable table, select **More Options**, and then select **Enable Carry
Forward** option.

![image of enabling and disabling columns](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/etcf.png)

Note: The carry forward is applicable only for numeric value and consecutive columns. If there
is a non-numeric column in between, the carry forward will not apply thereafter.

You cannot move the columns if Enable Carry Forward option is selected. If the user selects
**Disable Carry Forward**, then carry forward will be deactivated and the button will
appear as **Enable Carry Forward**, and vice versa.

The carry forward behavior is applicable only for the local session and does not persist.
Hence, every time the user returns, it will be in the default carry forward enabled
state.

## Update Data

Update Data refreshes the table content globally. It appears at the top or bottom right of the
editable table.

![image of refresh data option](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/etrefdate.png)

## Data Diagnostics

This feature allows you to open (/data) for further debugging. To see and open the full
data path, select the editable table, and click the three dots.

![image of data diagnostics](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/dd-1.png)

## Auto-Wrapping for Editable Table Headers and Cells

Editable Tables now support auto-wrapping of text in both column headers and cells,
improving readability and ensuring content is fully visible without manual resizing.

## Configuring Row Limits in Editable Tables

Editable Tables now support configurable row limits, allowing users to control the maximum number
of rows that can be added or edited within a table. This helps manage data entry workflows more
effectively and ensures better control over table size and usability.

![image to set row limit in editable table](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/row-limit-et.png)

## Displaying Formatted Data in Editable Tables

Editable Tables now support formatted data display, ensuring that values are shown using the
configured formatting rules within the table. This improves readability and provides a more
consistent reporting and data entry experience.

## Using Custom Formulas with Add to Filter in Editable Tables

Custom formulas can now be used with the “Add to Filter” capability in Editable Tables. This
enhancement enables users to create more flexible and dynamic filters based on calculated values
within the table.

![image to use custom formula in add to filter](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/cust-form-et.png)
