---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Cloud Sustainability Methodology"
breadcrumb:
  - "Insights"
  - "Cloud Sustainability Reporting"
  - "Cloud Sustainability Methodology"
source_path: "SSVCLNQ/product/cloud_sustainability_methodology.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Cloud Sustainability Methodology

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
