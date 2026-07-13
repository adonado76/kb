---
concept: "Variance Analysis (forecast-to-baseline comparison, thresholded exception review, audit trail)"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-planning
status: draft
generated_from:
  - 02-product-docs/apptio-planning/en/it-planning/planning/analyze-budget-variance.md
last_updated: "2026-07-05"
---
# Variance Analysis — How IBM Apptio Planning Addresses This TBM Capability

## The capability

A forecast is only useful if the organization can explain why actuals diverge from it — and
"explain" needs to mean something more rigorous than an ad-hoc conversation at month-end.
Without a structured process, variance explanation tends to happen inconsistently: some
departments document why they're over or under budget, others don't, and there's no durable
record for audit or for next cycle's planning assumptions. TBM addresses this through **Variance
Analysis**: comparing a forecast against a baseline, flagging only the differences that actually
matter, and building a structured, exportable commentary trail explaining the drivers.

## How Apptio Planning solves it

**Thresholds, not blanket review, focus the effort.** Rather than requiring commentary on every
line item, Variance Analysis is configured with a currency threshold, a percentage threshold, and
an AND/OR operator combining them — so only Account Categories whose variance genuinely crosses
the bar get flagged for explanation. This is a deliberate design choice: it keeps the review
burden proportional to materiality instead of turning variance review into a box-checking
exercise across thousands of immaterial line items.

**Variance is analyzed at the Account Category level, not raw GL account level.** GL Accounts are
first grouped into Account Categories (a configured rollup), and variance thresholds apply at
that grouped level — giving Finance a level of granularity that's meaningful for a variance
conversation without drowning reviewers in per-account noise.

**Configurable comparison basis and alignment.** A Variance Analysis compares the current
forecast against any non-archived plan (budget, prior forecast, etc.), over a chosen comparison
period, using either Matching Fiscal Year or Plan Start Year alignment — the same alignment
concept used elsewhere in Comparisons and Targets, kept consistent across the product.

**Drivers plus free-form commentary build a genuine audit trail.** Each flagged variance is
assigned one or more predefined **Variance Drivers** (e.g., project timing, accounting timing,
unplanned spend) plus a free-text explanation. Once every flagged variance has both a driver and
an explanation, the analysis's status flag turns green — giving a Budget Process Owner a visual,
binary signal of whether the review cycle is actually complete, rather than having to manually
check each line.

**Refreshable without losing structure, but not silently.** As new actuals or forecast values
come in, the underlying variance table can be refreshed (`Update Variance Analysis`), which shows
which line items are affected before applying — but explicitly warns that variance drivers and
explanations may be removed if the underlying variance has changed, since a driver assigned to a
$50K variance may no longer be valid once that variance becomes $5K.

**Export supports downstream reporting.** Completed commentary — drivers, explanations, and the
underlying variance records — exports to CSV for integration with other reporting tools, and a
Dashboard treemap view breaks down spend variances by driver and department for a portfolio-level
view.

## Why this matters in a client conversation

Variance Analysis is a strong answer to a very common Finance complaint: "we do variance review
every month, but it's inconsistent across departments and we have no record of why we approved
what we approved." The threshold-based flagging plus the green/red completion status gives a
Budget Process Owner an actual governance mechanism — not everyone reviewing everything, but
nobody being able to silently skip a material variance either.

The driver taxonomy (project timing, accounting timing, unplanned spend, etc., all
client-configurable) is worth positioning as a light-touch categorization layer that turns
free-text variance commentary — which is hard to aggregate or trend — into structured data that
can be rolled up and reported on across the whole variance dataset (e.g., "how much of this
quarter's total variance was accounting timing vs. genuinely unplanned spend").

The explicit warning that refreshing a variance analysis can clear existing explanations is worth
raising proactively during any conversation about frequency of forecast updates — a client
running very frequent forecast refreshes will want to understand that variance commentary isn't
necessarily permanent once assigned, and may want to time their variance review cadence
accordingly.

## Source documents

- Variance Analysis Overview — `02-product-docs/apptio-planning/en/it-planning/planning/analyze-budget-variance.md`

*Nota: versión en español/portugués se genera en una siguiente pasada, una vez confirmes que este formato sirve para tu caso de uso de RFP.*