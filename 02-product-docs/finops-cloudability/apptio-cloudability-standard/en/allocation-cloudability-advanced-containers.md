---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Cloudability Advanced Containers"
breadcrumb:
  - "Insights"
  - "Container Cost Allocation"
  - "Cloudability Advanced Containers"
source_path: "SSVCLNQ/product/advanced-containers.html"
images:
  - "03-media/apptio-cloudability-standard/UA-arch.png"
  - "03-media/apptio-cloudability-standard/prov_clust.png"
  - "03-media/apptio-cloudability-standard/prov2.png"
  - "03-media/apptio-cloudability-standard/adv1.png"
  - "03-media/apptio-cloudability-standard/adv2.png"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Cloudability Advanced Containers

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
