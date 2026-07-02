---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "TableInfo function"
breadcrumb: []
source_path: "formulas-and-functions/functions/tableinfo.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# TableInfo function

Applies to: TBM Studio 12.9 and later

The TableInfo function adds one or more table columns that provide information about the
last upload to the table. TableInfo columns are especially useful for data validation. Aggregate
periods are not supported.

Where to use

This function is used in any table where
you can apply
formulas.

Syntax

`TableInfo(metric,<tableName>,[timePeriod])`

Arguments

*metric*

Each
of the following metrics add a column:

- Last Updated - The date (time stamp) when the raw data was last updated. This metric
  returns the number of seconds since January 1, 1970, which can be optionally formatted with the
  DateFormat formula. For example:
- =DateFormat(TableInfo("Last Updated"), "M/d/yy hh:mm:ss a")
- Last Updated By - The userID of the person who last updated the raw data.
- Source - The name of the uploaded file, similar to the Source column in the .Datasets
  table.
- Type - The type of the data source, similar to the Type column in the .Datasets
  table.
- Uses Data From - The time period that the raw data is copying forward from.
- Updated this Period - True/false, indicating whether the file was uploaded in this
  period.
- *tableName*- The name of the table ingesting the retrieved information. Defaults to the
  name of the current table, unless otherwise specified.
- *timePeriod* - The current period, if not otherwise specified.
- Return type - The function supports both text and numbers.

## Examples

The following is an example of multiple metrics formulas and the resulting columns.

![](../../../resources/images/studio_images/studioimages/getgroupbycolumn.png)
