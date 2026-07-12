---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Cloud Sustainability Reporting"
breadcrumb:
  - "Insights"
  - "Cloud Sustainability Reporting"
source_path: "SSVCLNQ/product/cld-sustainability-reporting.html"
images:
  - "03-media/apptio-cloudability-standard/Sustainability-Metrics.png"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Cloud Sustainability Reporting

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
