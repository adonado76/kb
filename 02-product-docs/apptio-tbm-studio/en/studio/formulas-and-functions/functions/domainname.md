---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "DomainName function"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Formulas and functions"
source_path: "studio/formulas-and-functions/functions/domainname.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# DomainName function

**Applies to**: TBM Studio 12.0 and later

The DomainName function can be combined with the ProjectName function to provide a fully
qualified name: domain name:project name. For example: acme.com:ABCPRoject. Also, DomainName can be
used with the LookUpFromPath function as part of the Path argument.

## Where to use

This function can be used in:

- Data sets
- Calculated metrics and reports with metric columns
- Formula columns in report tables
- Dynamic Text

## Syntax

```
DomainName
        ( )
```

## Return type

Text

See also:

- [ProjectName](projectname.htm "(Opens in a new tab or window)")
- [LookupFromPath](lookupfrompath.htm "(Opens in a new tab or window)")
