---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Validation Configuration"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Report Studio Reference"
  - "Report Components: Editable Tables in Reports"
source_path: "studio/new-uc/reference/report-studio-reference/validation-config.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Validation Configuration

Validation rules ensure data quality by preventing invalid entries. TBM Studio provides multiple
validation mechanisms.

**Required Fields**

Mark columns as required to prevent saving rows with empty values:

- Enable Value Required in the Data Studio column configuration
- Users cannot save the table if required fields are empty
- Required fields are visually indicated in the report interface

**Data Type Validation**

The column Type setting enforces basic data validation:

- **Numeric:** Accepts only numeric entries in the project locale format
- **Date:** Validates entries match the configured Date Format
- **Label:** Accepts any text input

**Unique Value Validation**

Enable Allow Unique Values only to prevent duplicate entries in a column. This is essential for
primary key columns or any column that must contain distinct values.

**Dropdown Validation**

When Possible Values are configured:

- **Allow Values Not In Possible Values List:** If unchecked (default), users must select from
  the dropdown
- **Disallow Edit In Possible Values Cell:** If checked, prevents typing in the cell (useful
  for strict selection controls)

**Total Validators**

For numeric columns, you can validate row or column totals:

- **Total Column Validator:** Validates that row totals meet criteria (e.g., must equal 100 for
  percentage allocations)
- **Total Row Validator:** Validates that column totals fall within specified ranges

Configure validators by clicking the icon next to Validate Total in the Editable Tables ribbon.
Select a comparison operator (=, <, >, <=, >=) and specify the target value.

**Validation Error Display**

When validation fails:

- Invalid cells are highlighted in red
- Error messages appear near the affected values
- Rows with errors appear at the top of the table for easy identification
- Users can save the report with validation errors but cannot publish invalid data

Note: *The Enable Validation Step for Editable Table feature must be enabled in Project Settings >
Enable Features for advanced validation to function.*

**Parent topic:** [Report Components: Editable Tables in Reports](../../../../studio/new-uc/reference/report-studio-reference/report-component-editable-components.html)
