---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Input Component Types"
breadcrumb:
  - "Reference"
  - "Report Studio Reference"
  - "Report Components - Input Components"
  - "Input Component Types"
source_path: "SSWRJM/studio/new-uc/reference/report-studio-reference/input-component-types.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Input Component Types

TBM Studio provides input capabilities through editable table column configurations. Each column type determines how users enter data.

Text Input

Text input columns accept plain text data and are used for labels, descriptions, and other non-numeric values.

Configuration

| Property | Description |
| --- | --- |
| Property | Description |
| Type | Set to Label for plain text data |
| Name | Display name shown in column header |
| Description | Help text describing the column's purpose |
| Default Value | Pre-populated value for new rows |
| Possible Values | Optional: restrict to a controlled list (creates dropdown) |

Usage Notes

- Label columns cannot have mathematical operations performed on them
- Word wrap is not applicable for primary source columns in enriched editable tables
- Text can be copied and pasted from Excel using Control+C / Control+V (Windows) or ⌘+C / ⌘+V (Mac)

Numeric Input

Numeric input columns accept integer or decimal values and support the project's locale settings for number formatting.

Configuration

| Property | Description |
| --- | --- |
| Property | Description |
| Type | Set to Numeric for numeric data |
| Name | Display name shown in column header |
| Description | Help text describing the column's purpose |
| Default Value | Pre-populated value for new rows |
| Value Required | If checked, users cannot save without providing a value |

Usage Notes

- Numeric columns support locale-specific formatting (decimal separators, thousands separators)
- Currency and percentage formatting are applied at the report level, not the column configuration level
- Numeric values can participate in formula columns and calculations
- The Carry Forward feature (version 12.6+) allows numeric values to propagate across consecutive columns

Date Input

Date input columns accept date values with configurable display formats.

Configuration

| Property | Description |
| --- | --- |
| Property | Description |
| Type | Set to Date for date data |
| Date Format | Specify the format using standard patterns (e.g., MM/dd/yyyy) |
| Name | Display name shown in column header |
| Default Value | Pre-populated date for new rows |

Supported Date Formats

| Pattern | Example Output |
| --- | --- |
| Pattern | Example Output |
| MM/dd/yyyy | 01/15/2025 |
| yyyy-MM-dd | 2025-01-15 |
| MMM dd, yyyy | Jan 15, 2025 |
| dd-MMM-yy | 15-Jan-25 |

Note: The date format string should not be enclosed in quotes when configuring the column.

Selection Input (Dropdowns)

Dropdown selection inputs restrict data entry to a controlled set of values, ensuring data consistency and reducing entry errors.

Basic Dropdown Configuration

Configure a dropdown by setting the Possible Values property using one of these methods:

Method 1 - Static List: Enter a comma-delimited list of values such as "OpEx, CapEx, Transfer"

Method 2 - Formula-Based List: Reference values from another table using the syntax: %tablename/!LIMIT_COLUMNS[column_name]

Dropdown Properties

| Property | Description |
| --- | --- |
| Property | Description |
| Possible Values | Static list or formula defining available options |
| Possible Values Context | Set to Report for static context or Current Row for dynamic filtering |
| Allow Values Not In Possible Values List | If checked, users can type custom values |
| Disallow Edit In Possible Values Cell | If checked, users cannot type in the cell |

Note: The dropdown displays the first 15 unique values. For lists with more than 15 values, a Find button appears.

Cascading (Dependent) Dropdowns

Create dropdowns where the available options depend on another column's value using dynamic text. For example, a City dropdown that filters based on the selected State:

- Create a source table (e.g., States-Cities) with State and City columns
- Configure the State column's Possible Values: %States-Cities/!LIMIT_COLUMNS[State]
- Configure the City column with a filter: %States-Cities/!FILTER[State="<%=State%>"]/!LIMIT_COLUMNS[City]
- Set the City column's Possible Values Context to Current Row
