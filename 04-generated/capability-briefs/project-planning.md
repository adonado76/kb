---
tbm_concept: "Project / Integrated Investment Planning (IIP) — Build vs. Run TCO, project governance and access"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-planning
status: draft
generated_from:
  - 02-product-docs/apptio-planning/en/it-planning/planning/iip/gs-integrated-investment-planning.md
  - 02-product-docs/apptio-planning/en/it-planning/planning/iip/manage-iip-data-ref.md
  - 02-product-docs/apptio-planning/en/it-planning/planning/iip/project-list-document.md
  - 02-product-docs/apptio-planning/en/it-planning/planning/iip/project-level-access-control.md
  - 02-product-docs/apptio-planning/en/it-planning/planning/iip/asset-depreciation-cost-center.md
  - 02-product-docs/apptio-planning/en/it-planning/planning/iip/delegate-contract-costs.md
last_updated: "2026-07-05"
---
# Project Planning (Integrated Investment Planning) — How IBM Apptio Planning Addresses This TBM Capability

## The capability

Technology investments — new platforms, modernization initiatives, portfolio epics — have a cost
story that spans two very different phases: **Build** (the delivery cost of getting the
investment live) and **Run** (the ongoing operational cost of keeping it running afterward).
Planning these separately, without a structural link between them, hides the true multi-year
Total Cost of Ownership of an investment decision — a common failure mode where a project's
"cost" is reported as its build budget alone, with the Run-phase impact on future operational
budgets never surfacing until it actually lands. TBM addresses this through **Integrated
Investment Planning (IIP)**: a first-class Project dimension that any budget line — labor,
contract, asset, or general expense — can be tagged with, spanning both lifecycle phases.

## How Apptio Planning solves it

**Project as a cross-cutting dimension, not a separate plan.** Rather than maintaining Build and
Run as disconnected planning exercises, IIP lets any expense line (Labor, Contract, Asset, Labor
Activity, or Other) carry a Project tag. This means the same reporting dimension that tracks a
project's delivery cost can also carry forward to the resources it consumes once it transitions
to steady-state operations — Build and Run costs for the same investment stay traceable to one
another rather than living in disconnected models.

**Two-tier project hierarchy.** Projects (leaf-level investments) roll up to optional Project
Groups (portfolios, value streams, or strategic programs), giving PMO and portfolio reporting a
natural rollup structure without forcing a flat, unstructured project list.

**Global vs. plan-level project lists — a deliberate design choice for stability.** The global
Project reference data is the system-wide source of truth (used to validate actuals uploads), but
each plan maintains its **own local copy** of the project list, created at plan creation and
editable independently. This is a subtle but important governance mechanism: it means an admin
adding, removing, or renaming projects globally mid-cycle does **not** silently disrupt every
open plan — synchronization is an explicit, reviewable action (`Update Project Data`) that shows
an impact summary (lines to be deleted/updated) before being applied, rather than an automatic,
invisible propagation.

**Three access-control patterns cover the realistic range of budget ownership models.** (1)
Project Managers own all costs for dedicated project-only cost centers; (2) Cost Center Owners
manage both operational and project spend for their department with no separation (with the
explicit limitation that owners can't be restricted to project-only view in this model); (3) a
hybrid model where Department Owners see everything but Project Managers are filtered to only
their assigned project's lines, useful when project delivery teams contribute costs across
multiple departments' cost centers without being granted full departmental visibility.

**Delegation mirrors the same pattern across Contracts and Assets, but with different mechanics.**
Contract delegation splits cost by date — the original cost center owns costs before a Delegation
Start Date, the delegated cost center owns everything from that date forward — modeling a clean
Build-to-Run handoff at a specific point in time. Asset delegation, by contrast, is all-or-nothing:
the full depreciation stream (not the purchase) goes entirely to one Depreciation Cost Center,
with no partial or date-based split. This distinction is worth knowing before promising a client
a specific delegation behavior for asset costs.

## Why this matters in a client conversation

IIP is the capability that turns "what did this project cost to build" into "what is this
investment costing the organization over its full life" — a distinction that matters enormously
in a banking/insurance context, where large modernization or platform investments are exactly the
kind of decision that gets scrutinized on multi-year TCO, not just initial delivery budget. Being
able to show a project's Build cost transitioning into a specific Run-phase operational cost
center, on a specific date, is a concrete way to answer "what happens to the budget after this
project ships" — a question that's often answered with hand-waving in spreadsheet-based
processes.

The three access-control patterns are a useful diagnostic tool early in a sales conversation: ask
the client which of the three org structures they actually have (dedicated project departments,
unified Cost Center ownership, or hybrid Department Owner + Project Manager), and you can point
directly at the corresponding configuration rather than presenting IIP as one-size-fits-all.

The explicit, reviewable Global-to-Plan project sync (rather than silent auto-propagation) is
worth flagging to any client whose PMO restructures its project portfolio mid-year — a common
occurrence — since it directly addresses the fear of "will changing our project list break every
open budget."

## Source documents

- Project Planning Overview — `02-product-docs/apptio-planning/en/it-planning/planning/iip/gs-integrated-investment-planning.md`
- Configure Projects — `02-product-docs/apptio-planning/en/it-planning/planning/iip/manage-iip-data-ref.md`
- Manage Projects — `02-product-docs/apptio-planning/en/it-planning/planning/iip/project-list-document.md`
- Project Permissions — `02-product-docs/apptio-planning/en/it-planning/planning/iip/project-level-access-control.md`
- Delegate Asset Costs — `02-product-docs/apptio-planning/en/it-planning/planning/iip/asset-depreciation-cost-center.md`
- Delegate Contract Costs — `02-product-docs/apptio-planning/en/it-planning/planning/iip/delegate-contract-costs.md`

*Nota: versión en español/portugués se genera en una siguiente pasada, una vez confirmes que este formato sirve para tu caso de uso de RFP.*