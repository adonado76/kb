---
source_system: "apptio-billing"
practice: "tbm"
language: "en"
doc_type: "boit"
title: "Shared data foundations"
breadcrumb:
  - "Billing"
  - "Data Requirements and Integration"
source_path: "boit/billing/datareq-integrate/shared-data.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Shared data foundations

Billing sits on top of Costing. If the data feeding Costing and Billing is weak, the
bills will be weak. This section spells out what data Billing needs, how it is typically
structured, and where integration usually happens.

Both Billing Essentials and Billing Standard rely on a few common foundations:

- **Consumers**
  - Business units, cost centers, departments, projects, or other entities that receive
    charges.
  - Must have stable, unique identifiers and a hierarchy (for example, BU → Dept → Cost
    Center).
- **Offerings (services/products)**
  - The catalog of what is being billed.
  - Each offering should have:
    - A unique ID.
    - A name recognizable to business stakeholders.
    - A unit of measure (for example, user per month, GB per month).
    - A status (active, retired, internal only).
- **Consumption**
  - Records that show “how much of what” a consumer used in a period.
  - Needs at least:
    - Consumer ID.
    - Offering ID (or something explicitly mapped to it).
    - Period.
    - Units consumed.
- **Rates**
  - Pricing or recovery per unit.
  - Must be tied to offerings and periods, and be retrievable in a deterministic way
    (for example, rate effective for that period).

- **Costing outputs**
  - Costing results that represent the cost side (for example, cost per unit, cost by
    service, cost by consumer) that Billing may use for:
    - Validating rates.
    - Variance analysis.
    - True-ups or cost-based pricing.

If these foundations are unstable or incomplete, expect problems later: missing charges,
unexplained rates, or bills that cannot be reconciled back to Costing.
