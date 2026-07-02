---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "product"
title: "TrueCost Explorer"
breadcrumb:
  - "Cloudability Premium"
  - "Insights"
source_path: "product/explore-cost-drivers-with-truecost-explorer.html"
images:
  - "images/explore_cost_drivers_1.jpg"
  - "images/topline-items.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# TrueCost Explorer

TrueCost Explorer helps you to understand the structuring of cloud billing files. It offers a visually intuitive way to explore your billing data and answer questions about cost drivers.

![true cost explorer screenshot](../../../../03-media/cloudability-premium/images/explore_cost_drivers_1.jpg)

Use Case

Most customers have had an experience where data transfer costs spike. In most cases, it is not possible to know which of the dozens of attributes your vendor uses to identify data transfer, as well as the various ways that data transfer can manifest in the billing file (there are over 20,000 distinct line items that relate to data transfer in AWS alone).

With the TrueCost Explorer, you can do the following:

- Click  Add Filter  and Select  Usage Family 
  dimension that is equal to  Data Transfer  . You can see a single view of your data
  transfer costs across vendors. Also, irrespective of vendor, Data Transfer costs have a LeaseType of
  On-Demand. You can also see the Services that are driving Data Transfer costs, which in this example
  are primarily AWS EC2 and Azure Networking.
- Now rearrange the columns and add the  Operation  dimension to see additional
  insights about  Data Transfer  costs. Here, you can see that on the Azure side,
  your data transfer costs are driven by Data Transfer out. Also, you can see that the vast majority
  of Data Transfer costs are InterZone transfer costs. Since those costs relate to moving data between
  Availability Zones within AWS, call out the region and adjust the plotting filters to see how many
  small data transfer charges are available

So, here we have learnt that:

- Data Transfer costs are primarily driven by AWS EC2 and Azure Networking, with a long-tail of
  10 other services contributing minor amounts
- Over 80 percent of Data Transfer costs are related to moving data between AWS Availability Zones
  in US-East-1
- Azure Data Transfer accrue primarily in the NorthCentralUS and WestEurope regions

If you want to understand what is driving your costs at an individual resource level, click the
appropriate node and select the View Top Line Items option.

![top line items screenshot](../../../../03-media/cloudability-premium/images/topline-items.jpg)

- **[Cost Basis for Rightsizing and True Cost Explorer](../chatbot/cost-basis-for-rightsizing-true-cost-explorer.html)**
