---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Enter data manually using editable tables"
breadcrumb: []
source_path: "studio/data_studio/enter-data-manually.html"
images:
  - "resources/images/studio_images/enter-data-1.png"
  - "resources/images/studio_images/enter-data-2.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Enter data manually using editable tables

**Applies to**: TBM Studio R12.0 and later

You can use editable tables to enter data manually. This data is then maintained directly within
the Apptio project database. For example, you can use editable tables to map other cost pools to IT
Resource Towers.

You can create two different types of editable table:

- Blank editable table: This is a simple table where the row and column values are directly typed
  into the Apptio UI by one or more individuals.
- Enriched editable table: This is a blended table or generated table where some of the values are
  typed in and some of the values come from another table.

You should use an enriched editable table if you have machine-generated data which needs a human
to enrich it. For example, you may want a human to provide a "responsible project" for every
instance tag detected in an Amazon Web Services bill.

Tip: If end users want to be able to add and remove rows on the reporting surface,
create a standalone blank editable table. In this case, you should consider the editable table to be
the source of truth, not the reporting surface.

## Blank editable tables

You can create a simple table where the row and column values are typed directly into the Apptio
user interface by one or more individuals.

## Create a blank editable table

1. On the **Home** tab in the **Document** group, select New
   > Editable Table.
2. In the New Manually Entered Table dialog, select Blank Table.
3. When prompted, enter a name for the editable table then select OK.
4. Go to Steps > Configure Columns and update the column properties.

   [Learn more about column properties](editabletables.html "Applies to: TBM Studio 12.6 and later")
5. Check in the editable table.

## Enriched editable tables

You can create an editable table which is based off of an existing Transform table. Users cannot
delete rows from an enriched editable table because the included rows are based on the source
Transform table.

Note: Sometimes, users employ enriched editable tables when a [TableMatch
function](../formulas-and-functions/functions/tablematch.html "Returns a value based on a rules table that functions like a set of IF statements. Each row in the rules table defines one rule. Conditions in the same row are combined with AND, and values within the same cell are treated as OR conditions.") or similar would be a better choice. While there are valid use cases for enriched
editable tables, consider whether they are the correct solution.

## Create an enriched editable table

1. On the **Home** tab in the **Document** group, select New
   > Editable Table.
2. In the New Manually Entered Table dialog, select Enriched Table.
3. When prompted, enter a name for the editable table then select OK.
4. Go to Steps > Generated and configure the source table.
5. To add editable columns to the enriched table, go to Steps > Configure Columns, select Add a new
   column and update the column properties.

   [Learn more
   about column properties](editabletables.html "Applies to: TBM Studio 12.6 and later")
6. Check in the editable table.

## How data goes into editable table

**Editable Table report component**

The Editable Table report component allows you to directly enter, maintain, and upload data
without TBM Studio access.

**How to directly enter data online**

1. In the Project Explorer view, select **Reports**.
2. Select a report.
3. Select **Check Out** > the report component features are available.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/enter-data-1.png)
4. Select **Editable Table** from the feature list. Now, you can directly enter
   your data in the table > Select **Save**.

**How to upload data to Editable Table**

1. In the Project Explorer view, select **Reports**.
2. Select a report.
3. If you scroll down the table, you get download and upload options.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/enter-data-2.png)
4. Download the table with **Open In Excel** > Make your changes > Upload the
   table with **Click or Drag File** option.
5. Select **Check Out**.

Note: You may also wish to see [Table Upload component](../reports/table-report-upload-component.html "Applies to: TBM Studio 12.9.3 and later") to familiarize yourselves with that
feature as it serves a similar purpose.

The data flow from a raw table to the Transform table
will not happen, unless the raw table is checked in.
