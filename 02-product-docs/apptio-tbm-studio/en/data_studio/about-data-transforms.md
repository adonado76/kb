---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "data_studio"
title: "Data acquisition and transformation"
breadcrumb: []
source_path: "data_studio/about-data-transforms.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Data acquisition and transformation

Applies to: TBM Studio 12.0 and later

## About the table transform pipeline

To modify data in a table, you can add or modify steps in the transform pipeline. In the
pipeline, you can:

- See all of transform steps in the order they are executed.
- Add, edit, and delete transform steps to modify the output.
- Drag to reorder individual steps.
- Browse videos in the [Apptio community](https://community.apptio.com/communities/community-home/librarydocuments/viewdocument?DocumentKey=c7ec37da-b3ef-41af-9671-3039095fa2a9 "(Opens in a new tab or window)") (link requires TBM Connect credentials).

Note: Editable tables are not table transforms and are not covered in this article. For more
information, see [Editable tables:
Accommodating user input](editabletables.htm "(Opens in a new tab or window)").

## Table transform pipeline steps

When creating a new table, the following pipeline steps will automatically populate regardless of
the source of the data:

- Source: Determines the type of data on which to base a table.
- Table: Previews the data table created by the transform.

Depending on the Source option selected, other pipeline steps will automatically be added:

File Upload source options:

- Upload: Allows the user to select the file to upload.
- Import: Displays the settings used to define how the system should import
  a file.

Existing Table source option:

- Existing Table: Defines the table transform on which the table should be
  based.

You can add the following pipeline steps to any table:

- Append: Adds the rows from one table to the rows in another table. See
  [Append data](append-data.htm "(Opens in a new tab or window)").
- Assign Rows: Automatically added when using Map Columns to map to master
  data sets with machine learning capabilities and can be re-added to valid tables through the Add
  Step process. Uses machine learning and user created rules to map to ATUM concepts. See [Assign cost pools with machine
  learning](assigncostpools.htm "(Opens in a new tab or window)").
- Date Partition Use dates from the file, either in rows or columns, to
  automatically distribute the data across time periods. See [Partition data by date](partition-data-by-date.htm "(Opens in a new tab or window)").
- Filter: Remove specific rows based on values in one or more columns.
- Flatten Hierarchy: Provides the greatest flexibility when using slicers.
  This pipeline step adds one column for each level in the hierarchy to a table. You can then create
  slicers for each of the columns. See [Flatten a data hierarchy](flatten-hierarchy.htm "(Opens in a new tab or window)").
- Formulas: Add new formula columns based on data, change column types (for
  example, change a number to a label), or override existing values. See [Add and edit columns](add-edit-columns.htm "(Opens in a new tab or window)") and [Formulas and functions](../formulas-and-functions/introduction-to-formulas-and-functions.htm "(Opens in a new tab or window)").
- Group: Group the table by the values in one or more text columns.
- Hide and Rename: Hide or rename columns in the data.
- Join: Combine data from two or more tables into the same rows based on
  common values in one or more columns. See [Join data](join-data.htm "(Opens in a new tab or window)").
- Map Columns: Conforms the table's output to match the ATUM schema and
  adds the rows to the master data set. See [Map Columns](mapcolumns.htm "(Opens in a new tab or window)").
- Model: Allows the table to be used as an object in a model where users
  can define drivers and allocate values. See [About models](../model%20studio/about-models.htm "(Opens in a new tab or window)").
- Pivot: Converts rows to columns. See [Pivot data](pivot-tables.htm "(Opens in a new tab or window)").
- Remove Duplicates: Filters out rows in a table that have the same value
  in a column or set of columns.
- Row-Level Security: Allows users to filter tables and reports based on
  the current user. See [Apply Row-Level Security](apply-row-level-security.html "(Opens in a new tab or window)").
- Unpivot: Convert columns to rows.
