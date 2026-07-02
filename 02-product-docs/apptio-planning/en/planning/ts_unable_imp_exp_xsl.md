---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "planning"
title: "Troubleshoot: unable to import or export Excel files"
breadcrumb: []
source_path: "planning/ts_unable_imp_exp_xsl.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Troubleshoot: unable to import or export Excel files

## Before you begin

You cannot upload Microsoft Excel file data in the Planning tool, or export Excel file data
from Planning.

## About this task

Planning uses the .CSV file format for uploaded data, and does not support default Excel
file formats such as .XLS and .XLSX.

Adopt .CSV as your standard data file format when using the
Planning tool. You can export your .CSV budget to your computer, make changes to the .CSV file in
Excel, and then import the new .CSV file back to Apptio.

## Procedure

- **Saving Excel files as .CSV**
  1. Open Microsoft Excel and open the file you wish to upload to Apptio. Make any
     necessary adjustments.
  2. Click Save As and select the (\*.csv)
     file format.

     A new .CSV file is created. You can edit .CSV files within Excel, allowing you to make
     adjustments as needed before uploading your files.
- **Import .CSV files to Planning**

  When importing .CSV files, you are replacing all current line item data with those of the
  imported file. There is no data merge or addition when importing files into Planning.

  For more information, see[Learn
  more about entering or importing line item data in Planning.](enter-import-line.html)
- **Export .CSV files from Planning**

  Files exported from Planning to your computer will be in .CSV format by default.

  For more information, see[Learn
  more about exporting and populating line item tables or layouts in Planning.](export-populate-line.html)
