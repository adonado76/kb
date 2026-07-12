---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "GetNextPublishTime function"
breadcrumb: []
source_path: "formulas-and-functions/functions/getnextpublishtime.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# GetNextPublishTime function

Applies to: 12.11.10 and later

Returns the planned execution time when the next recurring publish will occur. These date/times
are maintained at the individual transform table level.

## Where to use

This function can be used in:

- Formula columns in report tables
- Dynamic text

## Syntax

`= GetNextPublishTime(“Table_name”)`

## Arguments

TableName

Name of the transform created from Editable table

## Return type

Date Time

## Example

`GetNextPublishTime(“Table_Demo”)`

Result : November 12, 2024 12:31:00 PM GMT+05:30
