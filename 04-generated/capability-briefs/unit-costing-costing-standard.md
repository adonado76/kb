---
tbm_concept: "Unit Costing (cross-cutting metric, not a standalone solution page)"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-costing-standard
status: draft
generated_from:
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/get-started/costing-terminologies.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/infra-use-cases/dc-overview.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/itf-overview.md
last_updated: "2026-07-02"
---
# Unit Costing — How IBM Apptio Costing Standard Addresses This TBM Capability

## A note on scope before the capability itself

Unlike the other briefs in this knowledge base, Unit Costing does not have its own dedicated
overview page in Costing Standard's documentation — there is no "Unit Costing Overview" the way
there is a Data Center Overview or Workforce Overview. It's a **cross-cutting metric concept**
that shows up inside nearly every other capability. This brief documents it as such, rather than
forcing a single-page capability narrative that the source material doesn't actually support.

## The capability

Unit cost — cost per rack, cost per user, cost per CPU hour, cost per application — is what turns
a raw allocation number into something comparable across time, across peers, and across
alternatives. A total cost figure by itself answers "how much did we spend"; a unit cost answers
"is that efficient," which is the question that actually drives optimization and investment
decisions.

## How IBM Apptio Costing Standard covers it

The foundation is defined at the glossary level: Costing Standard's terminology guide defines
**Metric** as "a quantitative value used to measure cost, consumption, or performance... [Metrics]
often serve as drivers in allocations and provide the basis for calculating unit costs and
comparing technology performance over time." Unit costs, in other words, are a derived output of
the same metric and allocation framework that drives the rest of the model — not a separately
configured feature.

That framework shows up concretely across the domains already documented in this knowledge base:

- **Data Center TCO** names specific unit economics explicitly: "cost per rack, cost per area, and
  cost per kilowatt" — the metrics that let a facility owner and a CFO discuss the same investment
  decision in comparable terms.
- **IT Financials** uses unit costs for external benchmarking: "benchmark IT spend against revenue
  and per-user metrics to identify potential areas for improvement" — turning an internal cost
  number into something comparable against industry norms.
- **Application, Product, and Service TCO** (see their respective briefs) all report cost per user
  or per unit consumed as a standard output, not an optional add-on.

## Why this matters in a client conversation

When a client asks "does Costing Standard do unit costing," the accurate answer is: yes, but it's
not a feature you turn on — it's the natural output of having Cost Pools, Resource Towers, and
allocations set up correctly. That's actually a stronger pitch than a bolt-on feature would be: unit
cost accuracy is only as good as the underlying allocation model, so a client asking specifically
about unit costing is really asking about allocation maturity — which is exactly the conversation
that should anchor a TBM engagement's early phases (see the Cost Pool to Resource Tower allocation
brief).

Worth being direct about in scoping: if a prospect's primary ask is a single polished "unit cost
dashboard" with minimal underlying allocation work, that's a mismatch with how this capability
actually works — the dashboard is the easy part, the allocation model underneath it is where the
real effort and value are.

## Source documents

- Costing terminology / glossary (defines Metric, the basis for unit cost) — `02-product-docs/apptio-costing-standard/en/cost-transparency/get-started/costing-terminologies.md`
- Data Centers Overview (concrete unit economics examples) — `02-product-docs/apptio-costing-standard/en/cost-transparency/infra-use-cases/dc-overview.md`
- IT Financials Overview (unit cost benchmarking use case) — `02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/itf-overview.md`