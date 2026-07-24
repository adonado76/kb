---
source_system: "apptio-cloudability-standard"
practice: "finops"
language: "en"
doc_type: "cloudability-standard"
consolidated_file: "04-Insights-TrueCost-Explorer"
source_files_count: 2
last_updated: "2026-07-13"
---

# 04-Insights-TrueCost-Explorer

## TrueCost Explorer

<!-- sub-header -->
- **breadcrumb:** Insights > TrueCost Explorer
- **source_path:** SSVCLNQ/product/explore-cost-drivers-with-truecost-explorer.html
- **original_file:** insights-truecost-explorer.md
- **images:**
  - 03-media/apptio-cloudability-standard/explore_cost_drivers_1.jpg
  - 03-media/apptio-cloudability-standard/topline-items.jpg

TrueCost Explorer helps you to understand the structuring of cloud billing files. It offers a visually intuitive way to explore your billing data and answer questions about cost drivers.

Use Case

Most customers have had an experience where data transfer costs spike. In most cases, it is not possible to know which of the dozens of attributes your vendor uses to identify data transfer, as well as the various ways that data transfer can manifest in the billing file (there are over 20,000 distinct line items that relate to data transfer in AWS alone).

With the TrueCost Explorer, you can do the following:

- Click Add Filter and Select Usage Family dimension that is equal to Data Transfer . You can see a single view of your data transfer costs across vendors. Also, irrespective of vendor, Data Transfer costs have a LeaseType of On-Demand. You can also see the Services that are driving Data Transfer costs, which in this example are primarily AWS EC2 and Azure Networking.
- Now rearrange the columns and add the Operation dimension to see additional insights about Data Transfer costs. Here, you can see that on the Azure side, your data transfer costs are driven by Data Transfer out. Also, you can see that the vast majority of Data Transfer costs are InterZone transfer costs. Since those costs relate to moving data between Availability Zones within AWS, call out the region and adjust the plotting filters to see how many small data transfer charges are available

So, here we have learnt that:

- Data Transfer costs are primarily driven by AWS EC2 and Azure Networking, with a long-tail of 10 other services contributing minor amounts
- Over 80 percent of Data Transfer costs are related to moving data between AWS Availability Zones in US-East-1
- Azure Data Transfer accrue primarily in the NorthCentralUS and WestEurope regions

If you want to understand what is driving your costs at an individual resource level, click the appropriate node and select the View Top Line Items option.

---

## Cost Basis for Rightsizing and True Cost Explorer

<!-- sub-header -->
- **breadcrumb:** Insights > TrueCost Explorer > Cost Basis for Rightsizing and True Cost Explorer
- **source_path:** SSVCLNQ/chatbot/cost-basis-for-rightsizing-true-cost-explorer.html
- **original_file:** explorer-cost-basis-rightsizing-true-cost.md
- **images:** []

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

---
