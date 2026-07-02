---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Published Tables"
breadcrumb:
  - "TBM Studio"
  - "Concepts and Architecture"
  - "Data Architecture"
  - "Tables and Table Types"
source_path: "studio/new-uc/concepts-architecture/data-architecture/published-tables.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Published Tables

**Purpose:** Share modeled data with external systems in a controlled, schema-stable
format.

Published tables are the primary data egress mechanism in TBM Studio. They provide a stable,
model-aligned dataset that external systems (such as Power BI, Snowflake, or enterprise data lakes)
can retrieve programmatically through an API URL.

Key characteristics of published tables:

- They are separate entities from reports and transform tables, designed specifically for data
  export.
- They reflect calculated model values—not draft values from development branches.
- They update automatically after successful staging or production calculations.
- By default, published tables are pre-calculated so they are ready immediately when requested via
  API.
- Only administrators can create or modify published tables.

Published tables were developed to replace the older pattern of creating locked reports solely
for data export, which added unnecessary system load during calculations.

Note:

**When to Use Published Tables**

Use published tables when you need to feed cost-model outputs into external analytics platforms,
data warehouses, or planning systems. They provide a stable schema that does not change as reports
evolve, making them ideal for automated integration pipelines

**Parent topic:** [Tables and Table Types](../../../../studio/new-uc/concepts-architecture/data-architecture/table-types.html)
