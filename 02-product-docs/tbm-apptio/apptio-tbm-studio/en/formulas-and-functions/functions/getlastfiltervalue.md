---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "GetLastFilterValue function"
breadcrumb: []
source_path: "formulas-and-functions/functions/getlastfiltervalue.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# GetLastFilterValue function

Applies to: TBM Studio 12.0 and later

Returns the last value applied to a filter.

## Where to use

This function can be used in:

- Formula columns in report tables
- Dynamic Text

## Syntax

`GetLastFilterValue(column)`

## Arguments

*column*

> The column from which to retrieve the last applied filter value.

## Return type

String

## Example A

The following would return the value "Sales."

> `!Filter[Business Unit=Sales]`

## Example B

Assume you have the report shown in the following image:

![](../../../resources/images/studio_images/studioimages/studio/stu283.png)

You would like the name of the table to change based on the slicer selection. For example, in the
previous image, UNIX has been selected in the slicer and you would like the name of the table to
read Server Costs - UNIX as shown in the following image:

![](../../../resources/images/studio_images/studioimages/studio/stu284.png)

To create the dynamic table name:

1. Hide the default header for the table by opening the Properties dialog for the table,
   selecting the General tab, and clearing the Show Header option.
2. Add an HTML text box to the report with the following HTML
   code:

   ```
   <font face="Arial"><p
                 style="color:#3366CD;text-align:left;font-size:10pt">Server Costs -
                 <%=getLastFilterValue()%></p></font>
   ```
3. Position the HTML box above the table to server as the table name.
4. Select the HTML text box.
5. In the HTML Configuration dialog, add the Server Type field to the Rows area.
6. Hide the default header for the HTML text box by opening the Properties dialog for the
   table, selecting the General tab, and clearing the Show Header option.

See also: [GetLastFilterColumn](getlastfiltercolumn.htm "(Opens in a new tab or window)")
