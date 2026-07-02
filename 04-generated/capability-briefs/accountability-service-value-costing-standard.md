---
tbm_concept: "Accountability for Service Value (Service Portfolio Matrix: business value x cost/performance/alignment)"
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
# Accountability for Service Value — How IBM Apptio Costing Standard Enables This TBM Evaluation

## The concept

Regardless of which technology business model archetype an organization operates in, the TBM
Council frames services — not projects — as what the business actually runs on: "Projects, while
important, merely implement new services or change the ones you have. Still your business runs on
your services, not your projects." Evaluating and continuously improving the value of that service
portfolio is a "constant balancing act" across two distinct dimensions that must be assessed
together.

**Dimension 1 — Intrinsic business value**, classified into three categories:

- **Essential** — necessary to run the business, but not competitively differentiating (the
  example given: a corporate financial reporting system).
- **Advantageous** — supports a competitive-advantage capability, but the service itself isn't
  unique or hard to replicate (the example given: a CRM built on public SaaS).
- **Differentiator** — unique, hard for competitors to replicate, and a direct source of
  competitive advantage (the example given: proprietary supply chain services).

**Dimension 2 — Cost for performance and alignment**, assessed by three concrete questions the TBM
Council poses directly: Is the service cost-effective versus business expectations or
alternatives? Is it meeting SLAs and satisfying users? Is total expenditure (OpEx and CapEx)
aligned to business needs — spending too much, or too little?

The two dimensions combine into what the TBM Council calls the **Service Portfolio Matrix** —
plotting cost/alignment/performance against business value, further layered with portfolio stage
(pipeline, catalog, retiring), TCO, and demand trend (growing vs. declining).

## How IBM Apptio Costing Standard enables this evaluation

Costing Standard's documented capabilities map cleanly onto **Dimension 2** — cost for performance
and alignment is, functionally, what the Services capability, Unit Costing, and IT Financials
already deliver:

- The three assessment questions the TBM Council poses translate almost directly into Costing
  Standard mechanics: "cost-effective vs. alternatives" is Unit Costing plus Benchmarking; "meeting
  SLAs" sits outside Costing Standard's documented scope (it's an operational/ITSM metric, not a
  cost metric — worth flagging this boundary explicitly); "OpEx/CapEx aligned to business needs" is
  directly the IT Financials and Fixed Assets capability already documented.
- **Service TCO** (from the Services capability brief) is literally the "TCO of the service" axis
  the matrix requires — both operating costs and investment spending, as the matrix specifies.
- **Growing vs. declining demand** — a matrix input — is observable through the same
  period-over-period spend and consumption tracking documented in the Resource Towers and IT
  Financials capabilities.

**Dimension 1** — the Essential / Advantageous / Differentiator classification — is a business
judgment call the documentation itself frames as something leadership decides, not something a
costing tool calculates automatically. But Costing Standard provides the structural hook to make
that classification usable and reportable: the **Labor Mapping** workbench (documented in the Cost
Pool to Resource Tower allocation brief) already captures "Solution Type and Solution Category" as
mapped attributes per resource. That same tagging mechanism — extended consistently across the
Solutions layer — is exactly the structural home for an Essential/Advantageous/Differentiator
classification, letting the business-value judgment be captured once and then carried automatically
into every TCO, showback, and benchmarking report already documented in this knowledge base.

## Why this matters in a client conversation

This is a valuable reframe for a client who already understands cost transparency but hasn't
connected it to strategy: cost data alone answers "is this service expensive," but the Service
Portfolio Matrix is what turns that into "should this service be expensive" — an Essential service
running lean is fine; a Differentiator service running lean might be starving the organization's
actual competitive advantage. Costing Standard supplies the defensible cost/performance axis of
that conversation reliably; the business-value axis has to come from a structured conversation
between IT and business leadership — which the TBM Council frames as itself a value-adding TBM
discipline, not a gap to route around.

Positioning this honestly (cost axis: strong, off-the-shelf; value axis: requires business
judgment, structurally supported via tagging) is more credible than implying the tool alone
produces a complete Service Portfolio Matrix without that leadership input.

## Source documents

- TBM — The 4 Value Conversations CIOs Must Have With Their Businesses (Chapter 3: Positioning for
  Value, "Accountability for Service Value" section) — `01-practice-sources/tbm-council/TBM-The_4_Value_Conversations_CIOs_Must_Have_With_Their_Businesses.md`
- Cross-referenced Costing Standard capabilities: see `cost-pool-to-tower-allocation.md` (Solution
  Type/Category tagging mechanism), and the Services-related content in
  `showback-chargeback-costing-standard.md`.