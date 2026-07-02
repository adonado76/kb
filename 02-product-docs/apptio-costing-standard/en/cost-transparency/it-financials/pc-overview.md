---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Public Cloud Overview"
breadcrumb:
  - "Costing Standard"
  - "Financial Use Cases"
  - "Public Cloud"
source_path: "cost-transparency/it-financials/pc-overview.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Public Cloud Overview

## Overview

Public Cloud provides visibility into cloud consumption and spend across infrastructure
services, applications, and business units. It helps organizations understand where cloud
costs originate, how they are consumed, and how they contribute to total technology spend.
By combining cost, usage, and allocation data, Public Cloud supports improved governance,
accountability, and optimization of cloud investments.

This capability enables IT Finance and FinOps teams to manage cloud spend proactively,
reduce waste, and make informed decisions around usage, purchasing, and optimization
strategies.

## Personas

- **IT Finance**

  Monitors cloud spend, supports budgeting and forecasting, and ensures financial
  accountability for cloud consumption.
- **FinOps / Cloud Center of Excellence (CCoE)**

  Optimizes cloud usage, manages allocation and governance, and drives cost efficiency
  across cloud platforms.
- **Solution Owners**

  Reviews cloud costs associated with applications, products, and services to ensure
  efficient consumption and accurate TCO.

## Use Cases

**Supported out-of-the-box**

**Cloud Cost Allocation & Showback (Foundational)**

Allocate and track cloud costs by department, team, environment, application, product, or
service to improve transparency, accountability, and responsible usage.

**Cloud Usage by Application (Intermediate)**

Tag and associate cloud usage with applications, services, products, or platforms to improve
governance, reduce sprawl, and enhance total cost of ownership (TCO) analysis.

**Pre-purchased Cloud Capacity Management (Intermediate)**

Monitor and manage pre-purchased cloud capacity such as reserved instances to secure lower
rates, prevent overruns, and maximize utilization.

**Cloud Cost Optimization (Advanced)**

Track, compare, and control cloud spend to identify inefficiencies, optimize consumption, and
improve overall cost efficiency.

## Outcomes

- Improved visibility into public cloud costs and consumption across applications, services,
  and business units.
- Increased accountability through accurate allocation and showback of cloud spend.
- Reduced cloud waste and improved cost efficiency through usage and optimization
  insight
- Better governance of cloud environments by linking usage to business and technology
  ownership.

- Stronger decision-making around cloud purchasing, capacity planning, and optimization
  strategies.

**Choosing Between Public Cloud Integrated and Public Cloud for IT Finance**

Apptio offers two Public Cloud capabilities designed to address different cloud cost
management needs. While both provide visibility into cloud spend, they differ in scope, data
sources, implementation effort, and the types of decisions they support. Selecting the right
option depends on the level of financial integration, depth of analysis required, and the
primary personas involved.

**Public Cloud Integrated (Integrated with Costing Standard Model)**

**Public Cloud Integrated** is the Public Cloud capability integrated with the Costing
Standard model. It combines cloud provider billing data with enterprise financial data from
the general ledger to provide a comprehensive view of total cloud cost.

This approach enables organizations to understand both **provider costs** (for example,
AWS, Azure, GCP bills) and **non-provider costs** (such as labor, support, and shared
services) associated with cloud usage. Non-provider costs are allocated to the Cloud IT
Resource Tower and weighted using cloud consumption data.

Public Cloud Integrated is well suited for organizations that require end-to-end cost
transparency and want cloud costs fully embedded into broader IT financial management and TBM
reporting.

**Best suited for organizations that:**

- Require a complete view of cloud TCO, including labor and shared services
- Want cloud costs aligned to IT Resource Towers and ATUM taxonomy
- Need chargeback/showback and allocation across applications, services, or business units
- Support advanced FinOps and TBM use cases

**Supported use cases include:**

- Cloud Cost Allocation & Showback
- Cloud Usage by Application
- Cloud Cost Optimization
- Public Cloud TCO within the broader IT cost model

**Key considerations:**

- Requires mapping of non-provider costs to the Cloud IT Resource Tower
- Implementation effort is higher due to model integration and allocations
- Designed for organizations with mature IT financial management practices

**Public Cloud for IT Finance (Standalone)**

**Public Cloud for IT Finance** is an independent, lightweight solution focused
exclusively on cloud provider spend. It consolidates cloud costs from multiple providers into
a single, easy-to-consume view without incorporating non-provider costs such as labor or
shared services.

This option is optimized for speed and simplicity, making it ideal for finance-led teams that
want fast visibility into cloud spend without the complexity of full cost model integration.

**Best suited for organizations that:**

- Need rapid visibility into cloud provider spend across AWS, Azure, GCP, and others
- Are primarily focused on IT Finance and high-level cost oversight
- Do not require allocation of non-provider or shared costs
- Want a solution that can be enabled in days rather than weeks

**Supported use cases include:**

- Cloud spend visibility across providers
- High-level cost tracking and trend analysis
- Finance-focused cloud reporting
- Pre-purchased Cloud Capacity visibility

**Key considerations:**

- Includes only provider-billed cloud costs
- Does not support full cloud TCO or cost allocations
- Not integrated into the Costing Standard model

**Which Option Is Right for You?**

|  |  |  |
| --- | --- | --- |
| **Consideration** | **Public Cloud Integrated** | **Public Cloud for IT Finance** |
| Cloud provider cost visibility | ✔ | ✔ |
| Non-provider cost inclusion (labor, support) | ✔ | ✘ |
| Integrated with Costing Standard & TBM | ✔ | ✘ |
| Cloud TCO and advanced allocation | ✔ | ✘ |
| Target persona | IT Finance, FinOps, CCoE, Service Owners | IT Finance |
| Time to value | Moderate | Very fast |
| Implementation complexity | Higher | Low |
