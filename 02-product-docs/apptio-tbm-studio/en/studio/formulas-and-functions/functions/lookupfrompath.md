---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "LookupFromPath function"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Formulas and functions"
source_path: "studio/formulas-and-functions/functions/lookupfrompath.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# LookupFromPath function

**Applies to**: TBM Studio 12.0 and later

Retrieves values from any table in any domain and project. If there are multiple matches, the
function returns {VARIOUS} for text columns and a sum for numeric columns.

Note: This function will not work in data sets if the function references a report component in the
same project.

## Where to use

This function can be used in formula columns in report tables.

Note: This function cannot be used in data sets.

## Syntax

`LookupFromPath("lookup_table_path",source_column,matching_column,lookup_value_column)`

## Arguments

*lookup\_table\_path*

Full path to the source table. Note that you must put quotes around the path if it is a literal
string.

For example:

`"abccompany.com:test/Data/September:2010/line items"`

You can build the path from other functions such as DomainName, ProjectName, and CurrentDate. See
the Examples section below.

*source\_column*

The column in the current table that links to the column in other table.

*matching\_column*

The column in the other table that links to the current table.

*lookup\_value\_column*

The column in the other table that will supply the values.

## Return type

The value of the lookup column. If there are multiple matches, the function returns {VARIOUS} for
text columns and a sum for numeric columns.

## Examples

- Below is an example of a simple path entered directly, and an equivalent path entered using
  functions. Literal strings entered in the path must be surrounded by quotes. The & sign is used
  as a concatenation operator.

  ```
  “apptio.com:BankDemo/Data/January:2010/GL Actuals”
                DomainName()& “:” & ProjectName() & “/Data/” & CurrentDate(“MMMM:yyyy”) &
                “/<some table name here>”
  ```
- Below is an example of a complex path using the DomainName, ProjectName, and CurrentDate
  functions.

  ```
  DOMAINNAME() & “:” & PROJECTNAME() &
                “/Reports/” &
  CURRENTDATE(“MMMM:yyyy”) &
                  “/
  CostModels/
  Default/
  .View:Product Capacity Owner/
  Business
                  Domains/
  .WithDefaultMetric-Planned Price/
  .DrillTo/
  <%/.DrillTo/<%=ObjectName%>/
  !FILTER[All IT
                  Products.ProductID=<%=ProductID%>]/
  !FILTER[All
                IT Products.Is Adjustment=%22No%22]/
  .LineItemsTable"
  ```

See also:

- [IPLookup](iplookup.htm "(Opens in a new tab or window)")
- [Lookup and
  Lookup\_Wild](lookupandlookup_wild.htm "(Opens in a new tab or window)")
- [LookupEx](lookupexandlookupex_wild.htm "(Opens in a new tab or window)")
- [LookupMetric](lookupmetric.htm "(Opens in a new tab or window)")
- [LookupObjectTotalAllocated](lookupobjecttotalallocated.htm "(Opens in a new tab or window)")
- [LookupObjectTotalValue](lookupobjecttotalvalue.htm "(Opens in a new tab or window)")
- [LookupObjectUnitAllocated](lookupobjectunitallocated.htm "(Opens in a new tab or window)")
- [LookupObjectUnitValue](lookupobjectunitvalue.htm "(Opens in a new tab or window)")
