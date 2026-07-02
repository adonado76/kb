---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Tag Plans as Active"
breadcrumb:
  - "Planning"
  - "Creating and Managing Plans"
source_path: "it-planning/planning/tag-plans-actve.html"
images:
  - "resources/images/it_planning_images/tagpln1.png"
  - "resources/images/it_planning_images/tagpln2.png"
  - "resources/images/it_planning_images/tagpln3.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Tag Plans as Active

The **Tag as Active** feature allows Administrators to prioritize important plans by
marking them as **Active**. This helps users quickly locate and focus on the plans that
matter most.

Note: Admin or Budget Process Owner roles are required to manage plans.

When a plan is tagged as Active, it will:

- Display an **“Active” label** next to the Plan name
- Automatically appear at the **top of the Plan dropdown menu**
- Be treated as the **default plan** when users log in

![image of tagging plan as active](../../../../../03-media/apptio-planning/resources/images/it_planning_images/tagpln1.png)

## How to Tag or Untag a Plan as Active

From the Plans Page 

- Right-click a plan and select **Tag Active**
- To remove the tag, right-click again and select **Untag Active**

![image of tag plan from plan page](../../../../../03-media/apptio-planning/resources/images/it_planning_images/tagpln2.png)

When Creating a New Plan 

- In the **Create New Plan** modal, check **Tag as Active**
- The plan will be marked Active immediately after creation

![mag foe new plan](../../../../../03-media/apptio-planning/resources/images/it_planning_images/tagpln3.png)

## Behavior of Active Plans

|  |  |
| --- | --- |
| **Behavior** | **Description** |
| Display | The Active tag appears next to the plan name in the Plan dropdown menu. |
| Ordering | Active plans always appear first, sorted alphabetically if more than one. |
| Non-Active Plans | Plans and folders without the Active tag are listed below Active plans, also alphabetically. |
| Default Plan on Login | If there is only one Active plan, users will be defaulted to that plan. If multiple Active plans exist, users will be defaulted to the most recently created one. |
| Archiving Rule | Archived plans cannot be tagged Active. If an Active plan is archived, the tag is automatically removed. |
| Audit Trail | All changes to a plan’s Active status are logged in Change History. |
