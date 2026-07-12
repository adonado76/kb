---
tbm_concept: "Showback / Chargeback — cost transparency and allocation basis"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-costing-standard
status: draft
generated_from:
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/solution-uc/bu-overview.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/solution-uc/services-overview.md
last_updated: "2026-07-02"
---
# Showback / Chargeback — How IBM Apptio Costing Standard Addresses This TBM Capability

## The capability

Showback and chargeback sit at the point where the TBM Taxonomy's Solutions layer meets the
Consumers layer: once cost has been allocated to a Solution (a service, an application, a
business unit), the organization needs to *show* that cost to the business consumer who
generated it — either as pure transparency (showback) or as an actual bill (chargeback). Both
depend on the same prerequisite: a complete, trustworthy, fully burdened cost allocation. Neither
is possible if the underlying Cost Pool → Tower → Solution allocation is incomplete or stale.

## How IBM Apptio Costing Standard covers it

Costing Standard delivers the **transparency half** of this capability through two purpose-built
solution use cases:

**Business Unit views** consolidate costs from applications, services, and projects into a
single picture of what each business unit consumes — supporting what the documentation
explicitly calls "TCO Showback": total costs, volumes, users, and unit costs presented together
to support "informed investment decisions and constructive cost discussions." Allocation methods
(direct and indirect) are standardized so the numbers are defensible in front of a business
leader who will naturally push back on them.

**Services views** do the same at the service/solution-offering level — consolidating
infrastructure, applications, labor, vendor, and platform costs into a single fully burdened TCO
per service, explicitly to "support service-based showback and chargeback." A named use case,
"Communicate IT Spend (Showback)," exists specifically to give business stakeholders transparent
visibility into what a service costs and who's using it.

## An important boundary to be precise about in client conversations

Costing Standard's documentation uses "showback and chargeback" together frequently, but the two
are not functionally identical, and it matters for scoping a proposal correctly:

- **Showback** — Costing Standard delivers this natively: the reports, unit costs, and
  drill/trace views described above are the showback capability itself.
- **Chargeback** — in the strict sense of generating an actual bill or a journal entry that
  posts to a business unit's books, that is delivered by **Apptio Billing (BOIT)**, not Costing
  Standard (see the separate capability brief on Bill of IT). Costing Standard provides the
  allocation basis and the "IT Finance... supports showback and chargeback discussions" role
  the documentation names — it is the upstream system of record, not the invoicing engine.

In an RFP, this distinction is worth making explicit: a client asking for "chargeback" in the
formal, billable sense needs Costing Standard **plus** Billing, not Costing Standard alone.

## Why this matters in a client conversation

The persona list here is telling: Business Unit Leaders, Department Leaders, Business
Relationship Managers, IT Finance, and Solution Owners are all named explicitly as consumers of
these views — meaning this capability is designed to be read by non-technical stakeholders, not
just modeled by IT Finance analysts. That's the real value proposition to lead with: Costing
Standard isn't just an internal costing engine, it's built to survive contact with a business
leader who will ask "why does my department cost this much?" and expects a defensible, drillable
answer in the same sitting.

## Source documents

- Business Unit Overview — `02-product-docs/apptio-costing-standard/en/cost-transparency/solution-uc/bu-overview.md`
- Services Overview — `02-product-docs/apptio-costing-standard/en/cost-transparency/solution-uc/services-overview.md`

*Nota: este brief cubre solo Apptio Costing Standard, por decision explicita. El brief separado
de Bill of IT (Apptio Billing) cubre el chargeback formal/facturado -- ver
`04-generated/capability-briefs/` cuando se genere. La version en español/portugues se genera en
una siguiente pasada.*