---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Labor Activity Type"
breadcrumb:
  - "Planning"
  - "Project Labor Activity Planning"
source_path: "it-planning/planning/iip/manage-labor-activity-type-data-ref.html"
images:
  - "resources/images/it_planning_images/three-dots.jpg"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Labor Activity Type

Important: *Available with the* ***Apptio Planning Standard****subscription*

Remember: *Integrated Investment Planning (IIP) feature is enabled*

The **Labor Activity Type** reference data defines how labor charges and cross-charges
flow between the **provider** (Department Cost Center) and **consumer** (Project Cost
Center) based on the type of labor activity performed.

Each Labor Activity Type specifies the financial accounts used for charging and crediting
labor, and whether the activity is capitalizable. These mappings are used during [Labor Activity Planning](labor-resource-planning.html) to ensure labor costs
are accurately allocated to the correct cost centers.

## Configure Labor Activity Type

***Note:*** *Admin or Budget Process Owner roles are required to perform these
tasks.*

1. In the navigation menu, go to: **Reference Data** → **Standard Dimensions** →**Labor Activity Type**
2. Click the ![ellipses menu](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/three-dots.jpg) menu and **Export Template**.
3. Download the template and populate the required fields:

   |  |  |
   | --- | --- |
   | **Field** | **Description** |
   | **Name** | The name of the labor activity (e.g., Development, Support, Maintenance). This is the value selected when planning labor effort in the Labor Activity tab. |
   | **Charge Account** | The account code for the Department (provider) cost center that receives the credit when labor is provided to a project or another cost center. |
   | **Cross-Charge Account** | The account code for the Project (consumer) cost center that receives the debit for labor consumed. |
   | **Is Capitalizable** | Indicates whether labor for this activity type can be capitalized. - True: Labor costs are eligible for capitalization. - False: Labor costs are expensed. |
   | **Is Default** | Determines the default Labor Activity Type applied when users enter labor in the Labor Activity tab. - Only one activity type can be marked as default. - If a user does not select an Activity Type, the default value is applied. |
4. Import the updated CSV.
5. Click the ![ellipses menu](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/three-dots.jpg) menu and **Publish** the changes so they are
   available for plans.
