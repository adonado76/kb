---
source_system: "apptio-billing"
practice: "tbm"
language: "en"
doc_type: "define-cost-model1.html"
title: "Define Cost model allocations"
breadcrumb: []
source_path: "define-cost-model1.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Define Cost model allocations

Perform this step if you have not already allocated value to the Business Services model object in the Cost model.

![](../resources/images/boit_images/boit_define-cost-model.jpg)

To define the Cost model allocations, use Cost Transparency to allocate your costs.

To use Cost based charges, use the following steps to provide cost information to the charge model.

1. If you have not yet added data to the Consumption Feed, see
   [Add consumption data for Price x Quantity calculations](add-consumption-data.html "Use consumption data when you want to charge business units based on their consumption of services rather than cost allocations based on factors such as head count. If no additional consumption data is known, use a list of the Service IDs, which may be provided via appending the raw data for the Service Library. Do not append the table for the Service Library itself, however appending the data appended to the Service Library is allowed.")
   . If you do not intend to provide quantities, append a list of your Service IDs using the same steps.
2. In the
   Project Explorer
   , click the
   Model
   step in the Business Services table.
3. Make sure the
   Cost
   metric is selected.
4. Add a new allocation by clicking
   Add Allocation
   .
5. Set the allocation to allocate the metric Cost to Business Services using Weighted Value,
   distributing via a data relationship based on Service ID.

   ![](../resources/images/boit_images/boit_define-cost-model2.jpg)
6. See
   [Define the Charge Model Allocations](define-charge-price.html)
   for instruction on completing the Cost Based Charge.

**Parent topic:** [Billing Standard](home.html)
