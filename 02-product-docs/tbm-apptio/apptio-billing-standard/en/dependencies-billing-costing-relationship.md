---
source_system: "apptio-billing-standard"
practice: "tbm"
language: "en"
doc_type: "billing"
title: "Billing and Costing relationship"
breadcrumb:
  - "Administration and Operations"
  - "Solution Architecture and Dependencies"
  - "Billing and Costing relationship"
source_path: "SSV8ML/boit/billing/sol-arch-depend/sol-arch-intro.html"
images: []
capability_ids: []
last_updated: "2026-07-06"
summary: ""
---
# Billing and Costing relationship

*This section explains how Billing is packaged, how it relates to Costing, and what must exist before Billing content can be used.*

## Billing and Costing relationship

Billing is not a standalone application. It is a set of components, models, tables, and reports that are installed into an existing Costing project and exposed to users through the front end.

At a high level:

1. Data flows into Costing from source systems.
1. Costing allocates and normalizes costs.
1. Billing components are added to a Costing project and: Define billable offerings, units, and rates. Consume Costing results and consumption data. Produce billing outputs such as invoices, detail reports, and journals.

Key points:

- Billing depends on the Costing project being deployed and stable.
- Billing uses the same environments and same modeling engine as Costing.
