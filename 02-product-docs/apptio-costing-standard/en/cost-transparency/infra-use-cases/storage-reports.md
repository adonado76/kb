---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Storage Reports"
breadcrumb:
  - "Costing Standard"
  - "Infrastructure Use Cases"
  - "Storage"
source_path: "cost-transparency/infra-use-cases/storage-reports.html"
images:
  - "resources/images/ct_images/storapp.png"
  - "resources/images/ct_images/stordev.png"
  - "resources/images/ct_images/storfin.png"
  - "resources/images/ct_images/storlun.png"
  - "resources/images/ct_images/storop.png"
  - "resources/images/ct_images/storspend.png"
  - "resources/images/ct_images/storsum.png"
  - "resources/images/ct_images/storutil.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Storage Reports

## Reports - Storage Cost Overview

**Storage TCO**

The Storage TCO report provides comprehensive visibility into
total storage costs and capacity across on-premises and public cloud environments. It
analyzes storage spend by sourcing type, environment, cost pool, IT tower, and vendor
while tracking key metrics such as addressable space, used space, and unit costs. This
report helps organizations understand how storage costs are distributed, how efficiently
storage capacity is utilized, and where cost optimization opportunities exist.

This
report is designed for use by the following roles:

- IT Finance
- Infrastructure and Storage Managers
- Cloud and Platform Owners
- Service and Solution Owners

Insights Provided:

- Understand total storage costs year-to-date across on-premises and public cloud
  environments with visibility into sourcing trends.
- Analyze storage spend by environment (Production, Development, Test) to support
  prioritization of critical workloads and investment decisions.
- Track addressable versus used storage capacity to identify over-provisioning,
  under-utilization, and reclamation opportunities.
- Compare unit costs such as cost per GB and cost per addressable TB to evaluate
  efficiency across storage platforms and tiers.
- Identify shifts in storage sourcing between on-premises and public cloud to support
  hybrid infrastructure planning and cloud migration strategies.
- Support budget planning, lifecycle management, and optimization initiatives by
  highlighting storage cost drivers, utilization patterns, and cost trends over time.

## Reports - Storage Insights & Optimization

The Storage (Insights & Optimization report) collection provides comprehensive
visibility into storage cost, capacity, utilization, and application consumption across
on-premises, public cloud, and hybrid environments. It brings together financial and
operational views of storage to help organizations understand how storage resources are
consumed, how costs are distributed, and where optimization opportunities exist across
devices, logical units, tiers, and applications.

This collection enables teams to monitor storage spend against plan, evaluate storage
efficiency and utilization trends, identify under-utilized or high-cost storage assets, and
support informed decisions around storage optimization, lifecycle management, and
infrastructure strategy.

The Storage Insights & Optimization collection includes the following reports:

- Storage Summary
- Storage Spend Profile
- Storage Operational Summary
- Storage Utilization Summary
- Storage Device Details
- Storage LUN Details
- Storage Financial View
- Storage By Application

Note: This collection is available in a separate endpoint: **Infrastructure Insights**.

**Storage Summary Report**

The Storage Summary report provides an enterprise-level view of total storage spend across
on-premises and public cloud environments. It highlights storage costs by IT tower,
environment, vendor, and sourcing model to help organizations understand where storage spend
is concentrated and how it is trending over time.

This report is designed for use by the following roles:

- IT Finance
- Infrastructure and Storage Managers
- Head of Operations
- Service Owners

Insights Provided:

- Understand total storage spend across on-premises and public cloud environments with
  year-to-date and monthly trends.
- Analyze storage costs by IT tower, cost pool, environment, and vendor to identify major
  cost drivers.
- Track changes in addressable and used storage capacity alongside unit cost metrics.
- Identify anomalies in storage spending and assess alignment with storage strategy over
  time.

For more details on how to use the Storage Summary report, go [here.](https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=reports-storage-summary "(Opens in a new tab or window)")

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/storsum.png)

**Storage Spend Profile Report**

The Storage Spend Profile report provides insight into planned versus actual storage spend
and capacity. It focuses on cost structure, installed and addressable capacity, and unit
cost trends to support financial planning and storage optimization.

This report is designed for use by the following roles:

- IT Finance
- Infrastructure and Storage Managers
- Service Owners

Insights Provided:

- Review year-to-date storage spend alongside installed and addressable capacity metrics.
- Understand storage cost distribution by cost pool and identify key contributors to
  monthly spend.
