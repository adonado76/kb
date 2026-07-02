---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "configuration"
title: "Load data into the Costing Standard application"
breadcrumb: []
source_path: "configuration/loaddata.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Load data into the Costing Standard application

Master data tables provide a way to map your data to the data required by the CT
application. The information below describes how to load data into the application.

## Introduction

Each Costing Standard (CT) component has a master data table. The master data table provides
structure to the related data. Reports, allocations, and other configuration items are tied to the
master data table structure. You do not directly edit the master data tables. Instead, you append
and map data to the tables. This ensures the structure of the master data tables is not changed.

The information below describes how to load data into the application. Refer to this topic as
needed when you have to upload a data table. The upload procedure is not described anywhere else in
the Configuration Guide.

## Upload your source data

You must upload your source data into the application. After you upload the data, you can map it
to the master data table for a component. The data tables you upload should contain fields that can
be mapped to the required fields in the master data tables. The data tables do not need to contain
all of the fields in the master data tables.

The general procedure for uploading a source table is given below:

1. Click the **Home** tab in the Ribbon.
2. Click the **New** menu and then click **Table**.
3. In the Create Table dialog, enter a name for the table.
4. Enter a category. As you start typing, matching names of categories that already exist will be
   displayed. Also, you can enter a new category name. The categories are used to organize the tables
   in the Project Explorer.
5. Click **OK**. The application creates the table and displays the Source step in the transform
   pipeline as shown below.
6. Click the **File Upload** option.
7. Do one of the following to add an Import step to the pipeline:
   - Click in the **Details** pane and browse to the file you want to upload.
   - Drag a file into the **Details** pane.An Import step is added to the pipeline.
8. Click the **Import** step in the pipeline and review the settings:
   - Start import at row - Indicate the first row in the table to be included in the import.
   - Columns to Exclude - Indicate if there are columns you want to exclude.
   - Text Encoding -If the data file uses a particular character encoding, select the encoding scheme
     from the list. If you are unsure about the encoding, select the Autodetect encoding option.
   - Delimited -Select the character that separates the data fields in the file. Most often this will
     be a comma.
   - Text qualifier -If there are special text characters in the data, indicate the text qualifier
     that is used to surround those characters.
   - Columns - Review the columns listed at the right, and if desired, change the column types. To
     filter by column type (key, text, number, date), click a type icon in the search field of the Type
     column.
9. To review the uploaded table, click the **Table** step in the pipeline.
10. If the table is acceptable, click **Save** in the Ribbon.
11. If you are done making edits, click **Check In** in the Ribbon.

**Parent topic:** [Costing Standard](../home.html)

## Related information

- ![](../../../../03-media/apptio-costing-standard/sout.gif)[Send feedback about
  Help Center](productfeedback@apptio.com "(Opens in a new tab or window)")
