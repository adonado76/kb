---
source_system: "apptio-cloudability-standard"
practice: "finops"
language: "en"
doc_type: "cloudability-standard"
consolidated_file: "04-Insights-Cloud-Sustainability"
source_files_count: 2
last_updated: "2026-07-13"
---

# 04-Insights-Cloud-Sustainability

## Cloud Sustainability Reporting

<!-- sub-header -->
- **breadcrumb:** Insights > Cloud Sustainability Reporting
- **source_path:** SSVCLNQ/product/cld-sustainability-reporting.html
- **original_file:** insights-cloud-sustainability-reporting.md
- **images:**
  - 03-media/apptio-cloudability-standard/Sustainability-Metrics.png

Overview

Using this feature Cloudability users will be able to view their Public cloud carbon footprint (Operational + Embodied) for the supported services.

Prerequisites

To access the Cloud Sustainability metrics, customers should meet the following prerequisites:

- For accessing cloud carbon metrics, customers must have Cost data for 1 month.
- Customers should have advanced credentials enabled for calculations at actual utilization levels else we'll default to 50% utilization levels
- For GCP customers, Detailed billing must be enabled.
- Applicable for Cloudability Standard and Cloudability Premium Customers.

Introduction

Cloudability users can quickly and easily view the cloud sustainability metrics to get insights into their public cloud carbon emissions. Cloud Sustainability metrics are available within Cloudability reports and dashboards using the below metrics:

- Operational Carbon Emission (MTCO2e) - This metrics represents the carbon emissions generated during the day-to-day operation of cloud services. It primarily comes from the electricity used to power and cool data centers while running workloads.
- Embodied Carbon Emission (MTCO2e) - This metrics represents the share of carbon emissions tied to the production and lifecycle of cloud infrastructure. In the cloud context, it’s estimated by allocating a portion of the total embodied emissions of physical servers and equipment based on your specific usage.
- Estimated Carbon Emissions (MTCO2e) – This metric represents the total estimated carbon emissions, sum of Operational and Embodied carbon emissions. This provides a complete view of your cloud carbon footprint in metric tons of CO₂ equivalent.
- Power Consumed (kWh) – Power consumed in kilo watt hours. Cloudability calculates the cloud carbon footprint for all major CSPs (AWS, Azure, GCP & OCI) and offers a uniform methodology for comparing cloud carbon emissions across different vendors.

These metrics are available at a resource level for the below supported services.

| AWS | Azure | GCP | OCI |
| --- | --- | --- | --- |
| EC2 | Compute | GCE | Compute |
| EBS | Managed Disk | Persistent Disk |  |
| RDS | Azure Database - SQL Server - PostgresSQL | Cloud SQL |  |

Where to find the metrics

Cloudability > New Reports or Add Widget > Sustainability category

There is also a Sample Dashboard - Cloud Sustainability configured which can be found in All Dashboards within Cloudability

Methodology

For calculating carbon emissions, our methodology is a bottom-up approach where the emissions from individual resources are calculated separately. These calculated emissions are then aggregated to collectively represent an organization’s total emissions resulting from its cloud infrastructure usage.

For more detail, see Methodology

Frequently Asked Questions

1. How Can I get started on viewing the Sustainability Metrics?

Please check the default dashboard configured for sustainability under all dashboards in Cloudability.

2.What differentiates Cloudability's solution from any other available solution?

- The methodology is cloud agnostic and applies same logic across ISPs making the comparisons easier and consistent.
- The methodology provides the results at a granularity of each Resource Id.
- The metrics can be rolled up to any supported dimensions like Region, Service, Vendor etc and also time dimensions like Year, Month, Week etc also allowing YTD, MTD or YoY and MoM comparisons.
- The metrics use actual utilization.
- Once available, the data honors the views, business mappings created which allows the cloudability users to view the emissions based on their data entitlement.
- The emissions can be used in conjunction with the cost and usage metrics to compare cost trends vs emissions trends.
- The solution uses Grid Emissions data from the latest data available by local government agencies like EEA and EPA to have authentic data for calculating carbon emissions.

3. Does Cloudability provide Scope 1, Scope 2 and Scope 3 emissions as part of this feature?

Cloudability provides Scope 3 Operational and embodied carbon emissions.

