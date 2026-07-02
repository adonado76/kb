---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "GROUPBY"
breadcrumb: []
source_path: "studio/data_studio/groupby.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# GROUPBY

The !GROUPBY function groups the entries in a table based on the value of a specific column. You
can perform multiple column grouping using the **Ribbon**.

!GROUPBY is one of the most widely used table functions. It takes a table and summarizes it based
on the values of a given column. Once grouped, you will no longer see single-line-item detail,
though there will be links that lead to detailed views.

Note: There is a limit of 15 columns in a GroupBy line for report table configurations.

There are three versions of the function:

- !GROUPBY[column name]
- !GROUPBY[column name,column name]
- !GROUPBY[column name|column name]

## !GROUPBY[column name]

This is the simplest version of the function. It groups the rows in a table by the column name
provided.

## Example

Assume you have the table shown in the figure below.

![Example](../../resources/images/it%20planning_images/groupby-1.png)

Below is the datapath used to generate the table:

```
docs.org:ABC Company/
Default/
.TableTransform:Data Center Services/
.Summary
```

Assume you want to group the table by data center. You add the !GROUPBY function to the datapath
as shown below.

```
docs.org:ABC Company/
Reports/
.DateGoesHere/
CostModels/
Default/
.TableTransform:Data Center Services/
!GROUPBY[Data Center]/
.Summary
```

The result is shown in the below figure. Note that the entries in the Data Center column are now
links that lead to detailed views for each data center. Also,Apptio adds a Count column indicating
the number of entries that make up each grouping.

![Data Center services](../../resources/images/it%20planning_images/groupby-2.png)

## !GROUPBY[column name,column name]

This version of the !GROUPBY function groups rows by two or more columns. Column names are
separated by commas. The order you enter the column names determines the order used to group the
rows and the order in which the columns are displayed.

## Example

Assume you have the table shown in below figure:

![Example](../../resources/images/it%20planning_images/groupby-4.png)

Below is the datapath used to generate the table.

```
docs.org:ABC Company/
Reports/
.DateGoesHere/
CostModels/
Default/
.TableTransform:Data Center Services - Subservice/
.Summary
```

Assume you want to group the rows by Service, then Sub Service. Add the !GROUPBY function to the
datapath as shown below.

```
docs.org:ABC Company/
Reports/
.DateGoesHere/
CostModels/
Default/
.TableTransform:Data Center Services - Subservice/
!GROUPBY[Service,SubService]/
.Summary
```

The result is shown in the below figure. Note that the entries in the Data Center column now
show{Various}. This indicates that there are two or more data center values for each row. In our
example, this would be Seattle and Chicago. Again, Apptio adds a Count column. Table after grouping
by Service and Sub-Service:

![grouping by Service and Sub-Service](../../resources/images/it%20planning_images/groupby-5.png)

You can perform this type of GROUPBY using the **Ribbon**:

1. Select the table to be grouped.
2. Select the **Data** tab in the **Ribbon**.
3. Select the **Group** icon and select the field(s) to be used for
   grouping.

## !GROUPBY[column name|column name]

Inherent in Apptio is the ability to drill down to successive levels of detail in reports by
clicking links. When you drill down, effectively you are filtering a report by the selected link.
This version of the !GROUPBY function checks to see if the datapath has been filtered by a given
column because of a drill down. If it has not, it groups by the first column listed. Otherwise, it
checks the next column in the list. If rows are grouped by the first column, the second column is
ignored.

This can be useful when combined with reports that are saved to apply ‘Even if filtered some
other way’. Note that this syntax cannot be practically used with some chart components,
specifically components that require you to specify the X Axis column name. This functionality has
not yet been widely used.

**Example**

The table shown in the below figure has been filtered by Data Center as a result of a drill
down.

![Filtered by Data Center](../../resources/images/it%20planning_images/groupby-6.png)

The datapath for the table is shown below.

```
docs.org:ABC Company/
Reports/
.TableTransform:Data Center Service - Subservice/
!FILTER[{Data Center}="Seattle"]/
.Summary
```

You now modify the datapath as shown below to group the results by Data Center if they have not
already been filtered, or by Service if they have been filtered.

```
docs.org:ABC Company/
Reports/
.DateGoesHere/
CostModels/
Default/
.TableTransform:Data Center Services - Subservice/
!FILTER[{Data Center}="Seattle"]/
!GROUPBY[Data Center|Service]/
.Summary
```

The result is shown in the below figue:

![Result](../../resources/images/it%20planning_images/groupby-7.png)

If we take the original unfiltered table shown in Figure G below and apply the same datapath, we
get the result shown in the below figure. Unfiltered table:

![](../../resources/images/it%20planning_images/groupby-8.png)

Unfiltered table grouped by Data Center:

![Unfiltered table grouped by Data Center](../../resources/images/it%20planning_images/groupby-9.png)

**Parent topic:** [Editable tables: Accommodating user input](../../studio/data_studio/editabletables.html "Applies to: TBM Studio 12.6 and later")
