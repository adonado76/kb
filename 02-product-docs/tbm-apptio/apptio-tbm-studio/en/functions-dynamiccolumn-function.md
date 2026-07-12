---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "DynamicColumn() function"
breadcrumb:
  - "Reference"
  - "Formulas and functions"
  - "DynamicColumn() function"
source_path: "SSWRJM/studio/formulas-and-functions/functions/dynamic-column.html"
images:
  - "03-media/apptio-tbm-studio/dynamic-columns.png"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# DynamicColumn() function

*Applies to : TBM Studio 12.10.9 and later*

A new function DynamicColumn() is introduced to replace the Eval() function. We want to eliminate the use of Eval() to enable the Precision Calc performance improvements coming in Server 12.10.10 in July 2023.

The DynamicColumn() function allows you to pass in a column name, and dynamically return the values in other columns where that name matches. Using Dynamic Column, you can make your configuration more programmatic and reduce the reliance on nesting if functions to return data in the same table.

In order to replace the full flexibility of the Eval() function, the new formula may need to be split into separate DynamicColumn() function calls to return the desired, concatenated results. See screenshot for a basic example formula using DynamicColumn().

To maximize the calc performance improvements of the new "precision calculations" feature, the functionality of the Eval() function is replaced with DynamicColumn() or other code changes. The customers that still have Eval() in their project configuration, can make the necessary changes using the OOTB Eval() replacement code document that has information of all the reports and metric changes.

NOTICE : If you have modified the OOTB reports, the Eval() will not be removed from reports in earlier templates (e.g. ,v104, v105, v106. v107).

## Where to use

- Tables

## Syntax

DynamicColumn()

## Arguments

Column

The name of a column to get the value from

defaultValue

The value that exists in the column based on the Column (name) value

## Return type

String

## Example

To see an example of this function, refer Dynamic Columns
