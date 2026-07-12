---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "troubleshooting"
title: "Limited threshold: Row Expanding"
breadcrumb: []
source_path: "troubleshooting/studio-troubleshooting-row-expanding.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Limited threshold: Row Expanding

The Row Expanding limiter prevents the generation of very large tables in Apptio
products. Certain functions, such as *LookupEx*, *SplitEx*, and *Unpivot*, can result
in unintentionally large tables.

If the Row Expanding limit is reached, it results from one of these functions exceeding the limit
set in Apptio.

![](../../resources/images/studio_images/troubleshooting/row-expanding-1.png)

![](../../resources/images/studio_images/troubleshooting/row-expanding-solution.png)

## Configuration recommendation for the Limited threshold: Row Expanding error

To resolve the error for the LookupEx function:

- Analyze the relationship between the two tables to determine why there is a large number of
  *one to many* matches, and reduce their variability.
- [LookupEx function](../formulas-and-functions/functions/lookupexandlookupex_wild.htm "(Opens in a new tab or window)")

The largest possible number of matches for LookupEx is the product of the two tables.

To resolve the error for the SplitEx function:

- Review the underlying data that is split and reduce the size of the data to limit the
  expansion.
- [SplitEx function](../formulas-and-functions/functions/splitex.htm "(Opens in a new tab or window)")

To resolve the error for the Unpivot function, do one of the following:

- Reduce the number of columns that are collapsed.
- Reduce the row count of the current table.
