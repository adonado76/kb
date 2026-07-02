---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "DataLink Connections"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Data Studio Reference"
source_path: "studio/new-uc/reference/datalink-connections.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# DataLink Connections

## DataLink Overview

DataLink provides connectivity between TBM Studio and external systems for both data ingress
(import) and egress (export).

**Connection Types:**

|  |  |  |
| --- | --- | --- |
| **Type** | **Direction** | **Description** |
| Ingress | External to TBM Studio | Import data from external systems |
| Egress | TBM Studio to External | Export data to external systems |

## ServiceNow Integration

**Purpose:** Push Total Cost of Ownership (TCO) data to ServiceNow

**Compatible ServiceNow Versions:** Quebec, Paris, Orlando

**Setup Steps:**

1. Install Apps & Services TCO app on ServiceNow platform
2. Set up TCO reports in TBM Studio

1. Configure DataLink egress connector

**Authentication Options:**

|  |  |  |
| --- | --- | --- |
| **Type** | **Agent Support** | **Notes** |
| Basic | Cloud and On-premise | Username and password |
| OAuth 2.0 | Cloud only | Requires client ID and secret from ServiceNow |

**Parent topic:** [Data Studio Reference](../../../studio/new-uc/reference/data-studio-reference.html)
