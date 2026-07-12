---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Analyze data for your Kubernetes containers"
breadcrumb:
  - "Insights"
  - "Container Cost Allocation"
  - "Analyze data for your Kubernetes containers"
source_path: "SSVCLNQ/product/analyze-data-for-your-containers.html"
images:
  - "03-media/apptio-cloudability-standard/audit2.jpg"
  - "03-media/apptio-cloudability-standard/cldy-idle-cost.jpg"
  - "03-media/apptio-cloudability-standard/container-cost-allocation-export.png"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Analyze data for your Kubernetes containers

## Container Cost Allocation

The Container Cost Allocation feature provides deeper insights into your provisioned clusters. This helps you allocate costs accurately by Kubernetes clusters, namespaces, labels, workloads, and other methods.

For more information, see Container Cost Allocation .

1. From the main menu, select Insights > Containers .
1. The Container Cost Allocation menu is displayed for you to provision your Kubernetes clusters.

Allocation and Idle Resources

The cost for idle resources is distributed across a given dimension based on the percent share of the total cost during that interval.

- For pods classified as Guaranteed Quality of Service , Cloudability utilizes the request data for allocation since the amount of requested resources is reserved, . For more information, see Configure Quality of Service for Pods .
- For pods classified as Burstable , Cloudability utilizes the request or usage information, whichever is of higher value for allocation.
- For pods classified as Best Effort , Cloudability leverages the usage information for allocation.

Cost Basis

The Cloudability collection agent compiles metrics from your Kubernetes clusters and sends them to Cloudability for analysis. Using native metric sources, Cloudability allocates cost and provides insights into idle resources for your clusters.

For more information, see Containers .

- Cloudability uses Cost (Adjusted) as default resource cost for allocation.
- If you do not use a Cost (Adjusted) metric, Cloudability uses Cost (Total) in its calculation.
- Cloudability also supports the Cost (Amortized ) metric in container cost allocation. This helps you understand the full cost of your Kubernetes cluster, including any consumed reserved instances (RIs) and savings plans (SPs). While analyzing clusters, switching to Cost (Amortized ) allows you to include full cost of consumed RIs and SPs.

You can split costs by namespace, services, and labels.

## Idle Cost Distribution

Overview

Containers have a spare overhead capacity not used by underlying workloads. This “idle” usage has an associated cost (for virtual machines and volumes). Cloudability distributes these idle container costs within its reports, dashboards, and container cost allocation.

This introduces the new metric category Containers along with six others. You can use these metrics to view separately Utilized , Idle and Fairshare costs for cash or amortized basis.

The Container Cost Allocation feature evaluates resource utilization on each node and adds it to the billing data to calculate the cost of each cluster. This associates the Utilized Cost to Kubernetes namespace and label values (available within reports by using the namespace or a label dimension). With this enhancement you can also report on the Idle Cost via the new metric, allocated to the namespace and label values proportionally based on their direct cost contribution of each node. The Fairshare Cost is the sum of Utilized Cost and the Idle Cost .

Considerations and reporting ideas to keep in mind with new metrics:

- For non-container costs, the new metrics will all display $0. To filter to container only data, use a filter such as “ Cluster Name not equals (not set) ”
- Use these metrics with different dimensions to easily visualize Utilized vs Idle Cost . For example, list out by Cluster Name or Resource ID .
- For the first time, use cash and amortized cost basis together for detailed container cost reporting.

## Container allocation data export

Click the Export icon to export the cost allocation data in .csv format.

You can export data when allocating across clusters, or within a single cluster, by Namespace , Service , and Label .

.CSV Data Definitions

