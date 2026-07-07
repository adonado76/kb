---
source_system: "apptio-billing-standard"
practice: "tbm"
language: "en"
doc_type: "billing"
title: "Core concepts: services, units, rates, recovery, journals"
breadcrumb:
  - "Getting started"
  - "Introduction to Billing"
  - "Core concepts: services, units, rates, recovery, journals"
source_path: "SSV8ML/boit/billing/getting-started/core-concepts.html"
images: []
capability_ids: []
last_updated: "2026-07-06"
summary: ""
---
# Core concepts: services, units, rates, recovery, journals

*The rest of this guide relies on a small set of recurring concepts. Understanding them here reduces confusion later.*

## Services, products, and offerings

Billing needs something to bill for . This is typically modeled as a catalog of services or products.

Common patterns:

- Service : A Technology offering consumed by business units (for example, “Email and Collaboration,” “Managed Database,” “Virtual Server”).
- Product : A productized Technology offering, often with defined versions, tiers, or bundles.
- Offering : A generic term for anything billable that can be shown on a bill line.

Each offering usually has:

- A name that business stakeholders recognize.
- A unit of measure (for example, GB per month, user per month, VM per month).
- One or more rates and drivers used to compute charges.

In Billing Essentials, offerings are typically managed through tables and reports that define which items are billable and at what rate.

In Billing Standard, offerings are often mapped across multiple domains (services, applications, infrastructure, cloud, projects) for more detailed analysis.

## Units and consumption

A unit is the measurable quantity of an offering consumed in a period:

- Number of users.
- Storage capacity.
- CPU-hours.
- Tickets handled.
- Project hours or points.

Consumption is the record of those units by consumer and period. Billing relies on:

- Consistent keys (for example, consumer, period, offering).
- A time grain (usually monthly).
- Clear mapping to the catalog of billable offerings.

Conceptually:

Units × Rate = Charge for a given offering, consumer, and period.

Rates and pricing methods

A rate is the amount charged per unit. Rates can be designed in multiple ways:

- Cost-based : Set equal to unit cost from Costing.
- Cost plus : Add a mark-up or overhead percentage.
- Price-based : Use a defined price that may be higher or lower than cost.
- Budget-based : Set rates to recover a target budget rather than current cost.
- Hybrid : Blend approaches, for example cost-based for some services and price-based for others.

Billing Essentials focuses on straightforward PxQ rating and basic adjustments.

Billing Standard supports more complex rate scenarios and domain-specific rate analysis (for example, unit-rate views by infrastructure type or cloud service).

## Consumers and chargeback vs showback

A consumer is the entity being billed:

- Business unit or function.
- Region or geography.
- Cost center or department.
- Project or product line, depending on design.

Billing supports both:

- Showback : Providing visibility of charges without actual financial transfer.
- Chargeback : Recording charges in financial systems and treating them as internal revenue and expense.

The same Billing configuration can support showback, chargeback, or a mix of both, depending on how journals are used and what agreements exist with Finance.

## Bills, journals, and archives

Billing outputs generally fall into three categories:

- Bills / Invoices Line-level or summarized views of charges by offering, consumer, and period. Used by business units and Service or Product Owners to understand and discuss charges.
- Journals Structured data representing the accounting view of charges. Used by Finance to post entries into the general ledger or other finance systems.
- Archives Snapshots of billing results for a given period. Used for audit, compliance, and historical analysis.

Billing Essentials focuses on invoice-style views, simple billing master tables, and archives.

Billing Standard layers additional domain-specific views and variance analysis on top of those basics.
