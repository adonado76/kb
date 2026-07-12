---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Editable Tables"
breadcrumb:
  - "Concepts and Architecture"
  - "Data Architecture"
  - "Tables and Table Types"
  - "Editable Tables"
source_path: "SSWRJM/studio/new-uc/concepts-architecture/data-architecture/editable-tables.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Editable Tables

Purpose: Enable manual data entry and human enrichment of machine-generated data.

Editable tables allow users to enter, modify, and manage data directly within TBM Studio. They serve as a bridge between automated data pipelines and the human judgment needed for tasks like cost-center classification, labor mapping, and budget annotations.

TBM Studio supports two types of editable tables:

Blank Editable Tables

- Use case: Fully manual data entry, such as creating a mapping table for cost-center-to-solution assignments, entering budget variance explanations, or building reference lookup tables.
- Users can add and remove rows freely.
- The editable table is the source of truth—it has no upstream data dependency.

Enriched Editable Tables

- Use case: Adding human context to machine-generated data. For example, an AWS billing file (source transform) might need a human to assign a responsible project for each instance tag (editable column).
- Source rows are read-only; only added columns are editable.
- Overlay records modify cells in the original source rows or add new rows, but cannot delete source rows.
