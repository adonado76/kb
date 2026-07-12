---
source_system: "apptio-billing-standard"
practice: "tbm"
language: "en"
doc_type: "billing"
title: "Data requirements for Billing Essentials"
breadcrumb:
  - "Data Requirements and Integration"
  - "Data requirements for Billing Essentials"
source_path: "SSV8ML/boit/billing/datareq-integrate/data-be.html"
images: []
capability_ids: []
last_updated: "2026-07-06"
summary: ""
---
# Data requirements for Billing Essentials

Billing Essentials uses a focused set of tables and datasets to run a PxQ billing process. Names and exact table structures may vary by template version, but the pattern is consistent.

Typical table families:

- Solution / Offering library A list of billable offerings (services, products, or bundles). Common fields: Offering ID and name. Unit of measure. Active flag or status. Flags to indicate whether the offering is billable, shown only, or internal.
- Consumption feed Units consumed by offering and consumer for a given period. Common fields: Consumer ID. Offering ID (or a key that maps to it). Period (month, quarter, etc.). Units consumed. Optional attributes such as environment, region, or cost center segment.
- Rate and pricing tables Rates per offering and period. Common fields: Offering ID. Period or effective date. Rate amount. Rate type (for example, standard, discounted, promotional).
- Billing master / output tables Charge results and any journal-ready outputs. Common fields: Consumer ID. Offering ID. Period. Units, rate, and total charge. Optional GL segment fields for journal exports.

Integration patterns for Billing Essentials:

- Consumption feeds often come from: Ticketing or ITSM systems. Identity/access systems (for user counts). Monitoring or metering tools. Spreadsheets or CSV files when no system of record exists.
- Data is typically loaded by: TBM Studio ETL processes. Datalink or other integration tooling. Table Upload for structured CSV inputs when Studio access is not available to the IT org.

If a consumer or offering in the consumption feed does not match the master tables, the related charges may drop or land in exception views. Plan for basic data QA around these joins.
