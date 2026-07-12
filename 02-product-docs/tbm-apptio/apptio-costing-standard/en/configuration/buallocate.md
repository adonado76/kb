---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "configuration"
title: "Direct vs indirect allocations"
breadcrumb: []
source_path: "configuration/buallocate.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Direct vs indirect allocations

Direct allocations are based on consumption. Indirect allocations are based on a selected
ratio such as Total Staff by Department.

## Direct costs

Direct costs can be assigned to a specific product, department, or project. Labor, software,
equipment, and raw materials are examples of direct costs. Direct costs can be identified with a
specific cost object. A large percentage of direct costs come from labor and materials.

## Indirect costs

Indirect costs generally include the infrastructure that keeps a company running. Indirect costs
can include items such as cleaning supplies, utilities, office equipment rental, desktop computers,
and cell phones.

## How direct and indirect costs are applied to the Apptio cost model

The direct and indirect costs are calculated at the top of the cost model using four objects:
Business Services, Service Allocations Direct, Service Allocations Indirect, and Business Units
Allocation. The model is shown below.

![](../../resources/images/ct_images/6857_1.png)

The Business Services costs are allocated to the Service Allocations Direct model object based on
the Service\_Service Allocations Direct field. The field is in the All Business Services data set
backing the Business Services model object, and in the Service Allocations Direct Master data set
backing the Service Allocations Direct model object.

The Business Services costs are allocated to the Service Allocations Indirect object based on the
Check for SAD field. The field is in the All Business Services data set backing both the Business
Services model object and the Service Allocations Direct model object.

**Parent topic:** [Costing Standard](../home.html)

## Related information

- ![](../../../../03-media/apptio-costing-standard/sout.gif)[Send feedback about
  Help Center](productfeedback@apptio.com "(Opens in a new tab or window)")
