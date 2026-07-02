---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "planning"
title: "Troubleshoot Planning data upload errors"
breadcrumb: []
source_path: "planning/troubleshooting.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Troubleshoot Planning data upload errors

You may encounter some of the following errors when uploading data into Planning. Please refer to
the following sections to identify the error you are experiencing.

Row Modifications

- [Uploaded file contains one or more unknown columns which will be
  ignored](#TroubleshootPlanningdatauploaderrors__Uploaded)
- [Invalid Formatting of uploaded data](#TroubleshootPlanningdatauploaderrors__Invalid)
- [Could not resolve one or more references to another table](#TroubleshootPlanningdatauploaderrors__Could)
- [Setting unknown lookup value to the default](#TroubleshootPlanningdatauploaderrors__Setting)
- [Uploaded files contains more than one column with alias names that are
  reserved for the same column](#TroubleshootPlanningdatauploaderrors__Uploaded2)

Row Omissions

- [Invalid Cost Center and Cost Object Mappings](#TroubleshootPlanningdatauploaderrors__Invalid2)
- [Could not resolve one or more references to another table](#TroubleshootPlanningdatauploaderrors__Could2)
- [Uploaded data includes items that have been delegated from other cost
  objects, these items will be excluded](#TroubleshootPlanningdatauploaderrors__Uploaded3)

Other Errors

- [We're sorry, but we cannot publish the...
  dimension](troubleshooting.html#TroubleshootPlanningdatauploaderrors__Were)
- [No Changes Detected: 1 error detected in <Dataset>, including the
  following: Uploaded file did not contain any columns in the header row](#TroubleshootPlanningdatauploaderrors__No)
- [No Changes Detected: 1 error detected in <Dataset>, including the
  following: Empty Header](#TroubleshootPlanningdatauploaderrors__No2)
- [The user's actuals data is not appearing in the forecast.](https://help.apptio.com/en-us/it-planning/planning/troubleshooting.htm#The "(Opens in a new tab or window)")
- [A specific dimension is blank in the forecast](https://help.apptio.com/en-us/it-planning/planning/troubleshooting.htm#A "(Opens in a new tab or window)")

## Row Modifications

Row Modifications errors occur when non-required values in your imported data are inconsistent
with the application's templates or Reference Data. Planning will automatically modify data when
these errors occur to ensure an otherwise successful import. In most situations, invalid data is
modified or removed from the import, while remaining data is imported.

## Uploaded file contains one or more unknown columns which will be ignored

Symptom
:   ![](../../resources/images/it%20planning_images/102-11870-20-228473_nl_unknowncolumns1.png)

    The listed columns are not imported to Planning, but other valid columns are imported
    normally.

What's going on
:   Uploaded files must follow Planning's template and column placement. Columns that are not part of
    Planning's templates are not recognized and will not be uploaded.

    The error message should list all instances of omitted columns.

Solution
:   Ensure you are importing data using the associated Planning template.

    1. Navigate to the page you wish to import data to.
    2. Click the Actions button, then select:
       - Export <Page name> Template... to download a blank template.
       - Export <Page name>... to download all current data in template format.
    3. Templates are in the .CSV filetype, which can be edited using Excel.
       - All columns accepted by Planning will be included in the template.

## Invalid Formatting of uploaded data

Symptom
:   ![](../../resources/images/it%20planning_images/102-11870-20-228451_nl_invalidformatting.png)

    The listed values are not uploaded into Planning, which may leave gaps in your dataset.

What's going on
:   Planning has identified data that is incorrectly formatted. As explained in the previous entry,
    Planning uses templates for data imports. Each template column requires a specific type of data
    (i.e. text, numerical, etc.). Failure to match the correct value type for a column is the most
    common cause of this error.

    The error message should list all instances of improperly formatted data.

Solution
:   Investigate your data and confirm that all column data is correctly formatted for its respective
    column.

    - Numbers: no formatting, punctuation, or symbols (600000).
    - Text: no punctuation (Executive). Spaces are allowed if necessary (Accounts Payable).
    - Date: For more information, see [Troubleshooting invalid date formats in Planning](ts_invalid_date_formats.html).
    - Excel equations or functions are invalid.

## Could not resolve one or more references to another table

Symptom
:   ![](../../resources/images/it%20planning_images/102-11870-20-228694_itperror2.png)

    The data listed in the error is not imported to Planning because it cannot be correlated to
    existing Reference Data.

What's going on
:   Imported data must correlate with your Reference Data, which acts as a key to link Departments,
    Accounts, and IDs. The non-required data you are importing cannot be found in your Reference
    Data.

    The error message should list all instances of data that cannot be correlated to Reference
    Data.

Solution
:   1. Verify that all values in your imported file correlates to your published Reference Data.
       - If not, update your Reference Data.For more information, see [Manage reference data
         dimensions](manage-reference-data.html).
    2. Select Update Reference Data only for the budgets you wish to apply changes to.
    3. Import your data again and confirm that your Reference Data changes are successful.

## Setting unknown lookup value to the default

Symptom
:   ![](../../resources/images/it%20planning_images/102-11870-20-231306_nl_settingunknownlookupvalue.png)

What's going on
:   In Reference Data, you can create custom lists and dimensions.

    Once established, these custom elements act in the same way as all other Reference Data.

    This error is functionally the same as the previous error, "Could not resolve one or more
    references to another table:", but specific to custom lists and dimensions.

Solution
:   1. Verify that all values in your imported file correlates to your published custom lists and
       dimensions. If not, update your custom information and import it into Planning.
    2. Click Update Reference Data only for the budgets you wish to apply changes to.
    3. Import your data again and confirm that your Reference Data changes are successful.

## Uploaded files contains more than one column with alias names that are reserved for the same column

Symptom
:   First encountered column of duplicates will be used: <Column1>. Duplicate column will be
    omitted: <Column2>.

    ![](../../resources/images/it%20planning_images/231305.png)

    <Column1> is imported while <Column2> is not imported to Planning.

What's going on
:   Planning has detected multiple column names matching the name of a template column.

    In the example image, there are two columns identified called "Cost Center Code" and "Cost
    Center." Both columns include the required column name "Cost Center."

    Planning will default to the first column that matches in order from left to right when reading
    the .CSV file. Any additional column matches will not be imported.

Solution
:   If you wish to use one name over the other, switch the order the columns so your preferred name
    will be read first (in order from left to right).

## Row Omissions

Row Omissions errors occur when required values in your imported data are inconsistent with
Planning templates or Reference Data. These errors are significant and may cause your data import to
fail entirely. It is important to resolve these errors when they appear.

## Invalid Cost Center and Cost Object Mappings

Symptom
:   ![](../../resources/images/it%20planning_images/102-11870-20-232951_itperror3.png)

What's going on
:   Departments and Projects can be associated with specific Cost Centers. If so, only those Cost
    Centers are considered valid.

    Your imported data is associating Cost Centers with Departments that are not explicitly permitted
    in your current settings.

Solution
:   For Departments:

    1. Go into Departments Reference Data and update the associated Cost Center Codes.
    2. You can leave the Cost Center Code column blank to allow all Cost Centers.

For Projects without Investment Planning:

- Go into Projects Reference Data and update the associated Cost Center Codes.

For Projects with Investment Planning:

- Go to the Project Listing view and modify the Cost Center Code column.

For Projects, you can enable the Allow Any Cost Center option to disable the mapping restriction.
This option is available in Project Reference Data or Project Listing, depending on whether you have
Investment Planning.

## Could not resolve one or more references to another table

Symptom
:   ![](../../resources/images/it%20planning_images/102-11870-20-232952_itperror4.png)

What's going on
:   Imported data must correlate with your Reference Data, which acts as a key to link Departments,
    Accounts, and IDs. The required data you are importing cannot be found in your Reference Data.

    The error message should list all instances of data that cannot be correlated to Reference
    Data.

Solution
:   1. Verify that all values in your imported file correlates to your published Reference Data.
       - If not, update your Reference Data.For more information, see [Manage reference data
         dimensions](manage-reference-data.html).
    2. Select Update Reference Data only for the budgets you wish to apply changes to.
    3. Import your data again and confirm that your Reference Data changes are successful.

## Uploaded data includes items that have been delegated from other cost objects, these items will be excluded

## Symptom

![](../../resources/images/it%20planning_images/232953.png)

## What's going on

Delegated costs occur when a project has ended and its upkeep costs have moved to a different
Department. Delegated costs will still appear in their original Department as greyed out, read-only
rows.

Delegated costs data must be updated where the cost has been delegated.

## Solution

Identify where the cost has been delegated. You must update these costs in their delegated
location, not their source location.

For more information, see [Delegate project costs](pfp/delegate-project-costs.html).

## Other Errors

Other types of errors that can occur in Planning.

## We're sorry, but we cannot publish the... dimension

## Symptom

Because one or more reference tables are using values that are no longer present in the version
you want to publish

![](../../resources/images/it%20planning_images/231008.png)

## What's going on

Publishing error: Reference Data that previously existed in Planning is now missing. Because
elements of your report depend on that Reference Data, a major error is produced and the publish
operation fails.

## Solution

See [Troubleshoot reference data
deletion errors](ts-reference-data.html).

## No Changes Detected: 1 error detected in <Dataset>, including the following: Uploaded file did not contain any columns in the header row

## Symptom

![](../../resources/images/it%20planning_images/246685.png)

## What's going on

Costing Standard to Planning Integration Error: This issue may be caused by:

- An error in the Costing Standard Integration settings or configuration.
- One or more imported tables are Checked Out in Costing Standard.

## Solution

Navigate to Planning, click the Settings Menu, then click Costing Standard Integration. Verify
the following:

- All tables are spelled and named correctly in the Plan Integration, Actuals Integration, and
  Reference Data Integration sections.
- The Import From field is set to Development.

Navigate to Costing Standard and verify the following:

- All tables are Checked In.
- Set the current Fiscal Year to Open.

## No Changes Detected: 1 error detected in <Dataset>, including the following: Empty Header

Symptom

![](../../resources/images/it%20planning_images/246687.png)

What's going on

Costing Standard to Planning Integration Error: Planning is pulling data from the current month
in Costing Standard. The month must be open in Costing Standard; otherwise the integration cannot
find any data.

Solution

1. Navigate to Costing Standard.
2. Open the Current Month in Costing Standard.
3. Click Save.
4. Return to Planning and try importing again.

## The user's actuals data is not appearing in the forecast.

Check following reasons where actuals data may not appear in the forecast and take the corrective
action

Reason

Forecast Start Month set incorrectly in Forecast Plan creation - Actuals data appears for the
periods upto forecast start month minus one.

Solution

Recreate the forecast plan by selecting correct forecast start month.

Reason

Actuals data is not available in Planning > Spend Management

Solution

Ensure Actuals period in Spend Management show actuals data. If not, populate actuals data in
Spend Management using Cost Transparecy Integration or using Automated Data Management or by
manually uploading the .csv file in the actuals period.

## A specific dimension is blank in the forecast

This could be due to one of the following reasons:

Reason

The dimensions is not enabled for the Actuals Summarization in the Company Profile.

Solution

Navigate to Company Profile, select the dimension from Actuals Summarization and Save the
changes. Recreate the forecast plan after the dimension is saved for summarization.

Reason

The dimension doesn't have data in Spend Management.

Solution

Ensure the actuals data for the dimension is available in the Spend Management. If not, populate
actuals data in Spend Management using Cost Transparecy Integration or using Automated Data
Management or by manually uploading the .csv file in the actuals period.

For additional information, please see:

- [Troubleshoot: unable to import or export
  Excel files](ts_unable_imp_exp_xsl.html)
- [Troubleshoot invalid date formats in
  Planning](ts_invalid_date_formats.html)
- [Manage reference data
  dimensions](manage-reference-data.html)
