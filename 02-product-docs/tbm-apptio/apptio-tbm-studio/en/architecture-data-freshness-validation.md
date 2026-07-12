---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Data Freshness and Validation"
breadcrumb:
  - "Concepts and Architecture"
  - "Data Architecture"
  - "Data Freshness and Validation"
source_path: "SSWRJM/studio/new-uc/concepts-architecture/data-architecture/data-freshness.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Data Freshness and Validation

Accurate cost analysis depends on timely, high-quality data. TBM Studio provides several mechanisms to help you monitor data freshness and validate data quality throughout the pipeline.

## Data Freshness

Data freshness tracks whether your data has been updated according to its expected refresh schedule. When you configure a table with a monthly refresh cycle, TBM Studio monitors whether each month’s data has actually been uploaded on time.

Why Freshness Matters

Stale data leads to inaccurate cost models. If your January GL file is not uploaded and the model calculates using December’s data (or no data at all), the resulting allocations and reports will be misleading. Data freshness monitoring helps you catch these gaps before they impact decision-making.

Freshness Monitoring

- Data Expiration Check: Configurable email notifications that alert designated users when uploaded data has expired based on the table’s refresh cycle. You can specify recipient email addresses, the number of days after expiration to send the first notification, and whether to send daily reminders until fresh data is uploaded.
- Data Freshness Dashboard: Accessible from the Project tab, this dashboard shows a summary of all tables with their expiration status and a list of configured freshness rules.

## Data Validation

Validation ensures that data entering the pipeline meets expected quality standards. TBM Studio provides validation at several levels:

- Column type detection: The platform auto-detects whether columns are Label (text), Numeric, or State. Incorrect detection is caught during import and can be overridden manually.
- Required fields: Transform tables that map to master datasets require specific fields. Missing required fields generate pipeline errors that block downstream model calculations.
- Cardinality validation: Validates data against expected patterns during upload.

Editable Table Validation

- Numeric range validation (for example, values must be between 0 and 100).
- Required field enforcement.
- Constrained value lists via dropdown menus (static enumerations or dynamic formula-driven values).
- Cascading dropdown logic that filters allowed values based on selections in other columns.

Invalid rows are highlighted with error messages and cannot be published to the transform table until the user corrects them.

Error Handling

- Type mismatches (a text value in a numeric column)
- Missing required fields for downstream model objects
- Invalid date values that prevent correct period assignment
- Transform step configuration errors

Errors propagate upward: a data error in an upstream transform can block model calculations for any model object that depends on that transform. The Errors panel helps you quickly identify and locate the source of issues.

## Data Quality Best Practices

- Validate at ingestion: Confirm column types during import. Catching type mismatches early prevents cascading errors downstream.
- Enable freshness monitoring: Configure email notifications for all critical data tables, especially financial data that feeds monthly close processes.
- Use constrained inputs for editable tables: Dropdown menus and validation rules prevent free-text errors in fields that feed model dimensions.
- Review errors regularly: Check the Errors panel after each data load. Unresolved errors can silently degrade model accuracy.
- Clean up unused tables: Use the unused document analysis feature to identify tables that are no longer referenced. Removing them reduces noise and simplifies troubleshooting.
