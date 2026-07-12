---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Filter Behavior"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Report Studio Reference"
  - "Report Components: Filters and Slicers"
source_path: "studio/new-uc/reference/report-studio-reference/filter-behavior.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Filter Behavior

**Default Value Configuration**

You can establish default filter selections that appear when users first open a report:

1. Select the desired values in the slicer
2. Save the report

When users open the report, the slicers display the default values selected. Users can modify
selections during their session.

**For Global Compact Slicers:**

- Individual users can save their own filter settings
- Saved settings persist across logout/login
- Changes in one report apply to all reports using the same global compact slicer

**Slicer States and Visual Feedback**

Slicer values display in three states, indicated by color:

|  |  |  |
| --- | --- | --- |
| **State** | **Description** | **User Interaction** |
| Selected | Currently active filter values | Highlighted; click to deselect |
| Related | Values related to current data display | Normal appearance; will filter data if selected |
| Unrelated | Values not related to currently displayed data | Grayed out; selecting has no effect |

**State behavior:**

- Selections in one slicer can change states in other slicers (making some values Unrelated)
- Values combined using OR logic within a slicer
- Values combined using AND logic between slicers

**Search Options**

When adding a slicer, configure how the auto-search box filters values:

|  |  |  |
| --- | --- | --- |
| **Option** | **Behavior** | **Example: User types "abc"** |
| Contains | Finds values containing the text anywhere | Matches: abcefg, defabc, defabcefg |
| Starts With | Finds values beginning with the text | Matches: abcefg, abc (not dabc or 1abc) |
| Group Search | Groups values by prefix plus one character (hierarchy codes only) | Creates groups: ABC1, ABC2, etc. |

**Parent topic:** [Report Components: Filters and Slicers](../../../../studio/new-uc/reference/report-studio-reference/report-component-filters-slicers.html)
