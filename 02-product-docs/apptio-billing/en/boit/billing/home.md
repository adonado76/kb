---
source_system: "apptio-billing"
practice: "tbm"
language: "en"
doc_type: "boit"
title: "Billing"
breadcrumb:
  - "Billing"
source_path: "boit/billing/home.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Billing

## Release Notes

- [Recent releases](release-notes/whats-new.html "This section describes changes to the out-of-box Billing content only, not the underlying platform. For platform-level updates such as TBM Studio and Client server behavior, readers should review TBM Studio’s Release Notes and consider applicable changes alongside what is documented here.")

## Getting Started

- Introduction to Billing
  - [Billing overview](getting-started/intro-billing-what-how.html)
  - [Billing editions and Costing editions](getting-started/bill-cost-editions.html "Billing is available in two editions. Each edition is associated with a different set of components and is designed for different levels of complexity and maturity.")
  - [Core concepts: services, units, rates, recovery, journals](getting-started/core-concepts.html "The rest of this guide relies on a small set of recurring concepts. Understanding them here reduces confusion later.")
  - [Key benefits](getting-started/key-benefits.html "At a high level, Billing helps you:")
- [Glossary & Acronyms](getting-started/key-concepts-terms.html "This appendix defines common terms and acronyms used throughout the Billing Help. Use it as a quick reference when reading other sections or working in the product.")
- User Roles & Permissions
  - [Overview and roles](getting-started/std-custom-role.html "User roles and permissions control who can see and work with Benchmarking. A Role is a collection of permissions that is assigned to a user, and no one can access an IBM Apptio product without at least one Role on their account, which is managed in Access Administration. In Access Administration, authorized Admins create and manage user registrations, assign or remove Roles, and control which Roles can access each product endpoint, which endpoints are open to any eligible Role, and which endpoints are hidden entirely.")
  - [Permissions and access types for Billing Standard](getting-started/perm-access-bs.html)
  - [Access patterns for Billing Essentials](getting-started/access-patters-be.html)
  - [Access patterns for Billing Standard](getting-started/access-patterns-bs.html "Billing Standard introduces a separate Billing endpoint in addition to the Costing project. Access needs to account for both.")
  - [Segregation of duties and recommended practices](getting-started/duty-segregation.html "When setting up roles and permissions, consider these practices:")
  - [Managing access over time](getting-started/manage-access.html "Access rarely stays static. People change roles, new services are added, and new Billing capabilities are rolled out.")
- [Support resources](getting-started/support-resources.html)

## How to Use This Guide

- [Who this guide is for](getting-started/audience.html "This section explains who the guide is for, how edition notices work, what each major section covers, and where different personas should begin.")
- [Edition and Costing notices](getting-started/edition-costing-notice-conventions.html "Billing always relies on a Costing project, but this guide keeps the labeling simple by focusing on Billing editions:")
- [What each section covers](getting-started/section-coverage.html "Use this as a quick map of the guide:")
- [Where to start by persona](getting-started/persona.html "You do not need to read the guide in order. Use the suggestions below to jump to the most relevant sections.")
- [Implementation Checklist](getting-started/checklist.html "For anyone planning or changing a Billing implementation, this high-level checklist ties the guide together. Later sections provide the detailed steps.")

## Data Requirements & Integration

- [Shared data foundations](datareq-integrate/shared-data.html "Billing sits on top of Costing. If the data feeding Costing and Billing is weak, the bills will be weak. This section spells out what data Billing needs, how it is typically structured, and where integration usually happens.")
- [Data requirements for Billing Essentials](datareq-integrate/data-be.html)
- [Data requirements for Billing Standard](datareq-integrate/data-bs.html "Billing Standard uses a wider set of components and, therefore, a broader data model. It still needs the same basic foundations as Essentials but spreads them across multiple domains.")
- [Data quality expectations](datareq-integrate/data-quality.html "Weak data will show up immediately in Billing outputs: missing lines, unexplained charges, or rates that look wrong.")
- [Calendars and periods](datareq-integrate/calendar.html "Billing needs a consistent notion of periods:")
- [Currencies and FX](datareq-integrate/currency.html "Billing can operate in multi-currency environments, but it is usually simpler if Billing outputs are presented in a single presentation currency for business stakeholders.")
- [Integration mechanisms and non-Studio options](datareq-integrate/integration.html "Data can reach Billing through several mechanisms. Which ones are used depends on who manages the implementation and what tools are available.")

