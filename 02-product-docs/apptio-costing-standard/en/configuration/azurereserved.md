---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "configuration"
title: "Azure Reserved Instances — Ingestion and Cost Allocations"
breadcrumb: []
source_path: "configuration/azurereserved.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Azure Reserved Instances — Ingestion and Cost Allocations

Microsoft Azure released Reserved Instances (RIs) in late 2017. The costs associated with
these RIs can be considerable and will need to be accounted for when considering your Azure spend.

Applies to: Cloud Cost Management on TBM Studio 12.5+.

**Parent topic:** [Costing Standard](../home.html)

## Overview

Currently, RI charges are not reflected in the Azure EA bill and need to be ingested separately
and then allocated to the appropriate resources (VMs) such that the effective costs of those VMs are
appropriately calculated.

This guide provides the steps necessary to ingest your organization’s RI charges and accurately
allocate those charges to the appropriate resources in your Azure EA bill.

Implications in Adaption:

- Access Reserved Instance charges — RI costs are not reflected in the Azure EA bill and will need
  to be brought into Apptio via a Datalink (Classic) REST connector.
- Amortization and allocation of Reserved Instance costs — RI costs will need to be amortized over
  the term of the RI and then allocated to the resources in the bill that benefit from those RI
  purchases.
