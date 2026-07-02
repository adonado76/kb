---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "product"
title: "Advanced Rightsizing Explorer"
breadcrumb:
  - "Cloudability Premium"
  - "Optimize"
  - "Rightsizing in Cloudability Premium"
  - "Advanced Rightsizing"
source_path: "product/advanced-rightsizing-explorer.html"
images:
  - "images/advanced-rightsizing-explorer.png"
  - "images/download_button.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Advanced Rightsizing Explorer

## Explorer Dashboard

Rightsizing Explorer dashboard enables you to group, filter and navigate all of your advanced
optimization recommendations that include savings and investments, allowing you to better understand
your opportunities and focus your efforts to maximize performance and minimize waste.

You can toggle between savings or investments view in the explorer.

Note: You need to ensure all your existing vendor credentials have relevant Turbonomic
required permissions granted without which Turbonomic engine may not be able to generate right set
of actions. If you were a Cloudability customer prior to Cloudability Premium upgrade, you still
need to re-credential every single vendor credential to grant additional set of permissions.

The Advanced Rightsizing Explorer is in  Optimize > Rightsizing > Advanced >
Explorer.

![](../../../../03-media/cloudability-premium/images/advanced-rightsizing-explorer.png)

Note:

Turbonomic Configuration policies are applied when optimization actions are generated. The
Rightsizing Explorer works with the optimization actions after they are generated. Due to grouping,
Cloudability recommends that you adjust your minimum savings amount to a lower setting if you are
using the Rightsizing Explorer.

Supported services

The services that are currently supported are:

- AWS: EC2, EBS
- Azure: Compute, Disk
- GCP: GCE, GPD

Navigate the Rightsizing Explorer

The most efficient way to use the Advanced Rightsizing Explorer is to filter first, find, and
then focus:

1. Apply filters to remove the largest amount of results first, such as Accounts, Vendors,
   Services. You can select Sankey nodes to quickly add filters
2. Remove any unnecessary dimensions from the menu. Add additional dimensions one-at-a-time to go
   deeper and discover additional trends.
3. Select a node to view the individual recommendations matching the node attributes.
4. Filter the table further by selecting specific values in the columns.

Dimensions

Dimensions are used in the Sankey diagram to split and group your optimization recommendations.
When you add a dimension to the Sankey diagram, it creates a set of nodes with the values of that
dimension. The size of the node corresponds to the total amount of savings or investments from
individual recommendations with that dimensions value.

Note:

Only On-Demand cost basis is supported because most services do not feature discount methods.

Dimensions are set though the menu bar at the top of the Sankey diagram.

- Add: Select Edit Dimensions and use the checkbox next to the required
  dimension to add. For performance, Cloudability recommends that you do not add multiple dimensions
  too quickly because you may hit rate limiting
- Remove: Select  Edit Dimensions  and use the checkbox next to the
  required dimension, or select the delete button next to the dimension.
- Re-order: The order of dimensions can be changed on the Sankey diagram by changing the order in
  the menu. Select and hold the dots next to the dimension name, then drag it to the new position.

Learn about  [Glossary of cost
dimensions and metrics](glossary-of-cost-dimensions-and-metrics.html)

Learn about  [Glossary of
utilization dimensions and metrics](glossary-of-utilization-dimensions-and-metrics.html)

**Optimization**
Recommendations

View recommendations

When you want to focus on a specific node and see the individual recommendations for that
dimension:

1. Select the node on the Sankey diagram
2. Select View recommendations

   The recommendations table is shown below
   the Sankey diagram, listing the recommendations for the node that you selected.

   To download
   a copy of this data, select ![Notes Icon](../../../../03-media/cloudability-premium/images/download_button.jpg)

Configure the table

- To order the columns in the table as required, select and hold on the column title then drag it
  to the desired location.
- To sort the data based on a column, select the column header.

View recommendation details 

1. Select the three dots to the right of the recommendation
2. Select View Details

You can view the details of recommendations.

## Advanced Rightsizing FAQ

How frequently are optimization recommendations updated?

We update the optimization recommendations every hour. You can access recommendations for
resources 24 hours after the resource is created, provided that there is enough utilization data.

**Parent topic:** [Advanced Rightsizing](../product/advanced-rightsizing-powered-by-turbonomic.html)
