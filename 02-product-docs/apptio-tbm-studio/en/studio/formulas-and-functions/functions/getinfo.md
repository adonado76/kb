---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "GetInfo function"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Formulas and functions"
source_path: "studio/formulas-and-functions/functions/getinfo.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# GetInfo function

**Applies to**: TBM Studio 12.0 and later

Returns a wide range of information about a project.

## Where to use

This function can be used in:

- Any field where you can enter a formula
- !NEWCOLUMN in a data path
- Formula columns in report tables
- Dynamic Text
- Apptio script

## Syntax

`GETINFO("attribute",["DomainName:ProjectName"])`

The quotes are required.

## Arguments

*attribute*

Can be one of the following:

- `"project.startDate"` (Returns the very first date of the project.)
- `"project.endDate"` (Returns the very last date of the project.)
- `"project.effectiveStartDate"` (Returns the set effectiveStartDate. Honors
  performance controls dates.)
- `"project.effectiveEndDate"` (Returns the set effectiveEndDate. Honors
  performance controls dates.)
- `“project.fyMonthIndex”` (Returns an index from 0 to 11 corresponding the which
  month in the fiscal year currentDete() is.
- `“project.isRealTimeCalculation”` (Returns ‘true’ is the project is in realtime
  mode, and ‘fals’ if it is precalculated.)
- `“project.request.currency.code”`(Returns the currency selected for the current
  session.)
- `“project.request.currency.exchange.rate.type”`(Returns the currency exchange
  rate type selected for the current session.)
- `“project.request.locale”`(Returns the locale selected for the current session.
  Defaults to the project locale, but it can be overridden by a user preference.)
- `“project.isRealTimeCalculation”`(Returns ‘true’ is the project is in realtime
  mode, and ‘fals’ if it is precalculated.
- `table.transformName`(Returns the name of the primary table backing the query, if
  any.)
- `table.lastMaterialRevision`(Similar to db.contents.lastMaterialRevision but
  giving back the last revision that required this table to be recalculated.)
- `db.contents.lastMaterialRevision` (The revision number of the last material
  change in the auditlog of a project. A change is material if it can affect numbers that have
  previously been calculated. The revision number is a .delimited list of the auditlog IDs of the last
  audit log entry in each audit log of the derived project stack for the project.)
- `db.contents.currentRevision` (The revision number of the last change the current
  project calculation is current as of. The revision number is a . delimited list of the auditlog IDs
  of the last auditlog entry in each auditlog of the project’s derived project stack.)

*DomainName:ProjectName*

Specifies the domain that contains the project and the name of the project. If specifying a
domain name, you must also specify the project name. They are part of the same argument. The
argument must be a hard coded label value enclosed in quotes. It cannot be a reference to another
column or formula.

## Return type

Label

## Notes

You can enter the following function in an HTML box to test if the function is working
correctly.

`<%=GETINFO("attribute",”<%=DomainName%>:<%=ProjectName%>”)%>`

## Example

The following example returns the start date for the ABC Company project in the docs.org
domain.

```
=GetInfo("project.startDate","docs.org:ABC
          Company")
```

`=GetInfo("project.startDate”)`
