---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Cost Basis for Rightsizing and True Cost Explorer"
breadcrumb:
  - "Insights"
  - "TrueCost Explorer"
  - "Cost Basis for Rightsizing and True Cost Explorer"
source_path: "SSVCLNQ/chatbot/cost-basis-for-rightsizing-true-cost-explorer.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Cost Basis for Rightsizing and True Cost Explorer

True Cost Explorer helps you understand the structuring of cloud billing files. It offers a visually intuitive way to explore your billing data and answer questions about cost drivers. Cost Basis are the Cost Metrics from Reports in Cloudability.

- Metric 'Cost(List)' is equal to Cost Basis 'List'
- Metric 'Cost(Total)' = Cost Basis 'Cash'
- Metric 'Cost(Adjusted)' = Cost Basis 'Adjusted'
- Metric 'Cost(Amortized)' = Cost Basis 'Amortized'
- Metric 'Cost(Adjusted Amortized)' = Cost Basis 'Adjusted Amortized'

Learn more about the Cost Metrics .

Rightsizing focuses on identifying potential cost savings for different resources and provides you with recommendations to optimize costs for these resources. Cost Basis determines how saving opportunities are calculated, based upon On-Demand cost or Effective cost. If your organization has enabled custom pricing in Cloudability , the relevant custom rates will be applied to the cost basis calculations.

On-Demand: The On-Demand cost basis provides a direct comparison between the instance listed in the Current column and the instance recommended in the New column based purely on on-demand pricing. It does not include any potential impact from Reserved Instances (RIs) or Savings Plans (SPs).

Effective: The Effective cost basis takes into account the historical impact of Reserved Instances (RIs) and Savings Plans (SPs) to calculate the cost for the current instance type over the reporting period. Like the Cost (Amortized) metric, it includes all associated upfront and recurring costs. In other words, the effective cost basis shows the effective cost of running your current instance. The cost figures for the recommended new instance type are based on the on-demand prices. This is because the new configuration may not benefit from RIs or SPs. This comparison is the more conservative option. Even if you inadvertently move away from RIs or SPs, your new overall rate is still lesser. As a result, the overall savings reported using this methodology will sometimes be lower.

Learn more about the Rightsizing feature .
