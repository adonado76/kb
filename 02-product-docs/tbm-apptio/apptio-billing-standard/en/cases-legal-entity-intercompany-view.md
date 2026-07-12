---
source_system: "apptio-billing-standard"
practice: "tbm"
language: "en"
doc_type: "billing"
title: "Legal entity and intercompany view"
breadcrumb:
  - "Design Patterns and Use Cases"
  - "Legal entity and intercompany view"
source_path: "SSV8ML/boit/billing/design-uc/uc-legal.html"
images: []
capability_ids: []
last_updated: "2026-07-06"
summary: ""
---
# Legal entity and intercompany view

Problem

Finance and tax teams need visibility into Technology charges crossing legal-entity boundaries.

Inputs

- Legal entity master table (entity, country, tax attributes)
- Mappings: Consumers → legal entity Services / infrastructure → providing entity
- Billing Standard transfer pricing configuration

Steps

1. Confirm legal entity mappings : Consumers have valid entity assignments. Providing entities are defined for services or domains in scope.
1. Run Billing Standard models with transfer pricing logic enabled.
1. Open the Intercompany / Transfer Pricing report : View charges by From Entity, To Entity, Service, and Period. Check totals against high-level Billing output.
1. Filter to specific entity pairs of interest.
1. Review tax attributes as needed (for example, country, type of service).
1. Use the results to: Support intercompany journal preparation. Provide extracts for tax or regulatory analysis.

Key reports

- Transfer pricing matrix (From Entity × To Entity)
- Legal entity Technology P&L style views
- Journal extract aligned with intercompany accounting requirements
