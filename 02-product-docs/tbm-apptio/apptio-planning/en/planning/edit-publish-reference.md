---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "planning"
title: "Edit and publish reference data tables"
breadcrumb: []
source_path: "planning/edit-publish-reference.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Edit and publish reference data tables

The tasks below can only be performed by users assigned to the Admin or Budget Process
Owner roles. For additional information on roles, see Frontdoor permissions and roles.

## Export a template

You can export a template that can be downloaded and populated with your reference data. This
feature could be useful if you want to upload a new reference data set, and just need a template to
guide you.

1. In the navigation menu, select Configuration > Reference Data.
2. Select the correct dimensions group tab, and select the appropriate dimension.
3. Select ![](../../resources/images/icons/icon-options_23x20.png) > Export
   Template.

   The Export File dialog opens.

   ![](../../resources/images/it%20planning_images/export_template_format.png)
4. Select Format Options to define the formatting options for the data.
5. Select Export.
6. Open and edit the exported .csv file. Enter data.

   Note: Do not change the column headings or data
   structure of the file.
7. Ensure to save the template in .csv format for import into Apptio planning applications.

## Export existing reference data

You can export your reference data table information which can then be edited and imported back.

1. In the navigation menu, select Configuration > Reference Data.
2. Select the correct dimensions group tab, and select the listed dimension which you need to
   export.
3. Select ![](../../resources/images/icons/icon-options_23x20.png) > Export.

   The
   Export File dialog opens.

   ![](../../resources/images/it%20planning_images/export_format.png)
4. Select Format Options to define the formatting options for the data.
5. Select Export.

   The reference data is exported as a .csv file.
6. Open and edit the exported .csv file.

   Note: Do not change the column headings or data structure
   of the file.
7. Ensure to save the file in .csv format for import into Apptio planning applications.

## Import and publish reference data

You can import data from an external .csv file into your Apptio Planning application. You can
also import reference data from Costing Standard. When you import reference data, your Apptio
Planning application imports the most recent reference data regardless of the active date setting in
Costing Standard. See [Integrate with
Cost Transparency](integrate-ct.htm "(Opens in a new tab or window)").

To import and publish dimension tables to populate or update them:

1. In the navigation menu, select Configuration > Reference Data.
2. Select the correct dimensions group tab, and select the appropriate dimension.
3. Select ![](../../resources/images/icons/icon-options_23x20.png) > Import.

   The
   Export File dialog opens.

   ![](../../resources/images/it%20planning_images/import_format.png)
4. Drag and drop the .csv file with the reference data onto the highlighted area of the Import File
   window. You can also click the arrow icon to navigate to the location of the .csv file on your local
   machine and import it.
5. Select Format Options to define the formatting options for the data.
6. Select Import, and then on the next dialog on successful import, select Continue.
7. Once the file is imported, and if you wish to publish the changes, select ![](../../resources/images/icons/icon-options_23x20.png) > Publish.

   The Publish dialog
   opens.

   ![](../../resources/images/it%20planning_images/publish_dialog.png)
8. Select Publish to go ahead with publishing the changes.
9. To cancel the changes instead of publishing them, select ![](../../resources/images/icons/icon-options_23x20.png) > Revert.

   The Revert dialog
   opens.

   ![](../../resources/images/it%20planning_images/revert_dialog.png)
10. Select Revert to roll back the changes.

## Edit dimension table values

1. In the navigation menu, select Configuration > Reference Data.
2. Select the correct dimensions group tab, and select the listed dimension which you need to edit
   data for.
3. Export the reference table to .csv file.

   To learn more about exporting reference data, see
   [Export template and reference
   data](edit-publish-reference.html#Editandpublishreferencedatatables__Exportexistingreferencedata)
4. Open and edit the exported .csv file.

   Note: Do not change the column headings or data structure
   of the file.
5. Import the edited .csv file.

   To learn more about importing reference data, see [Import and publish reference
   data](edit-publish-reference.html#Editandpublishreferencedatatables__Importandpublishreferencedata)
6. To publish the changes, select ![](../../resources/images/icons/icon-options_23x20.png) > Publish > Publish.
7. To cancel the changes, select ![](../../resources/images/icons/icon-options_23x20.png) > Revert > Revert.
