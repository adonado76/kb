---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Understanding Commitments Using Cloudability Native Reporting"
breadcrumb:
  - "Optimize"
  - "Guide to Advanced Commitment Functionality"
  - "Understanding Commitments Using Cloudability Native Reporting"
source_path: "SSVCLNQ/product/understanding_commitments_using_cloudability_native_reporting.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Understanding Commitments Using Cloudability Native Reporting

Savings Plans (SP) is the new discount instrument launched by AWS. This topic explains how the savings plans are different from traditional discounting with reserved instances (RI) and also gives in depth knowledge into billing implications. You can use the Lease Type dimension, along with other regular dimensions and metrics about your SP usage.

Comparison of RIs

- The discount rates are identical between EC2 Instance SPs and Standard RIs, and between Compute SPs and Convertible RIs.
- With Savings Plans, you can make a commitment above the service and regional level (in the case of compute savings plans). This has major implications for how you plan and govern your cloud bill.
- Instead of committing to instance hours , you are now committing to dollar hours . You can verify if the dollars per hour you are committing to are the after Savings Plan discount dollars or the net cost.

Deep dive into billing implications

The major differences between how Savings Plans and RIs are handled in the detailed billing (CUR file) are mentioned here:

- The usage hours covered by SPs are largely represented as On Demand hours. The item description looks like $0.156 per On Demand Linux ... The standard cost metrics Unblended Cost and Unblended Rate are based on the On Demand figures. This is in contrast to RIs where the figures are heavily reduced.
- While the recurring costs for RIs (in the case of no-upfront or partial upfront) appeared as one line item at the beginning of each month for SPs, the recurring costs are broken into individual lines for each hour in the month. All the lines for the month load as the month begins, meaning that you have future cost reporting in the CUR file.
- There is a brand new type of billing line called Negation that allows the regular cost metrics to accurately represent your bill at the monthly level.

Use Case

Let us see how this holds together for one SP being consumed over one hour. This is a very simple example from the CUR file for a no-upfront EC2 Instance Savings Plan:

![Notes Icon](../images/understanding_how_aws_savingsmceclip0.jpg)

The first two lines are the actual EC2 instance usage hours which fully consume the SP for that hour.

The scenario

The Unblended Cost nets out to the recurring fee, which is our discounted rate. This is a result of the negation line completely negating the two usage lines. However, neither the negation nor the recurring lines include the resource ID or important information, like tags. This means that if you are allocating costs based on tags or resource IDs, you are going to get the On-Demand cost for hours covered by SPs and heavily reduced costs for hours covered by RIs. What to do?

The solution

Cloudability gives you two straightforward ways to fairly allocate cost in a world where RIs and SPs are impacting cost line items. The Cost (List) metric completely removes the impact of any commitment based discounting, thereby removing the unpredictable nature of discounts being applied. The Cost (Amortized) metric allows you to pass on the benefits to your teams while making sure there's consistent behavior between RIs and SPs. This metric can be used throughout Cloudability and associates the full cost (including the upfront component) of RIs and SPs at the resource level. This allows for a complete True Cost roll up.

Further information

- To know the historical behavior of RIs, see Understanding AWS Cost Metrics: Do You Have a True Cost Metric?
- To know more about reports, see Custom Report .
