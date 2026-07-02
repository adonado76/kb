---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "product"
title: "Rightsizing for Kubernetes Containers"
breadcrumb:
  - "Cloudability Premium"
  - "Optimize"
  - "Rightsizing in Cloudability Premium"
  - "Rightsizing"
source_path: "product/k8s-container-rightsizing.html"
images:
  - "images/cloudy-vertical-elipsis.jpg"
  - "images/containers-summary-kpis.jpg"
  - "images/edit-icon.jpg"
  - "images/kubernetes-rightsizing-dash-new.png"
  - "images/rightsizing-recommendation-detail.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Rightsizing for Kubernetes Containers

With Cloudability rightsizing for Kubernetes containers, you can view recommendations for
optimizing your Kubernetes container deployments based on the previous 10 or 30 days of resource
usage.

Learn about  [Rightsizing in
Cloudability](get-recommendations-for-scaling-your-cloud-resources-with-rightsizing.html)

Learn about [Cloudability Container Cost Allocation](https://www.apptio.com/products/cloudability/container-cost-allocation/ "(Opens in a new tab or window)")

Note:

Visit the  [blog](https://www.apptio.com/emerge/cloud-cost-optimization-10-day-vs-30-day-rightsizing/ "(Opens in a new tab or window)")  to learn about using 10 or 30 days of resource usage to generate
recommendations.

Before you begin

Note: Container rightsizing uses the same reporting agent and data infrastructure as the container
cost allocation functionality. If your organization already uses this functionality in Cloudability , you don't need to do anything to use rightsizing.

Note: Although allocated costs will be reduced, there will not be any actual Kubernetes savings until
clusters are rightsized.

To use Rightsizing for GCP, make sure you have:

- Provisioned your Kubernetes clusters by deploying the opensource agent.

Learn about  [Kubernetes cluster provisioning](k8s-cluster-provisioning.html)

Accessing the Containers dashboard

From the
Cloudability
home menu, navigate to
Optimize > Rightsizing > Containers
.

![containers in rightsizing screenshot](../../../../03-media/cloudability-premium/images/kubernetes-rightsizing-dash-new.png)

You can select Workloads or the Clusters toggle to choose the type of recommendations.

Your resources are sorted by cost savings by default. The resources at the top of the list have
the highest potential savings.

Select  Export  to download the recommendations as a spreadsheet. Additional
account information is included such as region, operating system, tags available per resource, and
the  Effective Rate  for current and new resource types.

The dashboard displays the following:

Cost basis

- **On-Demand**: Savings values based purely on on-demand pricing. While custom pricing is
  included, the potential impact from commitments (Reserved Instances (RIs) or Savings Plans (SPs)) is
  not included.
- **Effective**: The effective cost of running your current configuration. This takes into account
  the historical impact of commitments in a similar manner to the Cost (Amortized) metric, where all
  associated upfront and recurring costs are included. For the recommended  New
   instance type, cost figures are based on the on-demand prices because the 
  New  configuration may not benefit from RIs or SPs. This comparison is the more
  conservative option. Even if you inadvertently move away from RIs or SPs, your new overall rate will
  still be better. As a result, the overall savings reported using this methodology will sometimes be
  lower. Custom pricing will be applied to these figures if applicable.

Filters

As with the container cost allocation functionality, you can leverage account-based views to filter recommendations down to a subset of your organization's accounts.

To add a filter:

1. Select **Add Filter** from the toolbar.
2. In the filter overlay choose a Dimension.
3. Select an Operator to provide a logical condition.
4. Choose a value to refine your filter.
5. Select **Add Filter** to apply the new filter to the page.

To remove a filter:

1. Select the filter icon ![edit icon screenshot ](../../../../03-media/cloudability-premium/images/edit-icon.jpg).
2. Select X next to the filter that you want to remove.

Apply filters with links

You can also add filters by selecting the blue hyperlinked values in the main table. Your filters are added to the Filter Configurator.

Note:

Only one value or parameter from each column can be selected at a time.

KPIs

Summary Key Performance Indicators (KPIs) are displayed depending on the views and filters you have selected.

![kubernetes containers screenshot](../../../../03-media/cloudability-premium/images/containers-summary-kpis.jpg)

Summary KPIs include:

- Total Spend: The total current allocated spend across all containers
  instrumented in the Cloudability platform.
- Estimated Idle Savings: Shows the estimated total savings for all
  Terminate  recommendations.
- Estimated Rightsize Savings: Shows the estimated total potential savings
  achievable for all Rightsize recommendations.
- Estimated Optimized Spend: The estimated total spend across all displayed
  containers after recommendations are applied.

Note:

Rightsizing containers adjusts the cost allocation for the containers and pods with that
container specification but ordinarily does not affect your bill. Rightsizing the container
specification makes capacity available in your deployment, which organizations can either use for
other workloads or to rightsize the underlying compute instance. Rightsizing the underlying compute
instance will have a positive impact on an organization's bill.

Viewing recommendation details

To view the details for a particular resource, select 
![vertical ellipsis screenshot](../../../../03-media/cloudability-premium/images/cloudy-vertical-elipsis.jpg) > View Details  .

Within the
Details
pane,
Cloudability
displays at least one recommendation, with the lowest risk option being the default selection.

Each option includes request and limit recommendations for memory and CPU for a given container specification. Graphs for individual resources display the current resource allocation (in red) and consumption (in blue) along with the recommended settings (in yellow).

![workloads screenshot](../../../../03-media/cloudability-premium/images/rightsizing-recommendation-detail.jpg)

**Parent topic:** [Rightsizing](../product/get-recommendations-for-scaling-your-cloud-resources-with-rightsizing.html)