- The combustion of any fuel to generate energy on-premise by an organization attributes to Scope 1, using the energy generated elsewhere to run the equipment contributes to Scope 2 while the supply chain contribute for Scope 3 emissions.
- As consumers of Public Cloud, we use the Cloud services offered by the CSPs while having no control over the electricity, maintenance of the cloud equipment or cooling of the data center. Hence the emissions scope is only Scope 3 emissions for a customer.

4. How frequently are the Carbon metrics updated?

Carbon metrics will be updated on 15th of every month for the previous month. e.g. on 15 April we’ll populate the metrics for March

5. I s it possible to get historical data on Cloud Emissions ?

No historical data updates are not available.

6. What is the granularity of Sustainability metrics?

The granularity is at resource level and Cloudability provides data at a daily granularity.

7. Are yearly, monthly, weekly comparisons possible?

Yes these comparisons are possible using Cloudability dashboards and reports.

8. Is it possible to compare cost trends vs emission trends?

Yes its possible to compare cost vs emission trends at a dimension of choice. Sharing a few commonly used dimensions below

- YTD, MTD
- Region
- Vendor
- Day, Week, Month, Year

9. Will the Carbon Emissions be available in the API?

Yes, all four metrics will be available through the API. Please ever the Cloudability API docs

10. Do you support views and Business Mappings with Sustainability metrics ?

Yes, all views and Business mappings are supported in Sustainability metrics, similar to reports and dashboards.

11. I am seeing a bump up in Emissions stating October 2025 data, why is it so?

This is because starting Oct 2025 data , Cloudability considers both Operational and Embodied emissions. Before this date Cloudability only considered Operational Emissions.

12. Is it mandatory to advance credential for getting sustainability metrics?

We recommend having advance credentials enabled for more accurate calculations, if enabled Cloudability considers actual utilization levels for the supported services else we consider a default 50% utilization for the calculations.

13. I compared Cloudability carbon emissions metrics with the CSP emissions and the numbers don't match, What should I do?

We don't recommend comparing the emissions as the Methodologies, data granularity, emission scopes can be different. Please refer Cloudability's Cloud Sustainability Methodology for more details on exclusions and inclusions.

14. Are there any permissions required to access the Sustainability reporting?

No Additional permissions are required for using Sustainability reporting. Reporting is available to all users and customers on Cloudability Standard and Premium.

---

## Cloud Sustainability Methodology

<!-- sub-header -->
- **breadcrumb:** Insights > Cloud Sustainability Reporting > Cloud Sustainability Methodology
- **source_path:** SSVCLNQ/product/cloud_sustainability_methodology.html
- **original_file:** reporting-cloud-sustainability-methodology.md
- **images:** []

Before diving into the methodology used to calculate carbon emissions, it’s important to first understand the two main types of emissions involved. Carbon footprints typically originate from two primary sources: operational emissions and embodied emissions.

Operational Emissions

Operational emissions result from the day-to-day operation of cloud infrastructure. These emissions are primarily generated from the electricity consumed by cloud data centers to power and cool servers, networking equipment, and storage devices that host cloud services.

Embodied Emissions

Embodied (or embedded) emissions refer to the amount of carbon emitted during the manufacturing, transportation, and disposal of hardware devices.

To estimate embodied emissions in the cloud, we calculate the fraction of total embodied emissions that corresponds to the customer’s usage or workload. For example, if a user utilizes only a subset of virtual CPUs available on a physical server, a proportionate amount of embodied emissions is allocated to represent this usage.

Furthermore, emissions are classified into two categories: direct and indirect.

- Direct emissions : Released directly from sources owned or controlled by the organization.

- Indirect emissions : Result from the organization’s activities but are generated from sources not owned or directly controlled by it.

- Scope 1 (Direct Emissions): Emissions generated from sources owned or controlled by the company. Examples include fuel combustion in company-owned generators, on-site manufacturing processes, and company-owned boilers.
- Scope 2 (Indirect Emissions): Emissions generated from the consumption of purchased energy sources such as electricity, steam, or gas. Examples include purchased electricity for office buildings or steam/gas for industrial processes.
- Scope 3 (Indirect Emissions): Emissions that occur as a consequence of the company’s activities but are generated within its supply chain. Example: Operational emissions from cloud services such as virtual machines and storage provided by CSPs.

