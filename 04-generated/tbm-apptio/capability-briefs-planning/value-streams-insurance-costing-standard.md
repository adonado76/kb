---
concept: "Value Streams — Insurance"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-costing-standard
status: draft
generated_from:
  - "01-practice-sources/tbm-council/HLProcessing_T3737 Insurance StratComm Taxonomy Extension Graphic (1).pdf"
last_updated: "2026-07-02"
---
# Value Streams for Insurance — How IBM Apptio Costing Standard Supports This Sector Extension

## A note on source depth

Unlike the Banking Extension (a detailed service taxonomy with definitions, metrics, and sample
offerings per service), the source for this brief is the TBM Council's **Insurance TBM Taxonomy
Extension v2.0** — an official structural graphic, not a narrative document. It defines category
labels and their layering within the taxonomy, but not the per-service definitions, metrics, or
example vendors that the Banking Extension provides. This brief is scoped accordingly: it
describes the structure accurately and maps it to Costing Standard's mechanism, without inventing
narrative detail the source doesn't contain.

## The sector extension structure

The Insurance Extension defines seven **Insurance Industry Application Service** categories, each
with named sub-services: **Sales & Marketing** (Marketing, Distribution, Lead Management, Policy
Acquisition/Sales), **Underwriting** (Evaluation, Quoting/Pricing, Issuance, Reservance),
**Policy Servicing** (Policy Management, Loans and Rollovers), **Claims** (Strategy and Planning,
Lifecycle Management, Claims Management), **Customer Management** (Customer Service,
Billing/Payments, Customer Analytics, Customer Success), **Investments** (Insurer's Investment
Management, Insured's Investment Management), and **Product** (Product Development, Product
Management).

Alongside these, the extension defines three **Shared Application Service** categories common
across insurers: **Finance** (FP&A, Treasury, A/P/A/R, Collections, Tax, Controllers), **HR**
(Payroll & Benefits, Talent Management, Training), and **GLCR** — Governance, Legal, Compliance &
Risk (Internal Audit, Compliance, Risk Management, Business Continuity, Legal, Regulatory).

Notably, the extension also defines **who the customer is** per category — for example,
Underwriting's customer is the Insured and Third-party Administrators; Investments' customer
depends on product type (Insured for retirement products, or the Insurer's own Investment
Management function). This customer dimension is structurally the same "who consumes this" data
the TBM Taxonomy's Consumer layer requires generically.

Structurally, the extension sits in the same taxonomy stack every TBM model uses: **Business
Capabilities → Business Application Services → IT Towers → Cost Pools** — meaning it's an
extension at the Solutions/capability layer, not a replacement for the standard Cost Pool or
Resource Tower layers already documented in `tbm-taxonomy-v5.yaml`.

## How IBM Apptio Costing Standard supports this taxonomy

Each of the seven Insurance Application Service categories (and their sub-services) maps onto
Costing Standard's Solution Type/Category/Name hierarchy the same way the Banking Extension's
services do:

- **Claims**, as a named category with its own sub-services (Strategy and Planning, Lifecycle
  Management, Claims Management), is a natural fit for Costing Standard's Product or Service TCO
  capability — an insurer wanting to know "what does it cost us to process a claim end-to-end" is
  asking exactly the fully-burdened-TCO question those capabilities already answer, scoped to this
  named value stream.
- The **Shared Application Services** (Finance, HR, GLCR) map onto the same Shared & Corporate
  Solution Type already defined in the core TBM Taxonomy (`tbm-taxonomy-v5.yaml`) — meaning these
  don't require insurance-specific configuration at all, only the sector-specific application
  categories do.
- The extension's explicit customer dimension per category is the structural input for
  Costing Standard's showback/chargeback capability (documented separately) — knowing that
  Underwriting serves the Insured and Third-party Administrators, for example, is what determines
  who a showback report for that value stream should actually be presented to.

## Why this matters in a client conversation

This gives an insurance client the same starting-point advantage a banking client gets from the
Banking Extension — a real, TBM Council-published taxonomy for their sector's application
services, rather than a generic technology taxonomy that has to be manually mapped to insurance
concepts from scratch. Claims and Underwriting in particular are strong candidates to lead with in
an early-adoption conversation, since both are widely understood as cost centers with real
optimization pressure across the industry.

An honest scoping note, given the source material itself: because this extension is a structural
graphic rather than a detailed service taxonomy, an actual implementation will require the client
and delivery team to jointly define the specific offerings, metrics, and allocation logic within
each category — the extension establishes *what the categories are*, not *how to cost them*, which
is a heavier lift than the Banking Extension's more prescriptive starting point.

## Source documents

- Insurance TBM Taxonomy Extension v2.0 (TBM Council, Insurance Strategy Community, 2022) — `01-practice-sources/tbm-council/HLProcessing_T3737 Insurance StratComm Taxonomy Extension Graphic (1).pdf`
- Cross-referenced Costing Standard capabilities: see `value-streams-general-costing-standard.md`,
  `showback-chargeback-costing-standard.md`.