---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Public Cloud Getting Started"
breadcrumb:
  - "Costing Standard"
  - "Financial Use Cases"
  - "Public Cloud"
source_path: "cost-transparency/it-financials/pc-getstart.html"
images:
  - "resources/images/ct_images/pc-itfin.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Public Cloud Getting Started

## Public Cloud Integrated Getting Started

Use the **Public Cloud Integrated (CTF-Cloud)**component to load, allocate, and analyze
public cloud spend as part of the Costing Standard model. This component enables reporting
on public cloud IaaS and PaaS costs and supports fully burdened cloud TCO analysis by
combining cloud provider billing data with general ledger–based IT costs.

Install and configure this component before reviewing cloud reports. After the component is
installed, cloud billing data is ingested automatically and mapped to the required master
data tables to support allocation, reporting, and analysis across IT Resource Towers,
applications, and services.

**Component Install** 

The CTF-Cloud component provides the foundational data
and logic required for public cloud reporting and analysis. It supports the following
capabilities:

- Enables reports and KPIs to track and manage public cloud spend across providers,
  services, and IT Resource Towers.
- Uses detailed cloud billing data to map cloud services to IT Resource Sub-Towers and
  allocate general ledger costs at a more granular level.

This component is used when organizations want visibility into both cloud provider
costs and associated non-provider costs**,** such as labor, software, and shared IT
services, required to operate cloud environments.

**Public Cloud TCO NX Reports (Additional Component)**

This component provides
predefined NX reports based on public cloud cost data for analysis across services, accounts, and
time periods.

Use this component when:

- You need standard cloud cost reports
- You want to compare actuals and budgets
- You require consistent cloud cost reporting

**Prerequisites**

Before using the CTF-Cloud component, ensure the following
components are installed and configured:

- CTF- Cost Source
- CTF- Vendor

These components provide the financial and vendor context required to fully burden
cloud costs.

**Cloud Data Sources** 

Public cloud cost data is sourced from Cloudability
and ingested into Apptio through Apptio Data Management (ADM)**.** The data is
refreshed on a scheduled basis and loaded into cloud-specific monthly billing tables,
including:

- AWS: `cldy_monthly_aws`
- Azure: `cldy_monthly_azure`
- GCP: `cldy_monthly_gcp`

For additional guidance on configuring Apptio Data Management (ADM), refer to the
documentation available [here](https://www.ibm.com/docs/en/apptio-platform/adm/saas?topic=creation-entity-cloudability "(Opens in a new tab or window)")

**Datasets** 

**CLDY Transform Master Data** - Billing data from the cloud
monthly tables is then mapped to the CLDY Transform Master Data, which normalizes
provider-specific services.

**Cloud Service Provider Master Data** - The
transformed data is subsequently mapped to the Cloud Service Provider Master Data,
enabling consistent classification across providers and alignment to the Apptio TBM
Unified Model (ATUM).

For detailed guidance, refer to the documentation available
here.

## Public Cloud for IT Finance Reports

The Public Cloud for IT Finance reports provide IT finance teams with a consolidated and
finance-focused view of public cloud spending across major cloud providers such as AWS and
Azure. These reports are designed to highlight the financial drivers of cloud costs,
including services contributing to spend growth, purchase model effectiveness, unit rate
behavior, and consumption trends. With built-in drill-downs, the reports enable deeper
analysis of cost movements by provider, service, account, and underlying business or
technical drivers, supporting stronger financial governance and informed decision-making.

This report is designed for use by the following roles:

- IT Finance
- Financial Controllers

**Insights Provided:**

- Identify the highest cost-driving cloud services and providers to focus cost control
  and optimization efforts.
- Evaluate the effectiveness of cloud purchase models against best-in-class benchmarks
  to uncover savings opportunities.
- Monitor unit rate and consumption trends to detect pricing anomalies, efficiency
  improvements, or usage-driven cost increases.
- Use drill-down analysis to link costs to specific accounts, business services, and
  applications for accountability, root-cause analysis, and informed budgeting decisions.

For more details on how to use the Public Cloud for IT Finance reports, go [here.](https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=reports-public-cloud-tcooverview "(Opens in a new tab or window)")

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/pc-itfin.png)

## Public Cloud for IT Finance Getting Started

Public Cloud for IT Finance enables organizations to analyze and govern public cloud spend
using a finance-centric model focused on provider costs, usage, and unit economics. The
solution integrates directly with Cloudability data to deliver standardized, cross-provider
reporting for AWS, Azure, GCP, and OCI, without requiring allocation of non-provider costs.
It is designed for rapid deployment and is well suited for IT finance teams seeking fast
visibility into cloud spending, trends, and optimization opportunities.

**Components Install**

**Public Cloud TCO**

This component supports integration with the following cloud providers:

- Amazon Web Services (AWS)
- Microsoft Azure
- Google Cloud Platform (GCP)
- Oracle Cloud Infrastructure (OCI)

Note: This component is available in templates **v120 and later**.

After
installing the component, proceed with loading and mapping the required datasets into the
master data tables to enable reporting.

**Common Sources of Data**

Public Cloud for IT Finance relies on Cloudability as the primary source of cloud cost
and usage data:

- **Apptio Data Management (ADM)**

  Provides monthly cloud spend and usage datasets such as
  `cldy_monthly_aws` and `cldy_monthly_azure`, which
  form the foundation for cost and consumption reporting.

  For additional guidance
  on configuring Apptio Data Management (ADM), refer to the documentation available
  [here](https://www.ibm.com/docs/en/apptio-platform/adm/saas?topic=creation-entity-cloudability "(Opens in a new tab or window)")
- **Cloudability Reserved Instance (RI) Reports via REST Services**

  Supplies reserved hours and utilization data used to calculate Reserved Instance and
  Savings Plan effectiveness across AWS, Azure, and GCP.

**Master Datasets** 

To enable reporting, the following **five input
datasets** must be created and mapped using Cloudability source data (for example,
`cldy_monthly_aws`, `cldy_monthly_azure`):

- **Account Mapping → Account Name Mapping**

  Aligns cloud account names extracted from Cloudability datasets.
- **BU Reference Input → Business Unit Reference**

  Normalizes regions or organizational identifiers into standardized business units.
- **Cloud Tower Mapping Input → Cloud Tower Mapping**

  Maps cloud usage families to normalized Cloud Tower names for reporting consistency.
- **CC Input → Cost Center Listing**

  Maps cost centers and categories; any unmapped values appear as *Unassigned*.
- **RI Input → Reserved Hours**

  Enables calculation of Reserved Instance and Savings Plan utilization metrics across
  supported providers.
- Map the above datasets to **IT Finance Cloud Master Data** using the *Data
  Source* column to reference the Cloudability dataset name (for example,
  `cldy_monthly_aws`).

For detailed configuration guidance, refer to the supporting documentation [here.](https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=reports-public-cloud-tcoconfiguration "(Opens in a new tab or window)")
