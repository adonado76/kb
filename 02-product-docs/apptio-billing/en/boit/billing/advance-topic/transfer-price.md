---
source_system: "apptio-billing"
practice: "tbm"
language: "en"
doc_type: "boit"
title: "Transfer pricing and legal entity views"
breadcrumb:
  - "Billing"
  - "Advanced Topics"
source_path: "boit/billing/advance-topic/transfer-price.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Transfer pricing and legal entity views

Transfer pricing and legal-entity level views become important when Technology charges
cross legal or tax boundaries.

Note: Applies to Billing Standard only.

## Legal entity modeling

Minimum elements:

- Legal entity master:
  - Entity ID, name, country, tax attributes.
- Mappings from:
  - Consumers to legal entities.
  - Services or infrastructure to legal entities where required.

## Intercompany flows

Common requirements:

- Identify charges that represent intercompany flows:
  - From one legal entity to another.
- Represent flows in a way Finance and tax teams can use:
  - Separate internal revenue and internal expense lines.
  - Use appropriate accounts and tax markers.

Typical configuration elements:

- Mapping tables to define from-entity and to-entity relationships.
- Rules in Billing models to:
  - Split or reclassify charges into intercompany lines.
  - Tag them with appropriate attributes.

The goal is to make transfer pricing transparent and traceable to the same unit-rate and
service definitions used elsewhere, not to maintain a separate black-box process.
