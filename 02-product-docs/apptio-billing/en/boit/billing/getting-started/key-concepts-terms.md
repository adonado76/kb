---
source_system: "apptio-billing"
practice: "tbm"
language: "en"
doc_type: "boit"
title: "Glossary & Acronyms"
breadcrumb:
  - "Billing"
  - "Getting started"
source_path: "boit/billing/getting-started/key-concepts-terms.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Glossary & Acronyms

This appendix defines common terms and acronyms used throughout the Billing Help. Use it
as a quick reference when reading other sections or working in the product.

## How to use this appendix

- Terms are grouped by theme:
  - Core concepts
  - Data and modeling
  - Reports and process
  - Acronyms
- Edition-specific terms are labeled:
  - “Billing Essentials only”
  - “Billing Standard only”

## Core Billing concepts

**Billing**

The set of models, tables, and reports that calculate, present, and optionally journal
Technology charges to consumers. Built on top of a Costing project.

**Billing Essentials**

Entry-level edition of Billing, focused on PxQ showback and simple chargeback. Delivered
as components inside a Costing Essentials project and surfaced as a “Billing” report
collection.

**Billing Standard**

Full edition of Billing, with additional domain-specific components (cloud, applications,
infrastructure, projects, variance, transfer pricing) and a dedicated Billing endpoint.
Built on a Costing Standard project.

**Costing**

The cost modeling layer that allocates Technology spend to services, applications, and
consumers. Billing depends on Costing for cost structures and often for unit cost
information.

**PxQ (Price times Quantity)**

The core Billing calculation pattern:

Charge = Units × Rate

Units represent consumption, Rate represents the price or recovery per unit.

**Consumer**

Any entity that receives Technology charges. Examples: business unit, department, cost
center, product, project, program, region, or legal entity.

**Service / Offering / Product**

The “what” that is being billed. This can be a Technology service, platform, product, or
bundle that appears on bills and in Billing reports.

**Showback**

Reporting charges or “as-if” prices to consumers without posting journals to the general
ledger. Used for transparency and behavioral change without formal internal revenue.

**Chargeback**

Using Billing to generate journal-ready charges that are posted into the general ledger as
internal revenue and expense.

**Edition**

The subscribed Billing capability level. For Billing, editions are Essentials and
Standard. A Costing project runs only one Billing edition at a time.

## Data and modeling terms

**Costing project**

The TBM Studio project where Costing models, tables, and many shared Billing components
live. Contains In Development, Staging, and Production environments.

**In Development environment**

The environment where configuration changes are made and tested first. Items are checked
out, edited, and checked in here. Builds created here are mirrored into Staging.

**Staging environment**

The environment used for QA and dress rehearsals. Builds in Staging are candidates for
promotion to Production after validation and sign-off.

**Production environment**

The live environment where end user reports, Billing models, and journal exports for
official periods run.

**Component**

A packaged set of models, tables, metrics, and reports that can be installed into a
Costing project. Examples: Billing – Charge, Billing – Charge Reporting, BoIT – Servers,
BoIT – Cloud.

**Endpoint**

The front-end entry point that surfaces reports for a given project and scope.

- For Billing Essentials, reports appear in the Costing Essentials endpoint as a “Billing”
  collection.
- For Billing Standard, a separate Billing endpoint exists.

**Master data**

Relatively stable reference data such as consumers, services, applications, legal
entities, and units. Used as keys and dimensions in models and reports.

**Consumption data**

Records that represent “how much” of a service was used, by which consumer, in which
period. Typically contains: consumer, service, units, period, and optional attributes.

**Rate / price**

The value per unit used in PxQ calculations. Rate tables define which price applies to
each service and period and sometimes by consumer type, region, or other dimensions.

**Unit**

The measurement for consumption and pricing. Examples: user per month, GB per month, VM
per month, ticket per month, device per month.

**Unit cost**

