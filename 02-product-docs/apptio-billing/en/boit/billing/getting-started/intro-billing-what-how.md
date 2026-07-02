---
source_system: "apptio-billing"
practice: "tbm"
language: "en"
doc_type: "boit"
title: "Billing overview"
breadcrumb:
  - "Billing"
  - "Getting started"
  - "Introduction to Billing"
source_path: "boit/billing/getting-started/intro-billing-what-how.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Billing overview

## What is IBM Apptio Billing

Billing is the content layer that turns Technology cost and usage data into **billable
charges** and **bill-ready reports** for internal consumers.

At a high level, Billing helps an organization:

- Define **what is billable** (e.g., services, products, solutions, or offerings).
- Attach **units and rates** to those offerings.
- Translate **cost and consumption** into **charges** for business units or other
  consumers.
- Present **clear, repeatable bills and journals** that Finance and business
  stakeholders can use.

Billing is not a separate platform. It is delivered as **out-of-box content** that runs
on top of an existing Costing project and TBM Studio, using the same modeling engine,
environments, and data foundations.

## How Billing Extends Costing

Costing answers questions like:

- How much does Technology cost, and where is it spent?
- How are costs allocated from infrastructure, applications, and platforms to business
  outcomes?

Billing builds on that foundation to answer questions like:

- Which services or products are being consumed, and by whom?
- What should each consumer be **charged** (or shown) for the current period?
- Are the **rates** and **charges** aligned with actual costs and planned
  recovery?

Conceptually:

1. **Source systems** (e.g., GL, HR, CMDB, cloud, PPM, monitoring, etc.) feed data into
   Costing.
2. **Costing** normalizes, allocates, and classifies costs across applications,
   services/products, and business units.
3. **Billing** consumes those Costing outputs plus additional consumption data to:
   - Attach units and rates.
   - Calculate charges.
   - Produce bills and journals.

Billing does not replace Costing models. Instead, it assumes that Costing is already in
place and providing the cost and usage signals needed to compute meaningful charges.
