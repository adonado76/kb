---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Autoscale Action for Rightsizing"
breadcrumb:
  - "Optimize"
  - "Rightsizing"
  - "Autoscale Action for Rightsizing"
source_path: "SSVCLNQ/product/rightsizing-autoscale-action.html"
images:
  - "03-media/apptio-cloudability-standard/rightsizing-autoscale-instance-to-asg.jpg"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Autoscale Action for Rightsizing

One challenge in resource optimization is correctly sizing for workloads that exhibit widely fluctuating and spiking workloads. As illustrated by large swings in the utilization metric data (CPU, network, memory, and GPU), this scenario is typically addressed by over-provisioning the resource to accommodate the highest peaks in these workloads, resulting in excess cloud spend.

To better fit compute resources to these highly elastic workloads, we are enhancing the Autoscale recommendation. The Autoscale action recommends converting a single instance to an Auto Scaling Group (ASG). Instead of a single high-capacity instance, the ASG comprises multiple, smaller instances that are spun up and down to meet this elastic workload's demands. If your workload can accommodate scaling across multiple machines, this is a cost-effective option.

Using the Autoscale Recommendation

The details pane shows the list of recommended actions. When an Autoscale action is selected, the minimum and maximum instance counts will be displayed. We model target tracking on CPU, network, memory (if available), GPU (if available) utilization data to derive these instance counts. The recommendation is for an ASG ranging from 1 to 4 of type c4.4xlarge instances in the example below.

Looking at the CPU and Memory charts above, notice the legend on the right represents the number of instances. In this example, the yellow dotted line moves between 1 and 3, indicating this range is sufficient to cover the workload. When determining the maximum instance count, we recommend the instance count that matches the original instance’s memory size. Specifically, the current c4.4xlarge has 30 GiB, while the recommended c4.xlarge instance has 7.5 GiB memory. The original has four times as much memory, so we recommend a maximum instance count that matches the upper bound. Recall that you will not be charged for instances in an ASG that are not active, so this is a cost-effective option.

Read this to learn more about ASG target tracking scaling policies and implementation details.

Considerations

Here is a list of issues to consider at this time:

The risk is set to a minimum of 1 as not all workloads are appropriate for ASGs.

Members of the existing Auto Scaling Group are excluded from this type of recommendation.

Only Amazon EC2 (Elastic Cloud Compute) is supported at this time.

Burstable instance, families (T2, T3, T3a, and T4g) are excluded.

EC2 target tracking dynamic scaling policies are triggered by either CPU utilization, Network In/Out bytes, or Application Load Balancer request counts by default. Optionally, other Cloudwatch or custom metrics can be used as triggers, with additional configuration.