## Configuring Billing Essentials (Implementation)

- [Scope and prerequisites](config-be/be-overvie.html "This section describes how Billing Essentials is configured in a Costing Essentials project, from installing components through to first usable bills. It assumes that Costing Essentials is already deployed and stable.")
- [Installing Billing Essentials components](config-be/install-be.html "Billing Essentials is delivered as components that are installed into the existing Costing Essentials project.")
- [Key datasets and tables](config-be/key-datasets.html)
- [Populating the offering catalog](config-be/populate.html "The offering catalog drives what appears on bills. It should be populated and validated before the first billing run.")
- [Preparing consumer data](config-be/prepare.html "The Billing Essentials model needs a consistent view of who is being billed.")
- [Integrating consumption data](config-be/integrate.html "Consumption data is what drives units in the PxQ calculation.")
- [Configuring and loading rates](config-be/configure.html "Rates translate units into monetary charges.")
- [Running the Billing Essentials calculation](config-be/running.html "With offerings, consumers, consumption, and rates in place, the Billing Essentials calculation can be run in In Development and Staging.")
- [Promoting to Production and first go-live run](config-be/prmoting.html "Once Billing Essentials behaves as expected in Staging:")
- [Handover and operationalization](config-be/handover.html "After the first successful Production run:")

## Configuring Billing Standard (Implementation)

- [Scope and prerequisites](config-bs/bs-overview.html "This section describes how Billing Standard is configured on top of a Costing Standard project, from installing components through to first usable domain-rich bills. It assumes that Costing Standard is already deployed and stable.")
- [Installing Billing Standard components](config-bs/bs-install.html "Billing Standard ships as a set of components installed into the existing Costing Standard project. The Billing Standard endpoint in the front end surfaces content created by these components.")
- [Core domain tables and relationships](config-bs/bs-core.html "Billing Standard’s strength comes from its domain-rich model. At minimum, expect to work with the following table families:")
- [Setting up services and offerings](config-bs/bs-setup.html "The catalog of what is billed is central regardless of edition, but Billing Standard often needs richer linkage to domains.")
- [Populating domain master data](config-bs/bs-pop-domain.html "Domain masters enable the Billing Standard reports that slice charges by application, infrastructure, cloud, project, and legal entity.")
- [Aligning cost, consumption, and unit definitions](config-bs/bs-align-cost.html "Billing Standard needs a coherent story across cost, units, and prices.")
- [Configuring price and variance logic](config-bs/bs-config-price.html "Billing Standard can analyze cost, plan, and price. The configuration decides how that works.")
- [Running the Billing Standard calculation in In Development / Staging](config-bs/run-bill.html "Once domain masters, units, prices, and mappings are in place, the Billing Standard calculation can be tested.")
- [Enabling the Billing Standard endpoint and report access](config-bs/enable-bill.html "With content validated in Staging, the endpoint and reports can be prepared for users.")
- [Promoting to Production and first full Billing Standard run](config-bs/promote-bill.html "After Billing Standard content and endpoint behavior are validated in Staging:")
- [Operationalizing Billing Standard](config-bs/operate-bill.html "After go-live, Billing Standard becomes part of the recurring Billing cycle described in Section 9, with added domain responsibilities.")

## Running the Billing Cycle

