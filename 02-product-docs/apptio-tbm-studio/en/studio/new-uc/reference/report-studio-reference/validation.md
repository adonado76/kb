---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Validation"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Report Studio Reference"
  - "Report Components - Input Components"
source_path: "studio/new-uc/reference/report-studio-reference/validation.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Validation

TBM Studio provides multiple validation mechanisms to ensure data integrity.

**Required Field Validation**

Property: Value Required - When checked, users cannot save the table if a row has an empty value
in this column.

**Data Type Validation**

The Type property automatically validates that entered values match the expected data type:

|  |  |
| --- | --- |
| **Type** | **Validation** |
| Label | Accepts any text |
| Numeric | Validates numeric format according to project locale |
| Date | Validates date format according to configured Date Format |

**Uniqueness Validation**

Property: Allow Unique Values only - When checked, users cannot save the table if the column
contains duplicate values.

**Range Validation (Table Level)**

Configure range validation through the Validate Total properties:

- Total Column Validator: Validates that row totals fall within acceptable ranges
- Total Row Validator: Validates that column totals meet requirements (e.g., percentages summing
  to 100%)

**Validation Error Display**

When validation fails:

- Warning or error messages appear near the respective cell
- Rows with errors are highlighted and sorted to the top of the table
- Users can save and check in reports despite errors (for draft work)
- Invalid rows cannot be successfully published to transform tables

**Parent topic:** [Report Components - Input Components](../../../../studio/new-uc/reference/report-studio-reference/report-component-input-components.html)
