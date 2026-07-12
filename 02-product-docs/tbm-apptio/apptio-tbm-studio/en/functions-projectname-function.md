---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "ProjectName function"
breadcrumb:
  - "Reference"
  - "Formulas and functions"
  - "ProjectName function"
source_path: "SSWRJM/studio/formulas-and-functions/functions/projectname.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# ProjectName function

*Applies to : TBM Studio 12.0 and later*

Returns the name of the current project.

The ProjectName function can be combined with the DOMAINNAME function to provide a fully qualified name: domain name:project name. For example: acme.com:ABCPRoject. Also, ProjectName can be used with the LOOKUPFROMPATH function as part of the "path" argument.

## Where to use

- Data sets
- Calculated metrics and reports with metric columns
- Formula columns in report tables
- Dynamic text

## Syntax

ProjectName( )

## Return type

Text

- DomainName
- LookupFromPath
- ProjectExists
