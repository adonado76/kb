---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "reports"
title: "Compact slicers"
breadcrumb: []
source_path: "reports/compact-slicers.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Compact slicers

Applies to: TBM Studio 12.0 and later

If you want to place multiple slicers in a report, but you do not want them to occupy a large
area of the report, create a compact slicer. Compact slicers can be local or global. The example
shown in the following image includes a local compact slicer and a global compact slicer:

![](../../resources/images/studio_images/studioimages/reports/rep331.png)

## Types of compact slicers

There are two types of compact slicers: local and global.

- Local - A local compact slicer has the same properties as a single slicer. It can use
  both locked and unlocked fields. Selections made in the slicers by users are not saved.
- Global - A global compact slicer has the same properties as a global filter.
  - Apply to all object-based tables and charts in a report.
  - Only fields locked to an object can be included in a global compact slicer.
  - Global compact slicers can include multiple fields. The fields must be from custom or
    application perspectives. You cannot use fields from the Data, Calculations, or Time
    perspectives.
  - Individual users can save their own global compact slicer filter settings.
  - Saved settings remain in place when the user logs out of the application and logs back in.
  - Changes made to a global compact slicer in one report apply to all reports that include the
    slicer.
  - Different global compact slicers can be added to different sets of reports.
  - If you email a report, the global compact slicer settings are saved with the report.

Global compact slicers are intended to replace global filters. Whenever possible, use global
compact slicers instead of global filters.

## Create a compact slicer

To create a compact slicer:

1. From the Report tab, click Compact Slicer.
2. Decide if the slicer will be local or global, and select the appropriate option on the
   Compact Slicer tab.NOTICE

   If you create a local compact slicer, and then change it
   to a global compact slicer, unlocked fields will be removed from the configuration panel and their
   corresponding slicers will be removed from the compact slicer.
3. In the Compact Slicer Configuration panel, drag fields into the Slice By area.When you
   add a field, a corresponding slicer is added to the compact slicer.

## Filter a compact slicer

You can apply filters to each of the slicers in a compact slicer by selecting a slicer and
creating the filters in the Slicer Configuration dialog. Users will not be able to modify the
filters. For more information, see [Filter slicers](filter-slicers.htm "(Opens in a new tab or window)").

## Select slicer values

You can select slicer values in a compact slicer by expanding the slicer. The values selected are
displayed in the line below the slicer name as shown in the following image. If there are more
values than can be displayed on the line, you can hover the mouse pointer over the line and a pop-up
will be displayed that lists all the vales. Users can modify filters created this way.

![](../../resources/images/studio_images/studioimages/reports/rep332.png)

## Format a compact slicer

As with standard slicers, you can format a compact slicer using the options on the **Compact
Slicer** tab.

To format a slicer:

1. Click the slicer in the compact slicer.
2. Click the Compact Slicer tab.
3. Select the formatting options.
   - For information on Search options, see [Select a search option](select-search-option.htm "(Opens in a new tab or window)")
   - For information on Sort options, see [Sort slicer values](slicer-states-and-values.htm "(Opens in a new tab or window)")
