---
concept: "Mainframe TCO, consumption, and NX Reports"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-costing-standard
status: draft
generated_from:
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/infra-use-cases/mf-overview.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/mf-nx-report.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/mainframe-tco-nx.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/mainframe-usage-nx.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/mainframe-nx-consumption-review.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/mainframe-applications-nx.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/mainframe-nx-analysis.md
last_updated: "2026-07-04"
---
# Mainframe — How IBM Apptio Costing Standard Addresses This TBM Capability

## The capability

Despite the shift toward modern architectures, mainframe remains the platform of choice for high-volume, high-availability core business processing. IBM Apptio Mainframe TCO delivers a clear, defensible view of mainframe cost and utilization, addressing historical challenges of limited transparency, unclear unit economics, and inconsistent cost allocation.

Three personas anchor this capability: IT Finance (mainframe financial governance), Application Owners (monitor application-level consumption), and Infrastructure and Platform Owners. Four use cases: Mainframe Total Cost of Ownership (consolidate hardware, software, labor, and external services into a single view), Mainframe Consumption and Unit-Cost Analysis (analyze consumption relative to business transaction volumes), Mainframe Cost Allocation by Application (allocate cost using consumption metrics like MSUs, allocated/used storage, and CPU seconds), and Mainframe Showback and Chargeback (generate transparent showback or chargeback views to encourage responsible consumption).

## Mainframe NX Reports: the richest reporting layer in Costing Standard

Mainframe is the one Resource Tower with a next-generation ("NX") report collection that goes well beyond the standard format used elsewhere in the product — each report documents numbered UI elements, explicit personas, business questions answered, and concrete recommended actions:

**Mainframe TCO (NX)** — understand mainframe cost, evaluate spend by category and period, and identify trends to support budget and investment decisions. Aimed at CFOs, IT Finance Managers, Mainframe Operations Managers, and Enterprise Architects. Exposes five key metric cards (projected annual cost, cost year-to-date, cost, GCP MSU consumption, zIIP MSU consumption) with period-over-period comparison indicators, five navigation tabs (Summary, Cost Pool, Labor, Vendor, Definitions), and breakdown/trend charts by category (CC Reconciliation, Desktop Enablement, CC Limit, Data Distribution, Finance Operations).

**Mainframe Usage** — understand processor consumption, evaluate usage by category and period, and identify trends to support capacity planning and workload optimization. Aimed at Capacity Planners, Performance Analysts, IT Operations Managers, and Infrastructure Architects. Distinguishes GCP vs. zIIP MSU consumption in separate tabs, with Month-over-Month, Quarter-over-Quarter, and Year-over-Year variance detail.

**Mainframe Consumption Review** — understand how mainframe cost is allocated, evaluate spend by application and period, and identify trends to support chargeback and financial planning. Aimed at Finance Managers, Business Unit Leaders, Department Heads, and Chargeback Administrators — this is, literally, the operational report underpinning the chargeback conversation for the Mainframe Resource Tower specifically.

**Mainframe Applications** — understand application cost, evaluate how resources align with business priorities, and track cost trends across product portfolios and application lifecycles. Aimed at Application Portfolio Managers, Business Unit Leaders, IT Financial Analysts, and Application Owners. Cross-references spend by product portfolio, by application investment objective (Tolerate, Migrate, Invest), and by lifecycle stage.

**Mainframe Analysis** — understand resource consumption patterns, evaluate usage by product line, application, and business unit, and identify cost trends for capacity planning and optimization. Aimed at Mainframe Capacity Planners, IT Financial Managers, Application Owners, and System Administrators. The most granular report in the collection: an interactive drill-down table with free filtering, and a metric selector panel (GCP MSU, zIIP MSU, Cost, Business Volume, Cost per Volume Unit).

## Why this matters in a client conversation

For any client with a significant mainframe footprint (very common in banking and insurance), this NX report set is the strongest evidence available in Costing Standard that the product treats mainframe as a first-class citizen, not an afterthought bolted onto a cloud-first cost model — the level of detail (numbered UI walkthroughs, explicit recommended actions) matches or exceeds what's available for cloud-native Resource Towers.

## Source documents

- Mainframe Overview — `02-product-docs/apptio-costing-standard/en/cost-transparency/infra-use-cases/mf-overview.md`
- Mainframe NX Reports (collection + 5 individual reports) — `02-product-docs/apptio-costing-standard/en/cost-transparency/reports/mf-nx-report.md` and related files listed in `generated_from`
