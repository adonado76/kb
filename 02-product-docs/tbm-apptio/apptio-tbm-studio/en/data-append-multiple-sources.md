---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Append multiple data sources"
breadcrumb:
  - "How-To Guides (Task-Based)"
  - "Work with Data"
  - "Transform & Enrich Data"
  - "Append multiple data sources"
source_path: "SSWRJM/studio/new-uc/howtoguides/work-with-data/append-multiple.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Append multiple data sources

## Objective

Combine rows from one or more source tables into a target table, creating a unified dataset from multiple sources.

## When to use this

Use Append when you need to:

- Combine data from multiple similar sources (e.g., virtual and physical server inventories)
- Consolidate regional data into a single master table
- Add supplemental data rows to an existing table
- Stack datasets with similar but not identical structures

## Prerequisites

- Target table is a transform table (not an uploaded table)
- Source tables exist with data to append
- Understanding of column mapping between source and target

## Time estimate

15-20 minutes for initial setup; 5 minutes to add additional sources

## Steps

1. Check out the target table in Project Explorer .
1. Add an Append step to the transform pipeline.
1. Click Append Data Source .
1. Select the source table to append and click Next .
1. Map source columns to target columns: Auto-matched columns: Columns with matching names (case-insensitive) are automatically mapped and shown with green checkmarks Manual mapping: For unmapped columns, use the dropdown to select the corresponding source column Fixed values: To use the same value for all appended rows, select "Enter a fixed value for all rows&" and enter the value Formulas: Enter a formula beginning with = to transform source data (e.g., ="pm-&"&{Asset Tag})
1. (Optional) Click Select additional source column to add new columns from the source table to the target table.
1. Review the preview tables at the bottom to verify the mapping.
1. Click Save .
1. To append additional source tables, click Append Data Source again and repeat steps 4-8.

## Expected results

Rows from all source tables are added to the target table. The preview shows combined data from all sources. Each source is listed in the Append step pane with the number of required columns mapped.

## Managing appended sources

From the Append step pane, you can:

- Edit : Modify column mappings for an appended source
- Remove : Delete an appended source from the target table
- Append data source : Add another source table to append

## Common pitfalls

- Column type mismatches: If a source column doesn&';t appear in the dropdown, verify it has the same type as the target column. Use formulas to convert types if necessary.
- Formulas vs. fixed values: Fixed values do not evaluate formulas. To use a formula, add a Formulas step before the Append step, then map the resulting column.
- Append locked for out-of-range periods: For versioned tables, appends apply to the current version only. When selecting a period outside the versioned date span, the append becomes locked and cannot be edited.

## Related tasks

- Join data from multiple sources
- Apply formulas to transform data
- Using Lookup functions (Reference: Formulas & Functions)
