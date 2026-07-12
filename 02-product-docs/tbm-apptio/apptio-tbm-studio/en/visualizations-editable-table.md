---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Editable Table"
breadcrumb:
  - "How-To Guides (Task-Based)"
  - "IBM Apptio Report Studio (New)"
  - "Visualizations"
  - "Editable Table"
source_path: "SSWRJM/studio/report-studio/visualizations/rs-editable-table.html"
images:
  - "03-media/apptio-tbm-studio/et-uploaddata.png"
  - "03-media/apptio-tbm-studio/et-sh-1.png"
  - "03-media/apptio-tbm-studio/et-sh-2.png"
  - "03-media/apptio-tbm-studio/apptio-script.png"
  - "03-media/apptio-tbm-studio/etspacer.png"
  - "03-media/apptio-tbm-studio/etcf.png"
  - "03-media/apptio-tbm-studio/etrefdate.png"
  - "03-media/apptio-tbm-studio/dd-1.png"
  - "03-media/apptio-tbm-studio/row-limit-et.png"
  - "03-media/apptio-tbm-studio/cust-form-et.png"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Editable Table

*An editable table allows you to edit the data directly within the table, such as updating values, adding new rows, or deleting existing rows, without having to leave the table or navigate to a separate editing interface.*

## When to use an Editable Table

- Update values inline
- Collaborate on structured data

## Add an Editable Table to the Report

1. Add an Editable Table from the Visualizations pane on the toolbar
1. Click on the Editable Table to enable the Data and Format panels.
1. Data Panel Drag one or more fields into the Columns area from the Dimension Explorer.
1. Format Panel General Properties – See Component Properties Editable Table specific properties Uneditable columns - Select/unselect specific columns in the Editable Tables as non-editable. Permissions - Give/remove permissions to table properties (like add row, delete row, change history, etc) to selected roles or the entire organization. Script - Edit the scripts to enable actions like table edits, emails, workflows, and button logic. Totals - Displays the total of numeric values in the rows and/or columns. Disable Edits - Enter the conditions to disable edits to the table.

Editable Table supports custom formulas and formula dimensions. For more details, see Custom Formulas

## Upload Data to Editable Table

The Upload Data feature allows you to quickly populate Editable Tables with data from files. This makes it easy to add or update information in bulk without manually entering each value.

1. Navigate to the Editable Table section within the application.
1. Click the Upload button located at the top-right corner of the table interface.
1. In the file selection dialog , choose the file you wish to upload Supported formats: .csv, .xlsx
1. Click Open to start the upload.
1. After upload completes, the table will refresh and display the newly added data.

![image of uploading data](../../../resources/images/studio_images/et-uploaddata.png)

## Show/Hide Columns in Editable Table

The Show/Hide Columns feature enhances data traceability and usability by allowing users to customize the columns displayed in an editable table. It also helps streamline your view by auditing and analysis by keeping sensitive or system-generated values (.pk,.Username, and .EditDate) hidden by default.

1. Open Column Settings (usually represented by a gear or column icon).
1. A list of available columns will appear with checkboxes.
1. Check the boxes for columns you want to display; uncheck those you want to hide.
1. The table view will update instantly to reflect your selections.

## Apptio Script

The Apptio script feature enables dynamic interactions and validations within editable tables through backend scripting.

1. The script runs automatically in the background – no user action is required.
1. It ensures that table behaviours such as conditional formatting, data validation, or auto-calculations are executed correctly as users interact with the table.

![image of apptio script](../../../resources/images/studio_images/apptio-script.png)

## Publish to Transform Table

The Publish to Transform Table feature enables users to publish changes made in an editable table to a linked transform table. This ensures that any updates or edits made at the date-entry level are reflected downstream for further processing and analysis.

1. After making edits in the editable table, click the Publish button.
1. A modal window will appear showing the associated transform table.
1. Review the details and click Confirm to proceed.
1. A notification will appear confirming that the changes have been appended to the transform table.
1. The Check-In modal will open, allowing you to finalize and submit the changes. Note: This functionality is currently available only to admin users .

## Disable Edits

```
“ {$CurrentUser:Users.ID}=ddavis@ABCCompany.com ”
```

## Spacer Column

Spacer Column adds visual separation between columns for better readability. To add a spacer column to an editable table, right-click on the table and then select Insert column to the right > Spacer column . A new column appears at the top of the editable table.

## Enable/Disable Carry Forward

This function allows you to carry forward the numeric values in a editable table (ET) report. From the editable table, select More Options , and then select Enable Carry Forward option.

You cannot move the columns if Enable Carry Forward option is selected. If the user selects Disable Carry Forward , then carry forward will be deactivated and the button will appear as Enable Carry Forward , and vice versa.

The carry forward behavior is applicable only for the local session and does not persist. Hence, every time the user returns, it will be in the default carry forward enabled state.

## Update Data

Update Data refreshes the table content globally. It appears at the top or bottom right of the editable table.

## Data Diagnostics

This feature allows you to open (/data) for further debugging. To see and open the full data path, select the editable table, and click the three dots.

## Auto-Wrapping for Editable Table Headers and Cells

Editable Tables now support auto-wrapping of text in both column headers and cells, improving readability and ensuring content is fully visible without manual resizing.

## Configuring Row Limits in Editable Tables

Editable Tables now support configurable row limits, allowing users to control the maximum number of rows that can be added or edited within a table. This helps manage data entry workflows more effectively and ensures better control over table size and usability.

## Displaying Formatted Data in Editable Tables

Editable Tables now support formatted data display, ensuring that values are shown using the configured formatting rules within the table. This improves readability and provides a more consistent reporting and data entry experience.

## Using Custom Formulas with Add to Filter in Editable Tables

Custom formulas can now be used with the “Add to Filter” capability in Editable Tables. This enhancement enables users to create more flexible and dynamic filters based on calculated values within the table.
