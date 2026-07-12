---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "EvalWiki function"
breadcrumb: []
source_path: "formulas-and-functions/functions/evalwiki.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# EvalWiki function

Applies to: TBM Studio 12.0 and later

The EvalWiki function is used to evaluate wiki links and dynamic text and format it for display
in a report. The function can be used only on reports. It cannot be used in data sets. For
additional information on using Wiki links, see Coding Links to other Reports in the Reporting
Guide.

## Where to use

This function can be used in:

- Formula columns in report tables
- Dynamic text

## Syntax

`EvalWiki(wikitext)`

## Arguments

*wikitext*

> A Wiki text string.

## Example 1: Using dynamic text on multiple reports

Assume you have a large block of text that you want to maintain in one place in the system and
place on multiple report pages. This can be done using EvalWiki. Make a one-row data set (e.g.:
TextBlocks) with a column named Text. Enter the block of text in the table cell.

On a report, add an HTML component that includes <%=EvalWiki(TextBlocks:Text)%>. This will
evaluate the wiki links and dynamic text in that value. Pulling the value in via a normal lookup
will not do this.

## Example 2: Adding links to the cells in a table

Assume you want to have multiple columns in a table on a report, and in those columns you want
links that will take the user to different places. This can be done using EvalWiki:

1. In TBM Studio, insert a new column in the table.
2. In the Edit Column dialog, check the Force Label option.
3. Enter a formula such as the
   following:

   ```
   =EvalWiki("[[/myObject/!FILTER[myColumn="""&myColumn&"""]/ myReport|click here
                 to see my report]]")
   ```

This will create a link that navigates to a filtered object report on the myObject object. It
will filter to only show the rows where myColumn on that object report equals the value of myColumn
in the current table.
