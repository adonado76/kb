---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Configuring Cloud for Costing Standard 12.6"
breadcrumb: []
source_path: "cost-transparency/configuration/ctconfig12_6.html"
images:
  - "resources/images/ct_images/10550_1.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Configuring Cloud for Costing Standard 12.6

Apptio empowers IT leaders to proactively manage and optimize public cloud consumption
and make more informed decisions about cloud usage and purchasing with real-time analytics to
monitor spending and other associated costs like labor and support.

Applies to: Costing Standard on TBM Studio 12.6 and later, with Template v106 and later.

**NOTE**: For instructions that apply to versions of Costing Standard previous to 12.6, see
[Configuring Cloud for Costing Standard 12.1 through 12.5x](cloudservices-12-5.html "Use the CTF - Cloud Service Provider component to import usage data from web services. The component is optional.").

## Before you begin

For cloud costs to be correctly calculated, vendor data must be entered into the Costing Standard
application. The vendor data identifies the costs coming from web services and allocates them to the
cloud services. The model shown below shows the relationship.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/10550_1.png)

## About this task

If you are using Amazon Web Services (AWS), Microsoft Azure, SoftLayer, or CenturyLink, you can
import usage data from the monthly usage and billing reports. The data is used in the CTF reports
and the Application and Services reports. The data can help you compare the cost of cloud services
to in-house services. To use the web services data, you must install the CTF - Cloud Service
Provider component.

The following optional components import usage data from web services:

- CTF - Cloud Service Provider
- CTF - Amazon Web Services
- CTF - Azure
- CTF - Cloud Business Management

Apptio Costing Standard on TBM Studio 12.6 and later includes the capability to import monthly
cloud data usage and billing reports. The data is used in the Costing Standard reports, allowing you
to compare the cost of cloud services to in-house services.

## Step 1 - Install the Cloud Service Provider component

### Procedure

1. Open the Costing Standard project.
2. Click the **Projects** tab.
3. Click **Components** in the ribbon.
4. Click the**CTF - Cloud Service Provider** component.
5. Click **Install**.

### Results

When you install the Cloud Service Provider component:

- A Cloud Service Provider object is added to the Cost model.
- The following data sets are created in the Cloud Service Provider category:
  - Cloud Service Provider Lookup Master Data is used to map your organization's usage types to the
    Apptio usage types.
  - Cloud Service Provider Master Data is used to map the cloud service billing data to the Apptio
    cloud reports.
- The following data sets are created in the z\_Cloud Service Provider Configuration category:
  - Cloud Service Provider Apptio Lookup lists the Apptio cloud service usage types.
  - Provider Lookup lists your organization's cloud service usage types.
- The following CBM reports are created:
  - Cloud Service Provider Summary
  - IT Finance - Cloud Service Provider Bill Summary
  - IT Management - Cloud Service Provider
  - IT Management - Cloud Service Provider – Detail
