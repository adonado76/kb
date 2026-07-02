---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "product"
title: "Containers Insights: Dashboard and Widget Guide"
breadcrumb:
  - "Cloudability Premium"
  - "Insights"
  - "Container Cost Allocation"
source_path: "product/containers-insight-2-dashboard-widget-guide.html"
images:
  - "images/container_10.jpg"
  - "images/container_11.jpg"
  - "images/container_12.jpg"
  - "images/container_13.jpg"
  - "images/container_14.jpg"
  - "images/container_15.jpg"
  - "images/container_16.jpg"
  - "images/container_17.jpg"
  - "images/container_3.jpg"
  - "images/container_4.jpg"
  - "images/container_5.jpg"
  - "images/container_6.jpg"
  - "images/container_7.jpg"
  - "images/container_8.jpg"
  - "images/container_9.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Containers Insights: Dashboard and Widget Guide

Overview

Containers Insights provides a default dashboard to display a summary of cost and efficiency for
all clusters. It also supports powerful customization of the dashboard. Custom widgets can be used
to query rich datasets to reveal deeper insights into cost, utilization, and efficiency within
Kubernetes, and OpenShift Clusters.

A dashboard appears by default. You can also create custom dashboards.

Default Dashboard

The default dashboard includes KPI widgets such as Total Cost, Idle Cost, and Efficiency Score.
It also displays time series chart widgets, showing trends for the top 10 idle cost clusters, and
total cost trends for the top 10 clusters. Any changes to the dashboard, such as adding or deleting
widgets, updating the layout, or adjusting global filters, are automatically saved. Each user has
his/ her own default dashboard that can be customized independently.

![Notes Icon](../../../../03-media/cloudability-premium/images/container_3.jpg)

![Notes Icon](../../../../03-media/cloudability-premium/images/container_4.jpg)

![Notes Icon](../../../../03-media/cloudability-premium/images/container_5.jpg)

Custom Dashboard

Users can create custom dashboards by saving any existing dashboards available to them. The
layout of the dashboard is structured with KPI widgets on the top, chart widgets in the middle, and
a table widget at the bottom. Within each section (KPI, chart), the placement of the widgets can be
adjusted. If a user deletes all dashboards, they will still receive the pre-configured built-in
default dashboard. Any changes, including global filters and layout adjustments, are automatically
saved.

![Notes Icon](../../../../03-media/cloudability-premium/images/container_6.jpg)

![Notes Icon](../../../../03-media/cloudability-premium/images/container_7.jpg)

There are several widgets that can be added to the dashboard.

Pre-Built KPI Widgets

There are four pre-built KPI widgets: Total Cost, Efficiency Score, Efficiency Score (Usage),
and Idle Cost. These widgets are displayed on the default dashboard and can be added to any
dashboard through the drop-down menu.

![Notes Icon](../../../../03-media/cloudability-premium/images/container_8.jpg)

Custom KPI Widget

Users can add custom KPI widgets through the drop-down menu to add a "Custom KPI" widget.

![Notes Icon](../../../../03-media/cloudability-premium/images/container_9.jpg)

Metric Type  : Options include Total, CPU, Memory, GPU, Network TX, Network
RX, FileSystem, and Persistent Volume. This shows the metrics for specific resource types.

Metric Summary  : Options include Cost and Utilization. This indicates
whether the KPI is based on cost metrics or utilization metrics.

Metric Allocation  : Options include "Fair Share," "Allocated," "Idle," and
"Efficiency." This shows whether the allocation is about fair share, allocated, idle, or efficiency
of the metric type, and summary.

- Fair Share  : Provisioned resources shared proportionally based on
  allocation among all tenants.
- Allocated  : Resources allocated to a container; the larger of usage and
  request.
- Idle  : Resources not allocated and fair shared among tenants; the
  difference between Fair Share and Allocated.
- Efficiency  : Calculated as Allocated divided by Fair Share.

The combination of metric type, summary, and allocation determines the KPI to be created. Here
are some examples:

| Metric Type | Metric Summary | Metric Allocation | KPI |
| --- | --- | --- | --- |
| Total | Cost | Efficiency | Efficiency Score = Allocated Cost / Fair Share Cost (or Total Cost) |
| CPU | Cost | Efficiency | CPU Efficiency Score = Allocated CPU Cost / Fair Share CPU Cost |
| CPU | Cost | Fair Share | CPU Fair Share Cost = Cost for the fair share CPU units |
| CPU | Cost | Allocated | CPU Allocated Cost = Cost for the allocated CPU units |
| CPU | Cost | Idle | CPU Idle Cost = CPU Fair Share Cost - CPU Allocated Cost |
| CPU | Utilization | Efficiency | CPU Utilization Efficiency = Allocated CPU Units / Fair Share CPU Units |
| CPU | Utilization | Fair Share | CPU Fair Share Units |
| CPU | Utilization | Allocated | CPU Allocated Units |
| CPU | Utilization | Idle | CPU Idle Units = CPU Fair Share Units - CPU Allocated Units |

These KPIs can be filtered by clusters, namespaces, workload, workload type, container, node, or
label keys. Filters are combined with "AND" operations, and only the "equals" operator is allowed.

![filter conditions screenshot](../../../../03-media/cloudability-premium/images/container_10.jpg)

There are also several chart widgets that can be added to your
dashboard.

Pre-Built Chart Widgets

There are four pre-built chart widgets:

- Efficiency for Top 10 Idle Cost Clusters
- Top 10 Costs by Clusters
- Top 10 Least Efficiency Score by Cluster
- Total Cost Trend

![Notes Icon](../../../../03-media/cloudability-premium/images/container_11.jpg)

Custom Chart Widgets

There are three types of custom chart widgets supported:

- Custom Time Series: Displays trend information on the queried
  datasets, based on any combination of metric type, summary, and allocation. It can be grouped by
  combinations of cluster, namespace, workload, workload type, node, container, or label keys. It also
  allows ordering by top 10 or bottom 10.

  ![Notes Icon](../../../../03-media/cloudability-premium/images/container_12.jpg)![Notes Icon](../../../../03-media/cloudability-premium/images/container_13.jpg)
- Custom Top/Bottom 10 Widget  : Displays queried datasets in a specified
  order, supporting only vertical bar charts.

  ![Notes Icon](../../../../03-media/cloudability-premium/images/container_14.jpg)

  ![Notes Icon](../../../../03-media/cloudability-premium/images/container_15.jpg)
- Custom Allocated vs Idle  : Displays queried datasets
  for allocated versus idle comparison, usable for both cost, and utilization metrics.

  ![Notes Icon](../../../../03-media/cloudability-premium/images/container_16.jpg)

  ![Notes Icon](../../../../03-media/cloudability-premium/images/container_17.jpg)

Customization and Layout

Users can easily customize the layout and content of their dashboards by adding, removing, and
rearranging widgets. Each widget's settings and filters can be adjusted to meet specific analysis
needs, providing a highly flexible and personalized visualization experience.

This guide covers the essential features and customization options available in the new
Containers Insights. By utilizing these dashboards and widgets, users can gain deeper insights into
their Kubernetes environments, optimizing cost, utilization, and efficiency.

**Parent topic:** [Container Cost Allocation](../product/k8s-cost-allocation.html)
