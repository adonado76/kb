---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Load Data"
breadcrumb:
  - "Costing Standard"
  - "Configuration"
source_path: "cost-transparency/configuration/config-loaddata.html"
images:
  - "resources/images/studio_images/load4a.png"
  - "resources/images/studio_images/load6.png"
  - "resources/images/studio_images/load7.png"
  - "resources/images/studio_images/load9.png"
  - "resources/images/studio_images/lod2a.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Load Data

Master data tables provide a way to map your data to the data required by the CT
application.

Each Costing Standard (CT) component has a master data table. The master data table
provides structure to the related data. Reports, allocations, and other configuration items
are tied to the master data table structure. You do not upload data directly to the master
data tables. Instead, you append or map data (using Map step in data pipeline) to the
tables. This ensures the structure of the master data tables is not changed.

You must upload your source data into the application. After you upload the data, you can
map it to the master data table for a component. The data tables you upload should contain
fields that can be mapped to the required fields in the master data tables. The data tables
do not need to contain all of the fields in the master data tables.

For more details on the types of data that can be uploaded and the different methods
available to upload data, go [here](https://www.ibm.com/docs/en/apptio-commercial/tbm-studio/saas?topic=data-upload "(Opens in a new tab or window)")

The general procedure for uploading a source table is given below:

1. Click the **Home** tab in the Ribbon.
2. Click the **New** menu and then click **Table**.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/lod2a.png)
3. In the Create Table dialog, enter a name for the table.
4. Enter a category. As you start typing, matching names of categories that already exist
   will be displayed. Also, you can enter a new category name. The categories are used to
   organize the tables in the Project Explorer.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/load4a.png)
5. Click **OK**. The application creates the table and displays the Source step in the
   transform pipeline as shown below.
6. Click the **File Upload** option. For more information on other options, go [here](https://www.ibm.com/docs/en/apptio-commercial/tbm-studio/saas?topic=data-upload "(Opens in a new tab or window)").

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/load6.png)
7. A upload step will get created where user can Click/drag file or Right-click to paste
   the file.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/load7.png)
8. An Import step is added to the pipeline.
9. Click the **Import** step in the pipeline and review the settings:
   - Start import at row - Indicate the first row in the table to be included in the
     import.
   - Columns to Exclude - Indicate if there are columns you want to exclude.
   - Text Encoding -If the data file uses a particular character encoding, select the
     encoding scheme from the list. If you are unsure about the encoding, select the
     Autodetect encoding option.
   - Delimited -Select the character that separates the data fields in the file. Most
     often this will be a comma.
   - Text qualifier -If there are special text characters in the data, indicate the text
     qualifier that is used to surround those characters.
   - Columns - Review the columns listed at the right, and if desired, change the column
     types. To filter by column type (key, text, number, date), click a type icon in the
     search field of the Type column.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/load9.png)
10. To review the uploaded table, click the **Table** step in the pipeline.
11. If the table is acceptable, click **Save** in the Ribbon.
12. If you are done making edits, click **Check In** in the Ribbon. For more information
    on Check In and Check out, go [here](https://www.ibm.com/docs/en/apptio-commercial/tbm-studio/saas?topic=administration-best-practices-check-out-check-in "(Opens in a new tab or window)")

For more details on additional functionality related to table uploads, go [here.](https://www.ibm.com/docs/en/apptio-commercial/tbm-studio/saas?topic=data-upload-file "(Opens in a new tab or window)")

**Delete a table**

1. Check out the table.
2. On the **Home** tab in the **Document** group, click **Delete**.
3. Check in the table.
