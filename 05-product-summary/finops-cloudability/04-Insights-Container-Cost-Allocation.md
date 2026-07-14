---
source_system: "apptio-cloudability-standard"
practice: "finops"
language: "en"
doc_type: "cloudability-standard"
consolidated_file: "04-Insights-Container-Cost-Allocation"
source_files_count: 10
last_updated: "2026-07-13"
---

# 04-Insights-Container-Cost-Allocation

## Container Cost Allocation

<!-- sub-header -->
- **breadcrumb:** Insights > Container Cost Allocation
- **source_path:** SSVCLNQ/product/k8s-cost-allocation.html
- **original_file:** insights-container-cost-allocation.md
- **images:**
  - 03-media/apptio-cloudability-standard/k83_cost_allocation-1.jpg
  - 03-media/apptio-cloudability-standard/k83_cost_allocation-2.jpg

## Container Cost Allocation

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

---

## Agent Observatory Tool

<!-- sub-header -->
- **breadcrumb:** Insights > Container Cost Allocation > Agent Observatory Tool
- **source_path:** SSVCLNQ/product/agent-observatory-tool.html
- **original_file:** allocation-agent-observatory-tool.md
- **images:** []

## Agent Observatory Tool

### Overview

The Agent Observability Tool provides real-time monitoring of Cloudability metrics agents in a tabular format across all your clusters, enabling you to track agent health, detect issues, and ensure accurate cost reporting.

Currently data is available for the past 7 days only .

To access the Agent Observability Tool:

Navigate to Insights > Containers > Monitor .

The Agent Observability Tool displays the list all monitored clusters for installed metrics agents in a table.

| Column | Description |
| --- | --- |
| Cluster Name | Name of your cluster. |
| Agent Status | Displays the status as Active / Inactive for the metrics agent. |
| Agent Version | The installed agent version. |
| Cluster Version | The Kubernetes/ Openshift version running on the cluster. |
| Last Seen | Timestamp of the last successful data ingestion. |
| Cluster Type | Identifies the cluster type (e.g., EKS, ROSA). |
| Vendor | The cloud service provider for the cluster (e.g., AWS). |

### Recommended Actions

- Check for Inactive agents: Filter by Inactive status to find clusters not reporting data, investigate connections, version, and configuration issues. A cluster is marked Inactive if the Last Seen value is greater than 12 hours.
- Monitor Agent Versions: Ensure all clusters are running the latest agent version for compatibility, new features, and security improvements.
- Review duplicate Cluster Names: If you see a warning icon, update unique cluster names for accurate reporting.
- Track data freshness: Use the Last Seen column to ensure data is recent. Agents not reporting for more than 24 hours should be reviewed.

---

## Analyze data for your Kubernetes containers

<!-- sub-header -->
- **breadcrumb:** Insights > Container Cost Allocation > Analyze data for your Kubernetes containers
- **source_path:** SSVCLNQ/product/analyze-data-for-your-containers.html
- **original_file:** allocation-analyze-data-your-kubernetes-containers.md
- **images:**
  - 03-media/apptio-cloudability-standard/audit2.jpg
  - 03-media/apptio-cloudability-standard/cldy-idle-cost.jpg
  - 03-media/apptio-cloudability-standard/container-cost-allocation-export.png

## Analyze data for your Kubernetes containers

### Container Cost Allocation

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

### Idle Cost Distribution

Overview

Containers have a spare overhead capacity not used by underlying workloads. This “idle” usage has an associated cost (for virtual machines and volumes). Cloudability distributes these idle container costs within its reports, dashboards, and container cost allocation.

This introduces the new metric category Containers along with six others. You can use these metrics to view separately Utilized , Idle and Fairshare costs for cash or amortized basis.

The Container Cost Allocation feature evaluates resource utilization on each node and adds it to the billing data to calculate the cost of each cluster. This associates the Utilized Cost to Kubernetes namespace and label values (available within reports by using the namespace or a label dimension). With this enhancement you can also report on the Idle Cost via the new metric, allocated to the namespace and label values proportionally based on their direct cost contribution of each node. The Fairshare Cost is the sum of Utilized Cost and the Idle Cost .

Considerations and reporting ideas to keep in mind with new metrics:

- For non-container costs, the new metrics will all display $0. To filter to container only data, use a filter such as “ Cluster Name not equals (not set) ”
- Use these metrics with different dimensions to easily visualize Utilized vs Idle Cost . For example, list out by Cluster Name or Resource ID .
- For the first time, use cash and amortized cost basis together for detailed container cost reporting.

### Container allocation data export

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

### Supported Kubernetes configurations

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

---

## Cloudability Advanced Containers

<!-- sub-header -->
- **breadcrumb:** Insights > Container Cost Allocation > Cloudability Advanced Containers
- **source_path:** SSVCLNQ/product/advanced-containers.html
- **original_file:** allocation-cloudability-advanced-containers.md
- **images:**
  - 03-media/apptio-cloudability-standard/UA-arch.png
  - 03-media/apptio-cloudability-standard/prov_clust.png
  - 03-media/apptio-cloudability-standard/prov2.png
  - 03-media/apptio-cloudability-standard/adv1.png
  - 03-media/apptio-cloudability-standard/adv2.png

## Cloudability Advanced Containers

Overview

The new Cloudability Advanced Containers module brings Kubecost’s real-time container cost visibility and other capabilities into the Cloudability SaaS framework, providing a unified view of cloud and Kubernetes spend for FinOps, Platform Engineering, and DevOps teams. This capability is available today as an optional paid add-on for all Cloudability Essential, Standard, and Premium customers . With this offering, you can allocate costs at an even more granular level (namespace, label, annotation, controller, service, etc), get immediate savings recommendations for Kubernetes workloads, and enforce cost governance – all within Frontdoor’s interface. It supports multi-cloud (AWS, Azure, GCP, Oracle) and hybrid/on-prem Kubernetes environments (OpenShift & more), so you can manage costs across clusters running anywhere.

Key Capabilities Available in the Advanced Containers Module

- Real-Time Kubernetes Cost Visibility Provides continuous, real-time monitoring of Kubernetes resource consumption and associated costs across all clusters, enabling immediate insight into spend trends and anomalies.

- Granular Cost Allocation & Showback Delivers precise cost allocation across all native Kubernetes constructs—including clusters, nodes, namespaces, deployments, services, labels, and annotations—fully reconciled with actual cloud billing data for accurate showback and chargeback.

- Optimization Insights and Recommendations Offers built-in optimization guidance and actionable savings recommendations to reduce Kubernetes spend while maintaining workload performance and reliability.

- Budgets, Alerts, and Governance Enables proactive financial governance for Kubernetes environments with real-time budgets, alerts, and spend controls at the cluster, team, or namespace level, aligned with existing cloud budgets.

Integration Architecture

Under the hood, the integration is powered by the IBM FinOps Agent , an open sourced ( GitHub ) unified in-cluster data collector that replaces the older Cloudability metrics agent and Kubecost’s standalone Prometheus collector. The FinOps Agent runs in each Kubernetes cluster and gathers resource usage and metadata directly from the Kubernetes API, node, kernel and other sources. It then emits that data to the Cloudability & Kubecost backend.

At regular intervals (by default, the agent scrapes every 30 seconds and emits every 10 minutes); the agent's exporter captures a snapshot of the cluster state—including pods, nodes, and usage metrics—and delivers it to each enabled emitter. This modular architecture ensures that data is collected once and efficiently sent to both core Cloudability and the Advanced Containers module.

This architecture allows Cloudability and Kubecost to work in tandem: Cloudability provides high-level cost reporting, trends, and multi-cloud context (with all cloud services), while Kubecost provides deep Kubernetes-specific insights and real-time exploration. The single agent deployment simplifies overhead by eliminating the need for a full Prometheus instance in each cluster (saving memory/CPU). The agent is lightweight and runs as a single container pod for easier scaling and resilience. All data collection uses Kubernetes-native APIs or metrics, and no sensitive payload (like application data) is sent – only resource and billing metadata needed for cost calculations.

(Architecture Diagram for IBM FinOps agent)

How to Get Access

The Cloudability Advanced Containers module is an optional paid add-on capability available to Cloudability customers. To get access, contact your IBM/Apptio representative or support to request access to these new capabilities. They will confirm any licensing requirements and enable the feature flag on your Cloudability environment (if applicable). If you are not an existing IBM/Apptio customer, contact us here

Setup and Installation

Setting up the Cloudability–Kubecost integration involves deploying the IBM FinOps Agent to each Kubernetes cluster that you want to monitor. Once deployed, the agent will automatically collect and send data to your Cloudability and Kubecost instance.

Overview of Installation process:

1. Collect API Key & Secrets: Cloudability uses its centralized Apptio “Frontdoor” authentication system for APIs. You can obtain these keys by following the steps in “ Authentication ” section in this documentation

2. Set Cluster ID: Decide on a unique identifier for your cluster (e.g. “prod-cluster-1”). If using the Cloudability UI wizard, you will enter the cluster name and Kubernetes version, and it will embed this in the config. The Cluster ID is used to tag the data sent to Cloudability and must remain consistent for that cluster. (For GKE clusters, also add a cluster label on GCP side: tag your cluster with key gke-cluster and value matching the Cluster ID. This helps Cloudability map GKE billing data to the right cluster.)

Tip: It’s recommended to use a naming convention for Cluster IDs that is unique globally across all your clusters (e.g. include an environment or region code). Once chosen, you should not change a cluster’s ID, or Cloudability will treat it as a different cluster.

