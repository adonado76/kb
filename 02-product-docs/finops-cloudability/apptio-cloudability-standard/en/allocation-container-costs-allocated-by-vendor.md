---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Container Costs Allocated By Vendor"
breadcrumb:
  - "Insights"
  - "Container Cost Allocation"
  - "Container Costs Allocated By Vendor"
source_path: "SSVCLNQ/product/container-costs-by-vendor.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Container Costs Allocated By Vendor

When allocating cost based on utilization, the Container Cost Allocation feature accounts for the following information depending on the vendor.

AWS (EKS/self-managed)

For AWS, we include cost for any Nodes (EC2 instances) that were present in the cluster during the time queried, as well as any attached EBS volumes.

GCP (GKE)

For GKE, we include cost for any billing line items that have both of the following:

Cluster label is key: gke-cluster

Value is a cluster name that Cloudability is collecting utilization data for

This also assumes a tag mapping set up in Cloudability for that label key. Typically, this includes GCP Compute Engine costs at a minimum.

Azure (AKS)

For Azure, we include any resources under the Resource Group identified in the list of nodes present in the cluster during the time queried. Typically, this includes Azure Compute.

Oracle Cloud (OKE)

For OCI, we allocate costs based on their resource IDs, which are matched with specific billing line items based on the metrics they support. This ensures that each container’s costs are accurately reflected according to its usage. You can find which instances support which metrics by visiting Oracle's compute pricing . This resource helps explain variances in costs, such as why some nodes accrue filesystem charges while others may not, based on the supported by-metric costs of each node type.

Red Hat OpenShift Service on AWS

Cloudability ’s Container Cost Insights has been extended to support ROSA similar to EKS. The setup process for ingesting ROSA data into Cloudability follows the same basic steps as setting up K8s – you download a Cloudability agent YAML file, which is then used within your cluster to provision the metrics agent .

Supported Kubernetes configurations

As the most popular container orchestrator out there, there are many different ways to deploy Kubernetes and OpenShift. We strive to support all versions that are certified by the CNCF, and we will keep this matrix updated as we roll out support for additional configurations.
