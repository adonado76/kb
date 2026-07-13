---
concept: "Cost Pool to Resource Tower allocation"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-costing-standard
  - apptio-benchmarking
status: draft
generated_from:
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/workbench/cs-labor-mapping.md
  - 02-product-docs/apptio-costing-standard/en/workbench/introduction.md
  - 02-product-docs/apptio-benchmarking/en/it-benchmarking/configuration/map-cost-pools.md
  - 02-product-docs/apptio-benchmarking/en/it-benchmarking/configuration/map-towers.md
last_updated: "2026-07-02"
---
# Cost Pool to Resource Tower Allocation — How IBM Apptio Costing Standard and Benchmarking Address This TBM Capability

## The capability

At the core of every TBM Model is a single operational question: how does raw spend, sitting
in a Cost Pool (Staffing, Hardware, Software & SaaS, Outside Services...), get allocated to the
Technology Resource Towers (Compute, Storage, Network, Application, Data...) that actually
consumed it? Without this step, an organization has categorized spend but has not yet connected
it to the technology that delivers value — the taxonomy exists on paper but not in the data.

## How IBM Apptio Costing Standard covers it

Costing Standard operationalizes this allocation through the **Workbench** — a set of editable,
permission-governed screens that let designated users enrich source data and refine allocation
mappings without needing to touch the underlying model directly. Each mapping report (Labor
Mapping, Vendor Mapping, etc.) follows the same two-tab pattern: a **Data Enrichment** tab to fix
gaps in fields the source system didn't provide (Team, Role, Employee Type, Location), and a
**Data Mapping** tab to actually apportion cost.

The Labor Mapping workbench is the clearest example: each labor resource gets mapped to one or
more IT Resource Towers, Sub-Towers, and an Application ID, with a **Weighting Factor** that lets
a single person's cost be split fractionally across more than one tower — capturing the reality
that most technologists don't work 100% on a single service. A dedicated **Missing Mappings** tab
flags any labor row that hasn't been assigned yet, so nothing silently falls out of the model.

One nuance worth flagging in client conversations: the initial setup of each Workbench component
(installing the CTF component, loading and transforming the source dataset, publishing the ET
Transform file) happens in **TBM Studio** — which is why this capability, as described here,
applies to Costing **Standard**, not Costing Essentials (Essentials does not include self-service
TBM Studio access; see `products-registry.yaml`). Once set up, the day-to-day mapping work itself
happens in the simpler Report View screens, not in Studio.

## How IBM Apptio Benchmarking covers the adjacent capability

Benchmarking depends on this same allocation being done consistently — but adds a second mapping
layer on top: aligning the *customer's own* Cost Pools and Towers to Apptio's **standard**
benchmark taxonomy (8 standard cost pools — External Labor, Facilities & Power, Hardware,
Internal Labor, Outside Services, Software, Telecom, Other; 10 standard towers — Application,
Communication, Compute, Delivery, End User, IT Mgmt, Network, Output, Security & Compliance,
Storage). Without this second mapping, benchmark reports simply won't populate.

An operationally important asymmetry: cost pool mapping is strictly one-to-one (each benchmark
cost pool maps to exactly one customer cost pool), while tower mapping allows one benchmark tower
to map to *many* customer towers — useful when a customer's model is more granular than the
standard, but not the reverse.

## Why this matters in a client conversation

This is the single most common point where a TBM initiative stalls: organizations classify spend
into cost pools correctly, but the mapping to resource towers is done once in a spreadsheet during
implementation and never revisited, so the model drifts from reality within a quarter. The
Workbench's separation of "data enrichment" from "data mapping," plus a dedicated view for
unmapped items, is specifically designed to make this an ongoing, governed process rather than a
one-time project artifact — which is the difference between a TBM Model that stays trustworthy and
one that Finance stops believing within a year.

## Source documents

- Labor Mapping (Costing Standard) — `02-product-docs/apptio-costing-standard/en/cost-transparency/workbench/cs-labor-mapping.md`
- Costing Standard Workbench introduction — `02-product-docs/apptio-costing-standard/en/workbench/introduction.md`
- Map the cost pools (Benchmarking) — `02-product-docs/apptio-benchmarking/en/it-benchmarking/configuration/map-cost-pools.md`
- Map the towers (Benchmarking) — `02-product-docs/apptio-benchmarking/en/it-benchmarking/configuration/map-towers.md`

*Nota: este brief es el primero construido sobre el crosswalk real de TBM. La version en
español/portugues se genera en una siguiente pasada, una vez confirmes que este formato sirve
para tu caso de uso de RFP.*