- Track changes in installed capacity and average cost per terabyte over time.
- Analyze storage spend by tier, location, and manufacturer to understand the overall
  storage cost profile.

For more details on how to use the Storage Spend Profile report, go [here.](https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=reports-spend-profile "(Opens in a new tab or window)")

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/storspend.png)

**Storage Operational Summary Report**

The Storage Operational Summary report provides operational visibility into storage costs
and capacity across locations, manufacturers, and storage types. It connects financial and
operational metrics to support day-to-day storage management decisions.

This report is designed for use by the following roles:

- Infrastructure and Storage Managers
- IT Operations
- Service Owners

Insights Provided:

- Analyze operational storage metrics such as cost, addressable capacity, and average unit
  cost by category.
- Compare storage costs across locations, manufacturers, and storage types.
- Identify operational cost anomalies and areas where storage efficiency can be improved.
- Support ongoing monitoring of storage operations against defined strategy and targets.

For more details on how to use the Storage Operational Summary report, go [here.](https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=reports-operational-summary "(Opens in a new tab or window)")

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/storop.png)

**Storage Utilization Summary Report**

The Storage Utilization Summary report focuses on how effectively on-premises storage
capacity is being used and how utilization impacts cost. It highlights allocated versus
available capacity and associated unit costs.

This report is designed for use by the following roles:

- Infrastructure and Storage Managers
- IT Operations
- Service Owners

**Insights Provided:**

- Understand effective cost per addressable and allocated terabyte of storage.
- Track utilization levels, including allocated versus available storage capacity.
- Identify under-utilized storage tiers and opportunities to reclaim unused capacity.
- Assess whether storage utilization aligns with cost and operational expectations.

For more details on how to use the Storage Utilization Summary report, go [here.](https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=reports-utilization-summary "(Opens in a new tab or window)")

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/storutil.png)

**Storage Device Details Report**

The Storage Device Details report provides granular visibility into physical storage
devices, including cost, capacity, allocation, and application usage. It enables detailed
analysis at the device level.

This report is designed for use by the following roles:

- Infrastructure and Storage Managers
- IT Operations

**Insights Provided:**

- Review storage spend and capacity metrics for individual storage devices.
- Compare installed, addressable, and allocated space at the device level.
- Identify high-cost or under-utilized storage devices.
- Understand which applications are supported by specific storage devices.

For more details on how to use the Storage Device Details report, go [here.](https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=reports-device-details "(Opens in a new tab or window)")

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/stordev.png)

**Storage LUN Details Report**

The Storage LUN Details report provides insight into storage costs and utilization at the
logical unit (LUN) level. It supports granular analysis of logical storage allocation and
application dependency.

This report is designed for use by the following roles:

- Infrastructure and Storage Managers
- IT Operations
- Service Owners

Insights Provided:

- Analyze storage spend and capacity at the logical unit level.
- Compare total versus used space for individual LUNs.
- Understand which applications consume specific logical storage units.
- Identify opportunities to optimize or consolidate logical storage allocations.

For more details on how to use the Storage LUN Details report, go [here.](https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=reports-storage-lun-details "(Opens in a new tab or window)")

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/storlun.png)

**Storage Financial View Report**

The Storage Financial View report provides a financial perspective on storage spend across
multiple dimensions such as location, manufacturer, product, and cost pool. It supports
financial governance and cost transparency.

This report is designed for use by the following roles:

- IT Finance
- Infrastructure Managers

Insights Provided:

- View storage spend by cost pool and IT sub-tower to understand financial distribution.
- Analyze year-to-date storage costs across locations, vendors, and storage types.
- Identify cost anomalies and shifts in storage spending patterns.
- Support budgeting and financial planning for storage investments.

For more details on how to use the Storage Financial View report, go [here.](https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=reports-financial-view "(Opens in a new tab or window)")

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/storfin.png)

**Storage By Application Report**

The Storage By Application report provides an application-centric view of storage
consumption and cost. It connects storage spend directly to applications to support
accountability and optimization.

This report is designed for use by the following roles:

- Application Owners
- IT Finance
- Service Owners

Insights Provided:

- Understand storage spend and allocated capacity by application.
- Analyze how storage usage varies by tier, environment, and application criticality.
- Identify applications driving disproportionate storage costs.
- Support application-level optimization, chargeback, and rationalization initiatives.

For more details on how to use the Storage By Application report, go [here.](https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=reports-by-applications "(Opens in a new tab or window)")

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/storapp.png)
