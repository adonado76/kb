---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "product"
title: "Advanced Rightsizing for Kubernetes Containers"
breadcrumb:
  - "Cloudability Premium"
  - "Optimize"
  - "Rightsizing in Cloudability Premium"
  - "Advanced Rightsizing"
source_path: "product/advanced-k8s-container-rightsizing.html"
images:
  - "images/advanced-k8s-container-rightsizing-cs-details.png"
  - "images/advanced-k8s-container-rightsizing-wc-details.png"
  - "images/advanced-k8s-container-rightsizing.png"
  - "images/edit-icon.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Advanced Rightsizing for Kubernetes Containers

You can use the Advanced Rightsizing dashboard to view the resource optimization recommendations
for your Kubernetes container deployments. The dashboard shows optimization recommendations for both
savings and investments powered by Turbonomic engine.

[Advanced Rightsizing
in Cloudability Premium](advanced-rightsizing-powered-by-turbonomic.html)

Before you begin

To view the Containers dashboard, make sure that you have installed both Cloudability and
Turbonomic Kubernetes agents in each of your clusters

Note: You need to ensure both Cloudability metrics agent and Turbonomic Kubeturbo agents in each of
your Kubernetes clusters. Please follow the installation instructions documented here - [Provision Kubernetes Agents](advanced-rightsizing-powered-by-turbonomic.html)

Access the Containers dashboard

To access the Containers dashboard, open the Cloudability home page, and from the left navigation
menu, select  Optimize > Rightsizing > Advanced. On the Rightsizing page,
select the Containers tab. You can see all the workload controller **resize**
optimization actions powered by the Turbonomic engine.

![](../../../../03-media/cloudability-premium/images/advanced-k8s-container-rightsizing.png)

Customize the dashboard

You can set the following options to customize your dashboard.

Specify Cost Basis

Cost Basis determines how recommendations are calculated. Cost basis can be On-Demand
or Effective. The Effective cost basis is selected by default.

Use the On-Demand cost basis if you are looking to remove the unpredictable nature of
commitment-based discounts from your analysis and to maximize the number of recommendations provided
to you. Use the Effective cost basis if you prefer to base your recommendations on the historical
True Cost of running your instances and to take a conservative approach.

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
rule is automatically applied to the  Filters  field. You can select only one
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

The dashboard contains a rightsizing recommendations table, which provides an overview of
workload controller resources for which recommendations have been identified. The table includes the
following columns:

Note:

By default, the data is sorted by the Cost Impact column. To change the
sort order, just select the column name.

- Status :  Status indicating readiness of action execution
- Workload Controller Name : The workload controller resource name
- Container Cluster Name : The cluster name
- Namespace : The namespace configured
- Replicas : The number of replicas configured
- Risk : The risk identified by Turbonomic engine
- **Cost** : The current workload controller instance cost
- Action Category : The category of the action recommended. Current
  supported ones are "Performance" or "Savings"
- Action : The action recommended. Table below lists various supported
  actions
- Cost Impact : Cost impact of implementing this action

| Recommendation | Description |
| --- | --- |
| Scale | Resize action recommended by the optimization engine. This can be "Scale up" or "Scale down" action based on the policies configured |

Export optimization recommendations to an Excel file

To export the recommended actions to an excel file, select Export. Note
that the excel file will include several additional columns, such as region, operating system, unit
price, and others.

Recommendation details

To view the recommended action details for a particular resource, select View Details
from the More Options (3 dots) menu. This brings up the details of the workload
controller chosen.

The following figure shows a sample workload controller action details panel.

![](../../../../03-media/cloudability-premium/images/advanced-k8s-container-rightsizing-wc-details.png)

You see a list of workloads listed under the "Workloads" section above. To view the workload
details for a particular workload, select View Details from the More Options
(3 dots) menu. This brings up the details of the workload chosen.

![](../../../../03-media/cloudability-premium/images/advanced-k8s-container-rightsizing-cs-details.png)

**Parent topic:** [Advanced Rightsizing](../product/advanced-rightsizing-powered-by-turbonomic.html)
