---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "data_studio"
title: "Upload a data file"
breadcrumb: []
source_path: "data_studio/upload-data-file.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Upload a data file

Applies to: TBM Studio 12.0 and later. TBM Studio accepts data
from flat files in comma-, tab-, pipe-, tilde-, colon-, and semi-colon-separated formats. Before you
can upload data, you must create a table where the data will be loaded, if it does not already
exist.

To learn more, see [Create a
table](create-table.htm "(Opens in a new tab or window)"). Watch this demo video from Apptio Education Services: [Data Import And
Header In First Row Setting (3 min.)](https://community.apptio.com/videos/1642 "(Opens in a new tab or window)")

Or, browse [all Apptio videos](https://community.apptio.com/docs/DOC-7714 "(Opens in a new tab or window)").

## Upload data

Tip: If the file name contains more than one period (.), TBM Studio will return an
unsupported file extension error and will not upload the file. Ensure that the name of your file
only has a single period before the file type extension. Examples:

- example\_data.xlsx is correct.
- example.data.xlsx is not correct.

1. In TBM Studio, check out a document. To learn more, see [Best practices: Check out and check in](../admin/bp-check-out.html "(Opens in a new tab or window)").
2. Click Source in the table transform pipeline.
3. In the Table Description field, enter a short description of what the
   table's purpose is.
4. Click File Upload.
   - If you checked out an existing table, you should already have an Upload step.
   - If you've created a new step, an Upload step is added to the
     pipeline.
5. Do one of the following:
   - Click in the Details pane and browse to the file you want to upload.
   - Drag a file into the Details pane.

     An Import
     step is added to the pipeline.

     ![](../../resources/images/studio_images/studioimages/studio/stu599.png)
6. Click the Import step in the pipeline and review the settings:
   - Start import at row: Indicate the first row in the table to be included
     in the import. The import always includes the header row in the file. The number you enter
     designates the data row where the import will start. For example, in the spreadsheet below, entering
     a 2 in the field will start with the New York row because it is the second row of data.![](../../resources/images/studio_images/studioimages/studio/stu657.png)
   - Columns to Exclude: Indicate if there are columns you want to
     exclude.
   - Text Encoding: If the data file uses a particular character encoding,
     select the encoding scheme from the list. If you are unsure about the encoding, select the
     **Autodetect encoding** option.
   - Delimited: Select the character that separates the data fields in the
     file. Most often, this will be a comma.
   - Text qualifier: If there are special text characters in the data,
     indicate the text qualifier that is used to surround those characters. The default is double
     quotes.
   - Columns: Review the columns listed, and if desired, change the column
     types. To filter by column type (key, text, number, date), click a type icon in the search field of
     the Type column.

     Tip: The Import step supports data and
     cardinality validations, as described below.
7. To review the uploaded table, click the Table step in the pipeline.
8. If the table is acceptable, click Save on the Home tab.
9. If you are done making edits, click Check In.

## Data and cardinality validation

(Applies to: TBM Studio v12.1 and later)

When you upload data, the application can check for data validation and cardinality validation.
The options are available on the Import step of transform pipelines.

![](../../resources/images/studio_images/studioimages/studio/stu680.png)

Data validation applies when you are uploading data to an existing table. It checks for the following:

- Column added
- Column deleted
- Column cardinality changed
- Column type changed between the type override, the existing raw table doc, and the staging table
  doc

Cardinality validation applies to new tables and existing tables. It checks the content of a
column. It can be applied to each column separately. There are three options:

- Any: Turns off cardinality validation for the column.
- One: Checks if the column contains unique values. There are no duplicates.
- Many: Checks if every entry in the column is duplicated.

## Upload additional data into a table

You can upload additional data into a table. For example, you may want to load monthly cost data.
You can append the data or replace the existing data with new data.

Uploading additional data into a table can take two forms:

- Appending multiple files to the same time period.
- Loading the same table's data into different time periods, which this section describes.

To upload additional data into a table:

1. Check out the table.
2. Change the date picker to the period where the data will be added. A place holder is added to
   the Upload step in the transform pipeline. In the following image, a March placeholder has been
   added:![](../../resources/images/studio_images/studioimages/studio/stu571.png)
3. Click the placeholder and navigate to the file you want to upload or drag a file from the
   Windows Explorer into the placeholder.
4. Save the changes.

Uploading data during invalid time period
:   A sample criteria for the following conditions

    ![](../../resources/images/studio_images/closed_period.png)

    ![](../../resources/images/studio_images/closed_period_1.png)

    ![](../../resources/images/studio_images/closed_period_2.png)

    ![](../../resources/images/studio_images/closed_period_3.png)

## Data formats

The application accepts data from flat files in comma-, tab-, pipe-, tilde-, colon-, and
semi-colon-separated formats. To upload a data file, click the File Upload option. Before you
can upload data, you must create a table where the data can be loaded.

Tip: If the file name contains more than one period (.), TBM Studio will return an
unsupported file extension error and will not upload the file. Ensure that the name of your file
only has a single period before the file type extension. Examples:

- example\_data.xlsx is correct.
- example.data.xlsx is not correct.

## Data Refresh Cycles

When you create a new table by uploading a data file, you can select a refresh cycle from the
field at the top of the screen that describes how often a data set is expected to be updated. The
options are shown below. This is descriptive only. It does not execute uploads.

![](../../resources/images/studio_images/image-upload-data-file-2021_700x328.png)

Tip: You can change the Data Refresh Cycle from Ad-Hoc updates to
Monthly or Yearly versions. To do this, you must make sure you upload data files for each of the
upload periods displayed in the Upload panel. If you leave upload periods
without data files, it may affect the cost model.

The Data Refresh Cycles are described below:

|  |  |
| --- | --- |
| Ad-Hoc updates | The updates will be made as needed. The data can be appended to the existing table or replace the existing table. No data expiration checks will be run. |
| 1 version; No scheduled updates | The uploaded data will replace the existing data. No data expiration checks will be run. |
| 1 version; Update every month | The data will be refreshed every month. The new data will replace the existing data. On the Costing Standard data quality report, the data expiration checks will show the data as expired if it has not been updated within the last month. |
| 1 version; Update every year | The data will be refreshed every year. The new data will replace the existing data. On the Costing Standard data quality report, the data expiration checks will show the data as expired if it has not been updated within the last year. |
| Monthly versions; Update every month | The data will be updated every month. The new data will be added to a different period and will not overwrite the existing data. On the Costing Standard data quality report, the data expiration checks will show the data as expired if it has not been updated within the last month. |
| Yearly versions; Update every month | A year's worth of data is uploaded every month, covering the last 12 months. The new data will be added to a different period and will not overwrite the existing data. On the Costing Standard data quality report, the data expiration checks will show the data as expired if it has not been updated within the last month. |
| Yearly versions; Update at the start of the year | A year's worth of data is uploaded at the beginning of each fiscal year. The new data will be added to a different period and will not overwrite the existing data. If a dataset is not uploaded for the next year, the data will carry forward to the subsequent period. On the data quality report, the data expiration checks will show the data as expired if it has not been updated within the last year. Select this option for tables where the values are different each year. |
| Yearly versions with carryover; Update at the start of the year | A year's worth of data is uploaded at the beginning of each fiscal year. The new data will be added to a different period and will not overwrite the existing data. If a dataset is not uploaded for the next year, the previous year's values are carried forward. Select this option for tables where the values are largely the same each year. |

## Data Expiration Check

This feature is applicable for 12.10.8 release and above.

The Click to configure notifications link allows you to configure the notifications to
users when the uploaded data has expired. It sends reminders prompting the users to upload the fresh
data, as per the chosen data refresh cycle.

Note: This link appears for all data refresh options, except Ad-Hoc updates
and 1 version; No scheduled updates.

![](../../resources/images/studio_images/config-notification_601x120.png)

Click the link to provide the details and select the Create button.

![](../../resources/images/studio_images/late-noti-popup.png)

|  |  |
| --- | --- |
| Send e-mail notification to: | Enter the email id of the user whom the notification must be sent to. You can enter multiple email ids here. |
| Send email notification | Choose the number of days after which the notification email should be sent. |
| Send late email notifications daily until upload completed | Select this check box if you want to send late file notification emails daily. The emails will be sent until the fresh data is uploaded. |

Once the configuration is created, you can hover the cursor on the link to see the configuration
details.

![](../../resources/images/studio_images/late-file-noti.png)

## Date Freshness Check

To verify if fresh data is uploaded, navigate to Project tab, and then select **the Data
Freshness** option.

![](../../resources/images/studio_images/data-freshness.png)

You can view the following details here:

- Data Freshness Summary: shows the list of files with their expiration
  information
- Data Freshness Rules: shows the list of rules, with option to add more
  rules

## Create a table from an existing table

To create a table from an existing table, right-click a step in the transform pipeline and click
Create New Table from this step. The Create New Table action is available from some, but not
all, of the steps in a pipeline. The table created will not be linked to the original table. To know
more, click [here](create-table-from-existing-table.htm "(Opens in a new tab or window)").
