---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Configure Enterprise Discount Program for AWS"
breadcrumb:
  - "Technical Support"
  - "Custom Discounts and Enterprise Discount Programs (EDP)"
  - "Configure Enterprise Discount Program for AWS"
source_path: "SSVCLNQ/chatbot/edp-request.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Configure Enterprise Discount Program for AWS

When a customer negotiates an Enterprise Discount Program (EDP) with AWS, both contractually agree upon discounts. Cloudability implements the same discounts at the resource level as well as in real time. AWS only shows these discounts at the end of the month.

Configuring custom pricing is not suitable for a customer with Automated Discount Program (ADP) deployed by AWS already.

Before submitting a request for EDP, answer the following in the AWS Private Pricing PDF form:

| Question | Description |
| --- | --- |
| Discount Term | Start and end of EDP |
| Contract Year | Defines when contract starts/stops (dates) |
| Eligible Payer Accounts | Lists payer account that EDP applies to |
| Credits Account | Lists accounts for credits |
| Cross Service Discount | Discount that applies when service specific discounts are not listed |
| Service Specific Discount | List specific AWS Services that receive discount different than Cross Service Discount |
| Service Specific Rates | List specific AWS Services that receive a specific rate rather than discount |
| Discount | Specifies which discounts apply (cross service, Service specific discount, service specific rate) |
| Service specific regions | Specifies which regions receive service specific discounts/rates |
| Spend Commitment | Good information - specifies what level of commitment they need to spend to hit discounts - not something we can programmatically use |

The EDP process takes some time to complete.

The Apptio support team can also investigate specific slowdowns in your environment with the help of HAR files. To learn how to collect a HAR file, visit the Apptio Community page.
