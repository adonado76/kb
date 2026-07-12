---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Container Cost Allocation"
breadcrumb:
  - "Insights"
  - "Container Cost Allocation"
source_path: "SSVCLNQ/product/k8s-cost-allocation.html"
images:
  - "03-media/apptio-cloudability-standard/k83_cost_allocation-1.jpg"
  - "03-media/apptio-cloudability-standard/k83_cost_allocation-2.jpg"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Container Cost Allocation

You can integrate Kubernetes (k8s) or OpenShift (ROSA) container data into Cloudability to gain visibility into the portion of your cloud spend due to container costs, and to assure it’s appropriately allocated.

View Container cost and usage data

You can view Kubernetes or OpenShift data on the Containers page or throughout Cloudability in tools such as Reports, TrueCost Explorer, and Tag Explorer.

For a holistic view of your Container cost and utilization data together, use the Containers page.

For investigating your container costs in relation to your total cloud spend, use Reports, TrueCost Explorer, and Tag Explorer.

Analyze Container data using reports and other tools

Container costs can be viewed alongside other cloud costs in a single report. Using kubernetes labels and business mappings, you can combine off-cluster costs (e.g. load balancers, and DBs among others) with container costs in a single report.

To see each dimension appear as a line item in your report (subject to filtering), select that dimension as a cost dimension.

There are two built-in dimensions for cost reports:

- Cluster Name
- Namespace

You can use these dimensions to build new cost reports or enhance existing cost reports.

Use the Cluster Name dimension

To see each Kubernetes (k8s) or OpenShift cluster name appear as a line item in your report (subject to filtering), select Cluster Name as a cost dimension. The Cost (Total) metric represents the entire cost attributed to that cluster, including idle resources, utilized and idle costs of the underlying compute nodes, and, on AWS, EBS storage volumes.

There will also be a (not set) value for Cluster Name, representing all costs within the account that are not part of any k8s or OpenShift cluster. Support for additional cost metrics, such as Cost (Amortized), Cost (Adjusted), and Cost (Adjusted Amortized), is also available.

Use the Namespace dimension

To see each unique namespace appear as a line item in your report (subject to filtering), select Namespace as a cost dimension. The Cost (Total) metric represents the k8s costs attributed to that namespace. Support for additional cost metrics, such as Cost (Amortized), Cost (Adjusted), and Cost (Adjusted Amortized), is also available.

NOTES:

- When you include Namespace as a dimension in a report, costs representing the allocated but unused resources within a cluster appear as a separate line item labeled 'IDLE RESOURCES' by default. To break down or fairly share those IDLE RESOURCES across each namespace, and to see more granular details on the idle and allocated costs within Cloudability core analytics (reports and dashboards), use the 'Containers' metric category, which introduces six additional metrics.
- When you add other dimensions to a report, such as Usage Family or Service Name, you will see additional cost details around each cluster name or namespace (subject to filtering).

To see only resources and costs associated with a specific namespace or cluster name, use the built-in filter function.

To see more granular details on the idle and allocated costs within Cloudability core analytics (reports and dashboards) on the cluster, Namespace dimension, use the "Containers" metric category, which introduces six additional metrics. These metrics enable users to view separately the utilized, idle, and fairshare costs on either a cash or amortized basis. For customers with custom pricing enabled, these metrics will be represented as "adjusted" metrics.

The Container Cost Allocation feature evaluates resource utilization on each node and correlates this with billing data to calculate the cost of each cluster. It associates a direct "utilized cost" to Kubernetes namespace and label values. This has been available within core reporting by using the namespace or a label dimension. With this enhancement, you can also report on the idle cost via the new metric, which is allocated to the namespace and label values proportionally based on their direct cost contribution of each node. The Fairshare Cost is the combined Utilized Cost and Idle Cost, representing the total cost.

Considerations and reporting ideas for these new metrics:

- For non-container costs, these metrics will return as $0. To filter to container-only data, try a filter such as “Cluster Name not equals (not set).”
- Use these metrics with different dimensions to visualize utilized vs. idle costs easily. For example, list by Cluster Name or resource ID.
- For the first time, you can use cash and amortized cost bases together for detailed container cost reporting.

Define additional dimensions based on K8s labels

Many organizations utilize labels in their k8s deployments in a similar way that they leverage resource tags within their cloud environments. To see these label key/value pairs appear within your Cloudability environment, you can map these label keys into dimensions in the same way that resource tags are mapped. Using the Tag & Label Mapping page, you can define new dimensions (and edit existing ones) and assign either resource tags or k8s labels to each dimension.

If you choose to map both k8s labels and resource tags into the same dimension, there are a couple key items to note.

- K8s labels should only be mapped into dimensions with resource tags when the values of both the labels and tags are homogeneous. Just as mapping unrelated resource tags into the same dimension can cause confusion, mapping unrelated labels and resource tags into the same dimension will only compound that confusion.
- In the event a resource tag and k8s label (both mapped to the same dimension) differ in value, the value from the k8s label will be selected and used, and the resource tag value dropped.

You are able to map up to 20 unique k8s labels keys within the Tag & Label Mapping page. Keep in mind that when you add or edit these mappings, you will start to see the values in reporting the next time we ingest a new vendor billing file. We will update the label mapping through the current month.

In reports and dashboards, a (not set) value for a Kubernetes label represents costs incurred when the Pod, Deployment, or other Kubernetes object did not have a value for that label.

(not set) will also appear for cost line items that were ingested and processed by Cloudability before the label was mapped to a dimension.

Cloudability does not currently support the back-filling of Kubernetes labels

Use the Tag Explorer

Just as with any other business mapping, mappings that you define using container-specific dimensions can be used in the Tag Explorer. This can help in understanding the costs associated with your k8s clusters and namespaces.

Use the TrueCost Explorer

Just as with any other business mapping, mappings that you define using container-specific dimensions can be used in the TrueCost Explorer. This can help in understanding how costs flow through your k8s clusters and namespaces.

Create business mappings

You can create a new business mapping (or edit an existing one) and use container-specific dimensions. The inclusion of these dimensions into a mapping is a powerful tool that enables you to combine different costs into a single construct. You can bring together k8s cluster costs with other, off-cluster costs to build a holistic view of your overall k8s computing costs.

Create views

You can create a new view (or edit an existing one) and use a mapping built from container-specific dimensions. Note that on the Containers page, the use of views based on business mappings are not supported, regardless of whether container-specific dimensions are used in the view definition.

Just as with other dimensions mapped from resource tags, you can use dimensions with k8s labels in Business Mappings, Views, TrueCost Explorer, Tag Explorer, and Reports.

When you compare cost allocation between the Containers page and a report, you may see differences. While cost at the k8s cluster level will be very similar (within a fraction of a percent), costs allocated to individual namespaces may differ.

On AWS accounts, EBS costs are handled differently. On the Containers page, EBS costs are allocated across each namespace based on their proportion of resource usage. In a report, however, these EBS costs are bundled together and left with the cluster. Therefore, you will see a (not set) bucket of EBS costs with the k8s cluster. The same is true for any non-node resources on Azure. In the near future we will allocate all cluster resources based on their usage.
