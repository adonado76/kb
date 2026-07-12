---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "reports"
title: "Slicer states and values"
breadcrumb: []
source_path: "reports/slicer-states-and-values.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Slicer states and values

Applies to: TBM Studio 12.0 and later

## Slicer states

The color of the values in a slicer indicates their state:

![](../../resources/images/studio_images/studioimages/reports/rep018.png)

Related values are related to the data displayed in the report. When you select a related value,
it impacts the display of the data. Unrelated values are not related to the data currently displayed
in the report. When you select an unrelated value, it does not impact the display of the data if
selected.

Clicking a value in a slicer toggles the selected/deselected state. To select more than one
value, hold down the Ctrl key and click the values.

Selections in one slicer can change the state of values in other slicers to Unrelated.

You can clear all selections in a slicer by clicking the reset icon ![](../../resources/images/studio_images/studioimages/icons/filter%20reset.png) in the slicer
header.

## Creating a default set of values

You can create a default set of values for a slicer by selecting values in a slicer and saving
the report. When a user opens the report, the slicers display with default set of values
selected.

## Sorting slicer values

There are two options for sorting the values in a slicer:

- By state - Values are grouped by state (Selected, Related, Unrelated) and then sorted
  alphanumerically.
- abc/123 - Values are sorted alphanumerically. State is ignored.

Set the values using the Sort options on the Slicer tab.

Users viewing the report cannot change the sort option.

By default, values in the three sections (Selected, Related, Unrelated) are sorted as follows:

- Text - alphabetical
- Numbers - ascending
- Dates - chronological