Cost per unit of a service, usually derived from Costing by dividing total cost by total
units. Used to compare cost vs price.

**Mapping table**

A table that links values from one domain or system to another. Examples: external cost
center to internal consumer, cloud tags to services and consumers, project IDs to
applications.

**Legal entity**

A company or entity that exists for legal and tax purposes. Used for transfer pricing and
intercompany views in Billing Standard.

**Transfer price**

The price used for cross-entity or cross-country internal charges. Usually derived from or
related to standard Billing prices, but constrained by tax and regulatory rules.

## Reporting and process terms

**Invoice-style report**

A report that shows charges for a given consumer and period in a bill-like layout,
typically with service, units, rate, and charge columns plus totals.

**Detail report**

A more granular report that shows line-level drivers behind a bill. Often includes
additional fields such as environment, region, project, or tag-based segments.

**Journal report / Journal export**

A Billing report shaped to meet Finance posting requirements. Includes GL account
segments, consumer segments, amounts, and references, and is used for chargeback
posting.

**QA report / Exception report**

Reports designed to highlight potential problems. Examples: missing mappings, zero or
negative volumes, unusual spikes, orphan records.

**Variance**

The difference between two values, commonly:

- Actual vs plan
- Cost vs price
- Current period vs prior period

**Unit rate analysis**

Analysis focused on the charge per unit of a service over time, often used to explain and
optimize Technology economics.

**Dress rehearsal**

A full end-to-end run of the Billing cycle in Staging before first go-live in Production.
Uses real or realistic data and validates models, reports, and exports.

**Hypercare**

The period immediately after go-live (usually one to three billing cycles) where incident
handling, QA, and support are intentionally more intensive.

**Runbook**

A documented, step-by-step description of the operational Billing cycle. Includes timings,
responsibilities, and dependencies for data loads, model runs, QA, and exports.

**Showback-only period**

A period where Billing is used to report charges but journals are not yet posted, often
during piloting or early adoption.

## Acronyms

**BU**

Business Unit. A high-level organizational segment that often acts as a consumer of
Technology services.

**CIO / CTO / CFO / COO**

Chief Information Officer, Chief Technology Officer, Chief Financial Officer, Chief
Operating Officer. Executive sponsors or stakeholders of Billing and Costing.

**GL**

General Ledger. The Finance system of record for accounting entries, including chargeback
journals where used.

**ITFM / ITFM(A)**

IT Financial Management. ITFMA refers to an analyst with responsibility for ITFM
processes, analysis, and tools.

**PMO**

Project Management Office. Often consumed with project views of Billing outputs.

**PPM**

Project and Portfolio Management. The tools and processes used to manage projects and
portfolios that may map into Billing.

**PxQ**

Price times Quantity, the core Billing calculation pattern that generates charges.

**QA**

Quality Assurance. Activities and checks that ensure Billing data and outputs are fit for
use before publication.

**RACI**

Responsible, Accountable, Consulted, Informed. A framework sometimes used to describe
roles and responsibilities for Billing and Costing processes.

**TBM**

Technology Business Management. The broader discipline and taxonomy for managing
Technology cost, performance, and value. Billing uses TBM-aligned constructs but can be used
by organizations that do not label their practice as TBM.

**TBMA**

TBM Analyst. Analyst responsible for working with TBM-aligned data, models, and tools such
as Costing and Billing.

**UOM**

Unit of Measure. The unit used to quantify service consumption and define rates, such as
user per month or GB per month.

## Where definitions show up in the product

Some implementations expose short definitions directly in report descriptions or
tooltips.

Examples:

- Report description fields that explain what a report shows and who it is for.
- Column descriptions for critical fields such as Unit, Rate, Consumer, and Service.
- Help links from within Billing reports that jump to this appendix.

Keeping terminology consistent across this appendix, the models, and the reports reduces
confusion and makes it easier for new users to trust and adopt Billing.
