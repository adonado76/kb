---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Agent Observatory Tool"
breadcrumb:
  - "Insights"
  - "Container Cost Allocation"
  - "Agent Observatory Tool"
source_path: "SSVCLNQ/product/agent-observatory-tool.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Agent Observatory Tool

## Overview

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

## Recommended Actions

- Check for Inactive agents: Filter by Inactive status to find clusters not reporting data, investigate connections, version, and configuration issues. A cluster is marked Inactive if the Last Seen value is greater than 12 hours.
- Monitor Agent Versions: Ensure all clusters are running the latest agent version for compatibility, new features, and security improvements.
- Review duplicate Cluster Names: If you see a warning icon, update unique cluster names for accurate reporting.
- Track data freshness: Use the Last Seen column to ensure data is recent. Agents not reporting for more than 24 hours should be reviewed.
