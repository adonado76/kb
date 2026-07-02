---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Analyze labor headcount"
breadcrumb: []
source_path: "it-planning/planning/analyze-labor-headcount.html"
images:
  - "resources/planning_images/itp_analyze-labor-headcount.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Analyze labor headcount

Once labor data is present, you can analyze labor headcount via the Summary page.

1. Ensure the labor planning features are enabled. See [Edit the Company Profile](edit-company-profile.html "The Company Profile allows Admin and Budget Process Owner users to configure application-wide settings that customize the display, enable or disable features, and define workflow behavior across Apptio Planning.").
2. In the Plan section menu, select Departments. See [Navigate in Apptio Planning
   applications](navigate-apptio-planning.html).
3. In the Plan sub-section menu, select a specific department or All
   Departments.
4. On the Component menu, select Planning. See [Navigate in Apptio Planning applications](navigate-apptio-planning.html). > Summary.
5. Select the Headcount tab.
6. Optionally, apply a different layout to the page by selecting a layout option from the upper
   right.

Unlike the financial analytics of OpEx or CapEx financial values, labor headcount analytics use
labor headcount as the unit of measure rather than financial values:

![image](../../../../../03-media/apptio-planning/resources/planning_images/itp_analyze-labor-headcount.png)

Note: The color-coded variance against labor targets appears only if labor targets are set. See
[Set labor headcount
targets](set-labor-headcount.html).

## Compare labor headcount

You can now compare the Labor data between two plans.

1. Ensure the Enable New Expenses Page Experience (Beta) option. See [Edit the Company Profile](edit-company-profile.html "The Company Profile allows Admin and Budget Process Owner users to configure application-wide settings that customize the display, enable or disable features, and define workflow behavior across Apptio Planning.").
2. Navigate to Expenses > Labor tab. Enable the
   New View toggle.
3. Expand the ![image](../../resources/images/it%20planning_images/three-dots_31x23.png)icon and select Compare Shortcuts
   option. See [Compare shortcuts](compare-versions-plans.html).

   ![image](../../resources/images/it%20planning_images/compare-shortcuts.png)
4. In the Manage Compare Shortcuts popup, select the plans that you want to compare and click the
   Compare button. The following page appears.

   ![image](../../resources/images/it%20planning_images/new-view.png)

   ![image](../../resources/images/it%20planning_images/vendor-location-labor.png)

   Note: The default grouping is by Cost Object. But if you wish to
   analyze the variance by other dimensions you can update the table view by adding more column groups.
   The above screenshot has default column grouping updated by adding Vendor and Location column group
   so that users can drill down in the grouped column view to understand headcount variance by vendor
   and location.
5. Click + Add Comparison to see the labor plans selected in step 3 above.
   If multiple years of data is available for the comparison, the user must select one year at a time
   for the comparison.

   ![image](../../resources/images/it%20planning_images/select-labor-plan.png)

   The plan comparison automatically updates the layout to
   Group by Cost Object.
6. Choose the appropriate plan and select Compare. The users can use this
   view to compare the labor headcount for different plans.

   ![image](../../resources/images/it%20planning_images/compare-lp.png)
7. To add additional plans for comparing, select any monthly column, and then choose Add
   comparison option.

   ![image](../../resources/images/it%20planning_images/add-monthly-comp_584x263.png)

   ![image](../../resources/images/it%20planning_images/monthly-add-comp_471x273.png)
8. Choose the appropriate values and click Compare. The additional plan is
   added to the selected month for comparison, as shown.

   ![image](../../resources/images/it%20planning_images/compare-monthly.png)
9. To add remove any plan from the comparison, select on that column, and choose Remove
   comparison.

   ![image](../../resources/images/it%20planning_images/remove-comparison.png)

You can add and remove comparisons multiple times, for different plans and alignment methods.
When there are no values for a matching fiscal year, then an error message will appear.
