---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Data Binding Configuration"
breadcrumb:
  - "Reference"
  - "Report Studio Reference"
  - "Report Components: Filters and Slicers"
  - "Data Binding Configuration"
source_path: "SSWRJM/studio/new-uc/reference/report-studio-reference/data-binding-config.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Data Binding Configuration

Source Field Configuration

Slicers are populated from fields in perspectives. The field type determines slicer behavior:

| Field Type | Slicer Behavior |
| --- | --- |
| Field Type | Slicer Behavior |
| Text/Label | Creates list slicer with selectable values |
| Numeric | Creates slider slicer with range handles |
| Date | Creates list slicer with chronological ordering |
| Locked field | Provides more predictable results; required for global compact slicers |
| Unlocked field | , Produces satisfactory results |

To add a slicer:

1. From the Report tab, click Row Slicer
1. Drag a field from a perspective into the Slice By area
1. Configure appearance and behavior using the Slicer tab

Sorting Options for Values

Slicer values can be sorted in two ways via the Sort options on the Slicer tab:

| Sort Option | Behavior |
| --- | --- |
| Sort Option | Behavior |
| By state | Groups values by state (Selected → Related → Unrelated), then sorts alphanumerically within each group |
| abc/123 | Sorts all values alphanumerically regardless of state |

Default sorting by data type:

- Text: Alphabetical
- Numbers: Ascending
- Dates: Chronological
