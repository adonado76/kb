---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Calc Prioritization"
breadcrumb: []
source_path: "studio/admin/default-calc-prioritization.html"
images:
  - "resources/images/studio_images/calc-prior-dragdrop.png"
  - "resources/images/studio_images/calc-prioritization.png"
  - "resources/images/studio_images/cm-proj-calc-mgmt.png"
  - "resources/images/studio_images/cp-dev-queue.png"
  - "resources/images/studio_images/cp-dragdrop.png"
  - "resources/images/studio_images/cp-phase2.png"
  - "resources/images/studio_images/cp-staging-q.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Calc Prioritization

Applies to: 12.10.9 and 12.10.10. From 12.11.0.

Administrators can prioritize the calculation of projects based on project importance or time
urgency. It is applicable across all projects, domains, and branches in their instance within TBM Studio. Projects will now be calculated according to the numbers assigned to them. Administrators
can drag-and-drop projects to the desired order and document the reason for the changes. The primary
benefit is to set the order for projects to calculate after an instance reset. Additionally, if a
calculation is underway, calc prioritization will determine the order of subsequent check-ins.

See [Calc Management](cacl-mgmt-settings.htm "(Opens in a new tab or window)")

Calc Prioritization is not active by default. To enable it, navigate to **Project** >
**Enable Features**, and then select **Project Calc Priority Management**.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/cm-proj-calc-mgmt.png)

Note: Default Calc
Prioritization is not supported for multi-tenancy instance. Current feature supports only Default
Calc Prioritization. The future enhancement will support changes within the Dev and Staging calc
queues.

:

## Navigation

Navigate to **Build** tab on the TBM Studio Ribbon and select **Calc Prioritization**![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/calc-prioritization.png)

The Calculation Prioritization popup appears with three tabs - Project Priority, Dev Queue, and
Staging Queue

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/cp-dragdrop.png)

## Project Priority

Applies to: 12.10.9 and 12.10.10 only. This tab shows the list of projects with their
priority.

This tab shows the list of projects with their priority.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/cp-phase2.png)

Enter a **Reason** to document the purpose for the change and click **Update Project Priority
Queue**.

## Dev Queue

This tab shows the list of tasks that are currently in the development queue. There are two
sections Active Calc and Queued Calc, and they show the tasks that are in-progress and in-queue
respectively.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/cp-dev-queue.png)

The active queue is static, while the queued list can be modified based on the user's
preference.

## Staging Queue

This tab shows the list of project/branches that are currently in the staging queue. There are
two sections Active Calc and Queued Calc, and they show the projects and/or branches that are
in-progress and in-queue respectively.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/cp-staging-q.png)

## Changing Priorities

You can change the priorities of all the in-queue items and for the project priority by either
drag and drop a project row or enter a manual value to change the priority. The priority number will
automatically adjust to create the desired prioritization. The system will assign number by adding 1
to the project directly below

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/calc-prior-dragdrop.png)

You can also search to filter across Domain, Project and Branch. The Dev and Staging queues can
be refreshed manually to check for updates.

note

Note: Priorities cannot be changed for the in-progress tasks.
