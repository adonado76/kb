---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Clean and map data using Map Columns"
breadcrumb:
  - "How-To Guides (Task-Based)"
  - "Work with Data"
  - "Transform & Enrich Data"
  - "Clean and map data using Map Columns"
source_path: "SSWRJM/studio/new-uc/howtoguides/work-with-data/clean-map.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Clean and map data using Map Columns

## Objective

Map source data columns to standardized master dataset schemas, ensuring data conforms to the expected structure for cost modeling and reporting.

## When to use this

Use Map Columns when you need to:

- Align external data (GL, budget, forecast) to canonical master tables
- Standardize diverse source data into unified structures
- Prepare data for consumption by model objects
- Ensure required fields are populated for downstream processes

## Prerequisites

- Source table uploaded and imported
- Understanding of target master dataset schema
- Column types correctly configured in source table

## Time estimate

15-20 minutes for initial setup; 5-10 minutes for routine updates

## Steps

1. Check out the source table you want to map in the Project Explorer.
1. Click Add Step in the transform pipeline and select Map Columns .
1. Select the destination master dataset (e.g., Cost Source Master, Vendor Master).
1. Map source columns to destination columns: The system auto-matches columns with identical names (case-insensitive) Review auto-mapped columns (indicated by green checkmarks) For unmapped required columns (marked with asterisks), select the appropriate source column from the dropdown To map columns with different types, enter a formula beginning with = (e.g., =Value({Column}) to convert text to numeric)
1. (Optional) Add custom columns to the master dataset by clicking Add Custom Column . These additions persist across upgrades.
1. (Optional) To pull additional data from related tables, click Join , add links to other tables, and map the joined columns.
1. Review the preview at the bottom of the dialog to verify the mappings.
1. Click Save to apply the Map Columns step.

## Expected results

Your source data now conforms to the master dataset schema and appears in the preview with all mapped columns. The table is ready for use in model objects and reports. A Source Table column is automatically added to track data lineage.

## Common pitfalls

- Column not appearing in dropdown: Verify the source column type matches the destination type. Numeric columns won't appear when mapping to label fields. Fix by going to the Import step and overriding the column type.
- Required columns not mapped: While you can save without mapping all required columns, downstream model objects may generate errors. Always map required fields (marked with *) before using the table in models.
- Type mismatch errors: If mapping a numeric code to a label field, use a formula like =NumberFormat({Account} ,"#,###.##”; ) to convert the type.

## Related tasks

- Apply formulas to transform data
- Join data from multiple sources
- ../../reference/data-studio-ref.html
