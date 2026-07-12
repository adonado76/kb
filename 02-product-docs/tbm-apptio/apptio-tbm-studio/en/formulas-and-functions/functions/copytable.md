---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "CopyTable function"
breadcrumb: []
source_path: "formulas-and-functions/functions/copytable.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# CopyTable function

Applies to: TBM Studio v12.0+

## About this task

The CopyTable function provides a way to copy report tables or raw data sets. CopyTable
allows you to copy tables within a project, or to a different project within the same instance. This
ability to copy tables to different projects can be very useful in a multi-project solution and
thereby prevent the need for using workarounds, such as export and re-upload. Also, the CopyTable
function is flexible and allows copying to a specific time period in a destination
project.

The CopyTable function is triggered using a button on a report. On the Properties
dialog, you enable CopyTable with syntax in the Server Action field on the Actions tab.

![](../../../resources/images/studio_images/studioimages/studio/stu277.png)

## Overview and Limitations

Before using CopyTable, review and understand the following important concepts about the
capabilities of this function:

- The CopyTable table path must be URL-encoded. To get the path for the table, right-click in the
  table and select Show Full Data Path. If the path is not encoded, you must escape the
  following special URL characters: " / + ?

  Check on the internet for information on how to escape
  the characters.
- The destination table is always a data set, in contrast to the source, which can be either a
  report table or a raw data set. Existing data sets in the destination can be overwritten, or new
  data sets can be created.
- When copying between projects, the two projects must reside on the same instance (URL). Assuming
  that the projects are on the same URL, tables can be copied across projects or across domains.

  Examples
  :   Example 1: (Same instance, same domain): Project A and Project B are on the same URL
      (customer.apptio.com), and same domain (customer.com). CopyTable can be used.

      Example 2: (Same instance, different domains): Project A and Project B are on the same URL
      (customer.apptio.com), but two different domains (customer.com and test.com). CopyTable
      cannot be used.

      Example 3: (Different instance): Project A and Project B are on two different URLs
      (customer-dev.apptio.com and customer-stg.apptio.com). They have the same domain (customer.com).
      CopyTable cannot be used.
- You can copy to multiple destinations simultaneously from a single source button. To do this,
  configure the button with multiple occurrences of CopyTable(), separated by a new line.
- Time Period Format used in CopyTable must always be Month:Fiscal Year or Period:Fiscal Year
  (example: January:FY2011 or P1:FY2011). For Gregorian calendars, you can use the full month word or
  the three-letter abbreviation (for example: January or Jan). Using the date format syntax in the
  application, this can be expressed as MMMM:ffff. For period calendar types, you can use
  ppp:ffff.

## Where to use

Use the syntax in the Server Action field of a button on a report.

## Syntax

```
CopyTable("Source Table","Destination Project","Destination Data Set","Time Period
        to Copy To", autocheckin=”true”|”false”)
```

Note: Each argument must be enclosed in quotes.

## Arguments

Source Table - Source Table can be either a report table or a raw data set.

Report Table - A report table is any table that is viewable in the application (basically
anything that has a data path). To use it as the source table in CopyTable, you need the full data
path only. To get the full data path:

1. Right-click on the table, then select Show Full Data Path. See the How To: Use show full data
   path to learn more.
2. Copy and paste the data path into a text editor.
3. Remove the line breaks so that the data path is on one line.
4. Replace the .DateGoesHere string with an appropriate time period. See Time Period to Copy To for
   more information on valid time period strings.
5. Remove the add\_total string if it is present to avoid having a total row in the target.

For example, let's say you start with the following data path (note the parts in
red):

```
customer.com:Test Project A/
Reports/
.DateGoesHere/
CostModels/
Default/
Test/
!GROUPBY[{Test Table.Item},{Test Table.Group}]/
.Summary/
!SORT[{Cost}|desc]/
!FILTER_ZERO[{Cost}]/
!PIVOT2[{Test Table.Item}][{Test Table.Group}][{Cost}]/
!LIMIT[0,2147483647,add_total]/
!LIMIT_COLUMNS[][][][orderByIncludeList] /
```

It would be edited to look something like the following if you wanted to use a dynamic time
period as the source.

```
customer.com:Test Project A/Reports/<%=CurrentDate("ppp:ffff")%>/CostModels/Default/Test/!GROUPBY[{Test Table.Item},{Test Table.Group}]/.Summary/!SORT[{Cost}|desc]/!FILTER_ZERO[{Cost}]/!PIVOT2[{Test Table.Item}][{Test Table.Group}][{Cost}]/!LIMIT[0,2147483647]/!LIMIT_COLUMNS[][][][orderByIncludeList]/
```

