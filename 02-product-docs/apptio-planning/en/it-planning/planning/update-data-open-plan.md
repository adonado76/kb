---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Update reference data in an open plan"
breadcrumb: []
source_path: "it-planning/planning/update-data-open-plan.html"
images:
  - "resources/images/icons/3-dots.jpg"
  - "resources/images/it_planning_images/icon_gear.jpg"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Update reference data in an open plan

When a plan is created, it inherits the published versions of reference data currently
loaded into the **Reference Data** module. If subsequent changes to reference data are made, then
the data in the plan will need to be updated. Since reference data is used to structure plan data
and to tag line items with reportable attributes, certain reference data changes can cause data
loss. For example, deleting a Cost Object will delete all the plan line items associated with that
Cost Object. Deleting an Account will cause all line items tagged against that account to become
invalid, and therefore, deleted. Other changes, such as deleting a Vendor, will not cause plan line
items to be deleted, but can result in loss of reporting fidelity as line items previously tagged
with the deleted Vendor will now be tagged with a blank Vendor.

## About this task

You can update plan reference data as long as the changes are non-destructive. If the update only
adds to or modifies existing reference data elements, it is allowed by default. However, updates to
plan reference data that could cause loss in plan data are generally disallowed. However, Admins can
disable this restriction in **Settings**. For more information, see [Remove update
restrictions](update-data-open-plan.html#Remove). Further details can be found at [Edit the Company Profile](edit-company-profile.html) .

A backup plan is automatically created to preserve data integrity whenever you make a potentially
destructive update.

Once the restriction is removed, the following updates become possible:

- You can delete items (such as Cost Objects or Accounts).
- You can re-organize your data structure (for example, you can assign a Cost Object to a
  different parent).

These capabilities allow you to continue using your current plan if your company undergoes a
reorganization.

First, determine whether it is necessary to remove these restrictions to make updates to your
plan. If your updates will not result in data loss, skip ahead to [Update an open plan](update-data-open-plan.html#Update).

## Procedure

- **Remove update restrictions**
  1. On the Apptio Planning menu, click the
     Settings button (![icon gear](../../../../../03-media/apptio-planning/resources/images/it_planning_images/icon_gear.jpg)), then click Company
     Profile.

     The Company Profile page opens.
  2. In the Settings section, select Disable Update
     Reference Data Restrictions.
  3. Select Save and Exit.

     The
     restrictions are now disabled.
- **Update an open plan**

  After making the changes to your reference data, you can enable a currently open plan to conform
  to those changes. For more information on updating reference data, see [Edit and publish reference data
  tables](edit-publish-reference.html).

  1. Navigate to Planning>Plans and select a
     plan.
  2. In the [Plan Sub-section Menu](navigate-apptio-planning.html#Plan_Sub-section_Menu) (after selecting Departments under
     Section drop-down), select All Departments (under the
     Department drop-down).
  3. Select ![three dots more menu](../../../../../03-media/apptio-planning/resources/images/icons/3-dots.jpg), and then select Update Reference
     Data.

     A dialog displays with information about your changes,
     including line-item deletions.
  4. Review your changes, then select Update.

     When you
     make the update, a backup plan is automatically created to mirror your plan prior to the
     updates.
- **About backup plans**

  Note: Plan history is not captured in a backup plan.

  If you have disabled the restrictions on updating reference data, a backup plan will
  automatically be created whenever you update reference data in an open plan. The backup plan
  contains all data from the plan prior to the update, with the notable exception of plan history.
  Additionally, if you make subsequent changes to the same plan, the backup plan will be overwritten
  with each change. At any given point of time, you essentially have a backup that preserves your data
  (and the supporting reference data) prior to your most recent update

## Related information

- <update-data-open-plan.html#Updatereferencedatainanopenplan>
- <update-data-open-plan.html#Removeupdaterestrictions>
- <update-data-open-plan.html#Updateanopenplan>
- <update-data-open-plan.html#Aboutbackupplans>
