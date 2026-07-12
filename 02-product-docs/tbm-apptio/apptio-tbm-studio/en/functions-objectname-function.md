---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "ObjectName function"
breadcrumb:
  - "Reference"
  - "Formulas and functions"
  - "ObjectName function"
source_path: "SSWRJM/studio/formulas-and-functions/functions/objectname.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# ObjectName function

*Applies to : TBM Studio 12.0 and later*

The function returns the name of the object driving the current report.

## Where to use

- Formula columns in report tables
- Dynamic text

This function is used most often in HTML text boxes on reports as part of dynamic text.

## Syntax

ObjectName()

## Arguments

None

## Return type

String

## Examples

The following dynamic text in an HTML text box on a report returns the name of the current report object.

<%=ObjectName()%>
