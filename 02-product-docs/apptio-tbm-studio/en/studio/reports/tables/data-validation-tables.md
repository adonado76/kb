---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Data Validation for Editable Tables"
breadcrumb: []
source_path: "studio/reports/tables/data-validation-tables.html"
images:
  - "resources/images/studio_images/data-validation.png"
  - "resources/images/studio_images/data-vld-msg.png"
  - "resources/images/studio_images/enable-validation-step.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Data Validation for Editable Tables

To enable the data validation in theUI, navigate to **Project** tab > **[**Enable
Features**](../../admin/enable-features.htm "(Opens in a new tab or window)")** > and select **Enable Validation Step for Editable Table (Beta)**
option.

![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/enable-validation-step.png)

When you enter corrupt or bad data into an editable table, an warning or error message will
appear near the respective value.

![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/data-validation.png)

![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/data-vld-msg.png)

As you rectify the errors, the validated rows will move down, and the rows that still have errors
will appear at the top.

You can save and check-in the report in spite of these errors.