3. Deploy the IBM FinOps Agent to Your Cluster – The FinOps agent is provided as a Helm chart for easy installation. You can either use the Helm command generated by Cloudability (via the Provision dialog) or manually install using the published Helm repo. To install manually using Helm 3 on your cluster:

The IBM FinOps Agent includes two emitters —one for Kubecost and one for Cloudability. To send data to both platforms, you must enable both emitters during installation. In the Generate Command section (under Provision Cluster ), click the link shown in the screenshot below and follow the instructions to enable both emitters.

Please note: the command displayed in Cloudability Container Insights enables only the Cloudability emitter . You will still need to configure the Kubecost emitter separately using the linked instructions.

![](../images/prov_clust.png)

This will open the following UI that walks you through the installation process

![](../images/prov2.png)

- Install or update the agent on your cluster:

```
helm upgrade --install ibm-finops-agent \
--repo https://kubecost.github.io/finops-agent-chart finops-agent \
--namespace ibm-finops-agent \
--set agent.cloudability.uploadRegion=us-west-2 \
--set agent.cloudability.parseMetricData=false \
--set agent.cloudability.secret.cloudabilityEnvId=<yourenvironmentid> \
--set clusterId=test \
--set agent.cloudability.secret.create=true \
--set agent.cloudability.secret.cloudabilityAccessKey=<AccessKey> \
--set agent.cloudability.secret.cloudabilitySecretKey=<SecretKey> \
--set agent.cloudability.enabled=true \
--set global.federatedStorage.existingSecret=adv-containers-fed-store-config
```

- In the above command, replace <YOUR_CLUSTER_ID> with the unique Cluster ID chosen, and provide the Cloudability API key and environment ID gathered in step 1. These values ensure the agent knows where to send data. The chart will create a Kubernetes Deployment (or DaemonSet) for the agent along with necessary RBAC roles.

- Permissions: Ensure you have cluster-admin privileges when installing. The Helm chart will set up a service account and cluster roles that allow the agent to read required metrics (pods, nodes, namespaces, etc.). If using restrictive RBAC policies, you may need to manually grant the agent permissions per the documentation.

- Network & Storage: The agent requires outbound HTTPS access from the cluster. Specifically, it must reach frontdoor.apptio.com (for auth) and api.cloudability.com (or regional equivalents) on port 443. It also uploads data to an Apptio-owned S3 bucket, so access to *.s3.amazonaws.com (with bucket name prefixed apptio) is needed. If your cluster is behind a proxy or firewall, configure egress rules to allow these endpoints. Additionally, the Helm chart by default creates a Persistent Volume Claim (PVC) (8Gi by default) for the agent. This storage is used to buffer metrics data in case of connectivity issues or agent restarts, preventing data loss. Make sure your cluster can provision this PVC (it can be adjusted in values if needed).

