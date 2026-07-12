---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Table Source Options"
breadcrumb:
  - "Reference"
  - "Data Studio Reference"
  - "Tables"
  - "Table Source Options"
source_path: "SSWRJM/studio/new-uc/reference/table-source-option.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Table Source Options

When you create a table, you must select a source type that determines how data enters the table.

File Upload

Description: Import data from local or network files

Supported Formats:

| Format | Extensions | Notes |
| --- | --- | --- |
| Format | Extensions | Notes |
| Excel | .xls, .xlsx | Single period in filename only |
| CSV | .csv | Comma-separated values |
| Delimited Text | .txt | Tab, pipe, tilde, colon, semi-colon |
| XML | .xml | Structured data |
| ZIP | .zip | Compressed archives |

File Naming Rule: File names must contain only one period (.) before the extension.

- example_data.xlsx - Correct
- example.data.xlsx - Incorrect (causes unsupported file extension error)

Pipeline Steps Created: Source > Upload > Import > Table

Existing Table

Description: Create a new table based on another table's output, maintaining a link

Use Cases:

- Creating filtered subsets of master data
- Building specialized reporting tables
- Applying additional transforms to processed data

Options:

| Option | Description |
| --- | --- |
| Option | Description |
| Source Data | Uses raw data from the source table |
| Output Table | Uses data after all transform steps are applied |
