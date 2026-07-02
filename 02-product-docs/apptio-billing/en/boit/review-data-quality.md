---
source_system: "apptio-billing"
practice: "tbm"
language: "en"
doc_type: "boit"
title: "Review data quality"
breadcrumb: []
source_path: "boit/review-data-quality.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Review data quality

Quality data is important when you send business units a summary of the services they have
used. Billing Standard comes with a set of data quality reports that you should review on a regular
basis to ensure that your data is accurate.

To access the Billing Data Quality reports:

1. On the **Application** menu, click **Billing Standard**
   (see [Billing Standard menu](getting_started/boit-menu.html)).
2. On the **Report collection** menu, click **Billing Data
   Quality** .
3. On the bar at the top of the page, select a report in the collection. Report options include:
   - Configuration Summary report
   - Data Freshness report
   - Data Quality reports
     - Consumption Feed Quality report
     - Service Library Quality report
     - Model Quality report

**Configuration Summary report**

The **Configuration Summary** report includes key metrics for data
quality.

**Data Freshness report**

The Data Freshness report displays information about the data tables that have been uploaded
to .

You define the data freshness rules when you first upload a table into the application. You can
chose from a range of options. The data freshness rules are used to determine if data has been
updated within the timeframe specified. They do not schedule or perform data uploads. For a
description of the options, see "Data refresh cycles" in [Upload a data file](../studio/data_studio/upload-data-file.html "Applies to: TBM Studio 12.0 and later. TBM Studio accepts data from flat files in comma-, tab-, pipe-, tilde-, colon-, and semi-colon-separated formats. Before you can upload data, you must create a table where the data will be loaded, if it does not already exist.") .

**Data quality reports**

The data quality reports (Consumption Feed Quality, Service library Quality, and Model Quality) display information about the quality of the data in the application.

While data quality can vary, you should aim for data that conforms to the following guidelines.

- **Consumption Feed Quality** :
  - The row count should be within the range you would expect. Any significant changes should be
    explainable.
  - The unit of measure should match the service.
- **Data Freshness** - The data should have been refreshed based on the
  scheduled uploads.
- **Model Quality** - The change in the largest bill should be relatively
  small and the unallocated charges should be within acceptable limits based on the allocations
  defined in the model.
- **Distribution** - The proper invoice recipients should be defined.

**Consumption Feed Quality report**

The Consumption Feed Quality report displays information about record counts, units of measure, and published fields for each key data table in the application.

**Service Library Quality report**

The Service Library Quality report displays relationship and record detail information about the Service Library entries.

**Validate Service ID relationships**

Use the top section of the report to check that the relationships are valid. Use
the **Service ID** tab to check that each Service ID is unique.

**Ensure Service Names are unique**

Use the **Service Name** tab to check that each Service Name/Service
Offering combination is unique.

If there are duplicates, the number of duplicates will be displayed in the **Total
Error Count** column.

**Check record details**

Use the bottom section of the report to check for blank values in the Service Library entries. You can filter the table by required fields and optional fields.

**Model Quality report**

The Model Quality report displays information about the model allocations in the**Allocation Overview/Allocation Details** and **Configured Allocations**
sections, and the month-over-month variance for the service offerings in the**Variance** section. You can filter the report for each of the model metrics: Charge,
Billable Units, Cost, Budget, Forecast, Business Budget, Business Forecast and Planned Billable
Units. The report contents will vary based on the metric you select.

**Review allocation details**

What to look for:

- Allocations should be relatively consistent over time.
- Determine the cause of any significant allocation variations by looking at the Allocation by Object table and by drilling into the Allocation Details for an object.

**Review variance**

What to look for:

- Variations should be consistent and within an acceptable range.
- Investigate any outliers.
