---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "View a model report"
breadcrumb: []
source_path: "studio/model_studio/view-model-report.html"
images:
  - "resources/images/studio_images/studioimages/icons/return.png"
  - "resources/images/studio_images/studioimages/studio/stu582.png"
  - "resources/images/studio_images/studioimages/studio/stu590.png"
  - "resources/images/studio_images/studioimages/studio/stu591.png"
  - "resources/images/studio_images/studioimages/studio/stu592.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# View a model report

**Applies to**: TBM Studio 12.0 and later

A project generally has a single model. To view a model report, from the **Reports** section
in the **Project Explorer**, click **Models** and click the name of the report. A sample model
report is shown in the following image:

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu582.png)

You can view a model in the model report screen shown in the preceding image, but you cannot edit
the model from that screen. On the model report screen, you can:

- Click a table element in the model to see the drivers and allocations. In the preceding image,
  the **Cost Source Actuals** table is selected.
- Continue to click table elements to trace the flow of value through the model (new in v12.1,
  v12.2+).
- Open the menu in a table and click **Drill Down** to see the columns in the
  table. You can select a column to focus the report on that column instead of the entire table.

Note: Beginning with v12.2.2, model reports can be added to report collections. In the example
below, the **saTestModel** report has been added to the **IT
Finance** report collection.

Watch this demo video from Apptio Education Services: [Using Model
Reports](https://community.apptio.com/videos/1583 "(Opens in a new tab or window)"). Or, browse [all Apptio videos](https://community.apptio.com/docs/DOC-7714 "(Opens in a new tab or window)").

## Drill to a column

By default, a model report shows tables. If you want to see more detail, you can drill to a
specific column by clicking the menu at the right side of the table.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu590.png)

For example, assume you have the model report shown in the first image. You would like to see the
allocation from the **Cost Source Actuals** table split out by cost pool. You can click the menu
and select **Cost Pool**. The model report now looks like the following image:

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu591.png)

To see how much of a specific cost pool value is allocated to the categories, click the cost
pool. In the following image, the **Facilities & Power** cost pool has been selected:

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu592.png)

To return to the table view, click the return arrow icon ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/icons/return.png) in the upper-left corner
of the tier.

## Trace value within a tier

Beginning with v12.2.2, value allocated between tables in the same tier are displayed as shown
below. Prior to v12.2.2, the **Storage** and **Servers** tables would have been vertically
aligned with an allocation line looping from **Storage** to **Servers**.

![](../../resources/images/studio_images/studioimages/studio_diagram_trace%20value%20within%20a%20tier.png)
