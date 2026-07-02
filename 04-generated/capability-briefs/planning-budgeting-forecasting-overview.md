---
tbm_concept: "Apptio Planning — collaborative budgeting, forecasting, and investment planning"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-planning
status: draft
generated_from:
  - 02-product-docs/apptio-planning/en/it-planning/planning/intro-planning.md
  - 02-product-docs/apptio-planning/en/it-planning/planning/adm/adm_overview.md
last_updated: "2026-07-02"
---
# Apptio Planning: Budgeting & Forecasting — Core Capability Overview

## The capability

Costing Standard (documented extensively elsewhere in this knowledge base) answers "what did
technology actually cost." Planning answers the forward-looking half of the same question: what
should it cost going forward, who's accountable for that plan, and how does the organization
govern changes to it collaboratively across Technology, Finance, and Business stakeholders.

## How IBM Apptio Planning covers it

Apptio Planning is described directly as "a collaborative financial planning and forecasting
solution designed for technology, finance, and business teams to create, manage, and analyze
budgets, forecasts, and investment plans with transparency and control." Its core capability set
spans the full planning lifecycle:

- **Budgeting & Forecasting** — governed by Plan States, which control "who can access the plan,
  what actions can be taken, and when data is locked for reporting," ensuring version control
  during the planning cycle rather than parallel spreadsheet versions circulating uncontrolled.
- **Labor Planning** — modeling staffing needs (salaries, benefits, taxes) and assigning costs to
  departments, aligned with workforce strategy.
- **Contract Planning** — budgeting and forecasting vendor/supplier contracts with support for
  multiple amortization methods, giving visibility into fixed and recurring obligations ahead of
  renewal decisions.
- **Asset Planning** — capital investment planning for fixed assets with configurable
  depreciation schedules — the forward-looking counterpart to Costing Standard's Fixed Assets
  capability (documented separately).
- **Project Planning** and **Project Labor Activity Planning** — covered in depth in the
  Integrated Investment Planning brief.
- **Variance Analysis** — comparing a current forecast against a baseline (budget or prior
  forecast) to identify significant differences and build a "commentary trail that explains the
  drivers behind variances" — turning variance reporting into a documented narrative, not just a
  number.
- **Workflows & Collaboration** — configurable approval workflows for submit/review/approve/return
  cycles, with role-based user permissions and data-level security.
- **Analytics & Reporting** — built-in KPI dashboards for exploring financial performance and
  uncovering trends.

**Integration with Costing Standard**, via **Automated Data Management (ADM)**, is a
foundational connective capability rather than an optional add-on: it "enables automated sharing
of data from Costing... to Planning" and supports importing plan data on-demand into a specific
plan — meaning Planning's forecasts and Costing Standard's actuals stay reconciled without manual
data reentry between the two products.

## Why this matters in a client conversation

The Variance Analysis "commentary trail" detail is worth calling out specifically in early
conversations: it's the difference between a budget variance report that shows a number moved and
one that documents *why* it moved — the latter is what survives a CFO review without follow-up
meetings. Combined with Plan States' governed lifecycle, Planning is positioned to replace the
common failure mode of budget cycles run in disconnected spreadsheets with no audit trail of who
changed what, when, or why.

The ADM integration is also a meaningful differentiator to lead with for any client already
running Costing Standard: Planning isn't a separate system requiring parallel data entry, it's
designed to consume Costing Standard's actuals directly — closing the loop between "what we
planned" and "what we spent" without a manual reconciliation step.

## Source documents

- Introduction to Apptio Planning — `02-product-docs/apptio-planning/en/it-planning/planning/intro-planning.md`
- ADM Overview — `02-product-docs/apptio-planning/en/it-planning/planning/adm/adm_overview.md`