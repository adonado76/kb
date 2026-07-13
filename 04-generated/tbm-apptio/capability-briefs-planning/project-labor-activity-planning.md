---
concept: "Project Labor Activity Planning (effort allocation, cross-charging, capacity analysis)"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-planning
status: draft
generated_from:
  - 02-product-docs/apptio-planning/en/it-planning/planning/iip/labor-resource-planning.md
  - 02-product-docs/apptio-planning/en/it-planning/planning/iip/manage-project-labor-role-data-ref.md
  - 02-product-docs/apptio-planning/en/it-planning/planning/iip/manage-labor-activity-type-data-ref.md
  - 02-product-docs/apptio-planning/en/it-planning/planning/iip/manage-over-under-allocation.md
  - 02-product-docs/apptio-planning/en/it-planning/planning/iip/unique-labor-resource-identification.md
last_updated: "2026-07-05"
---
# Project Labor Activity Planning — How IBM Apptio Planning Addresses This TBM Capability

## The capability

Labor is typically the largest cost driver on a technology investment, but a resource's HR role
(e.g., "Software Developer 2") rarely maps cleanly to how that effort should be priced, charged,
or credited when the person is actually working on a specific project rather than their home
department's day-to-day operations. This capability extends the Labor Planning foundation (see
the Labor Planning brief) specifically into the project context: translating HR-side headcount
into project-facing effort, hours, and cross-charges — and surfacing whether the organization has
enough real capacity to deliver what's been committed.

## How Apptio Planning solves it

**A two-step model separates "who is this person for project purposes" from "how much effort are
they contributing."** Step one, in the Labor tab, assigns a resource a **Project Labor Role**
(e.g., "Developer") distinct from their HR role, which auto-populates a **Project Labor Rate**
(overridable). Step two, in the Labor Activity tab, allocates that resource's effort — by role or
by named individual — to a specific project, in hours or FTE, tagged with an **Activity Type**.
Only resources that have been given a Project Labor Role in step one become selectable in step
two, which enforces that project labor planning always traces back to a real labor line.

**Labor Activity Type drives the cross-charge accounting, not just a label.** Each Activity Type
maps a **Charge Account** (the providing department cost center, credited) to a
**Cross-Charge Account** (the consuming project cost center, debited), and flags whether that
activity's cost **is capitalizable** — directly relevant to correctly separating CapEx-eligible
project labor (e.g., development) from opex labor (e.g., ongoing support) within the same
project. One Activity Type can be marked default, so effort entry doesn't require selecting it
every time for the common case.

**Over/under-allocation analysis turns capacity into a visible constraint, not an assumption.**
Once Labor Activity is enabled, an organization chooses to either **prevent** over-allocation
outright or **allow** it within a defined percentage threshold. A visual allocation analysis
(available in the New View) color-codes each resource's monthly allocation — blue for
under-allo