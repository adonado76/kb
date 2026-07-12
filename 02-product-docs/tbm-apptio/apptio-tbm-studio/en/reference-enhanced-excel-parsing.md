---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Enhanced Excel Parsing"
breadcrumb:
  - "Reference"
  - "Data Studio Reference"
  - "Enhanced Excel Parsing"
source_path: "SSWRJM/studio/new-uc/reference/enhanced-excel-parsing.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Enhanced Excel Parsing

Enhanced Excel parsing reads raw values directly from Excel files, bypassing Excel formatting for improved accuracy.

## Format Handling

| Excel Format | Old Parser | New Parser | Conversion Formula |
| --- | --- | --- | --- |
| Excel Format | Old Parser | New Parser | Conversion Formula |
| General | Hello | Hello | None needed |
| Number | 1 | 0.99999999 | =Round({Column},0) |
| Currency | $10.50 | 10.5 | =Currency({Column},"#,##0.00") |
| Accounting | 34,343.00 | 34343 | =NumberFormat({Column},"#,##0.00") |
| Date | 1-Jan-24 | 1704047400 (epoch) | =DateFormat({Column},"d-MMM-yyyy") |
| Percentage | 10% | 0.1 | =NumberFormat({Column},"#.00%") |

## Date/Time Conversion

Excel Date System: Sequential serial numbers starting with 1 = January 1, 1900

Unix Epoch: Begins January 1, 1970, 00:00:00 UTC

Conversion Formula: =DateFormat(({Column}-25569)*86400,"M/d/yy")

Explanation:

- 25569 = days between Excel epoch (1900) and Unix epoch (1970)
- 86400 = seconds per day
