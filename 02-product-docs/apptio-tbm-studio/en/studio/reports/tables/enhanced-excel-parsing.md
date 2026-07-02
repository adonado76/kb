---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "How Enhanced Excel Parsing Works in Apptio"
breadcrumb: []
source_path: "studio/reports/tables/enhanced-excel-parsing.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# How Enhanced Excel Parsing Works in Apptio

Note: As of release 12.11.16, the Enhanced Excel Parsing feature is automatically enabled for new
customers. There is currently no change for existing customers. Further information will be provided
in upcoming updates.

## What to Expect When Uploading Files

When uploading files to Apptio, you can expect the following:

- The file will be parsed and the data will be extracted as raw instead of any formatting applied
  in excel.
- Data in the table transform will be populated as per raw values defined in Apptio spec.
- If there are any issues with the table transform steps or need data in specific format please
  check the help doc to apply right formatting.
- If the Excel file contains any special formatting or macros, it may not upload correctly and
  formatting needs to be applied as part of table transform steps if required.

**Troubleshooting Tips**

If you encounter any issues with transform steps, please try the following:

- Check table transform steps and correct the formatter if data is not in requested format.
- Verify that the file does not contain any special formatting or macros.
- Contact our support team for assistance.

Benefits of moving to new spreadsheet parser.

- **Standardized Excel Data Formatting:** The new parser establishes a consistent format for
  Excel data.
- **Improved Numerical Precision:** It reads raw numerical values directly, bypassing any
  formatting that could alter the original data, resulting in more accurate computations.
- **Consistent Date & Time Representation:** All date and time values are converted to
  epoch format, eliminating the need for complex and error-prone conversions.

## FAQs

Q: **What spreadsheet formats does Apptio support ?**

A: Apptio supports XLSX, XLS

Q: **What if I encounter issues with uploading or parsing excel files?**

A: Contact our support team for assistance.

## What is changing with new excel parser vs old

|  |  |  |  |
| --- | --- | --- | --- |
| Formats | Current spreadsheet parser | New spreadsheet parser | Functions to convert from new parser format to old format |
| General | Hello | Hello | No Action Needed |
| Number | 1 | 0.99999999 | =Round({Column},0) |
| Currency | $10.50 | 10.5 | =Currency({Column},"#,##0.00") |
| Accounting | 34,343.00 | 34343 | =NumberFormat({Column},"#,##0.00") |
| **Date: Return epoch time** | **1-Jan-24** | **1704047400 (epoch)** | =DateFormat({Column},"d-MMM-yyyy") |
| **Time: (Epoch of 1/1/1970 + time in cell)** | **12:30 PM** | **45000 (epoch of 1/1/1970:12:30 )** | =DateFormat({Column}-25569)\*86400,"M/d/yy")},"hh:mm") Excel stores dates as sequential serial numbers, starting with 1 representing January 1, 1900. Unix epoch, begins at January 1, 1970, 00:00:00 UTC. To convert from an Excel date to Unix epoch seconds (DateFormat requires this) Calculate the number of days between the Excel date and the Unix epoch start date (25569) Convert the number of days into seconds (\*86400) |
| Percentage | 10% | 0.1 | =NumberFormat({Column},"#.00%") |
| Fraction | 1/2 | 0.5 | Make the column text in excel |
| Scientific | 9.88E+11 | 9.87654E+11 | Make the column text in excel (this is if you actually want the scientific notation to appear so in Apptio) |
| Text | Clouds drift, whispers echo, time. | Clouds drift, whispers echo, time. | No Action Needed |
| Special | (91987) 654-3456 | 9.19877E+11 | Make the column text in excel, or write a formula to add text where needed IE ="("&Left(Column,5)&") "&Mid(Column,5,3)&"-"&Right(Column,4) |
| Custom | 43333.45 | 43333.44555 | Make the column text in excel, or write a formula to format as desired |
| Formula | 100 | 100 | No Action Needed - Displays the results of the formula |

How time and date will behave with change in format

1. Date - If the date value coming into Apptio is a date type from excel, it will need to be
   converted to Unix epoch.

   Excel stores dates as sequential serial numbers, starting with 1
   representing January 1, 1900.   
   Unix epoch, begins at January 1, 1970, 00:00:00 UTC.
     
   To convert from an Excel date to Unix epoch seconds (DateFormat requires this)
     
   Calculate the number of days between the Excel date and the Unix epoch start date
   (25569)   
   Convert the number of days into seconds
   (\*86400)

   `=DateFormat(({Column}-25569)*86400,"M/d/yy")`

**Parent topic:** [Table Upload component](../../../studio/reports/table-report-upload-component.html "Applies to: TBM Studio 12.9.3 and later")
