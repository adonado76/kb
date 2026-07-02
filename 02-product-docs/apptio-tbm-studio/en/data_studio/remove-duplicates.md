---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "data_studio"
title: "Remove duplicates from a table"
breadcrumb: []
source_path: "data_studio/remove-duplicates.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Remove duplicates from a table

Applies to: TBM Studio 12.0 and later

If you are working with a data set that has duplicate entries in the key column, you can
eliminate the duplicate entries using the Remove Duplicates transform step.
If there are duplicate entries with the same value, the entry in the table that matches the
comparison type will be selected.

![](../../resources/images/studio_images/studioimages/studio_remove%20dup_remove%20dup.png)

## Remove duplicates

1. If the project is time enabled, select the period and year.
2. Check out the table.
3. Add a Remove Duplicates step to the transform.
4. Select values for the fields:
   - Key Column. Select the column to filter.
   - Comparison Column. Select the column that contains the values used to
     determine the row that will be kept.
   - Comparison Type. Select which rows to keep:
     Largest or Smallest. The comparison type you choose
     determines the values kept. For example, the column could include dates. If you choose the
     Largest comparison type, the row with the latest date will be kept.

## Filtering unique rows example

Assume you have a table that lists server purchases by purchase price and date as shown below.
You would like to filter the table so only the latest purchase for each server type is displayed.
You would set Key Column to Server, Comparison Column to Purchase
Date, and Comparison Type to Largest:

![](../../resources/images/studio_images/studioimages/studio/aug450.png)
