---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Tree View"
breadcrumb:
  - "TBM Studio"
  - "How-To Guides (Task-Based)"
  - "IBM Apptio Report Studio (New)"
  - "Visualizations"
  - "Table"
source_path: "studio/report-studio/visualizations/tree-view.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Tree View

**Tree View** allows you to visualise hierarchical data directly within a table. Instead
of displaying all rows in a flat list, Tree View organises data into expandable and
collapsible levels, making it easier to explore relationships and drill into details
progressively.

This is especially useful when your data has natural parent–child relationships, such as:

- Cost Centres → Accounts → Sub-Accounts
- Business Units → Teams → Applications
- Categories → Subcategories → Items

**Use this when**

- Your table uses multiple fields in the Rows configuration
- You want to navigate data hierarchically, rather than scanning a long flat table
- You want to control how much detail is visible at a time

**How to use Tree View**

1. Open a table
2. Toggle the **Show as tree table** under formatting properties
3. Ensure that multiple fields are added to the Rows section
4. Once enabled, only the top level (root) rows are shown initially.
5. Expand and collapse icons appear next to rows that have child data.
6. Expand a row to view the next level in the hierarchy.
7. Collapse a row to hide all its child rows.

Note:

- Child rows appear directly below their parent row, preserving context. This allows you to
  explore data incrementally without losing sight of the parent relationship.
- Tree-view only works on single object dimension and not on dimensions from multi-objects.

**Hierarchy Construction**

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

**Max Children Setting**

The Max Children setting lets you control how many child rows are displayed under each
parent node.

How It Works

- Default (Show all):

  All child rows for a parent are displayed when expanded.
- User-defined value (n):

  Only the first n child rows are shown for each parent.

This is helpful for:

- Preventing very large expansions
- Improving readability and performance
- Focusing on top child records

Note: Max Children applies per node, not to the entire table.

## Auto-Wrapping for Table Headers and Cells

Tables now support auto-wrapping of text in both column headers and cells, improving
readability and ensuring content is fully visible without manual resizing.

Table supports custom formulas and formula dimensions. For more details, see [Custom Formulas](../create-first/custom-formula.html "Custom formulas (also referred to as formula dimensions) allow you to define new calculated dimensions using existing fields in your data model. This enables deeper analysis and richer insights without requiring any changes to the underlying dataset or schema.")

**Parent topic:** [Table](../../../studio/report-studio/visualizations/rs-table.html "The table component displays data in a structured, tabular format. It is ideal for showing detailed information, summarizing metrics, and supporting interactive filtering within a report.")
