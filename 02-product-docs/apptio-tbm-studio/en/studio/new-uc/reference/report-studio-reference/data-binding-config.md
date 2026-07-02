---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Data Binding Configuration"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Report Studio Reference"
  - "Report Components: Filters and Slicers"
source_path: "studio/new-uc/reference/report-studio-reference/data-binding-config.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Data Binding Configuration

**Source Field Configuration**

Slicers are populated from fields in perspectives. The field type determines slicer behavior:

|  |  |
| --- | --- |
| **Field Type** | **Slicer Behavior** |
| Text/Label | Creates list slicer with selectable values |
| Numeric | Creates slider slicer with range handles |
| Date | Creates list slicer with chronological ordering |
| Locked field | Provides more predictable results; required for global compact slicers |
| Unlocked field | , Produces satisfactory results |

**To add a slicer:**

1. From the Report tab, click Row Slicer
2. Drag a field from a perspective into the Slice By area
3. Configure appearance and behavior using the Slicer tab

**Sorting Options for Values**

Slicer values can be sorted in two ways via the Sort options on the Slicer tab:

|  |  |
| --- | --- |
| **Sort Option** | **Behavior** |
| By state | Groups values by state (Selected → Related → Unrelated), then sorts alphanumerically within each group |
| abc/123 | Sorts all values alphanumerically regardless of state |

**Default sorting by data type:**

- Text: Alphabetical
- Numbers: Ascending
- Dates: Chronological

Note: Users viewing the report cannot change the sort option—it is set by the report designer.

**Parent topic:** [Report Components: Filters and Slicers](../../../../studio/new-uc/reference/report-studio-reference/report-component-filters-slicers.html)
