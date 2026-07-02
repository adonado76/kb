---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Clean and map data using Map Columns"
breadcrumb:
  - "TBM Studio"
  - "How-To Guides (Task-Based)"
  - "Work with Data"
  - "Transform & Enrich Data"
source_path: "studio/new-uc/howtoguides/work-with-data/clean-map.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Clean and map data using Map Columns

## Objective

Map source data columns to standardized master dataset schemas, ensuring data conforms to
the expected structure for cost modeling and reporting.

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
2. Click **Add Step** in the transform pipeline and select **Map Columns**.
3. Select the destination master dataset (e.g., Cost Source Master, Vendor Master).
4. Map source columns to destination columns:
   - The system auto-matches columns with identical names (case-insensitive)
   - Review auto-mapped columns (indicated by green checkmarks)
   - For unmapped required columns (marked with asterisks), select the appropriate source
     column from the dropdown
   - To map columns with different types, enter a formula beginning with = (e.g.,
     =Value({Column}) to convert text to numeric)
5. (Optional) Add custom columns to the master dataset by clicking **Add Custom
   Column**. These additions persist across upgrades.
6. (Optional) To pull additional data from related tables, click **Join**, add links to
   other tables, and map the joined columns.
7. Review the preview at the bottom of the dialog to verify the mappings.
8. Click **Save** to apply the Map Columns step.

## Expected results

Your source data now conforms to the master dataset schema and appears in the preview with
all mapped columns. The table is ready for use in model objects and reports. A ***Source
Table*** column is automatically added to track data lineage.

## Common pitfalls

- **Column not appearing in dropdown:** Verify the source column type matches the
  destination type. Numeric columns won't appear when mapping to label fields. Fix by going
  to the Import step and overriding the column type.
- **Required columns not mapped:** While you can save without mapping all required
  columns, downstream model objects may generate errors. Always map required fields (marked
  with \*) before using the table in models.
- **Type mismatch errors:** If mapping a numeric code to a label field, use a formula
  like =NumberFormat({Account}*,"#,###.##”;*) to convert the type.

## Related tasks

- [Apply formulas to transform data](apply-formula.html)
- [Join data from multiple sources](join-data.html)
- <../../reference/data-studio-ref.html>

**Parent topic:** [Transform & Enrich Data](../../../../studio/new-uc/howtoguides/work-with-data/transform-enrich-data.html)
