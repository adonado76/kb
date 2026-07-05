---
tbm_concept: "Plan Creation & Lifecycle Management"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-planning
status: draft
generated_from:
  - 02-product-docs/apptio-planning/en/it-planning/planning/create-plan.md
  - 02-product-docs/apptio-planning/en/it-planning/planning/manage-plan.md
  - 02-product-docs/apptio-planning/en/it-planning/planning/plan-states.md
  - 02-product-docs/apptio-planning/en/it-planning/planning/plan-folders.md
last_updated: "2026-07-05"
---
# Creating & Managing Plans — How IBM Apptio Planning Addresses This TBM Capability

## The capability

Every budgeting or forecasting cycle needs a governed container: something that defines what
period is being planned, what data it starts from, who can touch it, and when its numbers stop
moving and become the number everyone reports against. Without that container, "the budget" ends
up living in a dozen spreadsheet versions with no single source of truth and no way to tell which
one is authoritative on a given day.

TBM addresses this at the **Plan** level of IT financial management: the discipline of
maintaining a structured, versioned, access-controlled planning instance that can hold both
zero-based budgets and rolling forecasts, and that moves through a defined lifecycle from draft to
locked.

## How Apptio Planning solves it

Apptio Planning models this as a first-class object — the **Plan** — with three mechanisms that
work together:

**Plan types.** A Plan is either a **Budget Plan** (no actuals, every period editable, built from
scratch or reset without history) or a **Forecast Plan** (pre-populated with actuals from Spend
Management for historical periods, with only future periods editable). This distinction matters
operationally: it's what stops someone from accidentally overwriting historical actuals while
adjusting next quarter's projection.

**Plan creation and baselining.** Creating a plan means setting a start year, a duration (up to
ten years), and — critically — an optional **Baseline Reference**, which copies data from an
existing plan. Two supporting controls reduce rework when baselining: choosing whether to carry
over existing Line Item Codes or generate new ones, and an **Auto Fill** option that backfills
missing years when the baseline and new plan don't share the same fiscal calendar. Plans can also
be extended with optional modules — Labor, Contract, Asset, Project, and Project Labor Activity
Planning — enabled per company profile, so a Plan only carries the planning dimensions a given
organization actually needs.

**Plan states.** Every plan moves through three governed states: **New** (visible to admins only,
still being configured), **Open** (editable by Cost Center Owners, with optional email
notifications on open), and **Final** (read-only, locking the approved numbers for reporting).
Finalizing a plan with outstanding Department-level changes gives admins an explicit choice:
submit everything and finalize, or finalize without submitting and exclude what wasn't turned in
— and a Final plan can always be reopened if adjustments are needed later.

**Plan administration.** The Plans page (Available / Archived / All views) supports archiving,
restoring, and a two-stage deletion model — soft delete removes a plan from the UI immediately but
keeps it recoverable via support ticket for two days, after which a hard delete permanently
removes the data. Plan folders let admins organize plans hierarchically and bulk-move plans
between them.

## Why this matters in a client conversation

Most clients coming from spreadsheet-based budgeting don't have an answer to "which version of the
budget is the real one right now" — every stakeholder has a different tab, a different date
stamped in the filename, and no enforced cutoff. The Plan lifecycle (New → Open → Final) gives a
client an actual governance answer to that question: there is exactly one state that is locked and
reportable, and getting there is a deliberate, auditable action rather than someone forgetting to
save.

The Budget vs. Forecast distinction is also a good entry point into a maturity conversation. Many
clients starting out only do annual, from-scratch budgeting (Budget Plans). Introducing Forecast
Plans — which inherit actuals and only leave the future editable — is a natural "next step" pitch
once the client is comfortable with the base Plan structure, without requiring them to adopt every
planning module (Labor, Contract, Asset, Project) on day one. That modular enablement (Company
Profile → toggle modules) supports the same crawl/walk/run phasing referenced elsewhere in this
knowledge base for Costing Standard.

The two-day soft-delete recovery window is worth mentioning proactively in any conversation about
migrating a client's historical spreadsheet-based plans into the tool — it directly answers a
common risk objection ("what if someone deletes a live budget by mistake").

## Source documents

- Creating Plans — `02-product-docs/apptio-planning/en/it-planning/planning/create-plan.md`
- Managing Plans — `02-product-docs/apptio-planning/en/it-planning/planning/manage-plan.md`
- Plan States (New, Open, Final) — `02-product-docs/apptio-planning/en/it-planning/planning/plan-states.md`
- Plan Folders — `02-product-docs/apptio-planning/en/it-planning/planning/plan-folders.md`

*Nota: versión en español/portugués se genera en una siguiente pasada, una vez confirmes que este formato sirve para tu caso de uso de RFP.*