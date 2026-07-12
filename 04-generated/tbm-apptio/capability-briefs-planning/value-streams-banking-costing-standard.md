---
tbm_concept: "Value Streams — Banking / Wealth Management"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-costing-standard
status: draft
generated_from:
  - 01-practice-sources/tbm-council/TBM-Banking_Extension_V2.md
last_updated: "2026-07-02"
---
# Value Streams for Banking — How IBM Apptio Costing Standard Supports This Sector Extension

## The sector extension

The TBM Council's Banking Extension defines a detailed service taxonomy specifically for Wealth
Management and related banking lines of business — a concrete example of the sector-specific
extensions the TBM Taxonomy explicitly supports at the Solutions layer (see
`products-registry.yaml`-adjacent taxonomy notes on extensions). Named service categories include
Deposits/Treasury and Risk Management, Employee Benefit Solutions, Brokerage, Corporate and
Institutional Solutions, Digital Direct, Retirement Planning, Estate Planning, Tax Planning, Risk
Management and Insurance (advisory), Alternative Investments, Education Funding, and Portfolio and
Reporting Analysis.

Each of these functions as a value stream in practice: a cross-functional flow (people, systems,
data) organized around a distinct customer-facing outcome. Brokerage, for instance, is defined as
"full service Brokerage Capabilities providing clients with the ability to buy and sell various
financial assets... while also offering investment advice and research" — a description of an
outcome, not a single application or team.

## How IBM Apptio Costing Standard supports this taxonomy

Because the Banking Extension is structured as Service Type → Service Category → Service Name
(with sample offerings, representative products, and named business/operational metrics per
service), it maps directly onto Costing Standard's existing Solution hierarchy — the same
Type/Category/Name/Offering structure documented in the general Value Streams brief and the Cost
Pool to Resource Tower allocation brief.

Concretely:

- Each named service (Brokerage, Retirement Planning, Estate Planning, etc.) becomes a **Solution
  Name/Category** in Costing Standard, with the Labor Mapping and other Workbench mappings tagging
  resources to it directly — the same mechanism already used generically in Product and Service
  TCO.
- The Banking Extension's own **business and operational metrics** per service (e.g., for
  Brokerage: "Assets Under Management and AUM per advisor," "Net Asset Inflows/Outflows,"
  "Customer Retention Rate") are exactly the kind of metric Costing Standard's Unit Costing
  concept (documented separately) is built to support once cost is allocated to that service —
  cost per AUM, cost per new client acquired, and similar unit economics become directly
  calculable once the allocation is in place.
- The taxonomy's explicit "Who is the customer" dimension per service (e.g., for Corporate and
  Institutional Solutions: institutional clients; for Digital Direct: retail self-directed
  investors) maps onto the Technology Consumer layer — the same layer that defines Business Value
  Streams generically — giving a banking client a direct line from named service, to cost, to the
  specific customer segment it serves.

## Why this matters in a client conversation

A banking or wealth management client evaluating TBM adoption doesn't have to start from a blank
taxonomy — the sector work is already done by the TBM Council, and it's detailed enough to be
immediately actionable: sample offerings, named vendor/platform examples (e.g., Fidelity
Workplace Services, Advent's Black Diamond, Riskalyze), and specific metrics per service category
are already defined. That materially shortens the taxonomy design phase of an engagement, which is
often the slowest part of an early TBM rollout.

An honest scoping note: this extension is scoped specifically to Wealth Management and adjacent
lines (deposits, treasury, brokerage, retirement) — a client whose banking business spans
consumer/retail banking, commercial lending, or payments more broadly will need those areas
modeled using the standard TBM Taxonomy (already covered in this knowledge base) rather than this
sector extension, which doesn't cover them.

## Source documents

- TBM Banking Extension V2 (Wealth Management Service Taxonomy) — `01-practice-sources/tbm-council/TBM-Banking_Extension_V2.md`
- Cross-referenced Costing Standard capabilities: see `value-streams-general-costing-standard.md`,
  `unit-costing-costing-standard.md`.