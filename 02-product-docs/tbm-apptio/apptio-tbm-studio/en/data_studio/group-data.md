---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "data_studio"
title: "Group data"
breadcrumb: []
source_path: "data_studio/group-data.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Group data

Applies to: TBM Studio 12.0 and later

If a table has multiple rows with the same values in a column, you can group the table by that
column. The data is aggregated based on the entries in the column. This can be useful when creating
charts and tables in reports.

![](../../resources/images/studio_images/studioimages/studio_steps_group.png)

To group data:

1. Add a Group step to the data transform.
2. Select one or more columns to group by.

Watch this demo video from Apptio Education Services: [Troubleshoot "Various
over Time" message](https://community.apptio.com/videos/1902 "(Opens in a new tab or window)"). Or, browse [all Apptio videos](https://community.apptio.com/docs/DOC-7714 "(Opens in a new tab or window)").

## Example

Assume you have the table shown below:

![](../../resources/images/studio_images/studioimages/studio/stu505.png)

You group the table by the Vendor column to get the table shown below:

![](../../resources/images/studio_images/studioimages/studio/stu506.png)

The table is now organized by Vendor, and a new .Count field has been added. The
.Count field shows how many entries are in each aggregated row. Because the AGI/LENI and LENI
vendors have different values in the Equipment column, the column displays the three
dots.

If there are empty fields in the column by which you grouped, a row will be displayed at the
bottom of the table that has the following values:

|  |  |
| --- | --- |
| In this column: | This value is displayed: |
| The Group By column | Blank |
| .Count | Number of blank rows |
| Numeric columns | Sum of all rows with blanks in the Group By column |
