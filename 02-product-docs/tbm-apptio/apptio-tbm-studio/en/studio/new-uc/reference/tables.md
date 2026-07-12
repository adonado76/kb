---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Tables"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Data Studio Reference"
source_path: "studio/new-uc/reference/tables.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Tables

Tables are the fundamental data containers in Data Studio. Each table has a transform pipeline
that defines how data is processed from source to output.

## Table Types

|  |  |  |
| --- | --- | --- |
| **Table Type** | **Description** | **Use Case** |
| Transform Table | Standard table created from file upload or existing table | General data processing |
| Editable Table | Table that accepts manual user input | Budget adjustments, manual overrides |
| Enriched Editable Table | Editable table based on a source transform table | Overlay modifications on source data |
| Generated Table | Table created from existing table with linked updates | Derived datasets with automatic refresh |
| Master Data Set | Canonical schema table for application compliance | Cost Source Master, Chart of Accounts |
| Published Table | Table configured for external export | Data egress to other systems |

- **[Creating Tables](../../../studio/new-uc/reference/creating-tables.html)**
- **[Table Source Options](../../../studio/new-uc/reference/table-source-option.html)**
- **[Data Refresh Cycles](../../../studio/new-uc/reference/data-refresh-cycles.html)**
- **[Table Column Types](../../../studio/new-uc/reference/table-column-types.html)**

**Parent topic:** [Data Studio Reference](../../../studio/new-uc/reference/data-studio-reference.html)