| Name | Definition |
| --- | --- |
| Type | Displays whether the row is allocation data, or reporting on unallocated (idle) usage or cost. |
| Namespace | Kubernetes Namespace object name. |
| Service | Kubernetes Service object name. |
| Label | Kubernetes Label value. |
| cpu/reserved:allocation | Percentage of CPU usage allocated to that row during the timeframe queried. |
| cpu/reserved:fairShare | Percentage of CPU usage allocated to that row during the timeframe queried when sharing distributing across objects. |
| cpu/reserved:resource:mean | Average CPU usage observed during the time frame queried. |
| cpu/reserved:resource:unit | Unit of measurement for CPU usage. |
| memory/reserved_rss:allocation | Percentage of Memory Resident Set Size usage allocated to that row during the time frame queried. |
| memory/reserved_rss:fairShare | Percentage of Memory Resident Set Size usage allocated to that row during the timeframe queried when distributing unallocated (idle) across objects. |
| memory/reserved_rss:resource:mean | Average Memory Resident Set Size usage observed during the timeframe queried. |
| memory/reserved_rss:resource:unit | Unit of measurement for Memory Resident Set Size usage. |
| network/tx:allocation | Percentage of Network TX usage allocated to that row during the timeframe queried. |
| network/tx:fairShare | Percentage of Network TX usage allocated to that row during the timeframe queried when distributing unallocated (idle) across objects. |
| network/tx:resource:mean | Average Network TX usage observed during the timeframe queried. |
| network/tx:resource:unit | Unit of measurement for Network TX usage. |
| network/rx:allocation | Percentage of Network RX usage allocated to that row during the timeframe queried. |
| network/rx:fairShare | Percentage of Network RX usage allocated to that row during the timeframe queried when distributing unallocated across objects. |
| network/rx:resource:mean | Average Network RX usage observed during the timeframe queried. |
| network/rx:resource:unit | Unit of measurement for Network RX usage. |
| filesystem/usage:allocation | Percentage of Container Filesystem usage allocated to that row during the timeframe queried. |
| filesystem/usage:fairShare | Percentage of Container Filesystem usage allocated to that row during the timeframe queried when distributing unallocated (idle) across objects. |
| filesystem/usage:resource:mean | Average Container Filesystem usage observed during the timeframe queried. |
| filesystem/usage:resource:unit | Unit of measurement for Container Filesystem usage. |
| percentages:allocation | Overall Percentage across Memory, CPU, Network RX/TX, and Filesystem allocated to that row during the timeframe queried. |
| percentages:fairShare | Overall Percentage across Memory, CPU, Network RX/TX, and Filesystem allocated to that row during the timeframe queried when distributing unallocated (idle) across objects. |
| percentages:fairShareUnallocated | Overall Percentage of Unallocated (idle) across Memory, CPU, Network RX/TX, and Filesystem that is shared by that row when distributing Unallocated (idle) across objects. |
| costs:allocation | Overall Cost across Memory, CPU, Network RX/TX, and Filesystem allocated to that row during the timeframe queried. |
| costs:fairShare | Overall Cost of Unallocated (idle) across Memory, CPU, Network RX/TX, and Filesystem that is shared by that row when distributing Unallocated (idle) across objects. |
| costs:unallocated | Overall Unallocated (idle) Cost across Memory, CPU, Network RX/TX, and Filesystem during them timeframe queried when not distributed across objects. |

## Supported Kubernetes configurations

There are many different ways to deploy Kubernetes. We support all versions certified by the CNCF (Cloud Native Computing Foundation):

| Service | Vendor | Memory/CPU/Disk Average | % Allocation | $ Allocation |
| --- | --- | --- | --- | --- |
| None | AWS | Yes | Yes | Yes |
| None | Azure | Yes | Yes | Yes |
| None | GCP | Yes | Yes | Yes |
| GKE | GCP | Yes | Yes | Yes |
| EKS | AWS | Yes | Yes | Yes |
| AKS | Azure | Yes | Yes | Yes |

To learn more about Kubernetes, refer the following topics:

- Kubernetes cluster provisioning
- Common Kubernetes Metrics Agent - error messages
- Kubernetes Cost Allocation
- Container costs allocated by vendor
- Rightsizing for Kubernetes containers
