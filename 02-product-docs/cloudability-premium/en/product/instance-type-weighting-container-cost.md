---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "product"
title: "VM family-based weightings"
breadcrumb:
  - "Cloudability Premium"
  - "Insights"
  - "Container Cost Allocation"
source_path: "product/instance-type-weighting-container-cost.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# VM family-based weightings

What is Resource Weighting?

While it is relatively straightforward to calculate the cost of each K8s cluster – by mapping the underlying VMs and disks – additional work is required to break each VM/disk up so they can be allocated out (there is no information within vendor billing files to help do this). Identifying what resources (CPU, Memory, Network etc.) are being consumed across Namespaces or labels, it is then key to be able to tie a cost contribution to these resources. This is where resource weighting comes in.

When we say CPU weight or memory weight, what we refer is the percent of the total node (i.e., VM) cost that should be associated to CPU or memory usage. When we first launched our container cost allocation capability, this was based on standard weightings that were used across all VM types. While this generally worked well, it has become clear that the wide variety of node types in use has necessitated a more nuanced approach.

New VM family-based weightings

VM weighting system will best match how each of the vendors tie cost to CPU, memory, disk and network - this can be established by comparing the prices and amount of each resource between two families. Here is how we do this starting with disk and network.

Disk and Network

For VM families that do not have local storage, this is simple, the cost contribution is 0%. For families that do have local storage we calculate the impact of that storage. For example, looking at AWS EC2, the m5.xlarge and m5d.xlarge VM types have exactly the same vCPU and memory, with only m5d having local storage. With the m5.xlarge costing $0.192 per hour and the m5d.xlarge $0.226 per hour, this additional $.034 charge for storage makes up 15% of the total m5d.xlarge cost.

For network charges, since this is not VM specific and normally is a lesser factor, we have associated a standard 5% cost for all VM types. The remainder of the VM cost is therefore split between memory and CPU, which for m5.xlarge would constitute 95% and for m5d.xlarge 80%.

Memory and CPU

To split this remaining cost, we can do a similar - albeit more complex - comparison between VM families to work out the cost per vCPU and GB of memory. For any VM,

VM hourly rate = vCPU count \* vCPU rate + memory \* memory rate

If we can work out the vCPU rate and the memory rate, then it’s possible to establish the ratio (i.e., weightings) for any VM family. While there are two unknown variables (the rates), we can solve these by having two separate equations – one for the target VM family and one for a “base” VM family.

It is worth discussing briefly how a base VM family is picked. The first thing to note is that the base VM will belong to the same processor manufacturer, whether that is AMD, Intel, or graviton. We will also prioritize a VM family from the same generation. For example, if the target is c6i, the base VM family used will likely be either m6i or r6i.

Having resolved the vCPU rate and memory rate for each VM family it is straightforward to calculate the weightings – multiplying the amount of vCPU and memory by their rates, then establishing the ratio between CPU and memory cost. Note, due to how the vendors bill their VMs, that these ratios are consistent at the family level.

What does that mean for your cost allocation?

- Cluster level cost figures are not impacted. This change only applies to Namespaces and
  Labels.
- The standard weightings used previously skewed allocation towards memory usage. With this
  release, it is now completely dependent on how the vendor charges for the specific VM family, but
  overall, this has shifted the weightings back towards CPU usage.
- This change has been made to both the values found in the Container Cost Allocation feature and
  to the Namespace and label dimensions within core reporting.
- This enhancement applies to both Kubernetes and ROSA clusters

**Parent topic:** [Container Cost Allocation](../product/k8s-cost-allocation.html)