- [Annual planning and rate setting](run-bill-cycle/anual-plan.html "Most Billing implementations follow a yearly rhythm for planning and rates, even if adjustments happen during the year.")
- [Monthly billing process](run-bill-cycle/monthly-bill.html "Each billing period typically follows a repeatable set of steps.")
- [Validating current period bills](run-bill-cycle/validating.html "Validation is where most billing issues are caught before they reach consumers.")
- [Generating and distributing bills](run-bill-cycle/generating.html "Once billing results pass validation, the next step is to generate bill views and distribute them.")
- [Exporting and posting journals](run-bill-cycle/exporting.html "For chargeback, Billing outputs often feed Finance systems as journals.")
- [Billing admin checklist](run-bill-cycle/admin-checklist.html "This checklist summarizes the recurring tasks for each billing period. It can be adapted into a more detailed operational runbook.")

## Working with Billing Reports

- [Where to find Billing reports](work-bill-reports/where-to-find.html "Billing reports are where most people experience the outcome of the Billing model. This section focuses on how to find those reports, what the main report groups look like in each edition, and how they are typically used.")
- [Billing reports in Billing Essentials](work-bill-reports/billrep-be.html "Billing Essentials includes a small, focused set of reports installed via the “Bill- Charge Reporting” component:")
- [Billing reports in Billing Standard](work-bill-reports/billrep-bs.html "Billing Standard includes domain-specific views, invoices, and summary reports. Reports are grouped into sections shown in the home report’s page. Unless noted, reports are installed via the “BoIT- Foundation” component.")
- [Common report tasks and usage patterns](work-bill-reports/common-rep-ratasks.html "Regardless of edition, users tend to perform the same core actions in Billing reports. This subsection focuses on patterns rather than specific UI controls.")

## Administration & Operations

- [Overview](admin-ops/ao-admin.html "This section gives you concrete patterns for structuring Billing so you are not inventing everything from scratch every time.")
- [Simple service showback](admin-ops/ao-simple-service.html)
- [Chargeback with journals](admin-ops/ao-chargeback-journal.html)
- [Service catalog centric design](admin-ops/ao-service-catalog.html)
- [Cloud centric design](admin-ops/ao-cloud-centric.html)
- [Project centric design](admin-ops/ao-project-centric.html)
- [Legal entity and transfer pricing view](admin-ops/ao-legal-entity.html)
- [Combining patterns without creating chaos](admin-ops/ao-comb-patter.html)
- Editions and Capabilities
  - [Editions Overview and Summary](edition-capabilities/es-intro.html "Billing is available in two editions: Billing Essentials and Billing Standard.")
  - [Designing with the edition in mind](edition-capabilities/es-design.html "When working with Billing Essentials:")
- Solution Architecture and Dependencies
  - [Billing and Costing relationship](sol-arch-depend/sol-arch-intro.html "This section explains how Billing is packaged, how it relates to Costing, and what must exist before Billing content can be used.")
  - [Billing Essentials architecture](sol-arch-depend/be-arch.html "Billing Essentials is implemented inside the same project that runs Costing Essentials. There is no separate endpoint for Billing Essentials. All content is delivered as additional components and report collections within that project.")
  - [Billing Standard architecture](sol-arch-depend/bs-arch.html "Billing Standard extends the same architecture with an additional endpoint and a larger set of components.")
  - [Front-end and endpoint relationships](sol-arch-depend/fe-endpoint-relation.html "While this guide does not go deep into Frontdoor, it is important to understand how users reach Billing.")
  - [Dependency summary](sol-arch-depend/depend-summary.html "The table below summarizes key dependencies for each edition.")
- Environments and Release Management
  - [Costing environments: In Development, Staging, Production](environ-relnmgmt/environments.html "Billing uses the same environments as the Costing project it is installed into. Configuration changes to Billing are managed through the Costing project’s environments: In Development, Staging, and Production.")
  - [Check-out, check-in, and build creation](environ-relnmgmt/checkin-checkout.html "Configuration changes for Billing follow the same pattern as Costing:")
  - [Locking Staging and promoting to Production](environ-relnmgmt/lock-stage-promote.html "Before promoting changes to Production, the Staging environment should be locked to prevent new check-ins from generating additional builds.")
  - [Environment flow for Billing Essentials](environ-relnmgmt/env-be.html)
  - [Environment flow for Billing Standard](environ-relnmgmt/env-bs.html "Billing Standard follows the same environment lifecycle as the underlying Costing Standard project, but introduces a separate Billing endpoint for end users.")

