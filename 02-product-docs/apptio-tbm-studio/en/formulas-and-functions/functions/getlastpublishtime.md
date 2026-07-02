---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "GetLastPublishTime function"
breadcrumb: []
source_path: "formulas-and-functions/functions/getlastpublishtime.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# GetLastPublishTime function

Applies to: 12.11.10 and later

Returns the time that the recurring publish was executed to update the editable table data into
the associated transform table. It also displays the last publish for all three methods: recurring
schedule, publish button or Admin upload in Studio. These date/times are maintained at the
individual transform table level.

Editable table data is published in following ways:

- Publish from reporting surface
- Recurring schedule
- “Update to this period” in transform

Last publish is updated when the data gets published in any of the above ways.

## Where to use

This function can be used in:

- Formula columns in report tables
- Dynamic text

## Syntax

`= GetLastPublishTime(“transform_table_name”)`

## Arguments

TableName

Name of the transform created from Editable table

## Return type

Date Time

## Example

`GetLastPublishTime(“Table_Demo”)`

Result : November 12, 2024 12:31:00 PM GMT+05:30
