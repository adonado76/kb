---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "data_studio"
title: "Search for duplicate entries in a table"
breadcrumb: []
source_path: "data_studio/search_for_duplicates.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Search for duplicate entries in a table

Applies to: TBM Studio 12.0 and later

There may be times when you want to search for duplicate entries in a table column. For example,
you may have created a column that will serve as a unique identifier and you want to be sure there
are no duplicate keys.

To search for duplicate entries in a table:

1. Click the Table step in the transform pipeline, right-click in the header of the column,
   and then click Show Values.
2. In the Count column in the Values in... dialog, enter !=1. This will search for
   rows that do not have a value of 1, which will indicate duplicate entries.
