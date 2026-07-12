---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "apptioscript"
title: "CopyTable function"
breadcrumb: []
source_path: "apptioscript/copytable function.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# CopyTable function

Use the CopyTable function to copy editable tables (report editable tables or raw data
sets) within a project, or to a different project within the same instance. This ability to copy
transform tables to different projects can be very useful in a multi-project solution, preventing
the need for workarounds such as export and re-upload.

## Syntax

```
CopyTable(path, project, tableName, timePeriod)
```

Note: autoCheckIn is an optional parameter, with the default value as "false"

## path

The fully qualified path to the source table to copy. The source table can either be a report
table or a raw data set.

Tip: The date in the path cannot include .DateGoesHere

## Report table

A report table is any table that is viewable in Apptio (basically anything that has a datapath).
To use it as the source table in CopyTable, all you need is the full datapath. These paths are used
to extract partial or conditional information from a table.

To get the full datapath:

1. Right click on the table and select Show Full Data Path.
2. Copy and Paste into a text editor.
3. Remove the line breaks so that the path is contiguous.

Example:

```
Customer.com:Project A/Data/.DateGoesHere/Example Data/.RawTable/!LIMIT[0,20]/!LIMIT_COLUMNS[]/
```

The “.DateGoesHere” portion of the report path will not work with CopyTable, so you will need to
edit it.

- If you are copying from a non time-enabled project, replace .DateGoesHere with
  Eon:FY2000

  Example – Non
  Time-Enabled:

  ```
  Customer.com:Project A/Data/Eon:FY2000/Example Data/.RawTable/!LIMIT[0,20]/!LIMIT_COLUMNS[]/
  ```
- If you are copying from a time-enabled project, and want to copy from a single, static time
  period, replace .DateGoesHere with Month:Year (for example, January:FY2011)

  Example – Time
  Hardcoded:

  ```
  Customer.com:Project A/Data/January:2011/Example Data/.RawTable/!LIMIT[0,20]/!LIMIT_COLUMNS[]/
  ```
- If you are copying from a time-enabled project, and you want to copy from the time period
  selected at the top of the page in Apptio, then replace .DateGoesHere with
  /<%=CurrentDate("MMMM:yyyy")%>/

  Example – Time
  Hardcoded

  ```
  Customer.com:Project A/Data/<%=CurrentDate("MMMM:yyyy")%>/Example Data/.RawTable/!LIMIT[0,20]/!LIMIT_COLUMNS[]/
  ```

## Raw Data Set

A raw data set is considered uploaded, untransformed data that is not in a report table. The
easiest way to get the path for a raw data set is to click the URL icon in the table preview pane on
the Data tab.

## project

The destination project must be given in the format of “Domain Name: Project Name”.

The domain and project of the project to copy to, in the form of domain:project

Example:

`customer.com:Project B`

Tip: Tables can be copied within the same project. In this case, simply enter the same
project in the editableTableName parameter.

Remember, if copying between two projects, they must
reside in the same instance. Be very careful when typing the domain and project. If you mistype (and
therefore the domain or project do not match existing ones), new ones will be created.

## tableName

The name of the table to copy to in the project

tableName is the data set that you are copying your editable table into. The format should simply
be provided as the name of the data set.

If your intention is to copy into an existing data set, simply key in that data set’s name (case
sensitive).

Example:

`Example Data Set`

If you want to copy into a new data set, key in the name of a data set which does not yet exist,
and it will be created upon execution of CopyTable.

Tip: If your intention is to copy into an existing dataset, and you mistype it, you will
inadvertently create a new dataset and copy into it, rather than the intended existing one.

## timePeriod

The time period to copy the data to in the project, in the form of month:year.

## Guidelines

When copying between projects, the two projects must reside on the same instance (URL). Assuming
they are on the same URL, editable tables can be copied across projects or across domains.

| Projects | Guidelines |
| --- | --- |
| Same instance, same domain | Project A and Project B are on the same URL (customer.apptio.com), and same Domain (customer.com). This can be achieved with CopyTable. |
| Same instance, different domains | Project A and Project B are on the same URL (customer.apptio.com), but two different domains (customer.com and test.com). This can be achieved with CopyTable. |
| Different instance | Project A and Project B are on two different URL’s (customer-dev.apptio.com and customer-stg.apptio.com). They have the same domain (customer.com). This cannot be achieved with CopyTable. |

It is possible to push to multiple destinations simultaneously from a single source Button. To do
this, configure the button with multiple occurrences of CopyTable(), separated by ;.

In various parts of the CopyTable syntax, you may need to enter a Time Period format (for
example, when designating the destination time period).

The time period format must always be as follows: Month:Year

Example:

`January:FY2011`

Note that it has to be the full month word, not an abbreviation (i.e. “January” versus “Jan” or
“01”).

Using the date format syntax in Apptio, this can be expressed as “MMMM:FYyyyy”

Tip:

The following characters, often used in the !FILTER and !NEWCOLUMN functions, require escaping or
URL encoding:

"

/

+

?

## Button Configuration

To initiate CopyTable, you can put the syntax above within a button on the reporting surface.

To configure a button to use CopyTable:

1. Switch to Edit Mode.
2. Right click the button and select Properties.
3. Select the Actions tab.
4. In the Server Action field, enter the CopyTable syntax.
5. Click OK.

When clicked, the button will initiate CopyTable as defined by the parameters within its
syntax.

## Example

```
CopyTable( "demo.apptio.com:BankDemo/Reports/October:FY2010/CostModels/Default/Business Units/.Summary/!SORT[{Chargeback}|desc]/!LIMIT[0,20,add_other|0,20,add_other]/!LIMIT_COLUMNS[]/", "apptio.com:DevBlank", "MyTable", "January:FY2000")
```
