---
concept: "IT Financials — CapEx & OpEx consolidated visibility"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-costing-standard
status: draft
generated_from:
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/itf-overview.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/fa-overview.md
last_updated: "2026-07-02"
---
# IT Financials: CapEx & OpEx — How IBM Apptio Costing Standard Addresses This TBM Capability

## The capability

Every TBM Taxonomy Cost Pool distinguishes Operating Expense from Capital Expense, and that
distinction isn't just an accounting formality — it drives how spend gets recognized, depreciated,
and reported to the business. An organization that can't cleanly separate and reconcile OpEx and
CapEx across its technology estate can't produce a defensible financial picture for the CFO, no
matter how good its underlying allocation model is.

## How IBM Apptio Costing Standard covers it

Two complementary capabilities cover this ground:

**IT Financials** consolidates OpEx and CapEx visibility across cost centers and account groups,
built specifically to support "consistent evaluation of actuals, budget, and forecast across all
technology domains." Its named use cases go beyond simple spend visibility: **Budget Variance
Analysis** compares actuals to budget and forecast to catch deviations early; **Transaction-Level
Insights** lets an analyst drill into general-ledger transactions directly, to "validate spend
classification and strengthen cost controls" — a direct answer to the recurring audit question of
whether a given cost was actually classified correctly as OpEx or CapEx in the first place;
**Spend Reduction Analysis** separates fixed from variable spend to find run-rate reduction
opportunities; and **Cost Pool Analysis** benchmarks OpEx distribution against revenue and
per-user metrics using the standard TBM/ATUM cost pool categories.

**Fixed Assets** picks up the capital side specifically: capital cost, depreciation, utilization,
and lifecycle status for IT assets. Its core use case, **Depreciation Management**, tracks
"capital cost, monthly depreciation, and remaining depreciation of IT assets to support accurate
financial reporting and cost allocation" — the mechanism by which a CapEx purchase gets correctly
recognized as OpEx-equivalent spend over its useful life inside the cost model (the same
depreciation/amortization treatment the TBM Taxonomy's Cost Pool layer defines). A custom use
case, Asset Lifecycle Management, extends this to track assets through acquisition, aging, and
end-of-life — connecting the financial view to a practical retirement/replacement planning
conversation.

## Why this matters in a client conversation

CapEx/OpEx confusion is one of the most common reasons a TBM Model loses Finance's trust early:
if capitalized spend isn't depreciated consistently and flowed through the model correctly, TCO
numbers for applications or services will be systematically wrong in ways that are hard to
diagnose after the fact — a project that was mostly capital labor will look artificially cheap in
its first year and then jump the following year as depreciation kicks in, unless that treatment
is handled deliberately from the start.

Leading with this capability in an early-adoption conversation is also a credibility move with
Finance specifically: **Transaction-Level Insights** — the ability to drill to the GL transaction
behind a number — is the kind of feature that turns a skeptical controller into an advocate,
because it means the model isn't a black box asking them to trust aggregated numbers on faith.

An honest scoping note worth carrying into a proposal: Fixed Assets' out-of-the-box use case list
is intentionally narrow (Depreciation Management is the only supported out-of-the-box use case
named) — asset lifecycle management beyond depreciation tracking is explicitly a **custom** use
case, meaning it typically requires configuration effort rather than being available immediately.

## Source documents

- IT Financials Overview — `02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/itf-overview.md`
- Fixed Assets Overview — `02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/fa-overview.md`