---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "data_studio"
title: "Partition data by date"
breadcrumb: []
source_path: "data_studio/partition-data-by-date.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Partition data by date

Applies to: TBM Studio 12.0 and later

When you bring data into the application, you often bring it in to a specific period and year.
For example, utilization data and cloud services data usually are updated monthly. However, there
are times when you will bring data into the application that is date stamped and you will want to
distribute that data across periods based on the dates. An example would be a general ledger.

Most often you will want to distribute the data based on the transaction date. When you are
working with date-stamped data, use the Date Partition function to distribute the data to the
correct time periods. Time-stamped data is displayed based on the period selected in the date picker
at the top of the application window:

![](../../resources/images/studio_images/studioimages/studio/stu305.png)

When you date partition a table, one or more columns are added to the table that contain the
values for the selected period.

## Data formats

Time-stamped data usually takes one of two formats: row based or column based. Sometimes, it may
include both. A typical example of row-based data is a general ledger like the one shown below.
There is one column that contains the dates, and there is a date for each row:

![](../../resources/images/studio_images/studioimages/studio/aug103.png)

Column-based data includes a column for each month in a year. Budget and salary data is often
presented in this format. An example of column-based budget data is shown below:

![](../../resources/images/studio_images/studioimages/studio/aug104.png)

Less common is time-stamped data that also includes dates in rows and columns. Service desk
tickets are an example. Start and end dates would be represented in rows, and cost per month would
be represented in columns.

## Row-based data

Row-based data usually includes one or more columns with dates. For example, service desk ticket
data might include start-date and end-date columns. A table like the one shown in the following
image, when partitioned on the Baseline Start Date column, would look like the table shown in the
subsequent image:

![](../../resources/images/studio_images/studioimages/studio/stu507.png)

![](../../resources/images/studio_images/studioimages/studio/stu508.png)

To partition this type of data:

1. Select the Dates are represented in rows option.
2. Select the Start Date and End Date columns.

The application groups the rows into the correct periods.

## Column-based data

When you are working with column-based data, usually the data includes a column for each period
in a fiscal or calendar year. The column headings can be any valid date format such as Jan, Jan
2016, or P1 Jan 2016. A table like the one shown in the following image, when date partitioned,
would look like the table in the subsequent image:

![](../../resources/images/studio_images/studioimages/studio/stu509.png)

![](../../resources/images/studio_images/studioimages/studio/stu510.png)

To partition this type of data:

1. Select the Dates are represented in columns option.
2. In the Interpret Year As column, select either Fiscal Year or **Calendar
   Year**.
3. In the New Column Prefix field, enter a label you want to be added to the
   column label.For example, if the columns in the original table are labeled Jan, Feb, etc., and you
   enter Amount in the New Column Prefix field, the columns in the
   date-partitioned table would be labeled Amount Jan, Amount
   Feb, etc.
4. Select the column sets that should be used to partition the data. If the data set includes two
   or more sets of columns, you can partition the data by each set. For example, assume you have a data
   set that includes monthly columns for both cost and budget as shown in the following image:

   ![](../../resources/images/studio_images/studioimages/studio/stu306.png)
5. You can choose to partition the data by Cost, Budget, or both. If you choose
   Cost, the result would look like the following image:

   ![](../../resources/images/studio_images/studioimages/studio/stu307.png)

   If you choose
   Budget, the result would look like the following image:

   ![](../../resources/images/studio_images/studioimages/studio/stu308.png)

   And, if you choose
   both Cost and Budget, the result will look like the
   following image:

   ![](../../resources/images/studio_images/studioimages/studio/stu309.png)