- Image Source: Note that the FinOps Agent’s container image is hosted on the IBM Container Registry (icr.io), not Docker Hub. Ensure your cluster’s image pull policies or firewall allow icr.io/ibm-finops/*. If you use a private registry mirror, you may need to pull and push the image from icr.io manually (the documentation provides a Podman pull example).

Once the Helm install completes, verify that the agent pod is running:

```
kubectl get pods -n kubecost
```

You should see a pod named kubecost-finops-agent-... in Running state.

3. Data Ingestion and Verification – After deploying the agent, it will begin collecting data immediately. However, Cloudability’s SaaS processing will typically reflect the new data within one hour . In the Cloudability UI, go to Advanced Containers and verify that your cluster appears in the list of provisioned clusters. Initially, it may show as waiting for data. Within 24 hours, you should start to see cost allocation information for that cluster in Cloudability’s container cost dashboards. You can also check the agent’s logs to see if it’s successfully sending data (look for log lines indicating data uploaded).

Once data is flowing, Cloudability will display allocated costs for your cluster’s namespaces, labels, etc., alongside your other cloud costs. Kubecost (if installed) will also begin showing cost data in its UI in real-time (usually within a few minutes of deployment). Remember that Cloudability relies on cloud billing exports for the total cost of the cluster (e.g. the cost of the node VMs). If those billing exports are not yet configured or updated, you might see partial data. Make sure your cloud billing integration in Cloudability is in place (see Prerequisites below).

4. Enable SSO/Access (if applicable) – If your organization uses SSO for Apptio products, you can integrate Kubecost’s access with Cloudability’s login. The Kubecost module can leverage the same SSO via Apptio Frontdoor, so that users who are logged into Cloudability can seamlessly access Kubecost without a separate login. Work with IBM support to configure this shared authentication if you plan to use the standalone Kubecost UI. This typically involves setting up Kubecost with OIDC pointing to the Apptio Frontdoor IdP and granting users the appropriate roles in Kubecost (which can mirror Cloudability roles).

Product Usage

Cloudability Advanced Containers consists of two integrated components :

1. Advanced Container (Overview Page inside the Cloudability UI)

This provides a simplified, Cloudability-native experience tailored for FinOps workflows—highlighting cluster costs, efficiency, namespace trends, cloud spend, and network usage. It’s designed for quick insights, executive reporting, and day-to-day cost visibility.

2. Standalone Advanced Container Application (Kubecost 3.0 Experience inside Frontdoor)

This is the full-featured Kubecost interface that offers deep technical cost analytics, granular allocations, network flows, diagnostic tooling, and advanced configuration options. It’s built for engineering teams, SREs, and platform owners who need detailed, hour-level cost insights and operational controls.

Together, these two pieces deliver both FinOps-ready summaries and engineering-grade depth , creating a unified Advanced Containers experience across Cloudability and Kubecost.

1. Using Kubernetes Cost Analytics in Cloudability

1.a. Advanced Container (Overview Page inside the Cloudability UI)

In Cloudability SaaS, navigate to Insights > Advanced Containers . This will open the Advanced Container overview page .

![](../images/adv1.png)

- High-Level Cost Summary

Shows total Kubernetes costs, total cloud costs, and potential monthly savings in one place.

Surfaces week-over-week changes so users can instantly spot cost spikes or anomalies.

Highlights overall cluster efficiency, helping teams benchmark waste and optimization needs.

- Cluster-Level Breakdown

Lists all clusters with their individual spend and health status (active/unmonitored).

Helps users quickly identify the most expensive clusters and validate connectivity/monitoring.

Provides trends over time so teams can see how cluster costs evolve daily.

- Resource Efficiency Overview

Displays CPU, RAM, GPU, and Storage allocation vs. actual usage.

Makes idle vs. used cost visible, helping quantify waste across resources.

Supports immediate right-sizing and capacity planning decisions.

- Namespace-Level Cost Insights

Lists top namespaces driving spend across clusters.

Includes trend visuals to show when and where namespace costs are increasing.

Helps pinpoint noisy or growing workloads early.

- Network Cost Breakdown: Highlights network-heavy namespaces and services with high egress or traffic volumes. Surfaces expensive cross-region or cross-zone traffic destinations. Helps teams control hidden egress costs often missed in FinOps reviews.

Note: Advanced Containers cost data is generated in real-time from usage, whereas Cloudability’s official cloud billing data is typically updated daily. Discrepancies can exist between Kubecost’s immediate cost estimates and the final billed costs that appear in Cloudability due to timing, refunds, or discounts. Over a full month, the numbers should reconcile closely (especially if using Cost Adjusted/Amortized in Cloudability to include discounts). But don’t be alarmed if on a given day Kubecost’s UI shows $X for a namespace and Cloudability shows $X ± a few percent – this is expected due to the different metholodies used. The integration is meant to provide timely insights, not an exact accounting ledger at every moment.

1.b. Using the Advance Container Standalone Module

For users who need more interactive Kubernetes-specific analysis or real-time control, the Advanced Containers UI can be used alongside Cloudability:

![](../images/adv2.png)

- Accessing Advanced Containers UI: If Advanced Containers is deployed, it can be accessed directly in your browser through Frontdoor. Cloudability also surfaces a dedicated deep link on the Advanced Containers Overview page, allowing users to open the standalone advanced container (Kubecost 3.0 UI) in a new tab. With shared SSO, users can seamlessly navigate without requiring a separate login.

- Kubecost UI offers a richer and more interactive experience than the Cloudability Overview. For example, the Cost Allocation view supports multi-dimensional grouping, advanced AND/OR filtering (introduced in Kubecost 3.0), and immediate visualization of cost impacts. Kubecost also retains detailed historical data, including hourly resolution, with configurable retention settings to support deep analysis.

- Kubernetes Optimization and Actions: In Kubecost’s UI, you can explore specific optimization insights in depth. For example:

- Savings Recommendations (Savings Insights): A list of opportunities like “remove unused persistent volumes” or “downsize idle nodes” along with estimated savings. These are based on policies (e.g. detect if a node’s utilization < 5% for 7 days).

- Rightsizing Insights: Kubecost provides container right-sizing recommendations. You can view recommendations for each deployment’s CPU/memory requests based on actual usage. Kubecost 3.0 adds a new UI to manage container requests across clusters with just a few clicks. You could use this to reduce requested resources and immediately cut cost (especially in autoscaling environments).

- Node Group (Cluster) Optimization: Kubecost can suggest how to adjust node instance types or autoscaling settings. In v3.0, node sizing recommendations consider GPU usage and show visualizations of capacity vs. usage. These recommendations also take into account real cloud pricing (including your enterprise discounts or reserved instances) for realistic savings estimates.

- Network Monitoring: Provides a visual map of network traffic flows between workloads, namespaces, and services, helping teams identify high-cost egress paths, unexpected communication patterns, and potential performance bottlenecks.

- Automation: While Kubecost itself focuses on recommendations (and can execute some actions like applying new requests if granted permissions), pairing it with Turbonomic can enable automated resizing or scheduling based on those insights. This integration is part of IBM’s broader FinOps strategy, combining Cloudability’s cost transparency, Kubecost’s container insights, and Turbonomic’s action automation.

- Budgets and Alerts in Adv Containers: In addition to Cloudability’s budgeting, Advanced Containers allows setting up alerts on various conditions at the Kubernetes level. For example, you might set a monthly budget for a namespace or team and Advanced Containers can send an alert (email, Slack, etc.) if the projected cost will exceed that budget Advanced Containers supports alert types like budget thresholds, percentage spend changes, and efficiency alerts for resources. These can be managed in Advanced Containers’s UI (Alerts section). Cloudability’s integration doesn’t yet expose creating Kubernetes-specific budgets in the Cloudability UI, so using Advanced Containers for that granular budget alerting can be helpful. (Cloudability’s own budget feature could be used at the aggregate cluster level, but not per namespace – Advanced Containers fills that gap.)

API Access:

- Both Cloudability and Advanced Containers offer APIs for retrieving cost data. Cloudability’s API could be used to pull combined cost data (including container allocations) for integration with external systems (like CMDBs or chargeback systems). Advanced Containers provides an API (the Kubecost API) to query real-time cost metrics by aggregation (e.g. cost by label for last 7 days). In an integrated setup, you might use Advanced Containers’s API for on-demand queries (since it’s real-time and cluster-resident) and Cloudability’s API for official monthly cost reporting.

For example, a platform engineer could query the Advanced Containers API at the end of the day to see cost for a specific deployment that day (for quick feedback to developers), rather than waiting for the next day’s Cloudability update. On the other hand, a finance analyst might use Cloudability’s API at month-end to pull the fully reconciled container costs (with discounts applied) to feed into chargeback invoices.

To access to the Advanced Containers API endpoints you will need to a Cloudability API Key or an apptio-opentoken for authentication. Visit Getting started with Cloudability API V3 to learn more about how to create your Cloudability API Key and generating apptio-opentokens.

Once you have a Cloudability API key or apptio-opentoken, you can use it to access any of the APIs documented in Kubecost API Directory .

Be advised <kubecost-address> referenced in these endpoints will be replaced with < api.cloudability.com/v3/kubecost >.

Example command using API key:

```
curl 'https://api.cloudability.com/v3/kubecost/model/allocation?window=3d&offset=20&limit=10&accumulate=true' -u '<your_api_key>:' 
```

Same example using apptio-opentoken:

```
curl 'https://api.cloudability.com/v3/kubecost/model/allocation?window=3d&offset=20&limit=10&accumulate=true' -H ”apptio-opentoken: <your_apptio-opentoken>” -H “apptio-environmentid: <your_frontdoor_enviornmentId>”
```

Prerequisites & Compatibility

Before enabling the Advanced Containers integration, ensure your environment meets the following prerequisites and compatibility requirements:

- Cloudability Account & Billing Data: You must have an active IBM Cloudability (SaaS) account with access to configure the Containers feature. Typically, Cloudability should already be set up with your cloud billing exports :

- AWS: An AWS Cost and Usage Report (CUR) configured and linked to Cloudability (usually via an S3 bucket). This is required so Cloudability knows your EC2/EKS costs, including node costs.

- Azure: An Azure Enterprise or Cost Management export, or an authorized API connection, so Cloudability can ingest Azure usage details. This provides AKS node VM costs, etc.

- GCP: A BigQuery billing export for GCP linked to Cloudability, so GKE and GCE costs are available. Additionally, for GKE, ensure each cluster has the gke-cluster label as described earlier for cost mapping.

- On-Prem or Other: If you have on-prem Kubernetes, you’ll need to manually define costs in Advanced Containers (via custom pricing) since Cloudability won’t have a native billing source. Cloudability can still display those costs if the agent uploads them, but note that features like amortization or adjusted cost don’t apply (since those are cloud-specific). It’s primarily for visibility.

Why this matters: Cloudability uses cloud billing data as the source of truth for cost. The FinOps agent will tie Kubernetes metrics to those billing line items. If Cloudability doesn’t have the billing data, you’ll get incomplete cost info. Make sure your cloud integrations in Cloudability are up-to-date and include resource tags/labels where needed (especially for AWS and GCP as they rely on tags/labels to identify clusters).

- IBM FinOps Agent: version 1.0.0 or later of the agent is required (this comes bundled with Kubecost 3.0+ or as a separate chart).

- Cloudability SaaS: Ensure you are on the latest Cloudability (the service is updated continuously by IBM). The Container Insights 2.0 enhancements (which this integration uses) were introduced in 2024, so any Cloudability environment after that date is compatible. There is no “version number” on SaaS, but your rep can confirm if the Containers 2.0 feature is enabled.

Kubernetes Cluster Version: Kubernetes v1.29 or higher is recommended. Kubecost 3.0 officially supports K8s 1.29 through 1.34. Clusters running older versions (e.g. 1.21, 1.22, etc.) may still work with the agent, but have not been tested thoroughly with the new agent. If you have very old clusters, upgrade them if possible, or consult IBM – the open-source Kubecost had support matrices and you may need to use an older Kubecost version with limited integration. Also ensure your clusters have the Kubernetes metrics server installed (most managed K8s do); it’s needed for usage metrics if not using Prometheus.

- Helm and CLI Tools: You’ll need Helm 3.x to install the agent on each cluster. You should also have kubectl access to your clusters (with admin privileges) to perform the installation. If you use ArgoCD or GitOps, you can include the FinOps Agent Helm release in your config – just ensure secrets (API keys) are managed appropriately.

- Resource Requirements: The FinOps Agent is lightweight, but plan for its resource usage on each cluster:

- CPU/Memory:

- Persistent Storage: ~8Gi disk space (default) for local caching. If your cluster generates a very high volume of metrics (lots of pods flapping), monitor this usage – you can increase the PVC size if needed.

- Network: The agent will transmit data to the cloud (the data size is not huge – typically tens of MB per day per cluster, depending on activity). Ensure this outbound traffic is allowed and accounted for in your networking egress policies. If using a proxy, set the HTTPS_PROXY environment variables for the agent pod so it can route traffic properly.

- Security and Access: The integration touches sensitive cost data, so consider:

- RBAC: The agent’s Kubernetes RBAC is read-only (plus the ability to create its own resources). It does not have rights to modify workload configurations (unless you specifically enable Kubecost’s features to act on the cluster). Review the roles it creates if concerned. It needs access to resources like Pods, Nodes, Namespaces, PVs, etc., and metrics from the Metrics API. It may also use cluster-level metrics (cAdvisor stats) – if so, it accesses them via the K8s API or kubelet. Ensure your cluster’s security policies (PSPs, etc.) allow the agent to function. The agent container runs as non-root.

- API Keys: Treat the Frontdoor API key like a password. Only assign the minimal roles (the CloudabilityContainerUploader role as described). In Cloudability’s Access settings, you might create a separate Environment for these container uploads. If the key is compromised, an attacker could potentially upload bad data or access certain APIs, so guard it and rotate if needed. Cloudability logs the source of uploads; using a distinct service account helps track activity.

- Data Privacy: Kubecost’s design is that cost data is computed locally – the FinOps Agent exports metadata and resource usage. No application payload or customer data is transmitted, only cost-related info. IBM’s acquisition of Kubecost means the product adheres to enterprise data handling standards. If needed, you can get a list of exactly what data points are sent (generally: cluster IDs, resource IDs, usage quantities, cost figures, etc.). All transmission is encrypted (HTTPS). No data is sent to Kubecost’s cloud (unless you use their SaaS) – by default it only goes to your Cloudability instance’s storage and (if self-hosted Kubecost) to your configured storage.

- Networking Requirements: As mentioned, the cluster must allow egress to specific endpoints:

- Apptio Frontdoor ( https://frontdoor.apptio.com or regional variants like frontdoor-eu.apptio.com for EU) – used for agent authentication and API key validation.

- Cloudability API ( https://api.cloudability.com or regional domain) – used for uploading data and any API interactions.

- Apptio Storage (S3) – the agent will upload files to an S3 bucket managed by Apptio. The bucket name varies by environment (it starts with apptio); you may see it in the agent logs. You should allow *.s3.amazonaws.com or specifically the apptio-<something> bucket endpoint for HTTPS PUT operations. If your org restricts S3 access by bucket, ask Apptio support for the exact bucket name for your region.

- If your environment uses a web proxy for outbound traffic, configure the agent’s environment variables accordingly (the Helm chart can pass proxy settings). If using a private VPC without internet, you might need to route traffic through a NAT gateway or VPN to Apptio’s endpoints.

- Container Registry: Allow access to icr.io (IBM Cloud Container Registry) so the agent image can be pulled. If you use an internal registry mirror, you can pre-pull the image icr.io/ibm-finops/agent:<version> and host it internally.

By checking all the above prerequisites, you’ll set yourself up for a smooth integration. It’s a good practice to do a small pilot (integrate one non-prod cluster first, verify data) before rolling out to all clusters.

Troubleshooting

Having trouble with the integration? Here are common issues and troubleshooting steps:

- No Data Appearing in Cloudability: If after 24+ hours you don’t see any container cost data:

- Verify that the agent pod is running in the cluster (kubectl get pods -n kubecost). If it’s CrashLooping or not present, describe the pod to see error messages. Common causes are insufficient permissions or inability to reach the Cloudability endpoints.

- Check the agent’s logs (kubectl logs -n kubecost deploy/kubecost-finops-agent) for errors. Look for messages about failed uploads or authentication. For example, an HTTP 403 error might indicate an invalid API key or improper role (double-check the key has the CloudabilityContainerUploader role and wasn’t copied incorrectly). A networking timeout could indicate it can’t reach the API endpoints (check your egress firewall/DNS).

- Ensure your Cloudability API key and env ID are correct. If you generated a key in Apptio Frontdoor, make sure you used the correct environment (some customers have multiple Apptio environments – ensure you used the one corresponding to your Cloudability instance).

- For GCP GKE clusters, ensure you completed the cluster labeling and tag mapping step. If you forgot, Cloudability might not tie the usage to any cluster (especially if you see data in the agent logs but Cloudability UI still empty, this mapping could be the issue). Add the label and allow a new billing export to flow in (could take 1-2 days for GCP).

- Check that your cloud billing data is up to date in Cloudability. If the CUR or export isn’t being updated (or wasn’t configured before deploying the agent), Cloudability might drop the data. For AWS CUR, ensure it’s delivering daily and that Cloudability has ingested the latest files.

- If the cluster uses a proxy , ensure the agent is actually using it. You might exec into the pod and try a curl to api.cloudability.com to see if it connects. Set the HTTP_PROXY/HTTPS_PROXY env vars accordingly in the deployment if not.

- Lastly, try redeploying the agent with debug enabled (if available in values) or reach out to Apptio/IBM support. The Cloudability support team can check on their side if any data was received or if there were format issues.

- Data Mismatch or Incomplete: If you see data but it seems off (e.g. a known namespace’s cost is missing or zero):

- Confirm that namespace isn’t filtered out. Cloudability by default might hide system namespaces (like kube-system) from allocation views unless you choose to show shared costs. Check filter settings.

- If storage or network costs show as $0, confirm that you have those costs in your cloud bill (e.g. EBS volumes are tagged properly to attribute to the cluster). Kubecost can allocate network egress costs if configured, but Cloudability requires the billing data for network (for AWS, ensure VPC Flow Logs or Data Transfer costs are tagged or at least mapped).

- For on-prem clusters, if costs show as $0 it means you haven’t set custom pricing in Kubecost – update the custom pricing config (through Kubecost UI or ConfigMap) with your per-node costs so that the agent can report meaningful values.

- If idle cost seems abnormally high, it means most of your resource requests are low. This could be accurate (cluster is mostly idle) or a sign that your requests/limits in Kubernetes are not set properly (Pods running at BestEffort QoS will always count as usage == request which can skew allocation). Review the QoS rules: Cloudability uses Requests for Guaranteed pods and max(Usage, Request) for Burstable pods. So if teams aren’t requesting resources, usage might be counted, which if low leads to more “idle” classification. This is more of a finetuning issue; you might set a policy that all workloads must have requests/limits.

- In Kubecost’s own UI, you can check the Diagnostics page. Kubecost 3.0 introduced a health alert that notifies if it’s missing any data or has any integration issues. If Kubecost shows an alert like “Missing cloud billing data” or “Unable to reconcile costs”, that can clue you into issues (like missing permissions to fetch pricing, etc.). Many of those issues could impact Cloudability as well. Use Kubecost’s diagnostic as a quick sanity check (since it’s running locally, it might show data even if Cloudability doesn’t yet).

- If Cloudability UI is showing the cluster, but says “No cost data for selected time period,” ensure you have the time window correct (e.g. after integration start) and that usage has occurred. Also confirm the agent is still running – if someone removed it or it crashed a week ago, you’ll only see historical data up to that point.

- Agent or Kubecost Pod Performance: If you notice the agent or Kubecost pods using too much CPU/memory:

- Check if the agent is overburdened by too frequent snapshots. The default interval is typically a few minutes – you can adjust it if needed (there’s a Helm value for snapshot interval). For extremely large clusters, consider increasing the interval to reduce load (with the tradeoff of slightly less granular data).

- Ensure that the agent isn’t competing with other monitoring agents (if you still have a Prometheus collecting similar data, it might double-load the API). It’s best to disable any legacy cost collection once FinOps Agent is running.

- Kubecost’s frontend and aggregator (if you deployed them) might need more resources for large environments – monitor their resource usage and scale CPU/Memory or enable multi-replica mode for the API if needed. Kubecost 3.x moved to ClickHouse for faster queries and better scaling, but heavy querying of months of data can still be intensive. Use the Enterprise features (if licensed) like federated ETL offloading to a central ClickHouse for multi-cluster scale.

- Upgrading Components: If you upgrade your Kubernetes version or cloud provider accounts:

- After a K8s version upgrade, the agent should continue to work (it’s quite version-agnostic as long as APIs are stable). Keep an eye on it during cluster upgrades; if you do an in-place upgrade, the agent pod will restart on the new version – verify it comes back healthy.

- If you change cloud provider settings (like AWS account IDs or roll new CUR bucket, etc.), update Cloudability configuration accordingly. The agent itself doesn’t need changes, but Cloudability must have continuity of billing data to align costs.

- When new versions of the IBM FinOps Agent are released, plan to upgrade the Helm release. Check IBM/Apptio release notes for improvements or bug fixes (e.g., a future v1.1 might reduce idle calc errors, etc.). Upgrading the agent is typically done by running helm upgrade with the new chart version. This should be seamless (it will restart the pod). Do this in a test cluster first if possible.

- Upgrading Kubecost : If you deployed Kubecost, follow their upgrade guide. Going from 2.x to 3.x is a major change (with migration to the new architecture). Ensure you back up any persistent volumes (ClickHouse data) if applicable. Post-upgrade, verify that the FinOps agent is active (in Kubecost 3.x, it’s enabled by default; you might disable Prometheus as it’s no longer needed). Kubecost’s UI should show data as before.

- Getting Help: If issues persist, use the support channels:

- IBM Support: Since Cloudability and Kubecost are IBM products, you can open a support case. Provide them with your Cloudability environment ID, cluster ID, and timeframe of the issue. The support team can check backend logs. They may ask for agent logs or Kubecost diagnostics.

- Community & Docs: The OpenCost (Kubecost open source) community Slack or forums might help for generic questions about cost anomalies. The official docs (IBM Docs for Kubecost, Cloudability Knowledge Center) have more tips – for example, Cloudability’s docs have a page on verifying the container agent connection.

- Diagnostics Tools: Cloudability doesn’t have a direct UI for agent status, but you can use Kubecost’s multi-cluster diagnostics if you have multiple clusters. Kubecost Enterprise has a “Multi-Cluster Diagnostics” page to see all clusters health. This can show if one cluster’s agent is failing to send data.

In summary, most issues can be traced to configuration mistakes (API keys, permissions, or missing billing data) or environmental constraints (network, older cluster versions). Once configured correctly, the integration tends to be low maintenance. The agent is designed to recover from failures (using the PVC to buffer data until connectivity is restored), so short outages shouldn’t result in data loss. Keeping software up to date and monitoring the health via alerts will ensure smooth operation.

Performance & Scale

This integration is built to scale with large enterprise environments. Both Kubecost and Cloudability have made improvements to handle high volumes of data:

- Lightweight, Scalable Agent: The IBM FinOps Agent has a streamlined footprint. By removing the dependency on in-cluster Prometheus and running as a single-container pod, it significantly reduces overhead. Memory usage is reduced and performance improved. Each pod focuses on data collection and periodic batch exports, which is efficient. The architecture’s modular design (with independent emitters) means you can enable/disable outputs as needed without affecting core data collection. If you have hundreds of clusters, you simply run one agent per cluster. The agents work in parallel, scaling horizontally. The data is aggregated on Cloudability’s side which is built on a big-data backend capable of ingesting millions of cost data points.

- Cloudability Backend Scale: IBM Cloudability (Apptio) is proven to handle very large cloud environments (it’s used by many Fortune 500 companies for cloud spend in the tens of millions). Container cost data is just another stream of data. The Container Insights backend stores usage samples for your clusters and merges with billing data. There are limits – e.g., extremely high-frequency data will be rolled up to hourly in reports – but typical Kubernetes usage (even thousands of pods) is handled by daily processing. If you integrate, say, 50 clusters, Cloudability will process each cluster’s uploaded file daily. The processing time might increase slightly, but it’s within the normal operations. Gartner has recognized Cloudability as a leader in FinOps tooling in part due to its scalability in multi-cloud, multi-team scenarios.

- Kubecost Performance: Kubecost 3.0 introduced a faster query engine using ClickHouse, which drastically improves the speed of fetching allocation and asset data. Tests showed significant speed improvements for cost queries in large environments. So if you have Kubecost’s UI deployed analyzing months of data, it should be able to handle it better than previous versions. Kubecost’s architecture supports federation for scale – you can designate one cluster as the primary aggregator that stores data from all others. In such setups, each agent sends data to a central object storage (S3, etc.), and the aggregator Kubecost reads from there. This allows practically unlimited cluster count scaling, since each agent’s load is only its own cluster and the aggregator does the heavy lifting for queries. Enterprises with 100+ clusters use this model.

- Resiliency: The new agent’s design (single container per pod) improves resiliency and debuggability. It’s easier to restart or scale out components if needed. The agent uses a PVC to recover from outages, as mentioned, which improves reliability in unstable network conditions. Cloudability’s upload mechanism is idempotent – if an upload fails, the agent will retry and Cloudability will not double count data as it keys by timestamp and cluster.

- Optimizing Interval: By default, the agent might collect data every 1 minute (configurable). In most cases this is fine – the data will be aggregated by hour/day in Cloudability anyway. If you find the agent is using too much CPU on large clusters, you can decrease collection frequency to, say, every 5 minutes. This will still capture granular data but with less overhead. Conversely, if you need more real-time data in Kubecost, you can keep it at 1 minute or even 30 seconds, but note that Cloudability will still mostly use the rolled-up data daily (Kubecost UI would benefit more from a shorter interval).

- Large Cluster Considerations: For clusters with thousands of nodes or tens of thousands of pods:

- Ensure etcd and the API server can handle the agent’s list/watch calls. The agent is efficient in pulling data (similar to what a metrics server or metrics agent does). If your cluster is at etcd limits, consider segmenting the workload or using multiple agents (not currently needed for one cluster – one agent should suffice, but you could deploy multiple in read-only mode for splitting work in theory).

- The volume of metrics might be high. The FinOps Agent focuses on the core metrics (CPU, memory, storage, network usage) relevant to cost. It is not pulling every single Prometheus metric. So even large clusters should be within manageable data sizes. For context, Kubecost’s open-source could handle ~10k pods per cluster with Prometheus – the new agent is more optimized, so similar or better scale is expected. IBM likely tested with large RedHat OpenShift clusters as part of expanding OpenShift monitoring.

- Multi-Cluster Scale: As you add more clusters, monitor Cloudability’s cost analytics performance . In the Cloudability UI, if you run a report across 50 clusters and 2 years of data with many dimensions, it might be heavy – use filtering and proper time ranges to keep queries reasonable. Cloudability’s API and UI allow up to certain limits in a single call (for example, retrieving data for 500,000 allocation rows might time out). Typically, breaking it by month or by environment is best. These are general best practices for Cloudability, not specific to Kubecost integration.

- High Availability: Cloudability is SaaS and highly available by design. For Kubecost, if you need HA, you can run multiple replicas of its API and use a persistent storage or an external ClickHouse to ensure failover. The FinOps agent itself is stateless except for the PVC cache; you can generally run one per cluster (running multiple concurrently in one cluster is not recommended as they’d duplicate data unless one is disabled for Cloudability emitter). If uptime is critical, ensure you monitor the agent’s pod via a daemon like Prometheus or Kubernetes liveness probes (the chart has liveness probes configured).

In summary, the integration is designed for enterprise scale . It leverages architectural improvements from Kubecost 3.0 to minimize footprint and uses Cloudability’s mature big-data processing for handling large cost datasets. Whether you have one big cluster or hundreds of clusters, the solution can be configured to meet the need. Just follow best practices (unique IDs, adequate resources, proper monitoring) and it should scale linearly.

Limitations

While the Cloudability–Kubecost integration is powerful, it’s important to be aware of its current limitations and nuances:

- Timing and Data Sync: As noted, Kubecost’s real-time data versus Cloudability’s billing data can lead to timing differences . The integration does not (yet) continuously stream data into Cloudability in real-time – data is uploaded periodically and processed in daily batches. This means Cloudability’s Container reports are updated roughly once per day. If you need up-to-the-hour data, you’ll use Kubecost’s UI or API. Cloudability is working toward more frequent updates, but for now consider it near-real-time (Kubecost) vs. financially reconciled (Cloudability). They serve slightly different purposes.

- Cost Discrepancies: Because of the above, perfect alignment at all times is not guaranteed. Small discrepancies (a few percent) can exist between Kubecost and Cloudability figures for the same time period due to things like:

- Cloudability including amortized costs (RIs/SPs) that Kubecost might not include unless configured.

- Kubecost using estimated pricing for some resources in real-time, which later gets corrected by actual billing data. For example, if a cloud provider applies tiered pricing or sustained use discounts, Kubecost’s upfront calculation might differ until the bill is reconciled.

- Currency conversion timing (if any) and tax or support fees – Cloudability might include account-level charges in total cost that Kubecost doesn’t distribute.

Important: The integration’s goal is to get close alignment. Over a full month, you should reconcile Kubecost’s allocated costs with 100% of your cloud bill (Kubecost Enterprise supports reconciliation with billing exports to achieve this). However, day-to-day, treat Kubecost as an operational view and Cloudability as the accounting view. Don’t expect them to match to the penny every day.

- On-Premises Cost Support: Cloudability does not natively support on-prem costs. The integration will upload whatever cost data Kubecost computes for on-prem clusters, but Cloudability might categorize it differently or not include it in certain aggregate views (since it’s not tied to a cloud vendor account). You might see those clusters under Containers with costs, but they won’t show up under cloud provider reports. Also, amortization or other cloud-specific calculations won’t apply. Essentially, it treats it as a custom cost. This is fine for showback, but not for official accounting. Be cautious using on-prem data in Cloudability – it’s as accurate as you input it, but there’s no external validation.

- Single-Cluster vs Multi-Cluster Kubecost: If you deploy Kubecost across multiple clusters with a central aggregator, note that Cloudability still treats each cluster individually. Cloudability doesn’t know which clusters belong to a group or which is primary/secondary. Any Kubecost federation is transparent to Cloudability. A limitation is that Cloudability’s UI doesn’t group clusters by federation. If you have dozens of clusters, Cloudability will list dozens of cluster entries. It’s up to you to group or filter them (e.g. by naming convention). There’s no concept of a “merged view” of multiple clusters in Cloudability except via selecting multiple in a filter. This is different from Kubecost’s UI where an aggregator can show a single combined view. Just be aware of this distinction.

- Feature Gaps in Cloudability UI: Not all Kubecost features are exposed in Cloudability’s UI. For example, Kubecost Alerts and Governance (budget alerts, etc.) are not configurable from Cloudability; you must use Kubecost’s interface for those. Cloudability focuses on cost reporting and has its own alerting at a higher level (like anomaly detection on overall spend). Similarly, savings recommendations in Cloudability might not be as granular as Kubecost’s. Cloudability has rightsizing recommendations for EC2 and some container rightsizing suggestions, but Kubecost’s are often more detailed for Kubernetes specifically. Over time, IBM may integrate these deeper, but currently expect to use Kubecost UI for detailed optimization and Cloudability mainly for visibility and tracking the outcomes.

- Write-Back/Automation Limitations: The integration currently is read-only with respect to your clusters – it pulls data but doesn’t make changes. Kubecost can be configured to take actions (like apply new resource requests or evict idle pods) but those aren’t triggered via Cloudability. If you want automation, you’ll need to use Kubecost’s APIs or Turbonomic. Cloudability’s Savings Automation module covers things like rightsizing VMs or buying RIs, but not Kubernetes actions (yet). So any optimization identified will need to be implemented via DevOps processes or Turbonomic. There’s no one-click “apply this rightsizing” in Cloudability’s container view.

- Multiple Cloudability Environments: If you have separate Cloudability environments (say one for Prod, one for Dev, or for different business units), note that the integration’s data is tied to one environment via the API key and env ID. If you accidentally use the same cluster ID in two different Cloudability environments, that data will not merge – it will be isolated per environment. Also, you should deploy separate agents (or configure separate API keys) if you intentionally want to send some cluster data to one environment and some to another. This scenario is uncommon, but just be mindful when managing environments and API keys.

- Legacy Agents Deprecation: If you were using the older Cloudability container agent (the open-source “metrics agent” from 2020 era), note that it’s being deprecated. The new FinOps Agent is not backward-compatible with the old agent’s data format. You should not run both on the same cluster – it will double count or cause conflicts. Remove any old metrics-agent DaemonSet/Deployment from your clusters when moving to the new integration. This also means some legacy Cloudability container features (like certain older dashboards) might be replaced by the new Container Insights. Refer to IBM’s migration notes if applicable.

- OpenCost vs Enterprise: The integration uses the OpenCost model (which Kubecost is based on) for cost calculations. The FinOps Agent supports OpenCost out of the box. One limitation to note is that OpenCost (and thus Kubecost Community) doesn’t include some advanced features like business mapping or chargeback formulas that Cloudability has. Cloudability allows mapping costs to custom dimensions (like mapping a Kubernetes label to a corporate cost center via its tagging logic). Those mappings need to be configured in Cloudability separately (for example, creating a Cloudability “Business Mapping” to map namespace names to department names). The integration won’t automatically apply such business mappings to Kubernetes data – you have to set them up just as you would for cloud tags.

- Support for Non-Kubernetes Container Platforms: This integration specifically targets Kubernetes. If you run containers outside K8s (ECS, etc.), those are handled by Cloudability through other means (e.g., ECS cost allocation via AWS CUR). Kubecost doesn’t cover ECS or other container services. So this integration is not applicable to non-Kubernetes environments.

- Future Changes: This is a new integration , and IBM is actively improving it. Features like more real-time Cloudability updates, deeper Turbonomic integration, or unified UIs are on the roadmap. As such, consider this initial release as the foundation – always check release notes for new capabilities or lifting of limitations. For example, Turbonomic emitter support in the agent is “planned” (not yet active). When that comes, you might need to update agent configs to take advantage.

- Known Issues: As of this writing, check IBM’s documentation for any known issues. For instance, there might be known edge cases like “cost for terminating pods might show up in ‘unallocated’ if they didn’t exist at period end” or “if a cluster ID is changed, historical data doesn’t merge” etc. Always review the latest docs for such notes.

In conclusion, be aware that while the integration greatly enhances Cloudability’s Kubernetes cost management, it is not a silver bullet for all scenarios. Use Cloudability and Kubecost in tandem to get the best results, and understand the boundary between the two. As long as you keep these limitations in mind, you can plan processes (e.g., end-of-month reconciliation using Cloudability, day-to-day monitoring using Kubecost) that make the most of both tools without confusion.

By following this guide, you should be able to successfully deploy and use the Cloudability Advanced Containers module. The result is a powerful, comprehensive FinOps solution that provides visibility and optimization across your entire cloud footprint – from core cloud services to the containerized applications running on Kubernetes. This integration helps bridge the gap between finance and engineering, ensuring everyone has the data they need to manage and optimize costs in today’s hybrid, Kubernetes-centric cloud environments.

---

## Container Costs Allocated By Vendor

<!-- sub-header -->
- **breadcrumb:** Insights > Container Cost Allocation > Container Costs Allocated By Vendor
- **source_path:** SSVCLNQ/product/container-costs-by-vendor.html
- **original_file:** allocation-container-costs-allocated-by-vendor.md
- **images:** []

## Container Costs Allocated By Vendor

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

---

## Container Insights: Threshold-based Alerting Configuration Guide

<!-- sub-header -->
- **breadcrumb:** Insights > Container Cost Allocation > Container Insights: Threshold-based Alerting Configuration Guide
- **source_path:** SSVCLNQ/product/container-insights-threshold-based-alerting-configuration-guide.html
- **original_file:** allocation-container-insights-threshold-based-alerting-configuration-guide.md
- **images:**
  - 03-media/apptio-cloudability-standard/threshold-based_alerting1.jpg
  - 03-media/apptio-cloudability-standard/threshold-based_alerting2.jpg
  - 03-media/apptio-cloudability-standard/threshold-based_alerting3.jpg
  - 03-media/apptio-cloudability-standard/threshold-based_alerting4.jpg
  - 03-media/apptio-cloudability-standard/threshold-based_alerting5.jpg

## Container Insights: Threshold-based Alerting Configuration Guide

Overview

Container Insights now supports threshold-based alerting that can be configured in two ways:

1. Directly through Dashboard Widgets
1. Through the dedicated Alerts tab

Configuration Methods

Method 1: Configure Through Dashboard Widgets

1. Navigate to the Container Insights dashboard
1. Click the horizontal ellipsis (⋯) on any widget
1. Select Create Alert from the dropdown menu
1. In the Alert Configuration template: Enter Alert name and description Set Query values Define Trigger and filter conditions Assign users for notifications Save the configuration

Method 2: Configure Through Alerts Page

1. Navigate to the Container Insights page
1. Click Alerts tab (located next to "Dashboard" and "Treemap" views)
1. Select Configuration sub-tab and then New Alert at the right end
1. In the Alert Configuration template: Enter Alert name and description Set Query values Define Trigger and filter conditions Assign users for notifications Save the configuration

Managing Alerts

- View all configured alerts under Alerts tab
- Access Configured Alerts sub-page to see the complete list
- Edit or delete existing alerts as needed
- Monitor alert status and history

Important Notes

- The maximum number of alerts per organization is 100
- Email is currently the only supported notification channel
- All users can create alerts for themselves
- Cloudability Admins can assign alerts to other users

For additional support or questions, contact our support team.

p

---

## Containers Insights: Dashboard and Widget Guide

<!-- sub-header -->
- **breadcrumb:** Insights > Container Cost Allocation > Containers Insights: Dashboard and Widget Guide
- **source_path:** SSVCLNQ/product/containers-insight-2-dashboard-widget-guide.html
- **original_file:** allocation-containers-insights-dashboard-widget-guide.md
- **images:**
  - 03-media/apptio-cloudability-standard/container_3.jpg
  - 03-media/apptio-cloudability-standard/container_4.jpg
  - 03-media/apptio-cloudability-standard/container_5.jpg
  - 03-media/apptio-cloudability-standard/container_6.jpg
  - 03-media/apptio-cloudability-standard/container_7.jpg
  - 03-media/apptio-cloudability-standard/container_8.jpg
  - 03-media/apptio-cloudability-standard/container_9.jpg
  - 03-media/apptio-cloudability-standard/container_10.jpg
  - 03-media/apptio-cloudability-standard/container_11.jpg
  - 03-media/apptio-cloudability-standard/container_12.jpg
  - 03-media/apptio-cloudability-standard/container_13.jpg
  - 03-media/apptio-cloudability-standard/container_14.jpg
  - 03-media/apptio-cloudability-standard/container_15.jpg
  - 03-media/apptio-cloudability-standard/container_16.jpg
  - 03-media/apptio-cloudability-standard/container_17.jpg

## Containers Insights: Dashboard and Widget Guide

Overview

Containers Insights provides a default dashboard to display a summary of cost and efficiency for all clusters. It also supports powerful customization of the dashboard. Custom widgets can be used to query rich datasets to reveal deeper insights into cost, utilization, and efficiency within Kubernetes, and OpenShift Clusters.

A dashboard appears by default. You can also create custom dashboards.

Default Dashboard

The default dashboard includes KPI widgets such as Total Cost, Idle Cost, and Efficiency Score. It also displays time series chart widgets, showing trends for the top 10 idle cost clusters, and total cost trends for the top 10 clusters. Any changes to the dashboard, such as adding or deleting widgets, updating the layout, or adjusting global filters, are automatically saved. Each user has his/ her own default dashboard that can be customized independently.

Custom Dashboard

Users can create custom dashboards by saving any existing dashboards available to them. The layout of the dashboard is structured with KPI widgets on the top, chart widgets in the middle, and a table widget at the bottom. Within each section (KPI, chart), the placement of the widgets can be adjusted. If a user deletes all dashboards, they will still receive the pre-configured built-in default dashboard. Any changes, including global filters and layout adjustments, are automatically saved.

There are several widgets that can be added to the dashboard.

Pre-Built KPI Widgets

There are four pre-built KPI widgets: Total Cost, Efficiency Score, Efficiency Score (Usage), and Idle Cost. These widgets are displayed on the default dashboard and can be added to any dashboard through the drop-down menu.

Custom KPI Widget

Users can add custom KPI widgets through the drop-down menu to add a "Custom KPI" widget.

Metric Type : Options include Total, CPU, Memory, GPU, Network TX, Network RX, FileSystem, and Persistent Volume. This shows the metrics for specific resource types.

Metric Summary : Options include Cost and Utilization. This indicates whether the KPI is based on cost metrics or utilization metrics.

Metric Allocation : Options include "Fair Share," "Allocated," "Idle," and "Efficiency." This shows whether the allocation is about fair share, allocated, idle, or efficiency of the metric type, and summary.

- Fair Share : Provisioned resources shared proportionally based on allocation among all tenants.
- Allocated : Resources allocated to a container; the larger of usage and request.
- Idle : Resources not allocated and fair shared among tenants; the difference between Fair Share and Allocated.
- Efficiency : Calculated as Allocated divided by Fair Share.

The combination of metric type, summary, and allocation determines the KPI to be created. Here are some examples:

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

These KPIs can be filtered by clusters, namespaces, workload, workload type, container, node, or label keys. Filters are combined with "AND" operations, and only the "equals" operator is allowed.

There are also several chart widgets that can be added to your dashboard .

Pre-Built Chart Widgets

There are four pre-built chart widgets:

- Efficiency for Top 10 Idle Cost Clusters
- Top 10 Costs by Clusters
- Top 10 Least Efficiency Score by Cluster
- Total Cost Trend

Custom Chart Widgets

- Custom Time Series: Displays trend information on the queried datasets, based on any combination of metric type, summary, and allocation. It can be grouped by combinations of cluster, namespace, workload, workload type, node, container, or label keys. It also allows ordering by top 10 or bottom 10.
- Custom Top/Bottom 10 Widget : Displays queried datasets in a specified order, supporting only vertical bar charts.
- Custom Allocated vs Idle : Displays queried datasets for allocated versus idle comparison, usable for both cost, and utilization metrics.

Customization and Layout

Users can easily customize the layout and content of their dashboards by adding, removing, and rearranging widgets. Each widget's settings and filters can be adjusted to meet specific analysis needs, providing a highly flexible and personalized visualization experience.

This guide covers the essential features and customization options available in the new Containers Insights. By utilizing these dashboards and widgets, users can gain deeper insights into their Kubernetes environments, optimizing cost, utilization, and efficiency.

---

## Provision Your Container Agent

<!-- sub-header -->
- **breadcrumb:** Insights > Container Cost Allocation > Provision Your Container Agent
- **source_path:** SSVCLNQ/product/container-metrics-agent-provisioning.html
- **original_file:** allocation-provision-your-container-agent.md
- **images:**
  - 03-media/apptio-cloudability-standard/container-ua-1.png
  - 03-media/apptio-cloudability-standard/container-ua-2.png
  - 03-media/apptio-cloudability-standard/container-ua-3.png
  - 03-media/apptio-cloudability-standard/container-ua-4.png
  - 03-media/apptio-cloudability-standard/container-ua-5.png
  - 03-media/apptio-cloudability-standard/container-ua-6.png
  - 03-media/apptio-cloudability-standard/container-ua-7.png
  - 03-media/apptio-cloudability-standard/container-ua-8.png
  - 03-media/apptio-cloudability-standard/container-ua-12.png
  - 03-media/apptio-cloudability-standard/container-ua-13.png
  - 03-media/apptio-cloudability-standard/container-ua-14.png
  - 03-media/apptio-cloudability-standard/container-ua-15.png
  - 03-media/apptio-cloudability-standard/container-ua-16.png
  - 03-media/apptio-cloudability-standard/conatiner-ua-19.png
  - 03-media/apptio-cloudability-standard/containers-metrics-agent-provisioning-2.jpg

## Provision Your Container Agent

Legacy Metrics Agent Migration

IBM Cloudability is migrating from the legacy container metrics agent to the new IBM FinOps Agent. The legacy metrics agent is being deprecated and will reach end of functionality on November 19, 2026. Follow the instructions below for migration guidance.

Overview

In order to gather the data we need to perform allocation for a given cluster, you will need to deploy the IBM FinOps Agent, the next-generation data collection agent for Cloudability Containers. In order to get container optimization recommendations, you will need to deploy the Turbonomic kubeturbo agent to each cluster you want to report on.

This is achieved through a HELM deployment provisioned for each cluster. These HELM commands can be generated by following these steps:

Provision Cloudability Metrics Agent

1. Navigate to Insights > Containers .
1. Select the Provision Clusters button.
1. Fill out the form with your cluster name and either your Kubernetes version or your OpenShift version.
1. 4. Click Next -> Generate Command .

Cluster data should show up in Cloudability the following day. If you run into any issues with the deployment, contact Apptio support.

Google Kubernetes Engine (GKE)-specific instructions

You need to add a cluster label in each cluster as follows:

- key: gke-cluster
- value: The cluster name(s) you set in the form/YAML. This allows Cloudability to map GKE clusters to line items in the GCP billing file, and allocate costs to your clusters.

Cloudability will need to ingest a billing file with the cluster labels you added, which can take up to 48 hours. Once Apptio has processed the new billing file, you need to create a new tag mapping in the Cloudability application. Set a Cloudability Dimension as gke-cluster and map this to the gke-cluster tag. This is a one time need, not per cluster.

Ensure that your account has cluster-admin role before deploying the Metrics agent. By default, a user account does not have the cluster-admin role. Use the following command on the GKE cluster to grant a user the cluster-admin role:

```
"kubectl create clusterrolebinding username-cluster-admin-binding --
clusterrole=cluster-admin --user=username@emailaddress.com"
```

Deploy the agent

Prerequisites:

Networking Requirements:

In the Cloudability metrics-agent the networking requirements were documented in the README .

The unified agent has updated networking requirements in order to function properly and upload data to Cloudability’s S3.

The new Networking requirements for the agent are as follows:

Storage Requirements:

The IBM-Finops-Agent optionally supports a configurable persistent volume (PV) (default 8Gi). The PV should be used in environments where the network to the Kubecost object-store or Cloudability API is regularly disconnected. This is unlikely in the majority of environments. With the volume enabled, the agent will store samples on this volume and will attempt to recover any samples after a restart. This improvement vastly improves the agent’s ability to recover data in failure scenarios.

Container Registry change:

The IBM-Finops-Agent is not stored in docker like the existing metrics-agent. Instead the IBM-Finops-Agent is stored in ICR. So you may need to update your container registry whitelisting to allow the IBM-Finops-Agent deployment to pull the ICR image. The IBM-Finops-Agent container registry is:

```
icr.io/ibm-finops/agent:vx.x.x
```

If you need to pull the image locally to copy to your container registry. You can run the following docker/podman pull command:

```
 podman pull icr.io/ibm-finops/agent:v0.0.25 --platform=linux/amd64
```

Authentication:

It is important to call out that the Cloudability metrics-agent used a Containers specific API key. The IBM finops agent will no longer use/support this api key . Instead customers need to create an API key for the agent in Frontdoor and gather their Frontdoor Environment ID .

Creating User to manage container API key:

It is required that your Frontdoor environment has api keys enabled on it for the Containers Feature to work

It is recommended that customers create a containers specific service user within their own domain to manage their api key going forward. This way, the uploading api key is not associated with one specific user that may be deactivated in the future. The person creating the new user and api key needs to be an admin user in their Frontdoor environment.

1. Navigate to “Access Wizard” in “Access Administration”, select “Add User(s)”, set “Customer” and “Environment”. Finally, hit “Confirm”
1. Enter user information and hit “Next”
1. Select “Grant Role(s)”, “Do not send User an activation Email” and hit “Confirm” to create the user
1. Ensure user is selected for granting roles
1. Grant the “CloudabilityContainerUploader” Role to the user and hit “Next”/”Confirm”. Creating User to manage container API key:
1. Navigate to “Home”, search for the newly created user, and click on their “Username”
1. Hit “View User Profile”
1. Add an api key for the user
1. Enter a name for the API key (ex: IBM-Finops-agent), set “No Expiration” if not already set, and hit confirm.
1. Store the API Key Credentials ( Public Key and Private Key ) for later to be used in the helm installation of the agent.
1. Hit “Grant Access”
1. Select your environment and hit “Next”
1. Add the “CloudabilityContainerUploader” role to the key and hit “Next”. This role has limited access to on the containers uploading endpoint.
1. Check that your key has been created and has the correct Role

Gathering Frontdoor Environment ID

1. Navigate to Frontdoor
1. In the top right select the Profile logo and click on “User Account”
1. Navigate to the Environment Access tab
1. Gather the environment ID under the Environment tab in the table Ensuring the environment is the same as what you use to access Cloudability Example id format: xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx

Deploying the metrics-agent With Helm

Prerequisites:

- Install Helm must be installed to use the charts. Refer to Helm’s documentation to get started.
- Update Cluster’s Networking policies to allow for new Networking Requirements (if necessary)
- Gather API Public and Private Keys
- Gather Frontdoor Environment ID

Once Helm has been set up correctly, Add the repo as follows:

```
helm repo add ibm-finops https://kubecost.github.io/finops-agent-chart
```

If you had already added this repo earlier, Update it:

```
helm repo update
```

Install Helm Repo

```
helm install ibm-finops-agent ibm-finops/finops-agent \   
--set agent.cloudability.enabled=true \
--set agent.cloudability.uploadRegion=<uploadRegion> \      
--set agent.cloudability.parseMetricData=false \
--set agent.cloudability.secret.create=true \
--set agent.cloudability.secret.cloudabilityAccessKey='<AccessKey>' \
--set agent.cloudability.secret.cloudabilitySecretKey='<SecretKey>' \
--set agent.cloudability.secret.cloudabilityEnvId='<EnvID>' \
--set clusterId='<ClusterName> \
--create-namespace -n ibm-finops-agent
```

To Uninstall Helm Repo:

```
helm uninstall ibm-finops-agent
```

If your cluster is currently running the old Cloudability metrics-agent, feel free to keep that running until you see the new ibm-finops-agent start uploading successfully for 24 hours. The ibm-finops-agent can be installed and run in parallel to the Cloudability metrics-agent but it is recommended to spin down the Cloudability metrics-agent once the new agent is stable in your cluster.

UploadRegion depends on what region the customer’s Cloudability environment exists in. The supported values are below

- US: us (or us-west-2)
- EU: eu (or eu-central-1)
- AU: au (or ap-southeast-2)
- ME: me (or me-central-1)
- Hybrid EU (customers who have EU frontdoor but upload containers data to the US region) : hybrid-eu
- Hybrid AU (customers who have AU frontdoor but upload containers data to the US region): hybrid-au
- Hybrid ME (customers who have ME frontdoor but upload containers data to the US region) : hybrid-me

ClusterName should be the same value as what is currently in the metrics-agent CLOUDABILITY_CLUSTER_NAME to prevent any cost ingestion issues .

The unified agent supports many of the same configurations as the outgoing Cloudability metrics-agent. If your existing metrics-agent has any specific configurations (for example PROXY configurations) please check out the helm supported parameters here .

You can add these to your install command for example:

```
helm install ibm-finops-agent ibm-finops/finops-agent \   
--set agent.cloudability.enabled=true \
--set agent.cloudability.uploadRegion=<uploadRegion> \      
--set agent.cloudability.parseMetricData=false \
--set agent.cloudability.secret.create=true \
--set agent.cloudability.secret.cloudabilityAccessKey="<PublicKey>" \
--set agent.cloudability.secret.cloudabilitySecretKey="<PrivateKey>" \
--set agent.cloudability.secret.cloudabilityEnvId="<FDEnvID>" \
--set agent.cloudability.outboundProxy="http://x.x.x.x:8080" \
--set agent.cloudability.parseMetricsData="true"
--set clusterId="<ClusterName>" \
--create-namespace -n ibm-finops-agent
```

1. Ensure the ibm-finops-agent pod is running kubectl get pods -n ibm-finops-agent ### Example Output Below ### NAME READY STATUS RESTARTS AGE ibm-finops-agent-7bbf99d9fb-kmhh9 1/1 Running 0 1m
1. Check the pods logs in order to confirm the agent is successfully uploading data to Cloudability. It will take 10 minutes in order to see the first successful upload log. kubectl logs <POD_NAME> -n ibm-finops-agent ### Example Output Below ### INF Starting IBM Finops Agent... DBG HTTP server started on port 9003 INF Initializing cldy emitter INF emitting sample to Cldy 0 INF added sample to Cldy INF emitting sample to Cldy 1 INF added sample to Cldy INF emitting sample to Cldy 2 INF added sample to Cldy INF Attempt 1: performing login request to FrontDoor using KeyAccess and KeySecret INF Attempt 1: acquiring presigned URL from Cloudability with acquired Open-token INF Attempt 1: uploading sample to Cloudability S3 using presigned URL INF successfully uploaded metric sample xxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx_xxxx-xx-xx-xx-xx-xx.tgz to cloudability

Once again, it will take 10 minutes for the log “successfully uploaded metric sample to cloudability” to appear. This is a common point of failure in agent’s if they do not have the correct whitelisting/proxy settings enabled.

After 24 hours of the ibm-finops-agent running and uploading successfully. If you are still running a Cloudability metrics-agent deployment, you may now tear down that infrastructure and keep only the ibm-finops-agent helm chart running.

Provision Cloudability Container Optimization ( Turbonomic kubeturbo) Agent

1. Navigate to Insights > Containers .
1. Select the Provision Clusters button.
1. Fill out the form with your cluster name and either your Kubernetes version or your OpenShift version.
1. Select Generate Agent Script under the section Container optimization Agent .

Cluster data should show up in Cloudability the following day. If you run into any issues with the deployment, contact Apptio support.

Installation Steps

Once the script is downloaded, copy it to the location where you want to run it from, in an environment where you are connected to the destination cluster where you want the agent deployed.

Run the command using the example below:

```
chmod +x new-js-aks.sh &&./new-js-aks.sh
```

The summary for the installation is as below.

```

Parameter            Value
---------            ---------
Mode                 Create/Update
Kubeconfig           default
Host                 https://20.116.237.9
Namespace            turbo
Target Name          new-js-aks
Target Subtype       Kubernetes
Role                 turbo-cluster-admin
Version              8.14.5
Auto-Update          false
Auto-Logging         false
Proxy Server         false
Private Registry     false
```

Please confirm the above settings [Y/n]: Y

Your current Kubernetes context is set to the following.

```
NAME                     CLUSTER                  AUTHINFO                                                NAMESPACE
concise-lobster-aks      concise-lobster-aks      clusterUser_concise-lobster-rg_concise-lobster-aks           
```

Please confirm if the script should work in the above cluster [Y/n]: Y

```

Creating turbo namespace to deploy Kubeturbo operator
namespace/turbo created
secret/turbonomic-credentials created
% Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
Dload  Upload   Total   Spent    Left  Speed
100  159k  100  159k    0     0   920k      0 --:--:-- --:--:-- --:--:--  923k

customresourcedefinition.apiextensions.k8s.io/kubeturbos.charts.helm.k8s.io unchanged
serviceaccount/kubeturbo-operator created
clusterrole.rbac.authorization.k8s.io/kubeturbo-operator unchanged
Skip patching ClusterRoleBinding kubeturbo-operator as the clusterRole has bound to the operator service account already.
deployment.apps/kubeturbo-operator created
namespace/turbo configured
Waiting for deployment 'kubeturbo-operator' to start...
Resource is not ready, re-attempt after 10s ... (1/10)
pod/kubeturbo-operator-857855c6b5-d9x2c condition met
apply Kubeturbo CR ...
kubeturbo.charts.helm.k8s.io/kubeturbo-release created
Waiting for deployment 'kubeturbo-release' to start...
Resource is not ready, re-attempt after 10s ... (1/10)
pod/kubeturbo-release-7d499cf568-cg5sm condition met
Successfully apply Kubeturbo in turbo namespace!

NAME                                SECRETS   AGE
serviceaccount/kubeturbo-operator   0         32s
serviceaccount/turbo-user           0         12s

NAME                                     READY   STATUS    RESTARTS   AGE
pod/kubeturbo-release-7d499cf568-cg5sm   1/1     Running   0          12s

NAME                                 READY   UP-TO-DATE   AVAILABLE   AGE
deployment.apps/kubeturbo-operator   1/1     1            1           30s
deployment.apps/kubeturbo-release    1/1     1            1           12s

NAME                                       DATA   AGE
configmap/turbo-config-kubeturbo-release   2      12s
Done!
```

Run the command below to verify the 2 pods are running, as shown in the example below:

```
kubectl get pods -n turbo
```

```
NAME                                  READY   STATUS    RESTARTS   AGE 
kubeturbo-operator-857855c6b5-d9x2c   1/1     Running   0          105s 
kubeturbo-release-7d499cf568-cg5sm    1/1     Running   0          87s
```

The following image illustrates the Installation.

---

## Shared Cost Allocation - Container Insights UI

<!-- sub-header -->
- **breadcrumb:** Insights > Container Cost Allocation > Shared Cost Allocation - Container Insights UI
- **source_path:** SSVCLNQ/product/shared-cost-allocation-container-insights-ui.html
- **original_file:** allocation-shared-cost-container-insights-ui.md
- **images:**
  - 03-media/apptio-cloudability-standard/container_cost_allocation.jpg
  - 03-media/apptio-cloudability-standard/shared_rules.jpg
  - 03-media/apptio-cloudability-standard/shared_rules1.jpg
  - 03-media/apptio-cloudability-standard/namespace.jpg

## Shared Cost Allocation - Container Insights UI

We are introducing a new container cost allocation feature that transforms how shared infrastructure expenses are tracked in Kubernetes environments. This feature enables customers to annotate and allocate shared infrastructure costs, such as system proxies, monitoring tools, and other operational resources, to specific application owners or cost centers.

Previously, these shared infrastructure costs were indistinguishably reported as standard workload expenses. Now, organizations can precisely tag and distribute these operational costs, providing application teams and financial managers with a more transparent, granular view of their true total infrastructure expenditure.

To start, this capability supports allocating shared costs at the Kubernetes namespace level. We'll be looking to expand support to additional Kubernetes constructs in the future.

### Key Capabilities

Automated Shared Cost Identification

- Automatically recognizes shared infrastructure costs from predefined namespaces: kube-system Cloudability

- Applied consistently across all clusters

Flexible Administrative Controls

- Cloudability administrators can: Define shared infrastructure cost rules for applicable namespaces Configure organization-level or cluster-specific cost allocations Precisely target infrastructure-related workloads (namespaces) and the effective date for the rules to apply

New Cost Metrics

- New cost metrics have been introduced in the Container Insights UI to provide visibility into the allocated shared costs, including Shared Cost as well as resource-specific Network Shared , Memory Shared , CPU Shared , GPU Shared and others. This Shared Cost metric reflects the total cost, including allocated shared costs, after shared rules are applied.

Shared costs will only be calculated starting from the feature release date. Queries including dates before the release date will return empty results in the Shared Cost column.

How to Configure Manage Share Rules

To configure shared cost allocation, use Manage Share Rules in the Container Insights interface to define how shared costs should be distributed across Kubernetes namespaces.

1. Navigate to the Container Cost Allocation UI.
1. Locate the ellipsis menu (...) in the upper-right corner, next to the Provision Clusters button.
1. Click the ellipsis to open a dropdown menu.
1. From the dropdown, select Manage Share Rules .
1. Configure Rules and provide the Effective Date .
1. Select All Clusters for organization-level configuration or choose a specific cluster from the dropdown for cluster-level configuration. Then, specify the namespace values to allocate the shared costs.
1. Save changes.

The Shared Cost metric provides enhanced visibility into the total costs for your Kubernetes namespaces, including allocated shared costs. Once shared cost rules are applied, the Shared Cost column reflects the combined cost, distributing shared resources proportionally across the selected namespaces.

This feature ensures greater accuracy in cost allocation for showback and chargeback processes, helping you account for shared infrastructure and resource usage effectively.

### Customer Awareness: Known Behaviors and Clarifications

To ensure a smooth experience, please note the following:

- Future-Dated Rules Only Rules for shared cost allocation can only be created, updated, or deleted for future dates (in UTC). Changes will not apply retroactively to historical data.

- Effective Dates for Rule Updates and Deletions Rule updates or deletions do not take effect immediately. Instead, a new scheduled rule with the updated or empty value will be created, taking effect on the scheduled date.

- Union Relationship for Multiple Rules When multiple rules are applied, they work as a union. Example: If an All Clusters rule includes namespaces A and B, and a rule for cluster-foo includes namespace C, then all three namespaces (A, B, C) will be treated as shared costs for cluster-foo .

- Empty Shared Cost Before Feature Release Date If a query includes dates prior to the release date, the Shared Cost column will be empty, as shared costs are not calculated retroactively.
- Shared namespace reflecting non-zero shared cost amount If you're seeing non-zero shared cost for a given shared namespace like kube-system , it is likely due to the namespace existing on a node that does not have any non-shared application workloads (namespaces). This will result in the fair share cost being reflected as the shared cost for this namespace, because there are no "normal" workloads to share the cost with on the node.

---

## VM family-based weightings

<!-- sub-header -->
- **breadcrumb:** Insights > Container Cost Allocation > VM family-based weightings
- **source_path:** SSVCLNQ/product/instance-type-weighting-container-cost.html
- **original_file:** allocation-vm-family-based-weightings.md
- **images:** []

## VM family-based weightings

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

VM hourly rate = vCPU count * vCPU rate + memory * memory rate

If we can work out the vCPU rate and the memory rate, then it’s possible to establish the ratio (i.e., weightings) for any VM family. While there are two unknown variables (the rates), we can solve these by having two separate equations – one for the target VM family and one for a “base” VM family.

It is worth discussing briefly how a base VM family is picked. The first thing to note is that the base VM will belong to the same processor manufacturer, whether that is AMD, Intel, or graviton. We will also prioritize a VM family from the same generation. For example, if the target is c6i, the base VM family used will likely be either m6i or r6i.

Having resolved the vCPU rate and memory rate for each VM family it is straightforward to calculate the weightings – multiplying the amount of vCPU and memory by their rates, then establishing the ratio between CPU and memory cost. Note, due to how the vendors bill their VMs, that these ratios are consistent at the family level.

What does that mean for your cost allocation?

- Cluster level cost figures are not impacted. This change only applies to Namespaces and Labels.
- The standard weightings used previously skewed allocation towards memory usage. With this release, it is now completely dependent on how the vendor charges for the specific VM family, but overall, this has shifted the weightings back towards CPU usage.
- This change has been made to both the values found in the Container Cost Allocation feature and to the Namespace and label dimensions within core reporting.
- This enhancement applies to both Kubernetes and ROSA clusters

---
