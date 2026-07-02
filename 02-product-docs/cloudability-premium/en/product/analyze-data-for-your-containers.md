---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "product"
title: "Analyze data for your Kubernetes containers"
breadcrumb:
  - "Cloudability Premium"
  - "Insights"
  - "Container Cost Allocation"
source_path: "product/analyze-data-for-your-containers.html"
images:
  - "images/audit2.jpg"
  - "images/cldy-idle-cost.jpg"
  - "images/container-cost-allocation-export.png"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Analyze data for your Kubernetes containers

## Container Cost Allocation

The Container Cost Allocation feature provides deeper insights into your provisioned clusters.
This helps you allocate costs accurately by Kubernetes clusters, namespaces, labels, workloads, and
other methods.

For more information, see [Container Cost Allocation](k8s-cost-allocation.html).

1. From the main menu, select Insights > Containers.
2. The Container Cost Allocation  menu is displayed for you to provision
   your Kubernetes clusters. ![container cost allocation screenshot](../../../../03-media/cloudability-premium/images/audit2.jpg)

Note: Using EFS instead of EBS for storage for containers is not supported in Cloudability.

Allocation and Idle Resources

The cost for idle resources is distributed across a given dimension based on the percent share of
the total cost during that interval.

- For pods classified as Guaranteed Quality of Service , Cloudability
  utilizes the request data for allocation since the amount of requested resources is reserved, . For
  more information, see [Configure Quality of Service for Pods](https://kubernetes.io/docs/tasks/configure-pod-container/quality-service-pod/#qos-classes "(Opens in a new tab or window)").
- For pods classified as Burstable, Cloudability utilizes the request or
  usage information, whichever is of higher value for allocation.
- For pods classified as Best Effort, Cloudability leverages the usage
  information for allocation.

Cost Basis

The Cloudability collection agent compiles metrics from your Kubernetes clusters and sends them
to Cloudability for analysis. Using native metric sources, Cloudability allocates cost and provides
insights into idle resources for your clusters.

For more information, see  [Containers](https://app.apptio.com/cloudability#/containers "(Opens in a new tab or window)").

- Cloudability uses Cost (Adjusted) as default resource cost for
  allocation.
- If you do not use a Cost (Adjusted) metric, Cloudability uses
  Cost (Total)  in its calculation.
- Cloudability also supports the Cost (Amortized ) metric in container cost
  allocation. This helps you understand the full cost of your Kubernetes cluster, including any
  consumed reserved instances (RIs) and savings plans (SPs). While analyzing clusters, switching to
  Cost (Amortized ) allows you to include full cost of consumed RIs and SPs.

You can split costs by namespace, services, and labels.

## Idle Cost Distribution

Overview

Containers have a spare overhead capacity not used by underlying workloads. This “idle” usage has
an associated cost (for virtual machines and volumes). Cloudability distributes these idle container
costs within its reports, dashboards, and container cost allocation.

This introduces the new metric category Containers along with six others.
You can use these metrics to view separately Utilized,
Idle and Fairshare costs for cash or amortized basis.
![idle cost distribution screenshot](../../../../03-media/cloudability-premium/images/cldy-idle-cost.jpg)

The Container Cost Allocation feature evaluates resource utilization on each node and adds it to
the billing data to calculate the cost of each cluster. This associates the Utilized
Cost to Kubernetes namespace and label values (available within reports by using the
namespace or a label dimension). With this enhancement you can also report on the Idle
Cost via the new metric, allocated to the namespace and label values proportionally
based on their direct cost contribution of each node. The Fairshare Cost is
the sum of Utilized Cost and the Idle Cost.

Considerations and reporting ideas to keep in mind with new metrics:

- For non-container costs, the new metrics will all display $0. To filter to container only data,
  use a filter such as “Cluster Name not equals (not set)”
- Use these metrics with different dimensions to easily visualize Utilized
  vs Idle Cost. For example, list out by Cluster Name or
  Resource ID.
- For the first time, use cash and amortized cost basis together for detailed container cost
  reporting.

## Container allocation data export

Click the Export ![export csv icon](../../../../03-media/cloudability-premium/images/container-cost-allocation-export.png) icon to export the cost allocation data in .csv format.

You can export data when allocating across clusters, or within a single cluster, by
Namespace, Service, and
Label.

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
| memory/reserved\_rss:allocation | Percentage of Memory Resident Set Size usage allocated to that row during the time frame queried. |
| memory/reserved\_rss:fairShare | Percentage of Memory Resident Set Size usage allocated to that row during the timeframe queried when distributing unallocated (idle) across objects. |
| memory/reserved\_rss:resource:mean | Average Memory Resident Set Size usage observed during the timeframe queried. |
| memory/reserved\_rss:resource:unit | Unit of measurement for Memory Resident Set Size usage. |
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

There are many different ways to deploy Kubernetes. We support all versions certified by the CNCF
(Cloud Native Computing Foundation):

| Service | Vendor | Memory/CPU/Disk Average | % Allocation | $ Allocation |
| --- | --- | --- | --- | --- |
| None | AWS | Yes | Yes | Yes |
| None | Azure | Yes | Yes | Yes |
| None | GCP | Yes | Yes | Yes |
| GKE | GCP | Yes | Yes | Yes |
| EKS | AWS | Yes | Yes | Yes |
| AKS | Azure | Yes | Yes | Yes |

To learn more about Kubernetes, refer the following topics:

- [Kubernetes cluster provisioning](k8s-cluster-provisioning.html)
- [Common Kubernetes Metrics Agent - error messages](k8s-metrics-agent.html)
- [Kubernetes Cost Allocation](k8s-cost-allocation.html)
- [Container costs allocated by vendor](container-costs-by-vendor.html)
- [Rightsizing for Kubernetes containers](k8s-container-rightsizing.html)

**Parent topic:** [Container Cost Allocation](../product/k8s-cost-allocation.html)
