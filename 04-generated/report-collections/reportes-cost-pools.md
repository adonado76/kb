---
tbm_concept: "Report Collections — Cost Pools layer (IT Financials, Workforce, Fixed Assets, Vendor)"
practice: tbm
language: en
doc_type: report_collection_brief
products_covered:
  - apptio-costing-standard
status: draft
generated_from:
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/itfinancialsreportcollection.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/labor-report-collection.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/fixedassetsreportcollection.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/vendors-report-collection.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/vi-reports.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/itf-nx-report.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/fin-rev-nx-rep.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/fin-rev-capex-nx-rep.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/wf-nx-report.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/labor_analysis_nx.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/labor-cto-nx.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/vendor-nx-report.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/vendor-review-nx-rep.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/vendor-list-nx-rep.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/vendor-cto-nx-rep.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/pc-nx-report.md
last_updated: "2026-07-04"
---
# Report Collections — Cost Pools Layer

This brief documents every out-of-the-box report collection tied to the Cost Pools layer of the TBM Taxonomy in Apptio Costing Standard: IT Financials, Workforce, Fixed Assets, Vendor, and Public Cloud — both their base collections and their next-generation ("NX") report versions.

## IT Financials Report Collection

Spend and OpEx/CapEx variation broken down by cost center, cost center owner, and account, designed so budget owners understand how spend is tracking against plan and where variances exist. Four reports: **Financial Review (OpEx)** (executive view of OpEx spend and variance by cost pool and owner), **Financial Review – CapEx** (the same summary for capital spend), **Financial Analysis** (detailed analytical view of month-over-month and year-to-date OpEx/CapEx variance against budget and forecast, at account group, subgroup, account, and cost center level), and **Cost Pool Analysis** (spend aggregated into standard TBM Council Cost Pools, split by OpEx/CapEx and fixed/variable, with drill-down to accounts and transactions).

### Financials NX Reports
Three reports enrich this collection with numbered UI elements, personas, and recommended actions:
- **Financial Analysis (NX)**: monitors spend, evaluates budget performance, and understands cost trends by cost center, account group, and period. Aimed at Financial Controllers, Cost Center Owners, Finance Analysts, CFO, and Budget Planners. Distinguishes OpEx and CapEx views in separate tabs, color-coding budget variance status.
- **Financial Review (NX)**: analyzes year-to-date operating spend against allocated budget, identifying over/under-spend areas by category. Aimed at CFO, CIO, executive leadership, board members, and Finance leadership. Exposes three KPI cards (OpEx, OpEx year-to-date, OpEx forecast) and Top 5 categories over/under budget charts.
- **Financial Review – CapEx (NX)**: the same structure applied to capital spend. Aimed at CFO, CIO, executive leadership, PMO Leaders, and Capital Planning teams — answers whether capital projects are progressing as expected and whether capital budget will be fully used by year-end.

## Workforce (Labor) Report Collection

Combines current HR and general-ledger data into a single view, establishing an effective labor rate baseline across similar functions. Three reports: **Labor Review** (high-level cost and headcount metrics for internal and external labor, including open position count/nature and internal/external balance), **Labor Analysis** (ad-hoc analytical view of all labor spend data, filterable and combinable by any needed metric), and **ITP – Labor Review** (within Planning Integration Collection: a view of the year's labor plan to decide whether to accelerate or delay hiring against budget, showing month-by-month budgeted and forecast headcount — headcount data only, without the full financial detail of the main Labor Review).

### Workforce NX Reports
Three reports enrich this collection:
- **Labor Review (NX)**: tracks labor cost and headcount across the IT organization, comparing actual spend and headcount against budget. Aimed at IT Financial Controller, CIO, HR leaders, Cost Center Owners, and Finance teams. Exposes five KPI cards (total spend year-to-date, labor as percentage of IT spend, total/internal/external headcount).
- **Labor Analysis (NX)**: analyzes labor cost and headcount by cost center, location, role type, and vendor, comparing internal employees against external contractors and planned vs. actual headcount. Aimed at Financial Analysts, Cost Center Owners, Resource Managers, HR teams, and Procurement teams.
- **Labor Cost Take-Out (NX)**: identifies potential labor cost savings by comparing the current rate against the lowest observed rate for each role type, prioritizing high-impact reduction opportunities. Aimed at business leaders, Procurement, Resource Managers, HR leaders, and Finance teams — directly answers whether it is more cost-effective to use internal employees or vendor resources, and which locations offer the lowest-cost options for a given role.

## Fixed Assets Report Collection

Detail of depreciated assets (class, age, location, IT tower, vendor, asset type and category) over time. Two reports: **Fixed Assets** (the full detail) and **ITP – Asset Review** (the same view within Planning Integration Collection, for planning purposes).

## Vendor Report Collection (base) and Vendor Insights

The Vendor Collection base has five reports sharing a Key Elements / Questions Answered format: **Vendor Review** (top-10 vendor spend by category, with trend), **Vendor Portfolio** (the same distribution broken down by OpEx/CapEx and cross-referenced against IT Resource Tower and Cost Pool), **Vendor List** (holistic vendor view by function, location, and service), **Vendor Spend by Project** (vendor spend cross-referenced by project, cost center, and owner), and **ITP – Vendor Review** (within Planning Integration Collection: compares the original plan against the latest plan by vendor, cross-referenced by cost center, contract type, and location).

Vendor Insights extends this with nine deeper reports (Vendor Insights Dashboard, Vendor Summary, Purchase Order Burndown, Spend without POs, Contract Summary, Contract Expiration, Contract to Applications, Contract Expiration Notification, ARC RRC Summary, and ARC RRC RU Reconcile) — documented in full in the Vendor Management capability brief.

### Vendors NX Reports
Three additional reports:
- **Vendor Review (NX)**: analyzes vendor spend with budget comparison and trend analysis, identifying vendors over or under budget to prioritize contract negotiation. Aimed at Procurement Teams, Vendor Managers, Finance teams, IT Leaders, and Contract Managers. Distinguishes Strategic, Preferred, and Transactional spend, flagging remaining budget in red when a vendor exceeds its annual budget.
- **Vendor List (NX)**: view of all vendors with their operating and capital spend, identifying the largest vendors and comparing spend between periods. Aimed at Procurement Teams, Finance, Contract Managers, IT Leaders, and Audit teams.
- **Vendor Cost Take-Out (NX)**: analyzes annual spend with external vendors by function and type, identifying consolidation and renegotiation opportunities. Aimed at Procurement Teams, Vendor Managers, CFO, CIO, and Finance leadership. Allows pivoting by function, Resource Tower, Cost Pool, or vendor type — directly answering whether multiple vendors provide overlapping services that are candidates for consolidation.

## Public Cloud NX Reports

One report: analyzes cloud spend across providers, tracks resource efficiency through utilization and reserved instance coverage, and identifies cost optimization opportunities. Aimed at Cloud Architects, FinOps teams, IT Financial Controllers, Cloud Operations, and CIO — a single report with six navigation tabs (Overview, KPI Definitions, Filter Definitions, Cloud Credit Details, Cloud Tower Mapping, Definitions). Exposes five summary cards (cost, reserved instance coverage rate, utilization, reserved instance waste, cloud credits), with coverage/utilization trend charts against benchmark bands. A worked example in the documentation: a 22.69% RI coverage rate (well below the 75-85% "Best In Class" range) signals a significant savings opportunity, while 100% RI utilization confirms existing reservations are fully leveraged — there are just too few of them.

## Known limitation

The five base reports of the Vendor Collection (Vendor Review, Portfolio, List, Spend by Project, ITP – Vendor Review) have screenshots in Apptio's original documentation, but those specific images were not successfully extracted during the normalization of this knowledge base (they live under a folder path containing spaces that the extraction process did not capture) — this section documents them from their Key Elements / Questions Answered content only, without image reference.
