---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Labor Allocation Settings"
breadcrumb: []
source_path: "it-planning/planning/iip/allow-over-allocation.html"
images:
  - "resources/images/it_planning_images/allow-allocation-1.jpg"
  - "resources/images/it_planning_images/allow-oa-1.jpg"
  - "resources/images/it_planning_images/allow-oa-2.jpg"
  - "resources/images/it_planning_images/allow-oa-3.jpg"
  - "resources/images/it_planning_images/allow-oa-4.jpg"
  - "resources/images/it_planning_images/allow-oa-5.jpg"
  - "resources/images/it_planning_images/ao-1.jpg"
  - "resources/images/it_planning_images/three-dots.jpg"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Labor Allocation Settings

Important: *Available with the* ***Apptio Planning Standard****subscription*

Selecting this option will help the budget owners to allow over allocating the resource. It also
allows you to set 'over' and 'under' allocation threshold values to flag allocations that exceed or
fall below the configured thresholds. Follow the steps below to enable and use the feature.

## Enable Allow Overallocation

Navigate to Company Profile> Enable Capabilitiessection and select the Labor
Activity checkbox. Select Allow over allocation option and then Save and Exit from
the company profile page.

NOTICE: Labor Activity checkbox will be visible under Company Profile only if
“Enable Integrated Investment Planning” checkbox is enabled.

![image](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/allow-oa-1.jpg)

You can also set the threshold vaues of resource being 'over' allocated or 'under' allocated'. In
this case, if a resource is under allocated by 20% or over allocated by 10% or more, then the
difference will be flagged in the mentioned color. After setting the threshold values, select
Save and Exit.

Navigate to Expenses > Labor Activity tab. From
![more icon](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/three-dots.jpg), enable the Analyse labor allocation
option.

![image](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/ao-1.jpg)

The resources are grouped and the allocations that are beyond the defined threshold (under 20%
and over 10%) are highlighted in the appropriate color shades, as shown. The cells without any color
indicate that their allocation is within the defined thresholds.

![image](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/allow-allocation-1.jpg)

The shade of the colored cell can be matched with the key on the top, to understand what is the
percentage of the over or under allocation.

## Detect and Allow Overallocation

Consider that the working capacity for John in January 2024 is 88 hours and for June 2024 is 160
hours.

Navigate to Expenses > Labor Activity tab and slide the toggle to Hours.
Hover on any blue shaded cell. The popup will say that the resource is under-allocated by how many
hours, what is their total monthly capacity, and what are their other allocations.

In this scenario, the difference between the entered value 48 and John's capacity of 160 is 112
hours, and the resource is under allocated by 112 hours.

![image](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/allow-oa-2.jpg)

Similarly, now hover on any red shaded cell. The popup will say that the resource is
over-allocated by how many hours, what is their total monthly capacity, and what are their other
allocations.

In this scenario, the difference between the entered value 176 and John's capacity of 88 is 88
hours, and the resource is over allocated by these 88.00 hours.

![image](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/allow-oa-3.jpg)

Next, switch the toggle to FTE and hover on any red shaded cell. The popup will say that
the resource is over-allocated by how many FTE, what is their total monthly capacity, and what are
their other allocations, all in FTE.

In this scenario, the difference between the entered value 1 and John's capacity of 0.5 FTE is
0.5 FTE, and the resource is over allocated by 0.5 FTE.

![image](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/allow-oa-4.jpg)

Similarly, if you hover on any blue shaded cell, the popup will say that the resource is
under-allocated by how many FTE, what is their total monthly capacity, and what are their other
allocations, all in FTE.

In this scenario, the difference between the entered value 0.65 and John's capacity of 1 FTE is
0.35 FTE, and the resource is under allocated by 0.35 FTE.

![image](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/allow-oa-5.jpg)
