---
tbm_concept: "Report Collections — Technology Solutions layer"
practice: tbm
language: en
doc_type: report_collection_brief
products_covered:
  - apptio-costing-standard
status: draft
generated_from:
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/applications-report-collection.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/services-report-collection.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/ai-tco-report-collection.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/cost-take-out-reports.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/app-nx-report.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/nx-app-cto.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/nx-appiaa.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/nx-applist.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/nx-appnnr.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/nx-apprev.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/service-nx-report.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/service-review-nx-rep.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/aitco-nx-report.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/aitcosol-rep-nx.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/ai-platform-mapping-nx.md
last_updated: "2026-07-04"
---
# Report Collections — Technology Solutions Layer

This brief documents the report collections tied to Technology Solutions: Applications, Services, AI, and Cost Take-Out — including their base collections and next-generation ("NX") report versions.

## Applications Report Collection

Delivers application TCO, calculated consistently from real cost allocated through a standard best-practice cost model — with the ability to start with basic allocation strategies and refine them with additional infrastructure data over time. Five reports: Application Review, Application Portfolio, Application List, Infrastructure Analysis by Application, and New & Retired Apps.

### Applications NX Reports
Five reports enrich this collection with numbered UI elements, personas, and recommended actions:
- **Application Cost Take-Out (NX)**: identifies portfolio optimization opportunities, focusing on rationalization candidates, expiring contracts, and applications flagged for elimination or migration. Aimed at CIO, Application Portfolio Managers, IT Financial Controllers, Enterprise Architects, and Business Unit Leaders. Four tabs: Application Rationalization, Retired Applications, Expiring Contracts, and Application Optimization.
- **Infrastructure Analysis by Application (NX)**: analyzes infrastructure usage across applications — compute, storage, and environment distribution — identifying optimization opportunities for physical, virtual, and cloud resources. Aimed at Infrastructure Managers, Application Owners, IT Financial Controllers, Cloud Architects, and Capacity Planners.
- **Applications List (NX)**: analyzes the application portfolio by family, including business and IT ownership, with the ability to segment by key attributes and review spend by environment. Aimed at Application Portfolio Managers, IT Financial Controllers, Business Unit Leaders, Application Owners, and Finance teams.
- **New and Retired Apps (NX)**: tracks changes in the application portfolio — additions and retirements over time — identifying trends in how the portfolio state evolves. Aimed at CIO, Application Portfolio Managers, Enterprise Architects, IT Financial Controllers, and Business Unit Leaders.
- **Application Review (NX)**: monitors spend across the application portfolio, comparing cost between operating and development environments to identify trends and high-cost applications. Aimed at CIO, IT Financial Controllers, Application Portfolio Managers, CFO, and Business Unit Leaders.

## Services Report Collection

Quantifies the complete cost of individual services and the entire service portfolio, presenting cost in the business context and criticality that the business understands and can value. Data is modeled on a standard service hierarchy to create a defensible TCO and accelerate service definition per the standard TBM Taxonomy. Three reports: Services Review, Services Portfolio, and Service List.

### Services NX Reports
One report:
- **Services Review (NX)**: analyzes IT service spend across the organization by service category, owner, and offering, identifying the highest-spend areas and their trends. Aimed at Service Owners, IT Leaders, Finance teams, Business Unit Leaders, and Cost Center Owners. Exposes four KPI cards (OpEx year-to-date, CapEx year-to-date, total spend, service count) — directly answers whether infrastructure services cost more than business services, a useful positioning question in front of a CIO.

## AI Report Collection

Covers AI initiative TCO with five reports: AI TCO – Summary, AI TCO – AI Models, AI TCO – AI Solutions, AI TCO – Business Units, and AI TCO – Model Views.

### AI TCO NX: the richest layer of this brief
Two collections and six reports/views:
- **AI TCO and Usage (NX)**: analyzes AI service spend and usage across models, solutions, and business units, identifying optimization opportunities by lifecycle stage. Aimed at AI program managers, IT Finance/TBM analysts, AI platform or service owners, and business unit leaders. Exposes four summary cards (AI cost year-to-date, current period cost, token consumption, AI solution users) and a 6-month AI cost trend chart grouped by lifecycle stage (proof of concept, production, in service, pilot, training).
- **AI TCO – Summary**: tracks total TCO, model usage, and AI solution adoption at the enterprise level, comparing AI spend as a percentage of total IT spend.
- **AI TCO – AI Models**: TCO and unit cost visibility by model platform (Granite, Llama, and Claude are named explicitly as examples), with year-to-date token consumption analysis by vendor and token type.
- **AI TCO – AI Solutions**: TCO at the AI solution level and cost drivers across cloud, labor, vendor, and other AI spend, with consumption broken down by lifecycle stage and business criticality.
- **AI TCO – Business Units**: AI adoption and consumption patterns by business unit, to encourage responsible consumption through transparency.
- **AI Platform Mapping (NX)**: maps AI platform consumption to organizational cost centers, enabling precise chargeback by assigning AI service usage to specific solutions, business units, and users. Aimed at AI/ML Administrators, Finance teams, IT Operations, Data Science Teams, and Cost Allocation Analysts. Structurally, this is the same Labor Mapping mechanism applied to AI consumption — the mapping hierarchy guidance explicitly prioritizes Solution Offering-level allocation first, then Business Unit, then User ID as fallback.

## Cost Take-Out Collection

Unlike the collections above, Cost Take-Out is not a single-domain report catalog — it's a set of out-of-the-box reports that consolidate other Apptio reports already documented in this knowledge base, purpose-built to identify high-impact cost reduction and optimization opportunities. Three reports:
- **Vendor Cost Take-Out Reports**: optimizes the vendor portfolio by identifying high-spend or overlapping vendors, sorted and prioritized by annual run-rate, with pivot by function, tower, or cost pool to detect consolidation opportunities.
- **Application Cost Take-Out Reports**: rationalizes the application portfolio by comparing year-over-year annual run-rate to find redundancy or low-value applications, with pivot by function or family, and phased migration planning that accounts for depreciation.
- **Labor Cost Take-Out Reports**: supports strategic workforce planning and hiring decisions, identifying high-cost roles or teams and vendor duplication across locations.

## Known limitation

The base Applications and Services collections (the non-NX reports) do not have screenshots available in this documentation cut — they are documented by purpose and content only. The NX versions of Applications, Services, and AI TCO do include real screenshots.
