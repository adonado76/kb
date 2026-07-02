---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "configuration"
title: "Enter estimated non-provider costs"
breadcrumb: []
source_path: "configuration/estmatednonprov.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Enter estimated non-provider costs

The manually entered, estimated non-provider costs are primarily for new Cloud Cost
Management-only customers who have not lit up actuals with their GL in Costing Standard. For anyone
who has Costing Standard, the better option is to drive non-provider costs from the actuals in the
Costing Standard Cost model. There is a link between the two models (CT Cost model and CCM Cloud
Invoice model) to allow you to do this via the IT Resource Towers object.

Applies to: Apptio Costing Standard or Apptio Cloud Cost Management running on TBM Studio v12.3.3
or later.

Any costs in the Cost model that have "Is Cloud" set to "Yes" on the ITRT object and that are
not driven from the Cloud Service Provider object will flow into the Cloud Invoice model and be the
source of non-provider costs.

To enter estimated non-provider costs:

1. Log in to Apptio, then in the Home page, click Public Cloud.
2. On the Public Cloud dashboard, click the Estimated Non-Provider Costs
   icon.
3. Read "Learn More About Estimated Non-Provider Costs" to better understand the purpose and
   reasoning behind non-provider costs. The format of the data:

   ![](../../resources/images/ct_images/7873_1.png)
4. To upload user data, in Studio, expand Tables, then click
   Public Burdened Cost Master Data.
5. In the Project ribbon, click Check Out.
6. In the Step section, click Append.
7. Manually append the burdened cost, the data set you created. The required fields:
   - Annual Cost or Monthly Cost
   - Cost Pool
   - Cost Sub-Pool
   - Delivery
   - Description
   - IT Resource Tower Name
   - Type
   - Unit
   - Unit of Measure
8. Check in your changes.
9. To ensure that the user data was correctly appended and uploaded, in the Non-Provider Costs
   report (Public Cloud > Estimated Non-Provider Costs), click the My Estimated Non-Provider
   Costs tab and ensure that the uploaded data appears correctly.

**Parent topic:** [Costing Standard](../home.html)

## Related information

- ![](../../../../03-media/apptio-costing-standard/sout.gif)[Send feedback about
  Help Center](productfeedback@apptio.com "(Opens in a new tab or window)")
