---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Table Upload component"
breadcrumb: []
source_path: "studio/reports/table-report-upload-component.html"
images:
  - "resources/images/studio_images/append-1.png"
  - "resources/images/studio_images/append-2.png"
  - "resources/images/studio_images/append-3.png"
  - "resources/images/studio_images/append-4.png"
  - "resources/images/studio_images/append-5.png"
  - "resources/images/studio_images/append-data-upload.png"
  - "resources/images/studio_images/studioimages/reports/table-upload-component-2.png"
  - "resources/images/studio_images/studioimages/reports/table-upload-component-3.png"
  - "resources/images/studio_images/studioimages/reports/table-upload-component-4.png"
  - "resources/images/studio_images/studioimages/reports/table-upload-component-5.png"
  - "resources/images/studio_images/studioimages/reports/table-upload-component-6.png"
  - "resources/images/studio_images/upload-checkedout.png"
  - "resources/images/studio_images/upload-from-report.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Table Upload component

**Applies to**: TBM Studio 12.9.3 and later

The Table Upload component allows end users with appropriate permissions to directly upload data
from spreadsheets into tables without the need for TBM Studio access.

Tip: For the Table Upload component to be available via the Report ribbon it may need to
be enabled using Enable Features.

[Learn more about the Enable Features option.](../admin/enable_features.html "TBM Studio sometimes contains features that are not yet released to all customers. These are beta version features and may not work exactly as designed.")

## Simple configuration

To use the simple configuration option, do the following:

1. Add a Table Upload component to your report.
2. Click the Config button on the table upload component.
3. Drag uploaded tables into the list as shown in the following example.
4. ![image](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/table-upload-component-2.png)

   Note: If you choose the Enforce Errors option, this will run validation on the table. If validation
   errors are encountered, they will be displayed when you attempt upload. Validation errors including
   things like missing columns, columns with incorrect headers, etc.).
5. Click Apply to save the component configuration.
6. On the ribbon, click the Save button to save the report.

This will result in end users with access to the report being able to select the tables and
update them.

See the [User interaction](#TableUploadcomponent__Userinteraction) section later in this topic for details on
what the user experience is like.

## Advanced configuration

The purpose of the advanced configuration option is to support more granular control over which
tables individual users or groups can update without having to make multiple reports.

To use the advanced configuration option, do the following:

1. Create an editable table with the following columns:
   1. Table
   2. Role
   3. User
2. For the purposes of this example, we will call the editable table “Table Access”.
3. Populate the columns with data to specify the user or role that should have access to update a
   given table. Here is an example:

   | Table | Role | User |
   | --- | --- | --- |
   | Acme Contracts | Power User |  |
   | Acme General Ledger |  | bob@acme.com |
   | Acme General Ledger |  | sally@acme.com |
   | Acme IT Org Mapping |  | bob@acme.com |
   | Acme IT Org Mapping |  | roxanne@acme.com |

   Given the example table above, and knowing that Sally is also a Power User the tables
   each user will see in the drop down of the Table Upload component are as follows:

   - bob@acme.com will see Acme General Ledger and Acme IT Org Mapping.
   - sally@acme.com will see Acme Contracts (by virtue of her being in the Power User group) and Acme
     General Ledger.
   - roxanne@acme.com will only see the Acme General Ledger.
4. Add the Table Upload component to your report.
5. On the table upload component, click the Config button.
6. Toggle the Configuration Type to Advanced.
7. In the Table: field add the name of your editable table (“Table Access” in our example, and
   optionally specify matching for Roles and Users:
8. ![image](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/table-upload-component-3.png)

   Note: If you choose the Enforce Errors option, this will run validation on the table. If validation
   errors are encountered, they will be displayed when you attempt upload. Validation errors including
   things like missing columns, columns with incorrect headers, etc.).
9. Click Apply to save the component configuration.
10. On the ribbon, click the Save button to save the report.

This will result in end users with access to the report and access to the table as specified in
the editable table described above being able to select the tables and update them.

See the [User interaction](#TableUploadcomponent__Userinteraction) section later in this topic for details on
what the user experience is like.

## User interaction

When a user with access to the report browses to the report, they will see the Upload Table
component.

To use it, they would do the following:

1. Select one of the tables from the drop down.
2. Click the Edit button.

   This will result in the table being checked out. When the table is
   ready the page will refresh.
3. When uploading to a slot with existing data you will be presented with these options:

   ![image](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/table-upload-component-4.png)
4. After making the desired edits click Save.
5. You will be presented with a Check In dialog. Include a message that describes the nature of the
   change and click Check In.

   ![image](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/table-upload-component-5.png)

If you selected the Enforce Errors option during configuration and errors are detected, then an
error badge with dropdown will appear.

In the following example a column was not present that was expected, a new column was added, and
a column the system expected to be a numeric had label values:

![image](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/table-upload-component-6.png)

## Uploading data in editable tables

**12.11.3 and later**: The **Upload** button appears only for blank table and not for
generated table. To see this button, enable the **Enable/Disable Upload** option in the [Advanced Properties](tables/set-table-properties.html "Applies to: TBM Studio 12.0 and later")
popup.

If you upload data to a checked out report, the upload popup cannot be closed. Due to this, the
**Upload** and **Save** buttons will remain disabled and the uploaded file/data will not be
saved. You can close the popup only by refreshing the table - right-click on the table area, and
then select **Update Data** option.

![image](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/upload-checkedout.png)

However, when you upload data in a checked-in report, the upload popup has the close icon, and
hence the upload can be canceled or successfully saved.

## Uploading data via reports

Navigate to an editable table report and filter for the desired scope. <right-click> on the
menu just outside the table and select **Open in Excel**.

![image](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/append-1.png)

Make the desired changes offline in Excel [Avoid Download ET feature or Excel export from nav bar
(export not filtered)]

![image](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/append-2.png)

Upload the changes by selecting **Upload ET** and drag and drop or enter file name.

![image](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/append-3.png)

You can choose to either overwrite the existing data or to append the data. The **Upload Now**
button will be disabled until an option is selected.

![image](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/append-4.png)

Select the **Append** option and the new entries will be merged along with the older previous
entries. The **Append** option also works with the Data Validation - Table Upload integration
functionality.

Note: The **Overwrite** option is selected by default for first upload. For all the future
uploads, user must select one of the options, Overwrite or Append.

The uploaded file must be of the same config as that of the existing uploaded file. If the config
does not match, a pop up will appear restricting them to change the ET data.

![image](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/append-5.png)

## Append data upon upload

In an Editable Table report, right-click to select **Properties** > **Advanced** and then
choose 'Append data upon upload' option.

![image](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/append-data-upload.png)

Now, upload any file, to see the **Upload Options** popup.

![image](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/upload-from-report.png)

See how [Enhanced Excel
Parsing](tables/enhanced-excel-parsing.html) works in Apptio

- **[How Enhanced Excel Parsing Works in Apptio](../../studio/reports/tables/enhanced-excel-parsing.html)**
