---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Common Kubernetes Metrics Agent - Error Messages"
breadcrumb:
  - "Getting data into Cloudability"
  - "Kubernetes Cluster Provisioning"
  - "Common Kubernetes Metrics Agent - Error Messages"
source_path: "SSVCLNQ/product/k8s-metrics-agent.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Common Kubernetes Metrics Agent - Error Messages

Overview

During operation, the Cloudability Metrics Agent may log specific error messages. This article details how to review error message logs, common error messages and possible solutions.

Reviewing error message logs

1. From the command line, run the following command to view a list of all Metrics Agent pods available on a cluster. kubectl get pods -n cloudability
1. Run the following command to view the error message log of a specific Metrics Agent pod. Replace <pod-name> with the name of the Metrics Agent pod discovered in the previous step. kubectl logs <pod-name> -n cloudability

Exported metric sample <cluster_UID>_<timestamp> to cloudability

Error messages

| Error message | Solution |
| --- | --- |
| Warning non-fatal error: Agent error occurred retrieving runtime diagnostics: <detailed message> | RBAC role in the Cloudability namespace may need to be updated. Re-provision the metrics agent for this cluster as detailed in Kubernetes cluster provisioning . |
| error sending metrics: Error retrieving upload URI: 403 | Current Cloudability API key in use is not valid. The API key may be incorrect or may have expired. If it has expired, the API key needs to be re-enabled before re-provisioning the metrics agent as detailed in Kubernetes cluster provisioning . Contact support to re-enable expired API keys. If the API Key is incorrect, re-generate the API key by following the provisioning steps as detailed in Kubernetes cluster provisioning. |
| error sending metrics: Error retrieving upload URI: <detailed message> | Network transport issues are potentially blocking the agent from contacting the metrics collection API. This error may be caused by cluster security configurations or proxies set up in customer Kubernetes containers. These configurations are managed by the cluster administrators. Please contact your Kubernetes cluster administrators to confirm that the Metrics Agent can establish a connection to: https://metrics-collector.cloudability.com |
| Warning non-fatal error: Agent error occurred retrieving node source metrics: Unable to retrieve node metrics. Please verify RBAC roles: | RBAC role in the Cloudability namespace may need to be updated. Re-provision the metrics agent for this cluster as detailed Kubernetes cluster provisioning . |
| Fargate node found in cluster, direct node connection disabled. | Direct connection to an AWS Fargate node is not possible, so when a Fargate node is detected in the cluster, the agent switches to using kube-proxy for all node connections in the cluster. The allocation of EKS Fargate tasks are not currently supported via the containers feature dashboard. Contact your technical account manager for instructions on how to access EKS Fargate information via the reporting feature. |

For direct support for issues with the Cloudability Metrics Agent, contact Support .
