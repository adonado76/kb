---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Amazon Web Services configuration"
breadcrumb: []
source_path: "cost-transparency/configuration/awsreserved.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Amazon Web Services configuration

To configure the application for Amazon Web Services, you must install the CTF-Cloud
Service and CTF-Amazon Web Services components.

## About this task

When you install the CTF-Amazon Web Services component, it adds two data sets to the Cloud
Service Provider group:

- AWS Cost Allocation Bill Master Data: used to map the billing data you upload.
- AWS RI Purchases Master Data: used to map reserved instances data.

The component does not add an object to the cost model and it does not add any new
reports.

There are eight steps to configure the application for Amazon Web
Services.

## Step 1: Install the CTF - Cloud component

Install the Cloud component the same way you install the other CTF
components:

### Procedure

1. Open the Costing Standard project.
2. Click the Projects tab.
3. Click on Components.
4. Click the CTF - Cloud Service component.
5. Click Install.
