---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Debug function"
breadcrumb: []
source_path: "studio/apptioscript/debug_function.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Debug function

Use Debug() to display a dialog box that contains text or data in a specific place in the
script.

This function can be attached to a button or to an editable table's onCellValueChange.

## Syntax

`Debug(expression)`

## expression

The expression may be one of the following:

- A text string enclosed in double quotes.
- A row and column of an editable table.

## Example

Display the words I'm here when the script
runs:

`Debug("I'm here")`
