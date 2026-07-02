---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "reports"
title: "Slicer component"
breadcrumb: []
source_path: "reports/slicers.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Slicer component

Applies to: TBM Studio 12.0 and later

When you add a table or chart to a report, you make decisions about the data displayed. But, what
if you would like the users to be able to filter the report to meet their specific needs? You can
give them this ability by adding slicers to the report. A sample report with two slicers is shown in
the following image. The slicers are on the left:

![](../../resources/images/studio_images/studioimages/reports/rep016.png)

You can filter the report by server type and cost. The following image shows the same report
filtered for UNIX and Greater Than 10,000. This topic and its subtopics focus on creating slicers.
Slicers only work with tables and charts created with the Ad Hoc Component Configuration dialog.
They do not work with legacy tables and charts.

![](../../resources/images/studio_images/studioimages/reports/rep017.png)

## Slicer tab

After adding a slicer to a report, you control its appearance and functionality using the Slicer
tab:

![](../../resources/images/studio_images/studioimages/reports/rep045.png)

## Key points

Below are key points about creating and using slicers:

- Slicers only work with Ad Hoc Query tables and charts. They do not work with legacy tables and
  charts.
- Slicers must be added to a report by the person creating the report. End users cannot create
  slicers when they are viewing a report.
- Only users assigned to an Admin or Analyst role can create slicers.
- Slicers added to a report are available to all users of the report.
- Slicers only display values from the current month even if annualized tables in the report
  display entries from the entire year.
- Values selected in two or more slicers are combined using AND logic. Values selected within the
  same slicer are combined using OR logic.
- Slicers that are not in a group box apply to all tables and charts in the report (even those in
  groups and nested groups). Slicers in a group box only apply to the tables and charts within the
  group box and any nested group boxes.
- Slicers on a tab apply only to the tables and charts on the same tab.
- Slicers are applied immediately as you edit tables and charts in reports.
- Slicers can be hierarchical.
- A slicer can display only 250 values. If there are more values, a message is displayed at the
  bottom of the slicer.
- If you print a report, the slicers are printed as well to preserve information about how the
  report has been filtered.

## Combining slicers in a compact slicer

If you want to place multiple slicers in a report, but you do not want them to occupy a large
area of the report, create a compact slicer. An example is shown in the following image. For more
information see [Compact
slicers](compact-slicers.htm "(Opens in a new tab or window)").

![](../../resources/images/studio_images/studioimages/reports/rep331.png)

## Specific slicer details

Slicers are described in detail in the following topics:

- [Add slicers](add-slicer.htm "(Opens in a new tab or window)")
- [Arrange slicer
  values](arrange-slicer-values.htm "(Opens in a new tab or window)")
- [Slicer states and
  values](slicer-states-and-values.htm "(Opens in a new tab or window)")
- [Filter slicers](filter-slicers.htm "(Opens in a new tab or window)")
- [Select a search
  option](select-search-option.htm "(Opens in a new tab or window)")
- [Compact slicer](compact-slicers.htm "(Opens in a new tab or window)")
- [Hierarchical
  slicer](hierarchical-slicers.htm "(Opens in a new tab or window)")
