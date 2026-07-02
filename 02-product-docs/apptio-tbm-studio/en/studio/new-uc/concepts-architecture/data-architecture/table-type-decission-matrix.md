---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Table Type Decision Matrix"
breadcrumb:
  - "TBM Studio"
  - "Concepts and Architecture"
  - "Data Architecture"
  - "Tables and Table Types"
source_path: "studio/new-uc/concepts-architecture/data-architecture/table-type-decission-matrix.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Table Type Decision Matrix

Use this guide to select the right table type for your situation:

|  |  |  |
| --- | --- | --- |
| **Your Need** | **Recommended Table Type** | **Why** |
| Import external data files (GL, budget, forecast) | Source / File Table | Purpose-built for file ingestion with auto-detection and validation |
| Clean, join, or reshape data | Transform Table | Pipeline of configurable steps for data preparation |
| Manual data entry from scratch | Blank Editable Table | Users define all rows and values; no upstream dependency |
| Annotate or enrich machine-generated data | Enriched Editable Table | Combines automated data with human judgment |
| Export model data to external systems | Published Table | Stable schema, API-accessible, designed for data egress |

**Parent topic:** [Tables and Table Types](../../../../studio/new-uc/concepts-architecture/data-architecture/table-types.html)
