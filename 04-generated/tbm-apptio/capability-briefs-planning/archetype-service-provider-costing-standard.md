---
tbm_concept: "Technology Business Model Archetype: Service Provider"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-costing-standard
status: draft
generated_from:
  - 01-practice-sources/tbm-council/TBM-The_4_Value_Conversations_CIOs_Must_Have_With_Their_Businesses.md
last_updated: "2026-07-02"
---
# Technology Business Model Archetype: Service Provider — How IBM Apptio Costing Standard Supports This Model

## The archetype

Service Provider organizations "have defined a portfolio of services and formalized roles for
service owners and business relationship managers (BRMs)," and focus on service management
maturity (ITIL and similar frameworks). The TBM Council calls this "well suited for most shared
services organizations" — the model that serves multiple business constituencies with
standardized, clearly-priced services.

The TBM Council's description of how a mature Service Provider implements each TBM discipline
reads almost like a Costing Standard feature list:

- **Create Transparency**: "Tech leaders know the total costs of delivering services, including
  services/costs on a per-unit basis... Service owners understand how their services are consumed
  by their business partners and at what cost."
- **Deliver Value for Money**: "Tech leaders monitor the unit costs of their services and towers...
  They benchmark their costs and cost ratios regularly... against industry peers."
- **Shape Business Demand**: "Business partners are allocated costs based on the actual or planned
  consumption of services... They receive a bill of IT that provides the details of consumption."
- **Plan and Govern**: "The budget is often set based on the amount of services to be delivered and
  consumed by the business, after considering... headwinds... and tailwinds."

## How IBM Apptio Costing Standard addresses each discipline

- **Services capability** (Services Overview, already documented in this knowledge base) delivers
  exactly the "total service cost on a per-unit basis" the archetype requires — fully burdened
  service TCO combining infrastructure, applications, labor, vendor, and platform costs.
- **Unit Costing** as a cross-cutting concept (see that brief) is what makes "monitor the unit
  costs of their services and towers" concrete and repeatable rather than a one-off exercise.
- Apptio **Benchmarking**, layered on top of Costing Standard's cost pool and tower mapping,
  directly answers "benchmark their costs... against industry peers" — see the Cost Pool to
  Resource Tower allocation brief for how that mapping connects the two products.
- **Showback/Chargeback**, specifically the Services view's named use case "Communicate IT Spend
  (Showback)," is the mechanism for the "bill of IT" the archetype names as essential to shaping
  demand.
- **IT Financials'** Budget Variance Analysis, with its explicit actuals/budget/forecast
  comparison, is the direct match for planning around headwinds and tailwinds.

## Why this matters in a client conversation

Service Provider is the archetype most shared-services organizations should be operating in
today, and it's also the archetype Costing Standard is most directly built for — nearly every
capability documented in this knowledge base maps onto one of the four disciplines above without
much translation required. For a client that already identifies as Service Provider, the
conversation isn't "can Costing Standard support this model" — it clearly can — it's "which of
these already-mature capabilities do you have gaps in today," which is a faster, more targeted
scoping conversation than starting from an Expense Center baseline.

The TBM Council's own caution is worth carrying into the conversation too: Service Provider
organizations are "increasingly at risk of being replaced in whole or in part by external service
providers, including the cloud" — which is the natural bridge into positioning Value Partner
capabilities (Application/Product TCO, business-capability cost) as the next phase of maturity,
not a hard sell but a logical continuation.

## Source documents

- TBM — The 4 Value Conversations CIOs Must Have With Their Businesses (Chapter 3: Positioning for
  Value, "Service Provider" section) — `01-practice-sources/tbm-council/TBM-The_4_Value_Conversations_CIOs_Must_Have_With_Their_Businesses.md`
- Cross-referenced Costing Standard capabilities: see `showback-chargeback-costing-standard.md`,
  `unit-costing-costing-standard.md`, `it-financials-capex-opex-costing-standard.md`, and the
  Benchmarking mapping in `capability-product-map.yaml`.