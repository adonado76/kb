---
tbm_concept: "Technology Business Model Archetype: Business Driver"
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
# Technology Business Model Archetype: Business Driver — How IBM Apptio Costing Standard Supports This Model

## The archetype

Business Driver is the archetype where, per the TBM Council, "the technology organization IS the
business" — only possible when a company's products or services are themselves technology-centric
(SaaS/PaaS/IaaS providers, an online retail channel, a technology-enabled trading desk). Here the
distinction between "business process owner" and "IT service owner" largely dissolves.

The archetype's discipline implementation pushes cost thinking to its most granular, product-P&L
level:

- **Creating Transparency**: "Business (tech) leaders know the total cost of delivering business
  capabilities, including the per-unit basis. They understand their business cost dynamics and how
  all costs are shaped by changing business conditions and demands."
- **Delivering Value for Money**: "They manage the unit costs of their business capabilities, such
  as cost per trade or the monthly cost to serve a subscriber."
- **Shape Business Demand**: "The cost of technology is baked into the firm's product prices.
  Demand is shaped through the market."
- **Planning and Governing for Value**: "Technology budgets are integral to product-line fiscal
  plans. Business planning is also tech planning."

## How IBM Apptio Costing Standard addresses each discipline

This archetype is where **Unit Costing** and **Product TCO** stop being supporting capabilities
and become the core of the value proposition:

- The specific unit-cost examples the archetype names — "cost per trade," "monthly cost to serve a
  subscriber" — are structurally the same pattern as the "cost per rack, cost per kilowatt" unit
  economics Costing Standard already delivers for Data Center TCO, applied instead to a
  customer-facing product metric. The underlying mechanism (Metrics driving unit cost calculations
  across an allocation model) is the same one documented in the Unit Costing brief.
- **Product TCO's** design goal — supporting "product roadmap, funding, and lifecycle decisions"
  with cost "integral to product-line fiscal plans" — is close to a direct match for "technology
  budgets are integral to product-line fiscal plans."
- **IT Financials'** OpEx/CapEx consolidation remains the financial foundation underneath any
  Business Driver cost model — the archetype doesn't remove the need for disciplined cost pool and
  depreciation treatment, it adds a revenue-facing layer on top of it.

## An honest scoping note

Costing Standard's documented capabilities are strong on the *cost* side of this archetype — total
cost of a business capability, cost per unit consumed — but the archetype's demand-shaping
mechanism ("baked into the firm's product prices... shaped through the market") implies a pricing
and revenue integration that sits outside Costing Standard's documented scope. For a client
operating (or aspiring to) a true Business Driver model, Costing Standard is the system of record
for the cost side of that unit economics equation; connecting that cost to external pricing and
market-facing revenue typically requires integration with the client's own product/pricing systems
— worth flagging explicitly in a proposal rather than implying Costing Standard alone closes that
loop end to end.

## Why this matters in a client conversation

The TBM Council notes something important for positioning: "Many business driver technology
organizations start out that way; but a service provider or value partner often becomes... a
business driver" — meaning most clients approaching this archetype are transitioning into it, not
starting fresh. That means the realistic conversation is rarely "sell Business Driver capability
from zero" — it's "here's how the Application/Product TCO and Unit Costing work already in place
(from an earlier Value Partner phase) extends naturally as specific business lines spin out into
revenue-generating, technology-centric units."

## Source documents

- TBM — The 4 Value Conversations CIOs Must Have With Their Businesses (Chapter 3: Positioning for
  Value, "Business Driver" section) — `01-practice-sources/tbm-council/TBM-The_4_Value_Conversations_CIOs_Must_Have_With_Their_Businesses.md`
- Cross-referenced Costing Standard capabilities: see `unit-costing-costing-standard.md`,
  `product-tco-costing-standard.md`, and `it-financials-capex-opex-costing-standard.md`.