## Advanced Topics

- [Unit rate analysis and optimization](advance-topic/unit-rate-analysis.html "Unit rates are often the heart of Billing conversations. This subsection focuses on how to analyze and tune them over time.")
- [Cloud billing patterns](advance-topic/cloud-billing-patterns.html "Cloud billing depends heavily on tagging, account structure, and service mapping. Billing Standard cloud components are designed to make this manageable.")
- [Project-centric billing and views](advance-topic/project-centric-billin.html "Projects often represent investments in products, services, or change initiatives. Billing Standard project components enable project-centric billing and showback.")
- [Transfer pricing and legal entity views](advance-topic/transfer-price.html "Transfer pricing and legal-entity level views become important when Technology charges cross legal or tax boundaries.")
- [Plan vs actual vs price](advance-topic/plan-vs-actual.html "Applies primarily to Billing Standard, but the concepts can be used in a simplified way with Billing Essentials if plan data is available.")

## Design Patterns and Use Cases

- [Simple PxQ service showback](design-uc/uc-simple.html)
- [Chargeback with journal export](design-uc/uc-chargeback.html)
- [Investigate a unit rate spike](design-uc/uc-investgate.html)
- [Cloud cost and unit-rate view](design-uc/uc-cloud.html)
- [Project view of Technology spend](design-uc/uc-project.html)
- [Legal entity and intercompany view](design-uc/uc-legal.html)
- [Compare plan vs actual vs price for a key service](design-uc/uc-compare.html)

## Go-Live Playbook

- [What “go-live” means for Billing](go-live/gl-overview.html)
- [Pre-go-live readiness checklist](go-live/gl-checklist.html "This is the minimum you should have in place before you even schedule a go-live date.")
- [Dress rehearsal](go-live/gl-dress-rehersal.html "A dress rehearsal is a full end-to-end run in Development and verified in Staging that mimics what you will be published into Production.")
- [Cutover approach](go-live/gl-cutover.html "Cutover is the controlled move from “we are testing” to “we are using Billing as the source of truth.”")
- [Hypercare: first 1–3 cycles](go-live/gl-hypercare.html "Go-live is not finished when the first period closes. The first few cycles are where weaknesses show up.")
- [Fall-back and correction strategies](go-live/gl-falback.html "Things will occasionally go wrong. Decide up front how you will correct them.")
- [Go-live responsibilities](go-live/gl-resp-runbook.html "It helps to be explicit about who owns what during go-live.")
- [Capturing the “steady-state” runbook](go-live/runbook.html)

## Role-Based Training Guide

- [Training Objectives](role-based-tg/train-objectives.html "This section outlines how to train different audiences so Billing is actually used and trusted, not just technically deployed. Use it to design onboarding, recurring training, and handoffs when people change roles.")
- [Training Scope by Role](role-based-tg/train-scope.html "This subsection summarizes what each role needs to learn. The detailed training matrix can be documented separately.")
- [Onboarding path for Admins & Analysts](role-based-tg/op-admin.html "This is the most intensive training path and should be structured, not ad hoc.")
- [Onboarding path for Service and Product Owners](role-based-tg/op-so-po.html "This path is shorter and focused on interpretation, not configuration.")
- [Onboarding path for Finance](role-based-tg/op-finance.html "Finance training should be practical: how to reconcile and post, not how to write ETL.")
- [Training for Senior Leaders & Stakeholders](role-based-tg/op-sl.html "This is about decision support, not mechanics.")
- [Training, Cadence, and Formats](role-based-tg/cadence-format-measure.html "Once initial onboarding is done, training should not stop. At a minimum:")

## Troubleshooting

- [Troubleshooting](troubleshooting/troubleshoot.html "This appendix is a practical “what went wrong and what to check first” guide. Use it when numbers look off, reports are empty, or journals do not reconcile.")
