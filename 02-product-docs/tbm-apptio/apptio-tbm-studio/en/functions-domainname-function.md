---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "DomainName function"
breadcrumb:
  - "Reference"
  - "Formulas and functions"
  - "DomainName function"
source_path: "SSWRJM/studio/formulas-and-functions/functions/domainname.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# DomainName function

*Applies to : TBM Studio 12.0 and later*

The DomainName function can be combined with the ProjectName function to provide a fully qualified name: domain name:project name. For example: acme.com:ABCPRoject. Also, DomainName can be used with the LookUpFromPath function as part of the Path argument.

## Where to use

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

- ProjectName
- LookupFromPath
