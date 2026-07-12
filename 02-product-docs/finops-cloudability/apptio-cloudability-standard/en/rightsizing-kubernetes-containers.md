---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Rightsizing for Kubernetes Containers"
breadcrumb:
  - "Optimize"
  - "Rightsizing"
  - "Rightsizing for Kubernetes Containers"
source_path: "SSVCLNQ/product/k8s-container-rightsizing.html"
images:
  - "03-media/apptio-cloudability-standard/kubernetes-rightsizing-dash-new.png"
  - "03-media/apptio-cloudability-standard/edit-icon.jpg"
  - "03-media/apptio-cloudability-standard/containers-summary-kpis.jpg"
  - "03-media/apptio-cloudability-standard/cloudy-vertical-elipsis.jpg"
  - "03-media/apptio-cloudability-standard/rightsizing-recommendation-detail.jpg"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Rightsizing for Kubernetes Containers

With Cloudability rightsizing for Kubernetes containers, you can view recommendations for optimizing your Kubernetes container deployments based on the previous 10 or 30 days of resource usage.

Learn about Rightsizing in Cloudability

Learn about Cloudability Container Cost Allocation

Visit the blog to learn about using 10 or 30 days of resource usage to generate recommendations.

Before you begin

To use Rightsizing for GCP, make sure you have:

- Provisioned your Kubernetes clusters by deploying the opensource agent.

Learn about Kubernetes cluster provisioning

Accessing the Containers dashboard

From the Cloudability home menu, navigate to Optimize > Rightsizing > Containers .

You can select Workloads or the Clusters toggle to choose the type of recommendations.

Your resources are sorted by cost savings by default. The resources at the top of the list have the highest potential savings.

Select Export to download the recommendations as a spreadsheet. Additional account information is included such as region, operating system, tags available per resource, and the Effective Rate for current and new resource types.

The dashboard displays the following:

Cost basis

- On-Demand : Savings values based purely on on-demand pricing. While custom pricing is included, the potential impact from commitments (Reserved Instances (RIs) or Savings Plans (SPs)) is not included.
- Effective : The effective cost of running your current configuration. This takes into account the historical impact of commitments in a similar manner to the Cost (Amortized) metric, where all associated upfront and recurring costs are included. For the recommended New instance type, cost figures are based on the on-demand prices because the New configuration may not benefit from RIs or SPs. This comparison is the more conservative option. Even if you inadvertently move away from RIs or SPs, your new overall rate will still be better. As a result, the overall savings reported using this methodology will sometimes be lower. Custom pricing will be applied to these figures if applicable.

Filters

As with the container cost allocation functionality, you can leverage account-based views to filter recommendations down to a subset of your organization's accounts.

To add a filter:

1. Select Add Filter from the toolbar.
1. In the filter overlay choose a Dimension.
1. Select an Operator to provide a logical condition.
1. Choose a value to refine your filter.
1. Select Add Filter to apply the new filter to the page.

To remove a filter:

1. Select the filter icon .
1. Select X next to the filter that you want to remove.

Apply filters with links

You can also add filters by selecting the blue hyperlinked values in the main table. Your filters are added to the Filter Configurator.

Only one value or parameter from each column can be selected at a time.

KPIs

Summary Key Performance Indicators (KPIs) are displayed depending on the views and filters you have selected.

Summary KPIs include:

- Total Spend : The total current allocated spend across all containers instrumented in the Cloudability platform.
- Estimated Idle Savings : Shows the estimated total savings for all Terminate recommendations.
- Estimated Rightsize Savings : Shows the estimated total potential savings achievable for all Rightsize recommendations.
- Estimated Optimized Spend : The estimated total spend across all displayed containers after recommendations are applied.

Rightsizing containers adjusts the cost allocation for the containers and pods with that container specification but ordinarily does not affect your bill. Rightsizing the container specification makes capacity available in your deployment, which organizations can either use for other workloads or to rightsize the underlying compute instance. Rightsizing the underlying compute instance will have a positive impact on an organization's bill.

Viewing recommendation details

To view the details for a particular resource, select > View Details .

Within the Details pane, Cloudability displays at least one recommendation, with the lowest risk option being the default selection.

Each option includes request and limit recommendations for memory and CPU for a given container specification. Graphs for individual resources display the current resource allocation (in red) and consumption (in blue) along with the recommended settings (in yellow).
