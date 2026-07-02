---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "product"
title: "Advanced Rightsizing"
breadcrumb:
  - "Cloudability Premium"
  - "Optimize"
  - "Rightsizing in Cloudability Premium"
source_path: "product/advanced-rightsizing-powered-by-turbonomic.html"
images:
  - "images/advanced-rightsizing-explorer.png"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Advanced Rightsizing

## Optimization Actions Powered by Turbonomic

Turbonomic engine powering Cloudability collects historical resource utilization metrics to analyze workload performance holistically and then
recommends optimization actions to scale these workloads to assure performance at the lowest possible cost.

Turbonomic engine generates optimization actions for cloud and Kubernetes resources in your public cloud environment ensuring that your
applications receive the precise allocation of compute, storage, and network resources across every level of the technology stack. By
continuously optimizing resource allocation, your organization can achieve assured performance, significant time savings and optimal
cost optimization.

Currently, virtual machine, disk and workload controller service actions across AWS, Microsoft Azure and Google Cloud are supported in
Cloudability Premium, powered by Turbonomic.

Note: You need to ensure all your existing vendor credentials have relevant Turbonomic
required permissions granted without which Turbonomic engine may not be able to generate right set
of actions. If you were a Cloudability customer prior to Cloudability Premium upgrade, you still
need to re-credential every single vendor credential to grant additional set of permissions.

## Advanced Rightsizing Dashboard

The Advanced Rightsizing dashboard displays the Explorer tab by default. The Rightsizing Explorer
gives an overview of possible savings or investments across all Cloud resources used by your
company. You can use this dashboard to group, filter and navigate your optimization actions.

The additional tabs in Advanced Rightsizing are optimization actions for specific cloud
providers.

[Advanced Rightsizing Explorer](advanced-rightsizing-explorer.html)

![](../../../../03-media/cloudability-premium/images/advanced-rightsizing-explorer.png)

## Optimization Actions FAQ

Why is the action time periods supported?

Turbonomic supports look back period of 7 to 90 days. They can be configured in the global or
scoped policies.

Why doesn't Total Spend in this page exactly match the values shown in Reporting /
True Cost Explorer?

Optimization actions only lists resources for which it found at least one money-saving resource
so it is likely these values will not match exactly.

How frequently are actions updated?

We update the optimization actions hourly. You can access recommendations for resources 24 hours
after the resource is created, provided that there is enough utilization data.

What cloud services and what actions are supported in Cloudability Premium today?

Virtual Machine, Volume/Disk and Workload Controller services are supported in Cloudability
Premium as on date. In terms of actions, scale, resize, and suspend actions are supported for
virtual machines, scale and delete actions are supported for volume/disk services and resize actions
for workload controller services.

- **[Advanced Rightsizing Explorer](../product/advanced-rightsizing-explorer.html)**
- **[AWS EC2](../product/advanced-rightsizing-for-aws-ec2.html)**
- **[AWS EBS](../product/advanced-rightsizing-for-aws-elastic-block-store.html)**
- **[AWS RDS](../product/aws_rds.html)**
- **[Azure Compute](../product/advanced-rightsizing-for-azure-compute.html)**
- **[Azure Disk](../product/advanced-rightsizing-for-azure-disks.html)**
- **[Azure SQL](../product/azure_sql.html)**
- **[GCP Google Compute Engine (GCE)](../product/advanced-rightsizing-for-gce.html)**
- **[GCP Google Persistent Disk (GPD)](../product/advanced-rightsizing-for-gpd.html)**
- **[Advanced Rightsizing for Kubernetes Containers](../product/advanced-k8s-container-rightsizing.html)**
- **[Action Execution](../product/action_execution.html)**
- **[Rightsizing Preferences](../product/premium-rightsizing-preferences.html)**

**Parent topic:** [Rightsizing in Cloudability Premium](../product/rightsizing-in-cloudability-premium.html)
