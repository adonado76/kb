---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Rightsizing Explorer"
breadcrumb:
  - "Optimize"
  - "Rightsizing"
  - "Rightsizing Explorer"
source_path: "SSVCLNQ/product/rightsizing-explorer.html"
images:
  - "03-media/apptio-cloudability-standard/rightsizing-explorer-with-effective-cost.jpg"
  - "03-media/apptio-cloudability-standard/download_button.jpg"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Rightsizing Explorer

Rightsizing Explorer dashboard enables you to group, filter and navigate all of your rightsizing recommendations, allowing you to better understand your opportunities and focus your efforts to maximize returns.

The Rightsizing Explorer is in Optimize > Rightsizing > Explorer , and it is the default page for Rightsizing.

Rightsizing preferences are applied when recommendations are generated. The Rightsizing Explorer works with the recommendations after they are generated. Due to grouping, Cloudability recommend that you adjust your minimum savings amount to a lower setting if you are using the Rightsizing Explorer.

Supported services

The services that are currently supported are:

- AWS: EC2, EBS, S3, RDS, Lambda Note: Cloudability only generates 30 day recommendations for AWS S3. When a 10day timeframe is selected in the Rightsizing Explorer – 30 day recommendations for S3 are displayed.
- Azure: Compute, Disk, SQL
- GCP: GCE, GPD
- OCI: VM

Navigate the Rightsizing Explorer

The most efficient way to use the Rightsizing Explorer is to filter first, find, and then focus:

1. Apply filters to remove the largest amount of results first, such as Accounts, Vendors, Services. You can select Sankey nodes to quickly add filters
1. Remove any unnecessary dimensions from the menu. Add additional dimensions one-at-a-time to go deeper and discover additional trends.
1. Select a node to view the individual recommendations matching the node attributes.
1. Filter the table further by selecting specific values in the columns.

Dimensions

Dimensions are used in the Sankey diagram to split and group your rightsizing recommendations. When you add a dimension to the Sankey diagram, it creates a set of nodes with the values of that dimension. The size of the node corresponds to the total amount of savings from individual recommendations with that dimensions value.

Dimensions are set though the menu bar at the top of the Sankey diagram.

- Add: Select Edit Dimensions and use the checkbox next to the required dimension to add. For performance, Cloudability recommend that you do not add multiple dimensions too quickly because you may hit rate limiting.
- Remove: Select Edit Dimensions and use the checkbox next to the required dimension, or select the delete button next to the dimension.
- Re-order: The order of dimensions can be changed on the Sankey diagram by changing the order in the menu. Select and hold the dots next to the dimension name, then drag it to the new position.

Learn about Glossary of cost dimensions and metrics

Learn about

Glossary of utilization dimensions and metrics

Recommendations

View recommendations

When you want to focus on a specific node and see the individual recommendations for that dimension:

1. Select the node on the Sankey diagram.
1. Select View recommendations . The recommendations table is shown below the Sankey diagram, listing the recommendations for the node that you selected. To download a copy of this data, select .

Configure the table

- To order the columns in the table as required, select and hold on the column title then drag it to the desired location.
- To sort the data based on a column, select the column header.

1. Select the three dots to the right of the recommendation
1. Select either Open Details or Create Ticket .

You can view the details of recommendations and create tickets to action them.

Use Case

A customer using many Windows instances has a large number of disk rightsizing recommendations. They are all small savings and it would not make sense to rightsize any of them individually. Grouping the results by disk size reveals that they are all exactly 100 gigabytes which is the default boot volume. The customer makes one change to their boot image and receives the benefits over time. By changing the default template to a lower size, all newly built environments have no recommendations.

Rightsizing FAQ

Why are Spot Instances excluded from rightsizing recommendations?

Our rightsizing engine takes into account your workload (utilization metrics) and the cost to run it (current instance type and on-demand price) and generates a list of recommendations from which you can choose to help save you money. Spot Instances, on the other hand, are already offered at steep discounts; applying rightsizing in these situations results in negligible savings. For this reason, we have chosen to exclude Spot Instances from rightsizing.

How frequently are recommendations updated?

We update our rightsizing recommendations daily. You can access recommendations for resources 24 hours after the resource is created, provided that there is enough utilization data.
