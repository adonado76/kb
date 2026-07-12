---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "troubleshooting"
title: "No identifier on large model object"
breadcrumb: []
source_path: "troubleshooting/studio-troubleshooting-large-identifier.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# No identifier on large model object

To improve performance, model objects with a large number of rows should have an
identifier.

[Create a custom table identifier](../model%20studio/create-custom-table-identifier.htm "(Opens in a new tab or window)")

## Configuration recommendation for the No identifier on large model object error

To resolve this error:

1. Check out the affected object.
2. In the Rows drop-down, select Use object identifier, and then select the columns required for
   the identifier.

   ![](../../resources/images/studio_images/troubleshooting/large-identifier-solution.png)

Tip: The following columns are typically needed in the identifier:

- Trending By
- Allocating By
- Slicing By
- Pivoting On
- Grouping By
- Reporting On

Unless used for the above columns, identifiers do not have to be unique.
