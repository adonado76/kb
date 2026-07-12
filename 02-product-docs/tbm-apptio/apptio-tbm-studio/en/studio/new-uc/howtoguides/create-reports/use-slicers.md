---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Use Slicers for Interactive Filtering"
breadcrumb:
  - "TBM Studio"
  - "How-To Guides (Task-Based)"
  - "Create Reports"
  - "Report Basics"
source_path: "studio/new-uc/howtoguides/create-reports/use-slicers.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Use Slicers for Interactive Filtering

**Objective:** Add slicers to reports so end users can filter data without editing the
report

**When to use:** When you want users to explore data by selecting different categories,
time periods, or values; when different stakeholders need to see different subsets of the
same data

**Time estimate:** 10 minutes

## Understanding Slicers

Slicers are interactive filter controls that appear in your report. When a user clicks
values in a slicer, all linked tables and charts update instantly to show only the selected
data. This transforms static reports into exploratory tools.

**Key slicer concepts:**

- **Related values** (highlighted): Clicking these changes what's displayed
- **Unrelated values** (grayed): These have no data connection to current
  selections
- **Selected values**: Currently active filters

## Slicer types

- **List slicers:** Show text values as clickable items (most common)
- **Slider slicers:** Show numeric ranges with a draggable slider
- **Compact slicers:** Combine multiple slicers in a dropdown format to save space
- **Hierarchical slicers:** Allow drill-down through levels (e.g., Region > Country >
  City)

## Steps: Add a Basic Slicer

1. Open your report and **check it out**.
2. Click the **Report** tab, then click **Row Slicer**. A blank slicer placeholder
   appears, and the Slicer Configuration panel opens.
3. In the **Project Explorer**, find the field you want users to filter by. Good slicer
   candidates include Business Unit, Data Center, Expense Type, Cost Pool, Vendor.
4. Drag the field into the **Slice By** area of the Configuration panel. The slicer
   populates with values from your data.
5. Position the slicer in your report by clicking its title bar and dragging.
6. Resize the slicer by dragging its borders.

## Expected Results

- The slicer displays clickable values
- Clicking a value filters all tables and charts in the report
- Multiple values can be selected by Ctrl+clicking
- The reset icon (×) clears all selections

## Common Pitfalls

- **Too many values:** Slicers display a maximum of 250 values. If you have more, apply a
  filter to the slicer or use a compact slicer with a search.
- **Unrelated values confusion:** Users may wonder why some values are grayed out.
  Consider adding a note explaining that unrelated values have no data connection to current
  selections.
- **Performance with many slicers:** Reports with many slicers can become slow. Consider
  using compact slicers to consolidate filters.

**Parent topic:** [Report Basics](../../../../studio/new-uc/howtoguides/create-reports/report-basic.html)
