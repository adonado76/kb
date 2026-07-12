---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "technology-integration"
title: "Data Payload"
breadcrumb: []
source_path: "technology-integration/data-uploaded.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Data Payload

As described in the prerequisites, the data flow initiates in IBM Turbonomic. Once the IBM Apptio Target Type is configured, the data, including Turbo Pending and Turbo Executed Actions, is transferred to IBM Apptio's Datadrop. From there, Datalink Connectors transmit the data to IBM Apptio’s TBM Studio for further processing.

The following four files will be loaded

- Turbo On Prem Pending Actions
- Turbo On Prem Executed Actions
- Turbo Cloud Pending Actions
- Turbo Cloud Executed Actions

The files are distinguished by two key dimensions:

- **Action State**  : Either PENDING or EXECUTED.
- **Delivery**  : Either CLOUD or ON-PREM.

The key distinction lies in the data being transmitted. For CLOUD, only aggregated data is sent, which includes 14 columns, in contrast to the 25 columns sent for On-Prem data. The primary reasons for this difference in granularity are as follows:

- On-Prem data is quantified using the IBM Apptio model and data, as IBM Turbonomic does not
  provide financial details for On-Prem environments. To perform these calculations, a higher level of
  granularity is required, which is why detailed columns, such as Entity Id and Action Id, are
  included. In contrast, Cloud data already comes with pre-calculated $ Savings, as determined by IBM
  Turbonomic, eliminating the need for such granular details.
- IBM Apptio is not designed to store granular Cloud data—that's the purpose of the Cloudability
  product. Similar to how CSP Cloud Bills are ingested without including the most detailed information
  (e.g., Resource Id), this integration also avoids sending granular Cloud optimization data.

The sets of 25 columns for On-Prem data and 14 columns for Cloud data were carefully selected through a collaborative effort between IBM Apptio and IBM Turbonomic. This exercise focused on identifying the most important columns that would be valuable for both modeling and reporting in the integration.

**Parent topic:** [Costing Standard](../home.html)
