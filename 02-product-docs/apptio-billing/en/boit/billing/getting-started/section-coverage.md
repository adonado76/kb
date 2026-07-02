---
source_system: "apptio-billing"
practice: "tbm"
language: "en"
doc_type: "boit"
title: "What each section covers"
breadcrumb:
  - "Billing"
  - "How to Use This Guide"
source_path: "boit/billing/getting-started/section-coverage.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# What each section covers

Use this as a quick map of the guide:

- [Overview and Key Concepts](intro-billing-what-how.html) - Definitions and core ideas used throughout
  Billing.
- [User Roles and Permissions](std-custom-role.html "User roles and permissions control who can see and work with Benchmarking. A Role is a collection of permissions that is assigned to a user, and no one can access an IBM Apptio product without at least one Role on their account, which is managed in Access Administration. In Access Administration, authorized Admins create and manage user registrations, assign or remove Roles, and control which Roles can access each product endpoint, which endpoints are open to any eligible Role, and which endpoints are hidden entirely.") - Which roles exist, what they typically do, and how
  access is granted.
- [Editions and Capabilities](../edition-capabilities/es-intro.html "Billing is available in two editions: Billing Essentials and Billing Standard.") - Differences between Billing Essentials
  and Billing Standard, and when each is appropriate.
- [Solution Architecture and Dependencies](../sol-arch-depend/sol-arch-intro.html "This section explains how Billing is packaged, how it relates to Costing, and what must exist before Billing content can be used.") - How Billing is packaged as
  components, how it relies on Costing, and where endpoints fit in.
- [Environments and Release Management](../environ-relnmgmt/environments.html "Billing uses the same environments as the Costing project it is installed into. Configuration changes to Billing are managed through the Costing project’s environments: In Development, Staging, and Production.")
  - How environment builds affect Billing configuration and reports.
- [Data Requirements and Integration](../datareq-integrate/shared-data.html "Billing sits on top of Costing. If the data feeding Costing and Billing is weak, the bills will be weak. This section spells out what data Billing needs, how it is typically structured, and where integration usually happens.") -
  Required datasets, master tables, and common integration points for Billing to “light
  up.”
- [Running the Billing Cycle](../run-bill-cycle/anual-plan.html "Most Billing implementations follow a yearly rhythm for planning and rates, even if adjustments happen during the year.") - Annual and monthly activities to set
  rates, validate charges, and publish bills or journals.
- [Working with Billing Reports](../work-bill-reports/where-to-find.html "Billing reports are where most people experience the outcome of the Billing model. This section focuses on how to find those reports, what the main report groups look like in each edition, and how they are typically used.") - How to find, interpret, and export
  the key reports used by IT, Finance, and business units.
- [Configuring Billing Essentials (Implementation)](../config-be/be-overvie.html "This section describes how Billing Essentials is configured in a Costing Essentials project, from installing components through to first usable bills. It assumes that Costing Essentials is already deployed and stable.") -
  Out-of-box setup steps specific to Billing Essentials.
- [Configuring Billing Standard (Implementation)](../config-bs/bs-overview.html "This section describes how Billing Standard is configured on top of a Costing Standard project, from installing components through to first usable domain-rich bills. It assumes that Costing Standard is already deployed and stable.") - Out-of-box setup steps specific to Billing Standard and its additional
  components.
- [Advanced Topics](../advance-topic/unit-rate-analysis.html "Unit rates are often the heart of Billing conversations. This subsection focuses on how to analyze and tune them over time.") - Transfer pricing,
  cloud reporting, project views, forecasting, and unit-rate optimization.
- [Administration & Operations](../admin-ops/ao-admin.html "This section gives you concrete patterns for structuring Billing so you are not inventing everything from scratch every time.") - Ongoing
  monitoring, permission changes, and operational housekeeping.
- [Design Patterns & Use Cases](../design-uc/uc-simple.html) - Sample patterns for common billing scenarios and how to implement them with Billing.
- [Go-Live Playbook](../go-live/gl-overview.html) - Checklists and practices for moving Billing into Production and stabilizing the first
  cycles.
- [Role-Based Training Guide](../role-based-tg/train-objectives.html "This section outlines how to train different audiences so Billing is actually used and trusted, not just technically deployed. Use it to design onboarding, recurring training, and handoffs when people change roles.") - How different roles can build capability with Billing and which sections to focus on.
- [Glossary & Acronyms](key-concepts-terms.html "This appendix defines common terms and acronyms used throughout the Billing Help. Use it as a quick reference when reading other sections or working in the product.") - What each component adds (datasets, reports,
  metrics, and key dependencies), definitions for Billing and Costing terminology and common
  abbreviations.
- [Troubleshooting and FAQ](../troubleshooting/troubleshoot.html "This appendix is a practical “what went wrong and what to check first” guide. Use it when numbers look off, reports are empty, or journals do not reconcile.") - Common questions, typical symptoms, and where to look next in the guide
