---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Prevent Overallocation"
breadcrumb: []
source_path: "it-planning/planning/iip/prevent-overallocation.html"
images:
  - "resources/images/it_planning_images/enable-disable-labor-activity.jpg"
  - "resources/images/it_planning_images/fte-oa-error.jpg"
  - "resources/images/it_planning_images/la-import.jpg"
  - "resources/images/it_planning_images/labor-edit.jpg"
  - "resources/images/it_planning_images/labor-over-allocated.jpg"
  - "resources/images/it_planning_images/legacy-view.jpg"
  - "resources/images/it_planning_images/over-allocated-popup.jpg"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Prevent Overallocation

Important: *Available with the* ***Apptio Planning Standard****subscription*

Enabling this feature will help the budget owners to prevent over allocating the resource
beyond available capacity. Follow the steps below to enable and use the feature.

## Enable Prevent Overallocation

Navigate to Company Profile> Enable Capabilitiessection and select the Labor
Activity checkbox.

Note: Labor Activity checkbox will be visible under Company Profile only if “Enable
Integrated Investment Planning” checkbox is enabled.

The two options appear as below.

![image](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/enable-disable-labor-activity.jpg)

Select Prevent over allocation option and then Save and Exit from the company
profile page.

## Detect and Prevent Overallocation

In the below scenarios, we are attempting to allocate John, whose monthly capacity for January is
88 hours on 'P193 - BI Analytics Enhancements' project as 8 hours per day.

1. In the Legacy Expenses View, navigate to labor activity tab and enter a
   value greater than 88 in Jan FY24. If you hover on the cell, the popup error message appears as
   "*Resource is over-allocated for the period by 2.0 hours. please switch to New View for more
   details*". The difference between the entered value 90 and John's capacity of 88 is 2
   hours.

   ![image](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/legacy-view.jpg)
2. Since the previous message did not show all the details, we will switch to New
   Expenses View and slide the toggle to Hours. One again, enter the
   same value as above in Jan FY24. The cell is highlighted with a red error icon, and hovering on it
   will show the error message as below.

   ![image](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/over-allocated-popup.jpg)

   The popup will say that the resource is over-allocated for the
   period, and provide all details like the Total monthly capacity, allocation on current line item,
   allocation on other line item, over allocation, and the projects allocated, in Hours.

   In this
   scenario, the difference between the entered value 90 and John's capacity of 88 is 2 hours and this
   is displayed in red.
3. Now let us switch to New Expenses View and slide the toggle to
   FTE. Enter a value greater than 0.5 in Jan FY24. The cell is highlighted with
   a red error icon, and hovering on it will show the error message as below.

   ![image](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/fte-oa-error.jpg)

   The popup will say that the resource is over-allocated for the
   period, and provide all details like the Total monthly capacity, allocation on current line item,
   allocation on other line item, over allocation, and the projects allocated, in ftes.

   In this
   scenario, the difference between the entered value 0.9 and John's capacity of 0.5 is 0.4 ftes and
   this is displayed in red.
4. In the next scenario, let us prevent overallocation during Labor data edit from
   expenses UI. For this, navigate to the Labor tab, and change the allocation for John in
   Feb FY24 cell.

   ![image](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/labor-edit.jpg)

   Here, we see that total monthly capacity for John in February 2024
   is 84 hours (since February has only 21 working days). He is over allocated by 16 hours because his
   allocation for Feb FY24 in Labor Activity tab was 100. See the 2nd scenario above.
5. Let us now take the scenario to prevent overallocation during Labor Activity
   import. Export a file from the Labor Activity tab. In the downloaded CSV file, change
   the allocation for John for P1 FY2024 as 93, and save the file. When you upload this file, and
   select Import, a warning message appears as shown.

   ![image](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/la-import.jpg)

   The
   message shows the name of the labor activity file, and the issues it has - like overallocation, and
   row modifications. Expand the section to see the issue details.
6. In the last scenario, let us prevent overallocation during Labor import.
   Export a file from the Labor tab. In the downloaded CSV file, change the allocation for John for P2
   FY2024 as 0.4, and save the file. When you upload this file, and select Import, a warning message
   appears as shown.

   ![image](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/labor-over-allocated.jpg)

   The message shows the name of the labor file, and the issues it has
   - like overallocation, and row modifications. Expand the section to see the issue details.

Note:

- Feature is supported only when individual resources are assigned to Projects/Investments. If the
  Resource field in the labor activity is empty, the over allocation detection isn’t supported.
- When Prevent Overallocation feature is enabled, overallocations in the existing plans will be
  detected when user attempts to edit those lines from the UI or attempts to re-import the labor
  activity data.
- Changing the working calendar hours will lead to over allocating the resources, if the new
  monthly working hours are less than previous working hours. In such cases, the over allocated
  expenses will be detected when editing or re-importing the labor activity lines.
- If project level access control is configured and the logged in project manager doesn’t have
  access to view all the allocations for the selected resource, it will be still possible to detect
  the overallocation caused due to allocation of the resource to other projects. The Project code of
  the projects where the resource is allocated will be displayed in the over allocation detection
  pop-up message. This information will help the logged in project manager to resolve the
  overallocation by working with the project managers of the other projects.
- When the company profile settings are changed to Allow Overallocation, prevention of
  overallocation won’t be possible.
- Functionality to set the over allocation and under allocation threshold is work in-progress, it
  will be launched in early Q2 2024.
