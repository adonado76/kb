---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "planning"
title: "Force a plan to use updated reference data"
breadcrumb: []
source_path: "planning/force-plan-use.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Force a plan to use updated reference data

When an Admin or Budget Process Owner updates dimensions in reference data, existing plans do not
get updated simultaneously. For information on updating dimensions, see [Reference data dimensions](manage-reference-data.html "(Opens in a new tab or window)")
and select the appropriate dimension category link. Plans are associated with a snapshot of
reference data. The Admin or Budget Process Owner can view the specific reference data update that
has been made, and then proceed with updating the plan to use the most current reference data.

Note: You can disable the restrictions on updating data in an open plan. However, such updates carry
the risk of data loss. For more information, see [Update Reference Data in an Open Plan](update-data-open-plan.htm "(Opens in a new tab or window)").

## View and update reference data

1. Navigate to Planning > Plans and select the plan.
2. In the upper-right corner of the page, select Update Reference Data.
3. Review the reference data details. If the data is up to date, select Cancel. Else, select
   Update to update the new information.

## View and update reference data for an Open plan

You can update reference data for a plan in the New or Open state. A plan in the New state can
apply all reference data updates. A plan in the Open state can apply the following updates from
reference data:

- Create leaf Cost Objects
- Create custom dimensions
- Add or modify dimension attributes
- Add values to a dimension

If your plan is in the Open state and needs additional updates, you can accomplish this with the
following work-around. Note that you may want to turn off notifications in the Company Profile so
that when you make changes, notification emails are not sent to Budget Process Owners. See [Edit the Company Profile](edit-company-profile.htm "(Opens in a new tab or window)").

1. Archive the plan, giving it a new name (see [Archive, restore, or delete plans](manage-plans.htm "(Opens in a new tab or window)").)
2. Create a plan and name it the original plan name (see [Create a plan or forecast](create-budget-plan.htm "(Opens in a new tab or window)")). The new reference data is
   automatically used in the new plan. A reminder: if you turned notifications OFF, turn them back
   ON.
3. Open the new plan (see [Open a
   plan or a forecast](open-plan-forecast.htm "(Opens in a new tab or window)")).

Currently, it is not possible to update a part of reference in a plan. On selecting the **Update
Reference Data** option on the Plan, the admin is presented with details regarding the dimensions
that will be updated, how many lines will be modified, deleted if user proceeds with applying the
updates. The Admin can then decide to proceed with the reference data update or not.
