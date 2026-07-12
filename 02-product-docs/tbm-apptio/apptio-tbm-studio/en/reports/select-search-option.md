---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "reports"
title: "Select a search option"
breadcrumb: []
source_path: "reports/select-search-option.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Select a search option

Applies to: TBM Studio 12.0 and later

If there are many values in a slicer, users can limit the entries by using the auto search box at
the top of the slicer. In the following image, ABC has been entered and only values beginning with
ABC are shown. When you add a slicer to a report, you can set how the auto search box will work.

![](../../resources/images/studio_images/studioimages/reports/rep048.png)

## Two search options

There are two search options available from the Slicer tab.

- Contains - Finds all values that include the entered characters. If the user types abc,
  the filter will find abcefg, defabc, and defabcefg but not abdc or adbc.
- Starts With - Finds all values that begin with the entered characters. If they user types
  abc, the filter will find abcefg and abc, but not dabc or 1abc.

Select the option you think will best meet the needs of users. Users cannot change the search
option when working with the slicer.

## Hierarchy search

Hierarchy search finds all values that begin with the entered text plus one additional character.
It then creates a group entry for each. Hierarchy search only can be applied to slicers based on
fields locked to an object. Hierarchy slicers apply to all components in a report, or if contained
within a group, to all components in the group, including other slicers.

To illustrate how a hierarchy search works, assume you have the table shown in the following
image:

![](../../resources/images/studio_images/studioimages/reports/rep039.png)

You add a slicer based on the ID field with a Starts With search strategy as shown in the
following image. The slicer contains an entry for each match:

![](../../resources/images/studio_images/studioimages/reports/rep040.png)

If you enter the text ABC in the search field and select a value such as ABC100, you get the
results shown in the following image. Each slicer entry represents a single value in the table:

![](../../resources/images/studio_images/studioimages/reports/rep041.png)

If you switch the search strategy to Group Search, you get the results shown in Figure E
below. Note that each entry in the slicer represents a group of values. ABC1, when selected,
displays the values ABC100, ABC110, and ABC120:

![](../../resources/images/studio_images/studioimages/reports/rep042.png)

To create a hierarchy slicer:

- Right-click an object-locked field in a custom perspective and select Edit 'name'.
- In the Edit Published Field dialog, select the Represents a hierarchy code
  option.
