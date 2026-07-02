---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Set up table-update schedule"
breadcrumb: []
source_path: "studio/data_studio/table-update-schedule.html"
images:
  - "resources/images/studio_images/table-update-schedule.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Set up table-update schedule

**Applies to**: TBM Studio 12.6 and later

You can publish info from Editable Table to a Standard Table by three primary methods:

1. You can manually “update” in TBM Studio.
2. You can manually “publish” changes from the report.
3. You can automatically “publish” updates on a routine basis.

## Manually update in TBM Studio

1. Go to **TBM Studio**
2. Select your project from the left navigation
3. In the Project Explorer section, select a table you want to publish. For example: Select the
   Transform under Demand Planning (based on an editable table).
4. Select **Editable Table** option under **Steps**.
5. Once you select this, you can see different periods. Right click on the icon to update this
   period.

   ![Editable Table](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/table-update-schedule.png)

## Manually publish changes in the reporting surface

You can update data in a report and manually publish the Editable Table changes to the associated
transform table to see results the same day.

Prerequisites
:   To manually publish changes from the report, you need Dev access and Stage access as a user, but
    you do not need TBM Studio or Admin access.

How to manually publish changes from the report:
:   From a report with an editable table:

    1. Enter desired changes and select **Save**.
    2. Select **Publish** at bottom of report > select
       **Publish** again for warning pop-up.
    3. Enter description and select **Check In** on the Check In modal.

## Set up an automatic table-update schedule

1. On the TBM Studio ribbon bar, select the **Build** tab.
2. Select **Promotion Options**.
3. Select **Recurring Updates for Editable Tables**.
4. Schedule Repeat = Daily and set Start Time with Offset.
5. Select **Add new Start time** to create up to four run times.
6. Unselect Enable to disable feature.

**Parent topic:** [Editable tables: Accommodating user input](../../studio/data_studio/editabletables.html "Applies to: TBM Studio 12.6 and later")
