---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "product"
title: "Connect IBM Cloud"
breadcrumb:
  - "Cloudability Premium"
  - "Getting data into Cloudability"
source_path: "product/apptio_help_center_ibm_cloud.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Connect IBM Cloud

You can connect your IBM Cloud accounts to Cloudability to enable the ingestion of cost and
usage data. Cloudability supports both Enterprise and Standard account data ingestion. An **IBM
Cloud Standard Account** is simply a single stand-alone account for one organization or user, with
its own billing and access management. An **[Enterprise Account](https://cloud.ibm.com/docs/enterprise-management?topic=enterprise-management-what-is-enterprise "(Opens in a new tab or window)")** is a top-level parent account that
serves as a central hub to manage a hierarchy of multiple individual child accounts and account groups.

Note:

It takes 4 to 24 hours before your initial cost and usage data appears in Cloudability. This
depends on how long it takes IBM Cloud to generate your first billing reports.

**Two ways to connect**

There are two methods to connect your IBM Cloud accounts to Cloudability :

1. Cloudability method: A Terraform script is provided for credentialing which would be API-key
   based.
2. Deployable Architecture (DA) app method: IBM Cloud supports a Deployable Architecture (DA) app
   called 'IBM Cloudability Enablement', using which you can credential your IBM Cloud account in
   Cloudability. This is the preferred method for credentialing IBM Cloud accounts as the app helps
   speed up the process.

- **[Setup IBM Cloud Credentials using Cloudability Method](../product/setup_ibm_cloud_credentials_using_cldy_method.html)**
- **[Setup IBM Cloud Credentials using Deployable Architecture (DA) App](../product/setup_ibm_cloud_credentials_using_da_method.html)**
