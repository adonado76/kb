---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Deferred Refresh"
breadcrumb: []
source_path: "studio/reports/delayed-refresh.html"
images:
  - "resources/images/studio_images/del-ref-popup_885x911.png"
  - "resources/images/studio_images/delayed-refresh-new_875x416.png"
  - "resources/images/studio_images/df-checkin_855x279.png"
  - "resources/images/studio_images/df-chkout_842x344.png"
  - "resources/images/studio_images/df-report_844x395.png"
  - "resources/images/studio_images/df-tbm_883x327.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Deferred Refresh

The Delayed Refresh feature provides deferred time for the users to select filters, pickers, or
slicers and see the updated results based in the report. This is useful for large, complex reports
where multiple interactive selections are made.

In 12.10.8, this feature was available as part of Report Studio > Navigation bar, with the
options Live, 2 seconds, 5 seconds, and Manual refresh.

From 12.10.9, the feature has been enhanced to remove the Live, 2 seconds, and 5 second options.
The new options are:

- **Refresh Delay: 3s**: The system waits for 3 seconds before refreshing the screen.
- **Manual Refresh**: This mode requires the user to select Refresh to update the report.

This feature is available in three views:

## Cost Transparency

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/delayed-refresh-new_875x416.png)

Note: Changes done in the CT Report Studio are not user persistent. If the user is logged out, the
default settings of 3 seconds will be again be applicable.

## TBM Studio

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/df-tbm_883x327.png)

The Deferred Refresh feature is available to all users, with the default of **Refresh Delay:
3s** for all the projects, but the Admin can change the setting to Manual Refresh. For simple
reports, you can set to 3 seconds, while for a large report with numerous slicers, pickers, pivots,
the user may switch to **Manual Refresh** option. To change the refresh settings, navigate to
**Project** tab > **Project Settings** and change the value in **Deferred Refresh** field
in the Edit Project Settings popup.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/del-ref-popup_885x911.png)

This setting will apply to all reports. But you can change the refresh settings for specific
reports by following these steps:

1. From the **Home** tab of a report, select **Checkout**

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/df-chkout_842x344.png)
2. The **Report** tab is enabled. Apply the appropriate filters and modify the refresh settings
   as applicable.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/df-report_844x395.png)
3. From **Home** select **Save**, and then select **Checkin** option.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/df-checkin_855x279.png)
