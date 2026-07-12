---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "data_studio"
title: "Create a table from an existing table"
breadcrumb: []
source_path: "data_studio/create-table-from-existing-table.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Create a table from an existing table

Applies to: TBM Studio 12.0 and later

There may be times when you want to create a new table from an existing table. For example, you
may have a table that contains a great deal of information in multiple columns, and you want to
create a data set with only a few of the columns for reporting purposes.

When you create a new table from an existing table, the new table is linked to the source table.
You can use the source data or the output table. The source data uses the raw data uploaded into the
application. The output table uses the data after all the steps in the transform pipeline have been
applied.

There are many reasons why you might want to create a transform:

- Cleansing the data
- Creating the appropriate level of granularity in the data
- Validating the data
- Performing complex joins
- Performing calculations

There are two ways to create a new table from an existing table:

- Create a new table and use the Existing Table source option.
- Right-click either the Import step or the Table step in the transform pipeline of
  an existing table and click Create New Table from this Step.

After you create the table, click the Existing Table step in the transform pipeline of the
new table and click either the Source Data or Output Table option.
