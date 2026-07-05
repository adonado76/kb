---
tbm_concept: "Integration with Apptio Costing Standard (reference data, actuals, plan publishing — legacy CTI and modern ADM paths)"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-planning
  - apptio-costing-standard
status: draft
generated_from:
  - 02-product-docs/apptio-planning/en/it-planning/planning/configure-ct-support.md
  - 02-product-docs/apptio-planning/en/it-planning/planning/import-publish-actuals.md
  - 02-product-docs/apptio-planning/en/it-planning/planning/import-pl-acost.md
  - 02-product-docs/apptio-planning/en/it-planning/planning/pub-pl-ac.md
  - 02-product-docs/apptio-planning/en/it-planning/planning/integrate-ct.md
  - 02-product-docs/apptio-planning/en/it-planning/planning/cti_panel.md
last_updated: "2026-07-05"
---
# Integrations – Apptio Costing — How IBM Apptio Planning Addresses This TBM Capability

## The capability

Planning (the forward-looking budget/forecast discipline) and Costing Standard (the
actuals-based service costing and TCO discipline) are two different disciplines within the same
TBM practice, but they need to speak the same language: the same chart of accounts, the same cost
center/department hierarchy, the same projects. Without an integration, an organization ends up
maintaining reference data twice and manually re-keying actuals into the planning tool every
period — both a real effort cost and a real source of drift between what Planning shows as
budget-vs-actual and what Costing Standard reports as the true run cost. This capability
addresses that by connecting the two products for reference data, monthly actuals, and published
plans.

## How Apptio Planning solves it

**Two generations of the integration coexist.** The legacy **Cost Transparency Integration
(CTI)** connects directly to a Costing Standard instance via Token authentication (recommended,
R12+) or Service Account authentication (legacy, required only for TBM Studio v11), and is
managed either through Settings → Cost Transparency Integration or, since Planning 2.78, through
a consolidated **CTI Panel** that centralizes Configure / Import Actuals / Import Reference Data
/ Publish / Status into one place with one-click actions. The modern path uses **Automated Data
Management (ADM)**, Apptio's shared cross-product data exchange platform, for the Projects List
specifically — importing or publishing plan-level projects through an Entity Mapping
configuration rather than a direct CTI connection. Knowing which path a given client's
environment uses (CTI legacy vs. ADM) matters for scoping an integration engagement correctly.

**Reference data reconciliation is not automatic — it requires deliberate mapping.** Costing
Standard and Planning don't share an identical data model: Costing Standard's Account reference
data lacks Account Group, Account Subgroup, Fixed/Variable, and Discretionary/Non-Discretionary
dimensions that Planning's reporting depends on; its Department reference data lacks Owner and
Budget Owner. These gaps have to be explicitly filled in as part of setup, not assumed away — a
concrete scoping detail for any integration engagement estimate.

**Actuals flow one direction, with real operational cadence implications.** Actuals import
monthly (whether via legacy CTI's "Import Actuals" action or the newer per-Spend-Management-month
workflow), and multi-currency actuals require the *same* currency rate table on both sides of
the integration — a detail worth flagging early to avoid a reconciliation mismatch discovered
only after go-live.

**Plan publishing is deliberately constrained, not open-ended.** Costing Standard's data model
can hold only one active budget and one active forecast at a time — so "publish to Costing
Standard" isn't a bulk multi-scenario export; it's a single, chosen plan being pushed per type,
selected explicitly from Planning before each publish job. This constraint is worth setting
expectations around early, since clients running many parallel what-if scenarios in Planning need
to understand that only one lands in Costing Standard at a time.

**The Labor-specific data mapping is its own configuration exercise.** Because Costing Standard's
"Cost Object" concept and Planning's "Cost Center" concept don't map one-to-one (a Cost Object in
Costing Standard can represent a department, project, service, or business unit), labor budget and
forecast data requires explicit formula-based translation steps (e.g., `Cost Center = Cost
Object`, lookups for Cost Center Owner) configured in TBM Studio as part of the ITPF Labor
integration components — this is genuine consulting-delivery work, not a toggle.

## Why this matters in a client conversation

This integration is the concrete answer to a very common client question once they've adopted
both products: "does the budget I build in Planning actually reconcile with what Costing Standard
says we spent?" Framing the actuals import, currency rate alignment, and single
budget/forecast-at-a-time constraint honestly up front avoids a credibility problem later — this
is genuinely integration work with real reference-data reconciliation effort, not a plug-and-play
checkbox, and setting that expectation during scoping protects the engagement.

The reference-data gap table (Account and Department dimensions missing from Costing Standard's
native model) is a good, specific example to have ready in a technical discovery conversation —
it demonstrates practitioner-level familiarity with the actual data model mismatch rather than a
generic "yes, they integrate" answer.

The ADM vs. legacy CTI distinction is also worth surfacing directly with clients evaluating the
Apptio portfolio broadly (Costing, Planning, Cloudability), since ADM is the platform-level,
forward direction Apptio is investing in for cross-product data exchange, while legacy CTI is
the path an established client may already have in place.

## Source documents

- Configure Apptio Costing Integration Datasets — `02-product-docs/apptio-planning/en/it-planning/planning/configure-ct-support.md`
- Import Actuals — `02-product-docs/apptio-planning/en/it-planning/planning/import-publish-actuals.md`
- Import Projects List from Apptio Costing — `02-product-docs/apptio-planning/en/it-planning/planning/import-pl-acost.md`
- Publish Projects List to Apptio Costing — `02-product-docs/apptio-planning/en/it-planning/planning/pub-pl-ac.md`
- Cost Transparency Integration (Legacy) — `02-product-docs/apptio-planning/en/it-planning/planning/integrate-ct.md`
- Working with Cost Transparency Integration Panel — `02-product-docs/apptio-planning/en/it-planning/planning/cti_panel.md`

*Nota: versión en español/portugués se genera en una siguiente pasada, una vez confirmes que este formato sirve para tu caso de uso de RFP.*