---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Report overview - Reserved Instances"
breadcrumb:
  - "Costing Standard"
  - "Report Walkthrough"
  - "Previous Version Layouts"
  - "Cloud Reports"
source_path: "cost-transparency/reports-v104/reservedinstances.html"
images:
  - "resources/images/ct_images/reservedinstances_1.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Report overview - Reserved Instances

Note: Applies to: Apptio Costing Standard on TBM Studio 12.3.3 and later; Cloud Business Management
on TBM Studio 12.6 and later

The Reserved Instances report provides an explanation of your current inventory of AWS and Azure
reserved instances (RIs), and can help you to make decisions about ongoing purchases of reserved
instances. Azure reserved instances are available starting with TBM Studio 12.6.

This report provides a view into the following:

- The current set of reserved instances purchased by your organization
- The reserved instances that have expired recently, or that are due to expire soon

  Note: These analytics will only be populated if you bring in your reserved instance
  purchases via DataLink.
- Recommendations to purchase additional reserved instances

  Note: These analytics
  will only be populated if you bring in your AWS Trusted Advisor data. For more information, see
  [Configure recommendations for Public Cloud potential savings](../user%20guide/configrecsforpubliccloud-7051.html "(Opens in a new tab or window)").

## KPIs

- **Invoiced Cost** - This is the actual, invoiced monthly and YTD cost associated with your
  organization's reserved instance purchases. This data comes from the reserved instance purchase line
  items in your AWS bill.
- **Amortized Cost** - This is the amortized monthly and YTD costs associated with your
  organization's RI purchases. This cost is calculated in Apptio and spreads any upfront RI costs
  evenly across the life of the RI and adds in the monthly recurring costs. This data comes from the
  RI purchases that are separate from your AWS bill.
- **Instances Expiring Soon** - The number of instances that will expire in the next 30 days or
  have expired in the past 30 days. This data comes from the same RI purchase data used to calculate
  the amortized cost.
- **Recommended Additional 1 Year RIs** - The additional RIs recommended for purchase based on
  the AWS Trusted Advisor and Azure Advisor.
- **1 Year Total Savings** - The potential savings associated with the additional recommended
  RI purchases. This data comes from AWS Trusted Advisor.

## Reports

- **Active Reserve Instances** - An inventory and cost analysis of your Reserved Instances that
  your organization has purchased.
  - **Cash Based** - This tab provides a view into your actual billed RI purchase costs and is
    sourced from the AWS bill.
    - **Instance Count** - The number of instances associated with each Reserved Instance
      purchase.
    - **Cloud Invoice Cost** - The billed cost for the current month.
    - **Cloud Invoice Cost YTD** - The year-to-date billed cost.
  - **Amortized Based** - This tab provides a view into the amortized costs associated with the
    RIs your organization has purchased. Data within this tab is driven by the RI purchases, which is
    obtained through AWS APIs separate from your billing.
    - **Instance Count** - The number of instances associated with each RI purchase.
    - **Upfront Cost** - The upfront cost of the RI purchase.
    - **Monthly Recurring Cost** - The monthly recurring cost for the RI purchase. This will only
      be associated with No Upfront or Partial Upfront RI purchases, where your organization gets billed
      every month for the term of the RI.
    - **Amortized Monthly Cost** - This is an Apptio-calculated value that is based on adding the
      amortized Upfront Cost to the Monthly Recurring Cost.
- **Expiring Reservations** - This tab provides a view into those RIs that have expired
  recently or are due to expire soon.
- **RI Purchase Recommendations** - This tab is driven from AWS Trusted Advisor RI Optimization
  check and Azure Advisor. It surfaces additional RI purchases that your organization can make based
  on your actual on-demand EC2 usage. For more information from AWS, refer to the AWS Trusted Advisor
  documentation: [https://aws.amazon.com/premiumsupport/ta-faqs/](https://community.apptio.com/external-link.jspa?url=https%3A%2F%2Faws.amazon.com%2Fpremiumsupport%2Fta-faqs%2F "(Opens in a new tab or window)")
  - **Recommended Additional RIs** - The number of additional RIs you should purchase to achieve
    the cost savings.
  - **Upfront Cost** - The initial upfront cost required for the recommended additional RI
    purchases.
  - **Estimated Monthly Savings** - The approximate amount of savings to be achieved through the
    additional RI purchases.
  - **Total Savings Over Term** - The total savings to be achieved over the the term (1 or 3
    year) of the additional RI purchases.
- **RI Consumption** - This tab provides a view into the consumption of your reserved instances
  based on usage quantity and compares consumption between reserved instances and on-demand costs
  (available in v12.5+).
  - **Usage Qty** - the total Instance Hours used during the selected month
  - **Fixed RI Costs** - the total amortized RI costs (recurring + amortized upfront) associated
    with the line item for the selected month
  - **Usage Cost** - the total on-demand costs associated with the line item for the selected
    month
  - **Non-Provider Costs** - the total costs that are incurred as a result of using cloud, but
    that are not associated with a cloud provider (e.g. 3rd party software costs, labor costs, etc)
  - **Shared Cloud Infra** - the costs associate with those services in the cloud provider that
    are shared. These shared services could include Enterprise Support, VPCs, or any other tooling or
    foundational services used to deliver apps or services on AWS.
- **AWS RI Utilization** - This tab provides information about RI usage month over month,
  trends in usage, and the dollar amount saved in relation to RI hours. When on-demand usage is in
  excess of 100%, the cost of over-spending is shown.(Available in 12.6 and later, with template v106)
  - **Total Reserved Units** - The number of hours reserved for the selected month as part of the
    RI purchase
  - **Used Quantity** - The number of reserved hours used by resources during the selected
    month
  - **Reservation Utilization %** - The percent of purchased RI hours that are used during the
    selected month. This is calculated by dividing Used Quantity by Total Reserved Units.
  - **Effective Monthly Cost** - The RI costs (amortized upfront + monthly recurring) for the
    selected month
  - **Hypothetical On-Demand Cost** - the cost your organization would have incurred in the
    selected month if no RIs were purchased. This is calculated by multiplying the Used Quantity by the
    On-Demand rate for the types of instances associated with the line item in the table.
  - **Cost Savings / Overspend** - this is either the value you saved assuming by buying RIs or
    how much you organization has overspent by buying RIs and not fully utilizing those RI purchases.
    This is calculated by subtracting the Hypothetical On-Demand Cost by the Effective Month Cost.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/reservedinstances_1.png)
