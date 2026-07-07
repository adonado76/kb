---
source_system: "apptio-billing-standard"
practice: "tbm"
language: "en"
doc_type: "billing"
title: "Integration mechanisms and non-Studio options"
breadcrumb:
  - "Data Requirements and Integration"
  - "Integration mechanisms and non-Studio options"
source_path: "SSV8ML/boit/billing/datareq-integrate/integration.html"
images: []
capability_ids: []
last_updated: "2026-07-06"
summary: ""
---
# Integration mechanisms and non-Studio options

*Data can reach Billing through several mechanisms. Which ones are used depends on who manages the implementation and what tools are available.*

Common options:

- Structured ETL into TBM Studio Used where the IT organization, partner, or IBM team has full Studio and integration access. Suitable for recurring feeds from CMDB, PPM, cloud providers, HR, and Finance.
- Datalink or integration platforms Used to automate ingestion from multiple systems without manual file handling. Useful when source systems are cloud-based or when near-real-time updates are required.
- Table Upload and front-end maintenance Used where Studio access is limited or where certain reference data is maintained by business-facing teams. Examples: Uploading updated rate tables. Updating small reference lists for offerings or mapping tables.

Guidelines:

- Use automated integration for high-volume or frequently changing data (for example, consumption, cloud usage, project cost).
- Reserve manual uploads for: Small tables that change infrequently (for example, a product catalog or rate list). Controlled adjustments or one-time corrections.

Later sections in this guide assume that these data requirements and integration patterns are in place when describing configuration steps, the billing cycle, and how to interpret Billing outputs.
