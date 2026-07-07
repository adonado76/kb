---
source_system: "apptio-billing-standard"
practice: "tbm"
language: "en"
doc_type: "billing"
title: "Billing Standard architecture"
breadcrumb:
  - "Administration and Operations"
  - "Solution Architecture and Dependencies"
  - "Billing Standard architecture"
source_path: "SSV8ML/boit/billing/sol-arch-depend/bs-arch.html"
images: []
capability_ids: []
last_updated: "2026-07-06"
summary: ""
---
# Billing Standard architecture

*Billing Standard extends the same architecture with an additional endpoint and a larger set of components.*

Core elements:

- Components BoIT- Foundation Required for Billing Standard. It installs the core Billing models, tables, and report structures, including invoice-style reports that summarize charges by service and consumer. BoIT- Units Adds unit-based views across Billing reports. It introduces billable units for each service offering, calculates effective unit rates by dividing charges by units, and, when Cost Variance is also installed, enables comparisons between cost-based and price-based unit rates. BoIT- Applications Adds application-centric Billing views. It includes reports that show charges and license or usage units by application for business audiences, plus recovery views that compare charges to the underlying Technology cost of each application to highlight over- and under-recovery. BoIT- Servers Adds server-centric reporting to Billing. It introduces reports and tabs that break down server-related cost and charges, showing how server infrastructure contributes to the services and applications that are billed. BoIT- Storage Adds storage-centric reporting to Billing. It introduces reports and tabs that detail storage-related cost and charges, showing how storage tiers and pools roll into the services and applications that appear on bills. BoIT- End User Devices Adds device-level Billing views. It integrates device data from the Costing model and provides reports for both service providers and business consumers that focus on device allocation, consumption patterns, and the charges associated with end user devices. BoIT- Cloud Adds cloud infrastructure (IaaS)–focused reporting. It includes reports that show cloud service charges by provider, account, and service for business audiences, as well as recovery views that compare cloud charges to the cost of delivering those cloud services to highlight over- and under-recovery. BoIT- Projects Adds project-centric Billing views. It includes reports that show project charges and the underlying services consumed, along with recovery and variance views that combine over-/under-recovery, budget variance, and project status in a single place. BoIT- Price Enables exposing explicit prices to end users. Prices are defined in the Service Library and applied in Billing models; when multiple price adjustments or combinations apply to a service, the effective unit price shown in reports may differ from the base Service Library price. BoIT- Cost Variance Compares Billing charges to the actual cost of providing services. It adds reports, typically targeted at Service Owners and similar roles, that show cost, charge, and variance at the service and domain levels to support recovery and pricing decisions. BoIT- Plan Variance Introduces budget and forecast comparisons. It enables reports that compare charges to budget, and cost to budget, and it adds budget/forecast variance dimensions into existing Billing views for clearer performance-to-plan analysis. BoIT- Inter Company Transfer Pricing Supports modeling and reporting on charges across legal entities. It enables allocation and charging logic that traces the financial impact of consuming services between legal entities or cost centers, supporting cross-charging scenarios in decentralized or multi-entity Technology organizations.
- Where they install Installed into the Costing Standard project using TBM Studio. Add models, tables, metrics, and report definitions covering multiple Technology domains and financial views.

- How users see it Exposed to users via a separate Billing Standard endpoint in addition to the Costing Standard endpoint. Report collections inside the Billing Standard endpoint align to domains such as: Services and consumers Units and unit rates Cloud Applications Infrastructure (Servers, Storage, End User Devices) Projects Variance and pricing Transfer pricing and legal entities

Fig #: Frontdoor landing page with Billing Standard endpoint highlighted

Dependencies and assumptions:

- A Costing Standard project is deployed with a stable cost model.
- IBM has provisioned a Billing Standard endpoint and linked it to the appropriate Costing Standard project.
- The Billing Standard components are installed and configured so that: Domain master data tables are populated (Applications, Servers, Storage, Cloud, Projects, End User Devices, Legal Entities). Relationships to consumers, services, and pricing tables are defined.
- Users who need Billing Standard reports are granted access to the Billing Standard endpoint and relevant report collections.
