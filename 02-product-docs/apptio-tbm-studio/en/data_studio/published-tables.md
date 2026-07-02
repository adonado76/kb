---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "data_studio"
title: "Publish Tables for Export"
breadcrumb: []
source_path: "data_studio/published-tables.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Publish Tables for Export

Applies to: TBM Studio 12.11.3 and later. Published Tables are used to export data
from one Costing & Planning project to other Costing & Planning project, or to a 3rd party
system.

Prior to this feature, users had to create a report to export data. The major concern was to lock
the report so that end users could not access it. Some export tables were quite large, which in turn
added load on the system. This slowed down the staging calc process, due to which the table
availability was delayed.

Advantages of Published Tables

- Eliminates managing reports and associated permissions while exporting tables.
- Supports creating tables in the same way as a report.
- Supports export as soon as the dev calc finishes.
- Creates a more accessible, discoverable, and maintainable way to export modeled data.
- Removes dependency on the TBM Studio reporting surface, from non-Studio clients to export
  data.

## Creating a Published Table

There are two ways to create a Published Table.

## Method One: Create a Published Table

1. Navigate to Home tab and select New.

   ![](../../resources/images/studio_images/pt-new.png)
2. Select Published Table. Enter a name and category, and select
   OK.

   ![](../../resources/images/studio_images/method-1.png)
3. The newly created table will appear in the specified category in the Project Explorer.

   ![](../../resources/images/studio_images/pt-pe_304x333.png)
4. Configure the published table in the same way as a report table (see the [Tables in reports](../reports/tables/about-tables.htm "(Opens in a new tab or window)")
   help section).

## Method Two: Create a Published Table from an existing report table

1. Navigate to an existing report with a table that you wish to convert to a Published Table.
2. Right-click on the report table and select Create Published Table.
3. Enter a name and category, and select OK.

   ![](../../resources/images/studio_images/method-2a.png)
4. The newly created table will appear in the specified category in the Project Explorer.

   ![](../../resources/images/studio_images/method-2b.png)

## Configuration Options

Disable / enable pre-calculation

1. From Project Explorer, checkout any Published Tables.
2. Select the Published Table tab and adjust the Active setting appropriately.

   ![](../../resources/images/studio_images/pt-1_964x592.png)

   - If checked, the system will pre-calculate the table. This is the default option as it ensures
     the table will be ready for export when the API URL is used.
   - If unchecked, the system will not pre-calculate the table. The API URL will still work, but the
     system will need to calculate the table when it first receives a request for it.

## Using a Published Table

1. Right-click on the Published Table to see the API URL.

   ![](../../resources/images/studio_images/using-1.png)
2. Copy the URL and use it in DataLink or scripted automation.

   ![](../../resources/images/studio_images/using-2.png)
