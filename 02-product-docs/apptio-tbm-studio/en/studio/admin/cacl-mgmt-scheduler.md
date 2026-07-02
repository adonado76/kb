---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Calc Management Scheduler"
breadcrumb: []
source_path: "studio/admin/cacl-mgmt-scheduler.html"
images:
  - "resources/images/icons/pencil-icon.jpg"
  - "resources/images/studio_images/build-calc-schedule.png"
  - "resources/images/studio_images/calc-config-delete-confirmation.png"
  - "resources/images/studio_images/calc-config-scheduler.png"
  - "resources/images/studio_images/calc-scheduler.png"
  - "resources/images/studio_images/create-schedule-popup.png"
  - "resources/images/studio_images/project-config-calc-scheduler.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Calc Management Scheduler

Applies to: 2.16 and later. This feature will automate the staging calculations at a
project level and branch level.

To Enable Calc management Schedule navigate to **Project** > **Enable Features**, and then
select **Show Calc Scheduler**. A pop-up will appear to confirm that the feature is enabled.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/calc-scheduler.png)

## Project Configuration

Navigate to **Build** tab on the TBM Studio Ribbon and select **Calc
Schedule**.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/build-calc-schedule.png)

To create a schedule, do the following

1. Click **Create Schedule** button.

   ![Create Schedule](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/create-schedule-popup.png)
2. Enter **Schedule Name**.
3. From the **Weekly** field, select the desired days to perform calculations.
4. Select **Re enable time** to restart the calculations.
5. Select **Disable time** to stop the calculations .
6. Select **Time zone**.
7. Click **Submit** button.

Created schedules can be applied to multiple projects.

![Project Configuration](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/project-config-calc-scheduler.png)

It has the following information:

| Field | Description |
| --- | --- |
| Project Name | Name of the project |
| Branch | Name of the Branch |
| Schedule Name | Name of the Schedule. Select a schedule to assign to the project from the schedule list dropdown. |
| Occurrence | Display the days when the calculations happen |
| Disable Calc | Display disable time to stop the calculation. |
| Re-enable Calc | Display re-enable time to restart the calculation. |

## Calc Configuration

![Calc Configuration](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/calc-config-scheduler.png)

To edit the existing schedule, select edit icon![Pencil](../../../../../03-media/apptio-tbm-studio/resources/images/icons/pencil-icon.jpg)

- Once a calculation is initiated, editing the **Re enable time** or **Disable time** will
  not terminate the current running calculations.
- While calculating, changes to the **Re enable time** or **Disable time** will only take
  effect on future calculations.

To delete the existing schedule, select delete icon. Click **Confirm** button on the warning
pop-up.

![Delete Confirmation](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/calc-config-delete-confirmation.png)

Note: To change the Re enable/disable state of a project, navigate to **Build**  > **[Calc Management](cacl-mgmt-settings.html "Applies to: 12.11.0 and later. Customers can now disable/enable staging calculations at a project level, so that they can control which projects get calculated and in turn, reduce the number of total calculations.")** and manually edit
Disable/Enable Staging Calc as needed.
