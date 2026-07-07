---
source_system: "apptio-billing-standard"
practice: "tbm"
language: "en"
doc_type: "billing"
title: "Key datasets and tables"
breadcrumb:
  - "Configuring Billing Essentials (Implementation)"
  - "Key datasets and tables"
source_path: "SSV8ML/boit/billing/config-be/key-datasets.html"
images: []
capability_ids: []
last_updated: "2026-07-06"
summary: ""
---
# Key datasets and tables

Billing Essentials depends on a small number of core tables. Exact names may differ by template, but the patterns are consistent.

Typical categories:

- Offerings / services table Stores the catalog of billable offerings. Common fields: Offering ID and name. Unit of measure. Active / inactive flag. Billable flag (yes/no).
- Consumer master Shared with Costing or aligned to it. Common fields: Consumer ID and name. Hierarchy (for example, business unit, department, cost center). Optional attributes like region, function, or manager.
- Consumption table Holds usage volumes per offering and consumer per period. Common fields: Period. Consumer ID. Offering ID (or a key mapped to it). Units consumed.

- Rate table Holds rates for each offering and period. Common fields: Offering ID. Period or effective start/end. Rate amount and currency. Optional rate type (standard, adjusted, promotional).
- Billing output / archive table Stores calculated charges. Common fields: Period. Consumer ID. Offering ID. Units, rate, total charge. Optional journal mapping fields.
