---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "product"
title: "Azure Disk"
breadcrumb:
  - "Cloudability Premium"
  - "Optimize"
  - "Rightsizing in Cloudability Premium"
  - "Advanced Rightsizing"
source_path: "product/advanced-rightsizing-for-azure-disks.html"
images:
  - "images/advanced-rightsizing-for-azure-disks-details.png"
  - "images/advanced-rightsizing-for-azure-disks.png"
  - "images/edit-icon.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Azure Disk

You can use the Advanced Rightsizing dashboard to view the resource optimization recommendations
for Microsoft Azure Disk. The dashboard shows optimization recommendations for both savings and
investments powered by Turbonomic engine. You can view the recommendations across multiple Azure
accounts from a single dashboard.

[Advanced Rightsizing in Cloudability
Premium](advanced-rightsizing-powered-by-turbonomic.html)

Before you begin

To view the Azure Disk dashboard, make sure that you have connected Cloudability to the correct
Azure accounts.

[Connect Microsoft Azure](../admin/azure-cm-setup.html)

Note: You need to ensure all your existing vendor credentials have relevant Turbonomic required
permissions granted without which Turbonomic engine may not be able to generate right set of
actions. If you were a Cloudability customer prior to Cloudability Premium upgrade, you still need
to re-credential every single vendor credential to grant additional set of permissions.

Access the Azure Disk dashboard

To access the Azure Disk dashboard, open the Cloudability home page, and from the left navigation
menu, select  Optimize > Rightsizing > Advanced. On the Rightsizing page,
select the Azure tab, and then select the Disk subtab.

![](../../../../03-media/cloudability-premium/images/advanced-rightsizing-for-azure-disks.png)

Customize the dashboard

You can set the following options to customize your dashboard.

Note:

Only the On-Demand Cost Basis is supported for Disk.

The On-Demand cost basis provides a direct comparison between the instance listed in the
Tier column and the instance recommended in the New Tier
column based purely on On-Demand Pricing. It does not include any
potential impact from Reserved Instances (RIs) or Savings Plans (SPs). Note that the on-demand
prices will reflect any custom pricing agreements that you have configured in Cloudability.

Select Account

By default, the dashboard shows recommendations for all accounts. To view recommendations for a
particular account, select the account name from the Account drop-down.

Apply Filters

You can add filters to include or exclude data based on one or more conditions.

Add a filter

To add a filter:

1. Select Add Filter from the toolbar.
2. In the Add Filter menu, choose a Dimension.
3. Select an Operator to provide a logical condition.
4. Choose a value to refine your filter.
5. Select Add Filter to apply the new filter to the page.

Apply filters with links

You can also add filters by selecting the blue hyperlinked values in the main table. The filter
rule is automatically applied to the Filters field. You can select only one
value or parameter from each column at a time.

Remove a filter

To remove a filter:

1. Select the filter icon ![filter icon](../../../../03-media/cloudability-premium/images/edit-icon.jpg) .
2. Select  X  next to the filter that you want to remove.

Key Performance Indicators

You can view the following Key Performance Indicators (KPIs) on your Advanced Rightsizing
dashboard:

- Total Spend : Shows the total current allocated spend
- Potential Savings : Shows the estimated total potential savings
  achievable for all optimizationrecommendations with lower cost impact than
  the current cost
- Necessary Investments : Shows the estimated total potential investments
  across all optimizationrecommendations with higher cost impact than the
  current cost

Rightsizing recommendations table

The dashboard contains a rightsizing recommendations table, which provides an overview of Azure
Disk resources for which optimization recommendations have been identified. The table includes the
following columns:

Note:

By default, the data is sorted by the Cost Impact column. To change the
sort order, just select the column name.

- Status :  Status indicating readiness of action execution
- Resource Name : The Disk resource name
- Account Name : The account name
- Non Disruptive : Indication if the action presented is
  non-disruptive
- Reversible : Indication if the action presented is reversible or not
- Attached VM : Azure VM to which this Disk is attached to
- Tier : The current Disk storage tier
- Disk Size : Current Disk disk size
- IOPS : Current Disk IOPS
- **Cost** : The current Disk storage cost
- New Tier : The recommended Disk storage tier
- New Disk Size : The recommended Disk storage size
- New IOPS : The recommend Disk IOPS
- Action Category : The category of the action recommended. Current
  supported ones are "Performance" or "Savings"
- Action : The action recommended. Table below lists various supported
  actions
- Cost Impact : Cost impact of implementing this action

| Recommendation | Description |
| --- | --- |
| Scale | Resize to the resource type specified in the New Tier column. This can be "Scale up" or "Scale down" action based on the policies configured |
| Delete | Delete your resource |

Export optimization recommendations to an Excel file

To export the recommended actions to an excel file, select Export. Note
that the excel file will include several additional columns, such as region, operating system, unit
price, and others.

Recommendation details

To view the recommended action details for a particular resource, select View Details
from the More Options (3 dots) menu.

The following figure shows a sample action details panel.

![](../../../../03-media/cloudability-premium/images/advanced-rightsizing-for-azure-disks-details.png)

**Parent topic:** [Advanced Rightsizing](../product/advanced-rightsizing-powered-by-turbonomic.html)
