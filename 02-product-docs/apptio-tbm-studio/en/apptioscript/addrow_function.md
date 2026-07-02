---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "apptioscript"
title: "AddRow function"
breadcrumb: []
source_path: "apptioscript/addrow_function.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# AddRow function

Use AddRow() to add a row to a table, and to set values in the columns of that
table.

## Syntax

```
AddRow(date, tableName, columnName=value, columnName2=value, ...)
```

## date

Determines the date to modify the data sets. The date argument can use one of the following
formats:

| Argument format | Description |
| --- | --- |
| "February:2008" | Add a row in February 2008 |
| "!START\_OF\_YEAR(February:2008)" | Add a row for the first month of the fiscal year. |
| currentDate("MMMM:yyyy") | Add a row for the current month. |
| ".MostRecent" | Add a row in the most recently edited time period for the project. |

## tableName

The name of the data set, as indicated by the name of a table.

## columnName

The name of a column in the table identified in the tableName argument.

## value

The value to insert in the cell of the column in the new row.

## Example 1

This example is acting on a table named MyServers, that has columns named servername, ram, and
os. Note that the table may have other columns that the script is not acting on. This example adds a
row to a table named MyServers for the first month of the fiscal year and sets the following values
for the columns:

- servername = server001
- ram = 128
- os = WINDOWS

```
AddRow( "!START_OF_YEAR(February:2008)", MyServers, servername="server001", ram="128", os=UPPER("windows"))
```

## Example 2

This example is the same as Example 1, except it adds a row for the current month instead of the
first month of the fiscal
year.

```
AddRow(CurrentDate("MMMM:yyyy"), MyServers, servername="server001", ram="128", os=UPPER("windows"))
```

## Example 3

This example adds a row to a table named DeliveryTracking for February 2008. It indicates that
the name field value is Server203, and the AcceptedBy field contains an acceptance message
identifying the user, date and time of the
approval.

```
AddRow( "February:2008", DeliveryTracking, name="Server203", AcceptedB="Accepted by <%=$CurrentUser:Users.Full Name%> on <%=CurrentDate()%>")
```

## Example 4

```
AddRow(CurrentDate("MMMM:yyyy"), All Projects, Project Name="unnamed", Status="Pending")
```

To subsequently navigate to that row use the following
command:

```
[[tab:Demand and Resource/@.TableTransform:All Projects/!FILTER[{Project ID}=%22$ACTION_RESULT%22]/Update Project Definition]]
```
