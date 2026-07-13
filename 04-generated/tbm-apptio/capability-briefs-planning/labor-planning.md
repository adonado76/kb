---
concept: "Labor Planning (headcount, fully burdened cost allocation, compensation modeling, confidentiality controls)"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-planning
status: draft
generated_from:
  - 02-product-docs/apptio-planning/en/it-planning/planning/labor-planning.md
  - 02-product-docs/apptio-planning/en/it-planning/planning/manage-labor-allocation-rules.md
  - 02-product-docs/apptio-planning/en/it-planning/planning/configure-working-days.md
  - 02-product-docs/apptio-planning/en/it-planning/planning/labor-summarization.md
  - 02-product-docs/apptio-planning/en/it-planning/planning/plan-labor-compensation.md
  - 02-product-docs/apptio-planning/en/it-planning/planning/hide-sensitive-labor-data.md
  - 02-product-docs/apptio-planning/en/it-planning/planning/set-labor-headcount.md
  - 02-product-docs/apptio-planning/en/it-planning/planning/restrict-access-labor.md
last_updated: "2026-07-05"
---
# Labor Planning — How IBM Apptio Planning Addresses This TBM Capability

## The capability

Labor is consistently the largest cost pool in most IT budgets, and it's also the hardest to
plan accurately: a single headcount line implies a base salary, benefits, overhead, and possibly
bonuses or training costs, all of which need to land on the correct GL accounts and departments,
and all of which change over time as people are hired, promoted, or given raises. TBM addresses
this through **Labor Planning**: modeling headcount, fully burdening it into a true cost, spreading
that cost correctly across time, and protecting sensitive compensation data from
over-exposure while it's being planned collaboratively.

## How Apptio Planning solves it

**Headcount as the entry point.** A labor line captures the org-relevant attributes (Cost
Center, Role, Employee Type — Internal/External, Location, Vendor, optional Employee Name),
Base and Other Compensation, Quantity (headcount), and a Start/End Date. The system auto-generates
a headcount distribution across periods from these inputs, which planners can override.

**Labor Allocation Rules turn a base rate into a fully burdened cost.** Rules define, per
Account, whether the added cost is a **Flat Value**, a **Percent of Base Rate**, or a **Percent
of Other Rate** — this is how benefits, overhead, and burden get layered onto a raw salary
automatically rather than through manual spreadsheet formulas. Rules can also be marked to
exclude from the Fiscal Year total (e.g., cross-charges that shouldn't double-count).

**Amortization method controls how cost — not headcount — spreads across time.** Three (plus
two "fixed period" variants) amortization methods exist: Even Periods (flat monthly spread,
no date proration), Calendar Days (prorated by days in the period), and Working Days
(prorated by a configured working calendar). A subtlety worth internalizing before a client
conversation: **headcount quantity itself is never prorated** — a hire on January 15th still
counts as 1.0 FTE for all of January by default — only the *cost* is prorated, and only under
the Calendar Days or Working Days methods. Getting this distinction wrong is a common source of
confusion when a client is validating the model against their own numbers.

**Working Calendars** (Fixed — hours/month — or Variable — day-of-week plus holidays) are what
the Working Days amortization method references, and multiple calendars can coexist for
different regions or employee types, with one marked as default.

**Plan-level time-effective allocation rules** let a specific plan override the global burden
rate for a period range — for example, modeling a benefits rate that steps from 10% to 14%
across the planning horizon — without touching the shared global reference data other plans
depend on. This is the mechanism that supports genuine multi-year, multi-scenario labor cost
modeling (e.g., "what if benefits load increases 2% next year") without side effects on other
plans.

**Labor Compensation Adjustments** model raises, promotions, and market adjustments as
percentage changes with effective dates, compounding forward and flowing automatically into the
fully burdened cost and departmental allocations — this is the mechanism for merit-cycle
modeling rather than manually re-entering a new base salary.

**Confidentiality controls are layered, not all-or-nothing.** Three separate mechanisms let an
organization dial in exactly how much labor detail different roles can see: (1) **Labor
Summarization Settings** control which dimensions labor costs roll up by in the Summary tab
(Cost Center, Account, and Cost Object are always included; Employee Name and compensation
fields can be excluded from the rollup); (2) **Hide Sensitive Labor Data** hides specific
columns (e.g., Employee Name, Base Compensation) at the row level for users without the "View
Sensitive Columns"/"View Sensitive Financials" permission, while still showing them the labor
row and its fully burdened total; (3) **Restrict Access to Labor Salary Details** goes further,
using a custom role without the `ViewLabor` permission to block an entire user population from
the Labor tab altogether. This three-tier model lets a client match visibility exactly to their
existing HR/Finance confidentiality policy rather than forcing an all-or-nothing choice.

**Headcount Targets** mirror the financial Targets mechanism (top-down goals, Plan vs. Target
KPI comparisons, treemap/waterfall visuals) but track headcount counts specifically rather than
cost — a distinct lever for workforce planning conversations that are about capacity, not just
budget.

## Why this matters in a client conversation

Labor is usually the single cost pool where a client's spreadsheet-based process breaks down
fastest, because fully burdening a raw salary correctly (benefits, overhead, allocation rules) by
hand, for every hire, every year, is exactly the kind of repetitive calculation spreadsheets
handle badly at scale. Leading with the Labor Allocation Rules mechanism — "define the burden
rate once, it applies automatically to every matching labor line" — is usually the fastest way
to make the cost/benefit case for moving off manual formulas.

The confidentiality tiering is worth raising proactively in any banking or financial-services
engagement (Armando's core client base), where HR data governance is typically strict: being
able to show Cost Center Owners a labor cost total without ever exposing individual
compensation figures is often a hard requirement, not a nice-to-have, and having three distinct
mechanisms (summarization, column-hiding, role-blocking) gives enough granularity to match
whatever internal policy the client already has, rather than asking them to change their
governance model to fit the tool.

The headcount-vs-cost proration distinction is worth walking through explicitly during any
proof-of-concept, since it's the single most common "the numbers don't match what I expected"
moment when a client is validating the model against a manually-built comparison.

## Source documents

- Labor Planning Overview — `02-product-docs/apptio-planning/en/it-planning/planning/labor-planning.md`
- Labor Allocation Rules — `02-product-docs/apptio-planning/en/it-planning/planning/manage-labor-allocation-rules.md`
- Working Calendars — `02-product-docs/apptio-planning/en/it-planning/planning/configure-working-days.md`
- Summarize Labor Financials — `02-product-docs/apptio-planning/en/it-planning/planning/labor-summarization.md`
- Labor Compensation Adjustments — `02-product-docs/apptio-planning/en/it-planning/planning/plan-labor-compensation.md`
- Hide Sensitive Labor Data — `02-product-docs/apptio-planning/en/it-planning/planning/hide-sensitive-labor-data.md`
- Labor Headcount Targets — `02-product-docs/apptio-planning/en/it-planning/planning/set-labor-headcount.md`
- Restrict Access to Labor Salary Details — `02-product-docs/apptio-planning/en/it-planning/planning/restrict-access-labor.md`

*Nota: versión en español/portugués se genera en una siguiente pasada, una vez confirmes que este formato sirve para tu caso de uso de RFP.*