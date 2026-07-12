---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Join data from multiple sources"
breadcrumb:
  - "TBM Studio"
  - "How-To Guides (Task-Based)"
  - "Work with Data"
  - "Transform & Enrich Data"
source_path: "studio/new-uc/howtoguides/work-with-data/join-data.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Join data from multiple sources

## Objective

Combine data from two or more tables into the same rows based on matching values in key
columns, enriching your primary table with supplemental information.

## When to use this

Use Join when you need to:

- Add columns from a reference table (e.g., cost center details from HR data)
- Enrich cost data with asset information or organizational hierarchy
- Combine related datasets for comprehensive reporting
- Create a single table with all needed data for model unit drivers

Note: Join combines data into the same rows. If you want to add rows instead, use Append (see
C; Append multiple data sources).

## Prerequisites

- Primary table checked out
- Related tables exist with matching key columns
- Understanding of join keys (columns with matching values)

## Time estimate

15-20 minutes

## Steps

1. Open the primary table in the **Project Explorer**.
2. Add a **Join** step to the transform pipeline (appears after the Table step).
3. In the Join diagram, the primary table appears on the left. Related tables appear on the
   right with match percentages.
4. Click **Add Link** to create a join.
5. In the **Add Link** dialog:
   - **From Table**: Select the related table to join
   - **From Column**: Select the key column in the related table
   - **To Column**: Select the matching key column in your primary table
6. Click **OK** to create the link.
7. Review the join diagram:
   - Click the **+** sign on tables to see column-level match percentages
   - Click a link to view matched, unmatched, and reference details
8. Add additional joins if needed by repeating steps 4-6.
9. Click **Save** to apply the Join step.
10. Verify joined columns appear in the **Project Explorer** under your primary table
    (shown with notation like *TableName.ColumnName*).

## Expected results

Columns from the joined table are now available in your primary table. You can use these
columns in formulas, reports, and model configurations. The **Table** step preview will
not show joined columns, but they are available in downstream steps and in **Project
Explorer**.

## Common pitfalls

- **Low match percentage:** If the match percentage is low, verify that the join key
  columns contain the same values and data types. Leading/trailing spaces or case
  differences can prevent matches.
- **Joined columns not visible in Table step:** This is expected behavior. Joined
  columns appear in Project Explorer and downstream pipeline steps, but not in the Table
  step preview.
- **Using joined data in formulas:** If you need conditional logic based on both
  primary and joined columns, use Lookup() formulas in a Formulas step rather than relying
  solely on Join.

**Related tasks**

- [Apply formulas to transform data](apply-formula.html)
- [Clean and map data](apply-formula.html)
- [Using Lookup functions](../../reference/formula-function.html)

**Parent topic:** [Transform & Enrich Data](../../../../studio/new-uc/howtoguides/work-with-data/transform-enrich-data.html)
