---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "How Editable Tables Fit in the Data Flow"
breadcrumb:
  - "TBM Studio"
  - "Concepts and Architecture"
  - "Data Architecture"
  - "Tables and Table Types"
source_path: "studio/new-uc/concepts-architecture/data-architecture/editable-tables-fir-data-flow.html"
images:
  - "resources/images/studio_images/editable-data-flow.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# How Editable Tables Fit in the Data Flow

Editable tables participate in the data pipeline through a publish mechanism:

![EDitable Table Data Flow](../../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/editable-data-flow.png)

Publishing overwrites the entire editable-table dataset in the associated transform table. This
can happen manually or on a recurring schedule (hourly, daily, weekly, or monthly). Optionally,
publishing can trigger an automatic promotion to production.

Note:

**Important**

Editable tables are branch-specific. Creating a branch gives it its own copy of editable tables,
and modifications in the trunk do not appear in the branch (and vice versa).

**Parent topic:** [Tables and Table Types](../../../../studio/new-uc/concepts-architecture/data-architecture/table-types.html)
