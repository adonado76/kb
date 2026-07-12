---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Configure Dropdowns and Validation"
breadcrumb:
  - "How-To Guides (Task-Based)"
  - "Work with Data"
  - "Manual Data Entry"
  - "Configure Dropdowns and Validation"
source_path: "SSWRJM/studio/new-uc/howtoguides/work-with-data/config-dd-valid.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Configure Dropdowns and Validation

Objective: Add dropdown constraints and validation rules to editable table columns to ensure data quality and consistency.

## When to Use

- Any column used as a reporting dimension or allocation driver
- Classification fields where consistent values are critical
- Fields with a known set of valid values
- Multi-level classification schemes (e.g., Tower → Service → Subservice)
- Numeric fields requiring range validation

## Prerequisites

- An editable table (blank or enriched) already created
- Understanding of valid values for each column
- For cascading dropdowns: reference tables with hierarchical data

## Time estimate

10-30 minutes depending on complexity

## A. Configure Simple Dropdown Lists

1. Open your editable table Navigate to Data Studio Check out the editable table Go to Steps > Configure Columns
1. Select the column to configure Click on the column name in the column list The column properties appear on the right side
1. Define possible values Locate the Possible Values field Enter a comma-delimited list of allowed values Example: Development, Test, Production Example: High, Medium, Low
1. Set dropdown behavior Allow Values Not In Possible Values List: Unchecked (recommended) - Users must select from the dropdown Disallow Edit In Possible Values Cell: Unchecked (recommended) - Users can type to filter/search the dropdown

## B. Configure Dynamic Dropdown Lists

Dynamic dropdowns pull values from other tables, enabling centralized maintenance.

1. Create a reference table (if it doesn't exist) Create a transform table containing your list of valid values Example: "IT Towers" table with columns: Tower ID, Tower Name, Tower Description
1. Configure the formula-based dropdown In your editable table's Configure Columns step, select the target column In Possible Values , enter a formula using this syntax:

%TableName/TableFunction[].ColumnName

- Example: %IT Towers/Distinct[].Tower Name

## C. Configure Cascading (Dependent) Dropdowns

Cascading dropdowns filter based on values selected in other columns.

Example scenario: Users select Tower → Service → Subservice, where Service options depend on the selected Tower.

1. Set up the reference structure Create a reference table with hierarchical relationships Example: "IT Service Hierarchy" with columns: Tower, Service, Subservice
1. Configure the first-level dropdown (Tower) In Possible Values : %IT Service Hierarchy/Distinct[].Tower
1. Configure the second-level dropdown (Service) In Possible Values , use a formula that filters based on the Tower column:

```
%IT Service Hierarchy/Filter[Tower =
        [Tower]]/Distinct[].Service
```

- Set Possible Values Context to Current row Configure the third-level dropdown (Subservice)
- Similar formula, filtering on both Tower and Service:

```
%IT Service Hierarchy/Filter[Tower = [Tower] AND Service =
        [Service]]/Distinct[].Subservice
```

## D. Configure Validation Rules

1. Use built-in validation options Value Required: Check this box to prevent empty values Allow Unique Values Only: Check to prevent duplicates Data Type: Selecting "Numeric" automatically validates that entries are numbers
1. Enable validation UI (Beta feature) Navigate to Project tab > Enable Features Select Enable Validation Step for Editable Table (Beta) When enabled, validation errors appear inline when users enter data

## Common Pitfalls

| Issue | Solution |
| --- | --- |
| Issue | Solution |
| Dropdown values not appearing | Verify formula syntax is correct. Ensure the reference table exists and contains data. Check that column names are spelled exactly as they appear (case-sensitive). |
| Cascading dropdowns don't filter properly | Verify Possible Values Context is set to "Current row". Check filter formula syntax: Filter[ColumnA = [ColumnB]] where ColumnA is in reference table, ColumnB is in current row. |
| Too many values in dropdown (unusable) | If dropdown has >100 values, consider hierarchical approach (cascading dropdowns). Or enable "Allow Edit In Possible Values Cell" so users can type to filter. |
| Users can still enter free text despite dropdown | Ensure "Allow Values Not In Possible Values List" is unchecked. |
