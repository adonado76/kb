---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "troubleshooting"
title: "Transform Model Step Columns"
breadcrumb: []
source_path: "troubleshooting/transform-model-step.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Transform Model Step Columns

There is a maximum number of columns you can use in your table with a model step. If you
exceed this limit, TBM Studio takes longer to calculate results, and also does not calculate the
model object. This results in incorrect numbers on any models that use this object.

![](../../resources/images/troubleshooting_images/transform-model-step-columns-1.png)

## Configuration recommendation for transform model step columns exceeded error

To resolve this error, add a hide and rename step and hide any columns that are not needed.

To add a hide and rename step:

1. In the Project Explorer view > select Tables
2. Select the project drop-down, select the table required for the project
3. In the Home tab, select Check Out
4. Add the step from + icon shown in the configuration of the step
5. Select Hide and Rename from the configuration of the step, and then select **Add
   Columns**
6. Select the columns to hide to get under the limit.

   ![](../../resources/images/troubleshooting_images/transform-model-step-columns-2.png)
