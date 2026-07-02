---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Cloud Daily/Hourly Reports - Extending or Changing (12.6 and later)"
breadcrumb: []
source_path: "cost-transparency/reports-v104/clouddailyhourlyreportsextendingchanging12.6.html"
images:
  - "resources/images/ct_images/clouddailyhourlyreportsextendingchanging12.6_1.png"
  - "resources/images/ct_images/clouddailyhourlyreportsextendingchanging12.6_2.png"
  - "resources/images/ct_images/clouddailyhourlyreportsextendingchanging12.6_3.png"
  - "resources/images/ct_images/clouddailyhourlyreportsextendingchanging12.6_4.png"
  - "resources/images/ct_images/clouddailyhourlyreportsextendingchanging12.6_5.png"
  - "resources/images/ct_images/clouddailyhourlyreportsextendingchanging12.6_6.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Cloud Daily/Hourly Reports - Extending or Changing (12.6 and later)

- Applies to: Cloud on Costing Standard and Cloud Business Management on TBM Studio 12.6 and
  later

For information about the Daily/Hourly reports on TBM Studio 12.5.x and earlier, see [Cloud Daily/Hourly Reports - Extending or
Changing (12.5 and earlier)](clouddailyhourlyreportsextendingchanging12.6.html)

## Overview

The Daily/Hourly reports are built on a data format that enables rapid and efficient storage and
queries on very high-volume data sets, such as very granular cloud bills like the AWS Cost and Usage
Report (CUR). As a result, extending the schema of the data sets involved and modifying reports
built on those data sets requires some configuration.

Daily/hourly data is stored in a different format, separately from other Apptio data. The object
on which reports are built is called dbr\_daily, which can be found in the tables section of TBM Studio, but, because of the extremely high volume of data and the new data format, certain actions
cannot be performed:

- You will not be able to see the data in TBM Studio.
- You cannot add items to the transform pipeline (with the exception explained in the "Adding new,
  custom attributes" section, below).
- You cannot add transforms to the data set.

## Extending the daily/hourly schema

To use out-of-the-box attributes (the quickest way to see your organization’s specific data):

1. Map from the columns in the provider bills, such as Accounts or Tags, to the out-of-the-box CBM
   attributes.For example, if you have a tag user called Owner, map that tag to the existing System
   Owner attribute.
2. For more information, see [Cloud
   mapping](../configuration/cloudmapping.html "The cloud mapping feature (sometimes known as tag mapping provides the ability to map cloud metadata (such as tags and accounts) to attributes in Apptio, such as Business Unit, Application, etc. Mapping cloud data will allow you to see not only what cloud services are consumed, but also to tag cloud billing data with information that helps you understand your cloud spending and ownership.").

Add custom attributes to the Cloud Mapping pipeline step
:   The first step is to extend the list of Destination Columns that appear in the Cloud Mapping
    pipeline step for AWS and Azure. The default Destination Columns list is shown below.

    ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/clouddailyhourlyreportsextendingchanging12.6_1.png)

    1. In TBM Studio, navigate to Tag Mapping Reference Data.

       ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/clouddailyhourlyreportsextendingchanging12.6_2.png)
    2. Export the table to a .csv file and add rows with the new fields you want to add to the
       schema.
    3. Check the table out and upload the .csv file that was updated in the prior step.
    4. Check in your changes.
    5. Go to the Cloud Mapping pipeline step on AWS Cost and Usage Report Raw or Azure EA Bill Raw.
       Your new fields will appear in the Destination Column drop-down.
    6. Create mapping rules for those new columns in the Cloud Mapping pipeline step.

    Note: The Cloud Mapping changes need to be checked in and promoted to production
    before those mappings take effect in the daily/hourly data.

Add custom attributes to the dbr\_daily object
:   Now that you can map attributes from the bill to your new destination columns, you will also
    need to ensure that those new columns can be exposed in Report Editor. This is done by adding your
    new columns to the schema of the dbr\_daily object.

    1. In TBM Studio, go to the dbr\_daily object and add a new column to the formula step, ensuring
       that the column name matches the name you added to the Tag Mapping Reference Data.

       ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/clouddailyhourlyreportsextendingchanging12.6_3.png)
    2. Save the changes. The new column is now available for reporting.

Modify report components (pivots, slicers, charts, and tables)
:   You can modify existing Daily/Hourly report components as you do in normal reports, with some
    specific constraints and nuances.

    To add a non-numeric attribute to a pivot, chart, or other
    component:

    1. Select the component in question.
    2. Navigate to the Daily/Hourly perspective.
    3. Find the attribute you want to add to the component and drag it to the appropriate field. In
       this example, Environment was added to the Pivot on the Daily Transparency report.

       ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/clouddailyhourlyreportsextendingchanging12.6_4.png)
    4. Save the report

    Note: Because of the granular time-series nature of numeric fields in the Daily/Hourly reports,
    the following steps are required. To be used in reporting, numeric fields must already exist either
    in the Daily/Hourly perspective or in the dbr\_daily object.

    To add or modify numeric fields
    in a chart or table:

    1. Find the numeric field you want to use. This example uses Usage Qty on the dbr\_daily object.

       ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/clouddailyhourlyreportsextendingchanging12.6_5.png)
    2. Drag the numeric field into the **Values** column.

       ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/clouddailyhourlyreportsextendingchanging12.6_6.png)
    3. Remove any unnecessary numeric fields from the Values column and update the chart formatting as
       necessary.
    4. Ensure the proper time granularity column is in place.In many cases, the report components will
       need to know what time grain is to be displayed. For example, a column chart could be configured to
       show cost daily or hourly. The Granularity\_DD and Granularity\_HH columns are used for this
       granularity control. In genera,l only use Granularity\_HH in charts that you want to include hourly
       details. For all others, include Granularity\_DD in the **Axis** field (where days are an
       attribute to be displayed) or in the **Filter** field (where days are not an attribute to be
       displayed).
    5. Save your changes.
    6. Cost is now replaced with Usage Qty in the Daily Invoice Cost chart. Repeat steps 1-5 for the
       following numeric fields.
       - dbr\_daily object
         - **Cost** – The cost associated with the cloud service consumed. (This is currently the
           unblended cost in the Detailed Billing Report.)
         - **Rate** – The unit rate for the cloud service consumed. This field is calculated by dividing
           Cost by the Usage Qty. Note that because of the high number of unit rates in the cloud bill, this
           field will give unusual results when a chart or table is not filtered to a single unit rate.
         - **Usage Qty** – The quantity of units consumed for the cloud service. For example, for EC2
           compute services, this field will include the number of instance hours consumed.
       - Daily/Hourly perspective
         - **Cloud Invoice Cost MTD** – The total cost for the month being analyzed.
         - **Cloud Invoice Cost Today** – The total cost for the last full day. Currently, Daily/Hourly
           reports don't report on partial days.
         - **Cloud Invoice Cost Yesterday** – The total cost for the day prior to the last full
           day.
         - **Current Month Cloud Invoice Forecast** – The projected end of month spend for the month
           being analyzed. This is calculated through a linear projection of costs incurred in the month
           to-date. For prior months this will be equal to the actual costs incurred for that month.
         - **Daily Cloud Invoice Cost** – This is equivalent to the Cost field on dbr\_daily.
         - **Prev Month Invoice Cost** – The total cost of for the prior month.
         - **Prev Month Invoice Cost MTD** – The total cost for the prior month up to the same day as is
           measured for the current month.
    7. Save your changes.
