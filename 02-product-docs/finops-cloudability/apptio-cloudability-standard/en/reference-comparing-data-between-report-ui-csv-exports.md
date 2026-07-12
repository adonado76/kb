---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Comparing Data Between Report UI and CSV Exports"
breadcrumb:
  - "Data reference"
  - "Comparing Data Between Report UI and CSV Exports"
source_path: "SSVCLNQ/product/comparing-data-between-report.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Comparing Data Between Report UI and CSV Exports

When you export your reports in Cloudability , you may observe:

- The unit of measurements for some metrics do not match between report UI and exported CSV data.
- A few column headers do not match between report UI and exported CSV data.

Difference in Unit of Measurements (UoM) between report UI and exported CSV data

Exported data in CSV may show a different unit of measurement for some metrics. For some measures such as GB, and percentage, we want to provide values as decimals with full available precision and without formatting, so that you can format as desired for programmatic uses and don't have to try to "parse away" the formatting. However, providing such “raw numbers” with full decimal precision in the report UI would make the UI less usable.

Difference in Column Headers between report UI and Exported CSV data

Refer to this table to understand the mapping of those column headers that differ between exported CSV data and report UI:

| Header in Exported CSV | Header in Report UI | Remarks |
| --- | --- | --- |
| invoiced_cost | Cost (Total Blended) | � |
| blended_rate | Rate (Blended) | � |
| cost_before_tax | Cost (Total Unblended Before Taxes) | � |
| Iops | IOPS Months | � |
| gb_months | GiB Months | � |
| byte_hours | GiB Hours | � |
| Month | Month (Category) | � |
| service_key | Product Code | � |
| service_name | Product Name | � |
| region_zone | Availability Zone | � |
| account_identifier | Payer Account ID | � |
| account_name | Payer Account Name | � |
| vendor_account_identifier | Account ID | � |
| group_name [x] | Account Group [x] | 'x’ stands for the cardinality of Account Groups (For example: Account Group 1, Account Group 2, Account Group 3) in your Cloudability environment. |
| is_capex | One-time charges | � |
| Week | Week (Category) | � |
| bytes_transferred | Data Transfer (GiB) | � |
| unblended_cost | Cost (Total) | � |
| unblended_rate | Rate (Unblended) | � |
| reserved_utilization_rate | Reserved Coverage Rate | � |
| resource_identifier | Resource ID | � |
| resource_identifier_count | Resource Count | � |
| total_amortized_cost | Cost (Amortized) | � |
| reservation_identifier | Reservation ID | � |
| enhanced_service_name | Service Name | � |
| year_month | Month (Year) | � |
| year_week | Week (Year) | � |
| cost_adjusted | Cost Adjustment | � |
| adjusted_cost | Cost (Adjusted) | � |
| Category[x] | Business Dimension [x] | ‘x’ stands for the cardinality of Business Dimensions (For example: Business Dimension 1, Business Dimension 2, Business Dimension 3) in your Cloudability environment. |
| categorykey[x] | Business Dimension Key [x] | ‘x’ stands for the cardinality of Business Dimension Keys (For example: Business Dimension Key 1, Business Dimension Key 2, Business Dimension Key 3) in your Cloudability environment. |
| total_adjusted_amortized_cost | Cost (Adjusted Amortized) | � |
| public_on_demand_cost | Cost (List) | � |
| offering_class | Reservation Class | � |
| container_cluster_name | Cluster Name | � |
| container_namespace | Namespace | � |
| ancestry_numbers | GCP Ancestry Numbers | � |
| amortized_fairshare_cost | Fairshare Cost (Amortized) | � |
| amortized_utilized_cost | Utilized Cost (Amortized) | � |
| amortized_idle_cost Idle | Cost (Amortized) | � |
| adjusted_fairshare_cost | Fairshare Cost (Adjusted) | � |
| adjusted_utilized_cost | Utilized Cost (Adjusted) | � |
| adjusted_idle_cost | Idle Cost (Adjusted) | � |
| adjusted_amortized_fairshare_cost | Fairshare Cost (Adjusted Amortized) | � |
| adjusted_amortized_utilized_cost | Utilized Cost (Adjusted Amortized) | � |
| adjusted_amortized_idle_cost Idle | Cost (Adjusted Amortized) | � |
