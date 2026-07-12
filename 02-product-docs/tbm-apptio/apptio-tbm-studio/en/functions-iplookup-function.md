---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "IPLookup function"
breadcrumb:
  - "Reference"
  - "Formulas and functions"
  - "IPLookup function"
source_path: "SSWRJM/studio/formulas-and-functions/functions/iplookup.html"
images:
  - "03-media/apptio-tbm-studio/aug032.png"
  - "03-media/apptio-tbm-studio/aug033.png"
  - "03-media/apptio-tbm-studio/aug035.png"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# IPLookup function

*Applies to : TBM Studio 12.0 and later*

Finds an IP address in a specified source column in the current table and searches for an IP address in a specified column of a lookup table. IPLookup returns the value in the corresponding specified replacement column of the lookup table for the last match it finds. IP addresses can be entered individually or use masks and ranges.

## Where to use

- Data sets
- Formula columns in report tables

## Syntax

IPLookup(source_column,lookup_table,matching_column,replacement_column,"default_value")

## Arguments

source_column

The column in the current table containing the IP address for which you want to search. Note: only enter the column name, not the table name.column name.

lookup_table

The name of the table containing the return values.

matching_column

- Specific IP addresses such as 99.9.1.4.
- IP address masks such as 99.1.0.0 where 0.0 will match any set of numbers. For example, 99.1.0.0 would include IP addresses such as 99.1.5.6, 99.1.9.234, and 99.1.43.144.
- IP address ranges such as 99.1-99.6 which will match any IP ranges between the two values. For example, the range 99.1-99.6 would include IP addresses such as 99.1.1.4, 99.3.1.54, and 99.6.6.6.

replacement_column

The column in the lookup_table that supplies the return value.

default_value

The value to return if no match is found. The value must be in quotes.

## Return type

The type of either replacement_column or default_value , whichever applies.

## Example

Assume you have the following table called Machines that lists machines and their IP addresses:

Based on the IP address, you want to fill in the Location column. You have the following table called Locations that can supply the locations:

You enter the following in the Value Override field for the Location column in the Machines table:

```
=IPLookup(IP Address,Location,IP
          Address,Location,"Unknown")
```

The result is:

- The first two machines have an IP address of 99.9.1.4 and are assigned to Altanta, not New York. That is because in the Locations table, the last reference for IP address 99.9.1.4 is Atlanta.
- 77.1.2.3 is not listed in the Locations table, so the value Unknown is returned.

- Lookup and Lookup_Wild
- LookupEx
- LookupFromPath
- LookupMetric
- LookupObjectTotalAllocated
- LookupObjectTotalValue
- LookupObjectUnitAllocated
- LookupObjectUnitValue
