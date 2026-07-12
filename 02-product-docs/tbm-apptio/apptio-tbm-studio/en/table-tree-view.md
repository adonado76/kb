---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Tree View"
breadcrumb:
  - "How-To Guides (Task-Based)"
  - "IBM Apptio Report Studio (New)"
  - "Visualizations"
  - "Table"
  - "Tree View"
source_path: "SSWRJM/studio/report-studio/visualizations/tree-view.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Tree View

Tree View allows you to visualise hierarchical data directly within a table. Instead of displaying all rows in a flat list, Tree View organises data into expandable and collapsible levels, making it easier to explore relationships and drill into details progressively.

This is especially useful when your data has natural parent–child relationships, such as:

- Cost Centres → Accounts → Sub-Accounts
- Business Units → Teams → Applications
- Categories → Subcategories → Items

Use this when

- Your table uses multiple fields in the Rows configuration
- You want to navigate data hierarchically, rather than scanning a long flat table
- You want to control how much detail is visible at a time

How to use Tree View

1. Open a table
1. Toggle the Show as tree table under formatting properties
1. Ensure that multiple fields are added to the Rows section
1. Once enabled, only the top level (root) rows are shown initially.
1. Expand and collapse icons appear next to rows that have child data.
1. Expand a row to view the next level in the hierarchy.
1. Collapse a row to hide all its child rows.

- Child rows appear directly below their parent row, preserving context. This allows you to explore data incrementally without losing sight of the parent relationship.
- Tree-view only works on single object dimension and not on dimensions from multi-objects.

Hierarchy Construction

When Tree View is enabled:

- The table hierarchy is built using the fields added to the Rows section.
- The order of fields defines the hierarchy:
- First field → Root level
- Second field → Child level
- Subsequent fields → Deeper levels

Each row can be expanded to reveal its immediate children.

When Tree View Is Disabled:

- The table renders as a standard flat table
- No hierarchy or expand/collapse controls are shown
- All rows appear at the same level

Max Children Setting

The Max Children setting lets you control how many child rows are displayed under each parent node.

How It Works

- Default (Show all): All child rows for a parent are displayed when expanded.
- User-defined value (n): Only the first n child rows are shown for each parent.

This is helpful for:

- Preventing very large expansions
- Improving readability and performance
- Focusing on top child records

## Auto-Wrapping for Table Headers and Cells

Tables now support auto-wrapping of text in both column headers and cells, improving readability and ensuring content is fully visible without manual resizing.

Table supports custom formulas and formula dimensions. For more details, see Custom Formulas
