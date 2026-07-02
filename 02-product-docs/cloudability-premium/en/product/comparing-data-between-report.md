---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "product"
title: "Comparing Data Between Report UI and CSV Exports"
breadcrumb:
  - "Cloudability Premium"
  - "Data reference"
source_path: "product/comparing-data-between-report.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Comparing Data Between Report UI and CSV Exports

When you export your reports in Cloudability , you may
observe:

- The unit of measurements for some metrics do not match between report UI and exported CSV data.
- A few column headers do not match between report UI and exported CSV data.

**Difference in Unit of Measurements (UoM) between report UI and exported CSV data**

Exported data in CSV may show a different unit of measurement for some metrics. For some
measures such as GB, and percentage, we want to provide values as decimals with full available
precision and without formatting, so that you can format as desired for programmatic uses and don't
have to try to "parse away" the formatting. However, providing such “raw numbers” with full decimal
precision in the report UI would make the UI less usable.

**Difference in Column Headers between report UI and Exported CSV data**

Refer to this table to understand the mapping of those column headers that differ between
exported CSV data and report UI:

| Header in Exported CSV | Header in Report UI | Remarks |
| --- | --- | --- |
| invoiced\_cost | Cost (Total Blended) | � |
| blended\_rate | Rate (Blended) | � |
| cost\_before\_tax | Cost (Total Unblended Before Taxes) | � |
| Iops | IOPS Months | � |
| gb\_months | GiB Months | � |
| byte\_hours | GiB Hours | � |
| Month | Month (Category) | � |
| service\_key | Product Code | � |
| service\_name | Product Name | � |
| region\_zone | Availability Zone | � |
| account\_identifier | Payer Account ID | � |
| account\_name | Payer Account Name | � |
| vendor\_account\_identifier | Account ID | � |
| group\_name [x] | Account Group [x] | 'x’ stands for the cardinality of Account Groups (For example: Account Group 1, Account Group 2, Account Group 3) in your Cloudability environment. |
| is\_capex | One-time charges | � |
| Week | Week (Category) | � |
| bytes\_transferred | Data Transfer (GiB) | � |
| unblended\_cost | Cost (Total) | � |
| unblended\_rate | Rate (Unblended) | � |
| reserved\_utilization\_rate | Reserved Coverage Rate | � |
| resource\_identifier | Resource ID | � |
| resource\_identifier\_count | Resource Count | � |
| total\_amortized\_cost | Cost (Amortized) | � |
| reservation\_identifier | Reservation ID | � |
| enhanced\_service\_name | Service Name | � |
| year\_month | Month (Year) | � |
| year\_week | Week (Year) | � |
| cost\_adjusted | Cost Adjustment | � |
| adjusted\_cost | Cost (Adjusted) | � |
| Category[x] | Business Dimension [x] | ‘x’ stands for the cardinality of Business Dimensions (For example: Business Dimension 1, Business Dimension 2, Business Dimension 3) in your Cloudability environment. |
| categorykey[x] | Business Dimension Key [x] | ‘x’ stands for the cardinality of Business Dimension Keys (For example: Business Dimension Key 1, Business Dimension Key 2, Business Dimension Key 3) in your Cloudability environment. |
| total\_adjusted\_amortized\_cost | Cost (Adjusted Amortized) | � |
| public\_on\_demand\_cost | Cost (List) | � |
| offering\_class | Reservation Class | � |
| container\_cluster\_name | Cluster Name | � |
| container\_namespace | Namespace | � |
| ancestry\_numbers | GCP Ancestry Numbers | � |
| amortized\_fairshare\_cost | Fairshare Cost (Amortized) | � |
| amortized\_utilized\_cost | Utilized Cost (Amortized) | � |
| amortized\_idle\_cost Idle | Cost (Amortized) | � |
| adjusted\_fairshare\_cost | Fairshare Cost (Adjusted) | � |
| adjusted\_utilized\_cost | Utilized Cost (Adjusted) | � |
| adjusted\_idle\_cost | Idle Cost (Adjusted) | � |
| adjusted\_amortized\_fairshare\_cost | Fairshare Cost (Adjusted Amortized) | � |
| adjusted\_amortized\_utilized\_cost | Utilized Cost (Adjusted Amortized) | � |
| adjusted\_amortized\_idle\_cost Idle | Cost (Adjusted Amortized) | � |
