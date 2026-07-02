---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Fixed/variable reporting and allocations"
breadcrumb: []
source_path: "cost-transparency/reports-v103/fixedvariablereportingallocations-6558.html"
images:
  - "resources/images/ct_images/6558_10.png"
  - "resources/images/ct_images/6558_11.png"
  - "resources/images/ct_images/6558_2.png"
  - "resources/images/ct_images/6558_3.png"
  - "resources/images/ct_images/6558_4.png"
  - "resources/images/ct_images/6558_5.png"
  - "resources/images/ct_images/6558_6.png"
  - "resources/images/ct_images/6558_7.png"
  - "resources/images/ct_images/6558_8.png"
  - "resources/images/ct_images/6558_9.png"
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Fixed/variable reporting and allocations

Applies to: v12+

## Overview

Trying to figure out why your Fixed or Variable costs are:

- not looking correct?
- too low?

Are you asking any of these questions?

- How are Fixed and Variable costs calculated?
- How do I get dollars into the Fixed or Variable models?
- How do I ensure that the Fixed and Variable costs are flowing through their models?
- How do I directly affect the amount displayed in the Fixed/Variable reporting?

This topic will walk you through how the Fixed and Variable costs are set up in Costing Standard
and where you can look to edit these costs.

## How are the Fixed and Variable costs created?

The Fixed and Variable costs are created from the Fixed and Variable models, which are run in
parallel to the out-of-the-box Cost model.

Fixed model
:   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6558_2.png)

Variable model
:   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6558_3.png)

## How do I get dollars into the Fixed and Variable Models?

To ensure that there are values populated in both the Fixed and Variable models, follow these
steps.

1. Click the **Cost Source** table.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6558_4.png)
2. Select the **Fixed** or **Variable** metric in the dropdown menu.

   Fixed Dropdown
   :   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6558_5.png)

   Variable Dropdown
   :   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6558_6.png)
3. Click the **OpEx Fixed** driver.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6558_7.png)
4. Click the **Add To** dropdown menu.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6558_8.png)
5. Make sure that the **Fixed** button is selected.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6558_9.png)

Follow the previous steps to check both the Fixed and Variable models if you are running Cost
through Apptio. Additionally, you
would want to check both the Fixed and Variable models for each additional reporting metric: CapEx,
Budget,and Forecast.

## How do I ensure that Fixed and Variable costs are flowing through the model?

To ensure that the Fixed and Variable costs are functioning correctly and flowing dollars, you
will have to enable the Fixed and Variable allocation. To do this, select the Fixed and Variable
button in the allocation line Allocate dropdown window. Make this selection for all allocation lines
leading up to IT Resource Towers.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6558_10.png)

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6558_11.png)

## How do I directly affect the amount displayed in the App Dev reporting?

To affect the dollar amount that is tied to the Fixed/Variable reporting, you will have to select
the Fixed and Variable buttons for the allocation lines. For example: if you are trying to tell the
Fixed/Variable breakdown at the Labor level, then both the Fixed and Variable buttons will have to
be selected in all of the allocation lines flowing to the Labor object. If you are trying to tell
the Fixed/Variable breakdown at the IT Resource Tower level, then both the Fixed and Variable
buttons will have to be selected in all of the allocation lines flowing to the IT Resource Tower
object.

## Key Takeaways

- Any allocation lines below IT Resource Towers should have both the Fixed and Variable buttons selected.
- Only the allocation lines that are flowing directly into the object that is being reported on, and also have the Fixed and Variable buttons selected, will be displayed as Fixed/Variable costs in the reporting.
- To directly affect the amounts displayed in the Fixed/Variable reports, the allocation lines rolling to the object that is being reported on will have to be adjusted.

## Related information

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Send feedback about
  Help Center](productfeedback@apptio.com "(Opens in a new tab or window)")
