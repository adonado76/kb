---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "GetLastFilterColumn function"
breadcrumb:
  - "Reference"
  - "Formulas and functions"
  - "GetLastFilterColumn function"
source_path: "SSWRJM/studio/formulas-and-functions/functions/getlastfiltercolumn.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# GetLastFilterColumn function

*Applies to : TBM Studio 12.0 and later*

Returns the name of the last column to which a filter was applied.

## Where to use

- Formula columns in report tables
- Dynamic Text

## Syntax

GetLastFilterColumn()

## Return type

Text

## Example

The following would return the value "Business Unit"

!Filter[Business Unit=Sales]

See also : GetLastFilterValue
