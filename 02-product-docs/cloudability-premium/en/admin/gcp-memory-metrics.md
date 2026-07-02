---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "admin"
title: "Set up GCP Monitoring Agent for rightsizing"
breadcrumb:
  - "Cloudability Premium"
  - "Getting data into Cloudability"
  - "Connect Google Cloud"
source_path: "admin/gcp-memory-metrics.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Set up GCP Monitoring Agent for rightsizing

In order for Cloudability to utilize additional utilization
metrics such as memory, you will need to configure the GCP Monitoring Agent. Cloudability supports both the Ops Agent and the Legacy Monitoring
Agent. The following instructions detail ways on how to configure each agent:

1. Prerequisites

   To install the agent, ensure that all conditions are met.

   [Installing the Ops Agent on individual VMs](https://cloud.google.com/monitoring/agent/monitoring/installation#before_you_begin "(Opens in a new tab or window)")

   [Installing the Legacy Cloud Monitoring agent on individual VMs](https://cloud.google.com/monitoring/agent/monitoring/installation#before_you_begin "(Opens in a new tab or window)")
2. Install the agent using the command line

   To install the agent using the command line, use
   the following instructions.

   [Installing the Ops Agent using the command line](https://cloud.google.com/monitoring/agent/monitoring/installation#joint-install "(Opens in a new tab or window)")

   [Installing the Legacy agent using the command line](https://cloud.google.com/monitoring/agent/monitoring/installation#joint-install "(Opens in a new tab or window)")
3. Install the agent using the Google Cloud console

   You can install the agent on one or more
   Compute Engine VMs from the pre-configured Monitoring VM Instances dashboard.

   [Installing the Ops Agent using the Google Cloud Console](https://cloud.google.com/monitoring/agent/monitoring/installation#gce-ui-install "(Opens in a new tab or window)")

   [Installing the Legacy agent using the Google Cloud Console](https://cloud.google.com/monitoring/agent/monitoring/installation#gce-ui-install "(Opens in a new tab or window)")

**Parent topic:** [Connect Google Cloud](../admin/connect-google-cloud-premium.html)