## Raw data set

A raw data set is considered any uploaded, untransformed data that is not in a report table.

To get the path to a raw data set from /data, follow these steps:

1. Navigate to the table in TBM Studio.
2. Select Table in the Steps pipeline.
3. Copy the segment of the URL after the -@C.Example: Relevant portion of the URL
   highlighted:![](https://help.apptio.com/en-us/resources/images/studio_images/studioimages/studio_acme%20gl_table.png)
4. Replace the %253A with %3A and the .DateGoesHere with an appropriate time string.
5. Copy the segment of the URL after the -@C.Example: Relevant portion of the URL
   highlighted:![](https://help.apptio.com/en-us/resources/images/studio_images/studioimages/studio_acme%20gl_table.png)
6. Replace the %253A with %3A and the .DateGoesHere with an appropriate time string.

See the following section, Time for the Source, for more information in what can replace .DateGoesHere.

- Original - reference.apptio.com%253ACost+Transparency/Data/.DateGoesHere/Acme+GL
- Replacement - reference.apptio.com%3ACost+Transparency/Data/Jan:FY2018/Acme+GL

## Time for the source

When you craft the source for a CopyTable() operation, you must specify a valid time period. This
time period is injected into the .DateGoesHere when examining paths shown in the previous section.
It is not the current calendar date. Depending on the situation, you may need to use a
specific time period (for example: Jan:FY2018, September:2018, and so forth), or you may want
something dynamic that executes within the time period you currently have selected in the date
picker. You can specify time periods as:

## Non time-enabled project

If you are copying from a project which is not time enabled, then there is only one
eligible time period to get the path from Eon:FY2000. Here is an example of what you would do in
that case:

- Original - customer.com%3AProject+A/Data/.DateGoesHere/Example+Data+Set/
- Replacement - customer.com%3AProject+A/Data/Eon:FY2000/Example+Data+Set/

## Time-enabled project

If you are copying from a time-enabled project, you have two options:

1. Replace the .DateGoesHere with a valid date string as shown here:
   - Original - customer.com%3AProject+A/Data/.DateGoesHere/Example+Data+Set/
   - Replacement - customer.com%3AProject+A/Data/January:FY2011/Example+Data+Set/
2. Replace the .DateGoesHere with [wikitext](https://community.apptio.com/docs/DOC-5729 "(Opens in a new tab or window)") calling the [CurrentDate function](https://help.apptio.com/en-us/studio/formulas-and-functions/functions/currentdate.htm "(Opens in a new tab or window)") as shown here:
   - Original - customer.com%3AProject+A/Data/.DateGoesHere/Example+Data+Set/
   - Replacement -
     customer.com%3AProject+A/Data/<%=CurrentDate("ppp:ffff")%>/Example+Data+Set/

## Destination project

The destination project must be given in the format Domain Name:Project Name.

Example: customer.com:Project B.

Note:

The project name does not need to be encoded. If there are spaces in the name, they should
be retained and not substituted with encoding characters.

## Destination data set

The destination data set must be a raw table. It cannot be a transform table. The destination
table is provided as a quoted string, which is simply the name of the table. Spaces are allowed and
need not be encoded.

Example: Project B

Tip:

- Tables can be copied within the same project. In this case, simply enter the same project in the
  Destination Project parameter.
- If copying between two projects, the projects must reside in the same instance.

## Time period to copy to

This is the destination time period that you want to have the data applied to.

Different syntax may be required depending on the time scenario.

- If you are copying into a non time-enabled project, you would enter
  Eon:FY2000.NOTICE

  R12 requires that you have time configured so this only applies to
  R11.
- If you are copying into a time-enabled project and want to copy to a specific, static time
  period, you would hard code a value of Period:Fiscal Year (example: January:FY2011).
- If you are copying from a time-enabled project, and want to drive the destination time period
  based on the time period selected at the top of the report in the application, then you can use
  <%=CurrentDate("ppp:ffff")%>.

At this time, you cannot copy from a non time-enabled project and dynamically select a specific
destination month.

## Control edit permissions in the target

If you are copying from a source table that is editable, then the raw table will have a .PK
column when it is copied. Apptio will then recognize the table as editable. If you do not want the
target table to be editable, you would filter out the .PK column using the !LIMIT\_COLUMN syntax as
shown in here:

> `customer.com%3AProject+A/Data/<%=CurrentDate("ppp:ffff")%>/Example+Data+Set/!LIMIT_COLUMNS[][][{.PK}]`

## Configure a button to use CopyTable

To configure a Button in a report to use CopyTable:

1. Navigate to the report in TBM Studio (r12) or switch to Edit Mode (r11).
2. Add a button and name it appropriately.
3. Right-click the button, then select Properties.
4. Select Actions.
5. In the Server Action field, enter the CopyTable syntax.

Now, when a user clicks the button, the CopyTable function will be executed.

A button can be configured to execute multiple CopyTable functions by putting more than one
CopyTable() function in the Server Action field. Each function must be separated with a newline line
return.

Example: Suppose you want to copy a table from Project A to Projects B, C, and D. You
would enter the following CopyTable functions in the Server Action field:

> ```
> CopyTable("customer.com%3AProject+A/Data/<%=CurrentDate("ppp:ffff")%>/Example+Data+Set/","customer.com:Project
>           B","Example Data Set","<%=CurrentDate("ppp:ffff")%>")
> ```
>
> ```
> CopyTable("customer.com%3AProject+A/Data/<%=CurrentDate("ppp:ffff")%>/Example+Data+Set/","customer.com:Project
>           C","Example Data Set","<%=CurrentDate("ppp:ffff")%>")
> ```
>
> ```
> CopyTable("customer.com%3AProject+A/Data/<%=CurrentDate("ppp:ffff")%>/Example+Data+Set/","customer.com:Project
>           D","Example Data
>     Set","<%=CurrentDate("ppp:ffff")%>")
> ```

## Examples

- Example 1 - Copy a data set in Project A to a data set in Project B (R11 only, time
  disabled in both projects). Please note: the following example wraps, but it is all on a single
  line.

  ```
  CopyTable("customer.com%3AProject+A/Data/Eon%3A2000/Example+Data+Set/","customer.com:Project
                B","Example Data Set","Eon:2000")
  ```
- Example 2 - Copy a data set in Project A to a data set of the same name in Project B
  (specific times). Please note: the following example wraps, but it is all on a single
  line.

  ```
  CopyTable("customer.com%3AProject+A/Data/Jan%3AFY2019/Example+Data+Set/",
                  "customer.com:Project B","Example Data
                Set","January:FY2018")
  ```
- Example 3 - Copy a data set in Project A to a different name in the same project (dynamic
  time period). Please note: the following example wraps, but it is all on a single
  line.

  ```
  CopyTable("customer.com%3AProject+A/Data/<%=CurrentDate("ppp:ffff")%>/Original+Data+Set/",
                "customer.com:Project A","Another Data
                Set","<%=CurrentDate("ppp:ffff")%>")
  ```
- Example 4 - Copy an editable data set in Project A to Project B converting to
  non-editable - (R11 only, dynamic time period). Please note: the following example wraps, but it is
  all on a single
  line.

  ```
  CopyTable("customer.com%3AProject+A/Data/<%=CurrentDate("ppp:ffff")%>/Editable+Data+Set/!LIMIT_COLUMNS[][][{.PK}]",
                  "customer.com:Project A","Data
                Set","<%=CurrentDate("ppp:ffff")%>")
  ```
- Example 5 - Copy a report path in Project A to a data set in Project B (dynamic time
  period). Please note: the following example wraps, but it is all on a single
  line.

  ```
  CopyTable("customer.com:Test Project
                  A/Reports/<%=CurrentDate("ppp:ffff")%>/CostModels/Default/.View:Report
                  Name/Source/!GROUPBY[{Source.UID},{Source.Group}]/.Summary/!SORT[{Cost}|desc]/!LIMIT[0,2147483647]/!LIMIT_COLUMNS[{Source.UID},{Source.Group},{Cost}][][][orderByIncludeList]/","customer.com:Test
                  Project B","Table
                Name","<%=CurrentDate("ppp:ffff")%>")
  ```
- Example 6 - Copy a report path in Project A to a data set in the same project (dynamic
  time period). Please note: the following example wraps, but it is all on a single
  line.

  ```
  CopyTable("customer.com:Test Project
                A/Reports/<%=CurrentDate("ppp:ffff")%>/CostModels/Default/.View:Report
                Name/Source/!GROUPBY[{Source.UID},{Source.Group}]/.Summary/!SORT[{Cost}|desc]/!LIMIT[0,2147483647]/!LIMIT_COLUMNS[{Source.UID},{Source.Group},{Cost}][][][orderByIncludeList]/","customer.com:Test
                Project A","Table Name","<%=CurrentDate("ppp:ffff")%>")
  ```