Cloudability’s sustainability metrics are based on the Cloud Carbon Footprint (CCF) methodology, enhanced with additional factors such as actual utilization data and machine learning–based power consumption modeling.

This approach uses a bottom-up methodology, where emissions for individual resources are calculated separately and then aggregated to represent an organization’s total cloud-related emissions.

Formula: Estimated Carbon Emissions (CO₂e) = Power Consumption per hour × Power Usage Effectiveness (PUE) × Grid Emissions × Usage Hours

Where:

- Power Consumption per hour: Calculated using ML models trained on machine specifications and utilization metrics.

- Power Usage Effectiveness (PUE) : A measure of data center energy efficiency which are published by the CSPs.

- Grid Emissions : Carbon emitted per unit of electricity generated (annual average).

- Usage Hours : Total operating hours of the machine.

Data Sources

| Dataset | Source |
| --- | --- |
| Dataset | Source |
| Power Usage Effectiveness (PUE) | GCP PUE – Google Cloud; AWS/Azure – Cloud Carbon Footprint; OCI – Oracle Cloud Infrastructure |
| Grid Emissions | EEA, EPA, Our World in Data, and Cloud Carbon Footprint |
| Usage Hours | Derived from cost data provided by each cloud provider |
| Utilization | Based on utilization data collected by Cloudability |
| Machine Specifications | Based on pricing and resource description data collected by Cloudability |

Calculation Methodology – Embodied Emissions

Embodied emissions are calculated using the Cloud Carbon Footprint methodology.

Formula: Embodied Emissions = TE × (TR1 / EL) × (RR / TR2)

Where:

- TR1 = Time Reserved, the length of time the hardware is reserved for use by the software (the amount of time a given compute instance was running for)

- EL = Expected Lifespan, the anticipated time that the equipment will be installed (4 years chosen by the Teads team) ( Dell PowerEdge R740 Full Lifecycle Assessment)

- RR = Resources Reserved, the number of resources reserved for use by the software (number of vCPUs of the given instance)

- TR2 = Total Resources, the total number of resources available (the largest instance vCPUs for the given family)

- TE = Total Embodied Emissions, the sum of Life Cycle Assessment (LCA) emissions for all hardware components. TE we are calculating with the help of Machine learning.

Total Embodied (TE) Emissions

Cloudability follows the Cloud Carbon Footprint (CCF) methodology to calculate Embodied Emissions, the carbon emissions associated with the manufacturing, transportation, and end-of-life processing of cloud hardware such as servers, networking, and storage equipment.

While the CCF framework provides a strong foundation, its publicly available embodied emissions data has not been updated since 2022. As a result, data for newer machine types and hardware generations from major Cloud Service Providers (CSPs) may be incomplete. To ensure comprehensive and up-to-date coverage, the Cloudability team has developed a machine learning–based model that estimates the Total Embodied Emissions (TE) for all available machine types across AWS, Azure, and Google Cloud. This enhancement enables Cloudability to deliver more accurate, current, and reliable embodied carbon estimates, supporting organizations in making informed sustainability decisions.

Example : For the m5 instance family, the largest machine (m5.24xlarge) has 96 vCPUs and total embodied emissions (TE) of 1610.79 kgCO₂e with a 4-year lifespan. If an m5.xlarge instance (4 vCPUs) runs for 30 minutes, its embodied emissions equal 1610.79 × (0.5 / 35,040) × (4 / 96) = 0.00134 kgCO₂e.

Benefits of this Methodology

- Comprehensive coverage: Captures both operational and embodied emissions, offering a complete view of cloud-related carbon impact.

- Cross-cloud consistency: Uses a unified methodology across Cloud Service Providers (AWS, Azure, GCP, and OCI) for accurate comparison.

- Actual Utilization: Leverages actual utilization metrics and machine learning–based modeling to improve precision in both operational and embodied carbon estimates.

- Up-to-date estimation: Addresses data gaps in public frameworks (such as CCF) by applying ML models to estimate values for newer hardware generations.

- Granular visibility: Provides emissions insights at the resource ID level, with roll-ups by region, service, vendor, or time period (month, year, year to date etc.).

- Lifecycle perspective: Accounts for emissions across the full hardware lifecycle from manufacturing and operation to decommissioning.

- Decision support: Enables correlation of cost and emissions trends to drive sustainable and cost-efficient cloud operations.

---
