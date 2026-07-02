---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "product"
title: "Resource Inventory"
breadcrumb:
  - "Cloudability Premium"
  - "Insights"
source_path: "product/resource-inventory.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Resource Inventory

Resource Inventory enables creating a list of cloud resources from multiple accounts with various
dimensions and metrics. By unifying billing, utilization, and descriptive meta data you are able to
achieve a more comprehensive inventory view for your resources.

## Key Use Cases for Resource Inventory

1. **Cost to Utilization Data Mapping**

   **Solution:** By combining the Resource Inventory with Cloudability's synthetic tags (tag dimensions, account groups and business mappings),
   you can accurately map resource costs. For example, you can see the exact CPU and Memory utilization of a specific Compute Engine instance
   belonging to "Team Alpha" and allocate its cost accordingly. This enables the creation of robust show back reports for teams to understand their consumption
   and informed chargeback models for internal billing.
2. **Waste Reduction**

   **Challenge:** Over-provisioned resources lead to unnecessary cloud spend. Identifying underutilized Compute Engine instances or Managed Disks
   manually is time-consuming and prone to error.

   **Solution:** Leverage the CPU Utilization (Avg), Memory Utilization (Avg), and Memory Used metrics from the inventory.
   Identify instances with consistently low average CPU or memory usage. For Managed Disks, monitor their size relative to actual
   data stored to identify opportunities for downsizing.
3. **Performance Optimization and Bottleneck Identification**

   **Challenge:** Under-provisioned resources can lead to performance bottlenecks, impacting application responsiveness and user
   experience. Identifying the root cause requires detailed utilization data.

   **Solution:** Analyze CPU Utilization (Max), Memory Utilization (Max), and Network Utilization (Max). Spikes in these metrics
   could indicate a need to scale up resources. This data helps you proactively optimize resource allocation to ensure optimal
   application performance.
4. **Proactive Issue Resolution**

   **Challenge:** Unexpected cost spikes or performance degradation can be difficult to pinpoint without granular resource-level data.

   **Solution:** Regularly monitor the utilization metrics provided by the Resource Inventory. Sudden, unexplained increases in
   CPU Utilization (Min) or Memory Used on an otherwise stable instance could indicate a runaway process, misconfiguration, or even a
   security incident. By setting up alerts based on these metrics, you can detect anomalies early and take corrective action before they
   significantly impact costs or operations.
5. **Lifecycle Management and Resource Governance**

   **Challenge:** Tracking the lifecycle of cloud resources, from launch to de-provisioning, can be complex, leading to "zombie" resources
   that incur costs without providing value.

   **Solution:** The "launch date of resources" combined with utilization metrics, are invaluable.
   Identify resources that have been running for an extended period with persistently low utilization.
   For instance, a Compute Engine instance with a very old launch date and consistently low CPU Utilization (Avg) and Memory Utilization (Avg)
   might be a forgotten resource that can be safely terminated. This proactive approach ensures better resource governance and prevents
   unnecessary spending.

By providing a unified view of your inventory, complete with detailed utilization metrics and critical metadata,
Cloudability empowers you to make data-driven decisions, optimize your cloud spend, and enhance the efficiency of your cloud operations.

- **[AWS Resource Inventory](../product/aws-resource-inventory.html)**
- **[Azure Resource Inventory](../product/azure-resource-inventory.html)**
- **[GCP Resource Inventory](../product/gcp-resource-inventory.html)**
- **[OCI Resource Inventory](../product/oci-resource-inventory.html)**
- **[Resource Inventory FAQs](../product/resource-inventory-faqs.html)**
