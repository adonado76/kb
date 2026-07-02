---
source_system: "apptio-billing"
practice: "tbm"
language: "en"
doc_type: "define-billable-model.html"
title: "Define Billable Units model (metric) allocations"
breadcrumb: []
source_path: "define-billable-model.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Define Billable Units model (metric) allocations

If the Billing Standard Units component is installed, you must define the allocations from
Consumption Feed to Business Services, and from the Business Services table to the Business Unit
Allocation Master Data table. Use the settings shown in the following images. Be sure to select the
Billable Units metric.

![](../resources/images/boit_images/boit_define-billable-model1.jpg)

![](../resources/images/boit_images/boit_define-billable-model2.jpg)

![](../resources/images/boit_images/boit_define-billable-model3.jpg)

![](../resources/images/boit_images/boit_define-billable-model4.jpg)

To establish the data relationship, map the Business Unit ID column in the All Business Services table to the Ident column in the Business Unit Allocation Master Data table as shown below.

![](../resources/images/boit_images/boit_define-billable-model5.jpg)

**Parent topic:** [Billing Standard](home.html)
