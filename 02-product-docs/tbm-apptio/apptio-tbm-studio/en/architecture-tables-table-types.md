---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Tables and Table Types"
breadcrumb:
  - "Concepts and Architecture"
  - "Data Architecture"
  - "Tables and Table Types"
source_path: "SSWRJM/studio/new-uc/concepts-architecture/data-architecture/table-types.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Tables and Table Types

Tables are the fundamental data containers in TBM Studio. Every piece of data that enters, moves through, or exits the platform does so via a table. TBM Studio provides several table types, each designed for a specific role in the data lifecycle.

## Source / File Tables

Purpose: Bring external data into TBM Studio from files or database connections.

A source table is the entry point for your data. When you create a new table and upload a CSV or Excel file, TBM Studio creates a source table with an associated transform pipeline. The platform parses your file, auto-detects column types (Label, Numeric, or State), and presents a preview for your confirmation.

- File Upload: Drag and drop or browse to upload CSV, TSV, XLS, or XLSX files. The platform parses the file and detects the header row, data rows, and column types automatically.
- DataLink (Classic) Connector: Import data using a predefined connector to pull from external databases or systems directly.
- Generated Table: Create a new table derived from an existing table in the project. The new table will not be linked to the original.
- Existing Table (Linked): Create a new table from an existing table, maintaining a link so the derived table stays connected to its source.

After upload, your data lives within a transform pipeline where you can add steps to clean, filter, join, and reshape it before it feeds into the cost model.

When to Use Source Tables

Use source tables whenever you need to bring external data into TBM Studio. This includes general ledger exports, budget files, forecast spreadsheets, asset inventories, and any other data that originates outside the platform.
