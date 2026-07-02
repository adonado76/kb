---
source_system: "apptio-billing"
practice: "tbm"
language: "en"
doc_type: "boit"
title: "Define the Charge Price x Quantity relationship"
breadcrumb: []
source_path: "boit/define-charge-price.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Define the Charge Price x Quantity relationship

In the Charge model, you must first define the drivers to the Consumption Feed object, and then define the allocations to the Business Services modeled table and the Business Unit Allocation modeled table.

**Define the drivers to the Consumption Feed object**

There are three basic types of drivers: cost based charges, budget based charges, and price based charges.

**Cost based charges**

Cost based charges pass cost to the business user. The costs per service are determined in the Cost Transparency application. Cost based charges may have additional information provided through the Consumption Feed.

1. If you have not yet added data to the Consumption Feed, go to [Add consumption data for Price x Quantity
   calculations](add-consumption-data.html "(Opens in a new tab or window)") . If you do not intend to provide quantities, append a list of your Service IDs
   using the same steps.
2. Follow the steps in [Define
   the Cost model allocations](define-cost-model1.html "(Opens in a new tab or window)") to allocate Cost to the Consumption Feed.
3. In the Service Library table, set the **Pricing Methodology** to**Cost** for all services that will use Cost to determine the charge.
4. In the **Project Explorer** , click the **Model** step
   in the Business Services table.
5. Make sure the **Charge** metric is selected.
6. Validate that the provided driver now shows values.

**Budget based charges**

Budget based charges pass to the business user a budgeted charge determined per service. Budget based charges may have additional information provided through the Consumption Feed.

1. Follow the steps in [Add
   the consumption data](add-consumption-data.html "(Opens in a new tab or window)") .
2. In the Service Library table, set the **Pricing Methodology** to**Budget** for all services that will use Cost to determine the charge.
3. In the **Project Explorer** , click the **Model** step
   in the Business Services table.
4. Make sure the **Charge** metric is selected.
5. Validate that the provided driver now shows values.

**Price based charges**

Price based charges multiply a price determined by service and the units of the service that have been consumed. Price based services should have consumption feeds with the units provided through the Consumption Feed.

1. Follow the steps in [Add
   the consumption data](add-consumption-data.html "(Opens in a new tab or window)") .
2. Follow the steps in[Define the Billable Units model allocations](define-billable-model.html "(Opens in a new tab or window)") .
3. In the Service Library table, set the **Pricing Methodology** to**Price** for all services that will use (Price x Quantity) to determine the charge.
4. In the **Project Explorer** , click the **Model** step
   in the Consumption Feed table.
5. Make sure the **Charge** metric is selected.
6. Validate that the provided driver now shows values.

**Define the allocations**

In the Charge model, you must define the allocation from the Consumption Feed model object to the Business Services model object, and from the Business Services model object to the Business Unit Allocation model object. Use the settings shown in the following images.

Consumption Feed to Business Services allocation

Business Services to Business Unit Allocation allocation

If you do not have any consumption or services wholly attributable to one business unit, then use an allocation similar to:

Otherwise, use this allocation:
