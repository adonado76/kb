---
concept: "Cost Pools & Resource Towers — IT Financials transparency, budget/forecast variance"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-costing-standard
status: draft
generated_from:
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/get-started/intro-ibm-cost.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/itf-overview.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/rt-overview.md
last_updated: "2026-07-02"
---
# Cost Pools & Resource Towers: Cost Transparency, Budgets & Forecast — How IBM Apptio Costing Standard Addresses This TBM Capability

## The capability

The Cost Pool and Resource Tower layers of the TBM Taxonomy are two different lenses on the
same spend, and organizations need both to run a defensible budget cycle. Cost Pools answer *what*
was spent (labor, software, hardware...); Resource Towers answer *where it went functionally*
(Compute, Applications, End User...). Getting variance analysis right — actuals vs. budget vs.
forecast — requires being able to slice the same number both ways without the two views drifting
out of sync.

## How IBM Apptio Costing Standard covers it

Costing Standard delivers this through two complementary capabilities, both under its Financial
Use Cases:

**IT Financials** consolidates OpEx and CapEx visibility across cost centers and account groups,
and is explicit about its budget/forecast role: it "standardizes how financial data is reviewed,
enabling consistent evaluation of actuals, budget, and forecast across all technology domains."
Its named use cases include Budget Variance Analysis (comparing actuals to budget and forecast to
catch deviations early), Transaction-Level Insights (drilling into GL transactions to validate
classification), and Cost Pool Analysis — explicitly described as analyzing "OpEx distribution by
Cost Pools (standard Technology Business Management (TBM) and Apptio TBM Unified Model (ATUM)
categories)."

**Resource Towers** takes the same underlying spend and reorganizes it functionally. The
documentation draws the distinction precisely: "While Cost Pools classify costs by what they are
(for example, labor or software), Resource Towers classify costs by where and how they support the
technology stack (for example, Applications, Platforms, End User)." This view supports
period-over-period spend monitoring, budget variance *by tower and sub-tower* (a finer grain than
the IT Financials view), and identification of primary cost drivers within each functional area.

Together, these two capabilities are effectively the operational front-end for the TBM Taxonomy's
Cost Pool and Resource Tower layers — not just a data model underneath the platform, but reporting
built specifically around that structure.

## Why this matters in a client conversation

Budget cycles fail most often not because the numbers are wrong, but because two stakeholders
looking at the "same" spend from different angles (Finance's expense-type view vs. IT's functional
view) can't reconcile what they're seeing without a lot of manual translation. This capability pair
is the direct answer to that friction — Cost Pool Analysis and Resource Tower Analysis are drawing
from the same underlying allocation, so a Finance-oriented budget variance conversation and an
IT-oriented tower spend conversation are provably talking about the same dollars.

The mention of Accruals Management as a named custom use case is also worth flagging for clients
with a disciplined month-end close process — it signals this isn't just a reporting layer, it can
sit inside the actual close cadence.

## Source documents

- Introduction to IBM Apptio Costing — `02-product-docs/apptio-costing-standard/en/cost-transparency/get-started/intro-ibm-cost.md`
- IT Financials Overview — `02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/itf-overview.md`
- Resource Towers Overview — `02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/rt-overview.md`