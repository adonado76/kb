---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Filter and Slicer Component Types"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Report Studio Reference"
  - "Report Components: Filters and Slicers"
source_path: "studio/new-uc/reference/report-studio-reference/filter-slicer-types.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Filter and Slicer Component Types

**Slicer Components**

TBM Studio provides several slicer types to accommodate different filtering needs:

**Row Slicer (List Slicer)**

The standard slicer type for text and categorical fields. Displays values as a selectable list
where users can click to filter data.

|  |  |
| --- | --- |
| **Property** | **Description** |
| Data Type | Text/Label fields |
| Selection Mode | Multi-select (Ctrl+click for multiple) |
| Display | List of values with states (Selected, Related, Unrelated) |
| Max Values | 250 values per slicer |

**When to use:** Category filtering, dimension selection, any text-based field where users
need to select from discrete values.

**Numeric Slider**

Automatically created when you add a numeric field to a slicer. Provides a range slider for
filtering numeric data.

|  |  |
| --- | --- |
| **Property** | **Description** |
| Data Type | Numeric fields |
| Selection Mode | Range selection via slider handles |
| Display | Horizontal slider with min/max handles |
| Operators | Supports greater than, less than, between |

**When to use:** Cost thresholds, quantity ranges, any numeric metric where users need to
filter by value ranges.

**Hierarchical Slicer**

Enables drill-down filtering through multiple levels of a hierarchy (e.g., Type → SubType →
Detail).

|  |  |
| --- | --- |
| **Property** | **Description** |
| Basis | Custom perspective group with ordered fields |
| Navigation | Expandable tree structure |
| Selection | Parent selection filters child values |
| Use with | Compact slicers supported |

**When to use:** Geographic hierarchies, organizational structures, product taxonomies, any
multi-level classification.

**Compact Slicer**

Combines multiple slicers into a space-efficient dropdown interface. Available in two variants:

**Local Compact Slicer**

- Uses both locked and unlocked fields
- Selections not saved across sessions
- Applies like standard slicers (report or group scope)

**Global Compact Slicer**

- Only fields locked to an object can be included
- User selections persist across sessions and logout/login
- Changes apply to all reports containing the same global compact slicer
- Recommended replacement for legacy global filters

Tip: Use global compact slicers instead of global filters whenever possible. They
provide better user experience and persistent filter settings.

**Filter Types and Configuration**

**Component-Level Filters (Filters Area)**

Filters added to the Filters area of the Component Configuration panel restrictto restrict data
before it reaches the table or chart.

**Configuration steps:**

1. Drag a field from a perspective into the Filters area
2. Right-click the field and select Edit Filter
3. Select values to include or exclude
4. Click OK to apply

**Filter dialog options:**

|  |  |
| --- | --- |
| **Option** | **Description** |
| Value selection | Check/uncheck specific values to include |
| Add custom filter | Enter custom filter values not in the list |
| Values not currently shown | Include values exceeding the 1,000 value1,000-value display limit |
| Filter search box | Search for specific values when list is large |

**Note:** If more than 1,000 values exist for a filter field, use the Filter search box to
locate additional values.

**Auto-Search Filter (In-Table Filtering)**

Tables support inline filtering via search fields below column headers.

**Search operators:**

|  |  |  |  |
| --- | --- | --- | --- |
| **Operator** | **Number Column** | **Text Column** | **Description** |
| text | No | Yes | Find rows containing the text |
| !text | No | Yes | Find rows NOT containing the text |
| = | Yes | Yes | Exact match (case-sensitive for text) |
| > < >= <= != | Yes | No | Numeric comparisons |
| BLANK | Yes | Yes | Find empty cells |
| !BLANK | Yes | Yes | Find non-empty cells |
| && | Yes | Yes | AND logic (e.g., Save && Master) |
| || | Yes | Yes | OR logic (e.g., Save || Master) |

Note: You can use multiple && or multiple || in a search, but search but cannot combine both
operators in the same search.

**Parent topic:** [Report Components: Filters and Slicers](../../../../studio/new-uc/reference/report-studio-reference/report-component-filters-slicers.html)
