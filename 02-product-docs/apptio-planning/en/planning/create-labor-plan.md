---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "planning"
title: "Create a labor plan"
breadcrumb: []
source_path: "planning/create-labor-plan.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Create a labor plan

The tasks below can only be performed by users assigned to the Admin or Budget Process Owner
roles. For additional information on roles, see Frontdoor permissions and roles.

Planned staff labor details account for anticipated labor costs related to upcoming new hires or
internal or external engagements, and are subject to any labor costing rules that have been set up.
See [Manage Labor
Configuration reference data](manage-labor-configuration.htm "(Opens in a new tab or window)"). Managing planned staff labor details allows you to do the
following:

- Model and report on the fully burdened costs of planned labor for the full planning period.
- Follow applicable labor costing rules so that your planned labor costs are itemized and
  projected onto the correct general ledger account codes throughout the planning period.

## Before you begin

Before you begin, ensure you enable the labor planning features. See [Edit the Company Profile](edit-company-profile.htm "(Opens in a new tab or window)").

## Enter labor data

Apptio recommends that you periodically update your planned labor details with new information.
Work with planned labor details on the Labor tab, Planned page. After a planned labor resource has
started incurring costs, account for them via the Existing labor line item and remove from the
Planned items. See [Enter or import
line item data](enter-import-line.htm "(Opens in a new tab or window)").

1. In the plan menus at the top right, select a plan, a Cost Object category, and a cost object or
   cost object group.

   [Learn more about
   navigating in Planning](navigate-apptio-planning.htm#Toolbar)

   Note: Cost Center Owners can only edit their assigned Cost Centers.
   See [Manage Cost Object Permissions
   reference data](manage-cost-object.htm "(Opens in a new tab or window)").
2. Navigate to Planning > Expenses.
3. Select the Labor tab.
4. Select Planned or Existing sub-tabs.
5. Enter values, import a .csv (NOTE: Enter FALSE for the Is
   Existing Employee value to indicate a resource is planned rather than current), or edit
   labor details in the following columns:
   - Cost Object - Unique identifier per Cost Object, organized across rows
     corresponding to each Cost Object type (Departments, Services, and Projects). The Cost Object
     reference data itself may be organized into parent and child hierarchical relationships between
     departments, and if enabled, services and projects.
   - Allocations - Allows you to allocate labor to a project, Service, or
     labor pool (see [Allocate
     department labor](allocate-department-labor.htm "(Opens in a new tab or window)")).
   - Employee Type - Determines whether this rule applies to internal staff or
     external labor resources, such as vendors or contractors.
   - Role - Provides available options provided by Roles reference data.
   - Location - Provides available options provided by Location reference
     data.
   - Vendor - Determines available options provided by Vendor reference
     data.
   - Employee Name - The name of a specific labor resource, if known, or
     another unique identifier. For multiple people, you can track on aggregate and enter a team or
     function name, for example, QA Team.
   - Currency - Visible only when multiple currencies is enabled (see [Support for multiple
     currencies)](support-multiple-currencies.htm "(Opens in a new tab or window)").
   - Base Compensation - The annual base salary value for this labor resource.
     Note the following:
     - This value can be the planned gross salary of an individual, the average salary of a
       multi-person team, or some other value.
     - This value becomes the basis for labor rule calculations. If you are working with a multi-person
       team, the Base Compensation value should be the per-person average value (not the sum of the team).
       The per-person average value times the Quantity value will result in the overall cost value of the
       team.
     - The Base Compensation amount and the Quantity value (1 for a single resource) produce the
       distributed monthly compensation values per labor line, which in turn cumulatively produce the total
       base compensation value for the annual planning period.
     - On the Expenses page, Summary tab, the monthly
       compensation values per labor line are run through labor costing rules, allocated, and charged to
       the correct general ledger accounts per applicable month (see [Manage Labor reference
       data](manage-labor-configuration.htm "(Opens in a new tab or window)")). The sum of a given labor line’s resulting OpEx expenses represents the burdened labor
       rate of that labor resource.
   - Quantity - For an individual full-time labor resource allotment, enter 1.
     For fractional allotments of a resource to a Cost Center, enter a decimal value (for example, .5 for
     a half-time allotment). For a labor resource allotment that represents multiple people, enter the
     planned headcount sum.
   - Start and End Dates - These dates determine the initial per-month
     allotments of the labor resource in the current planning period. You can enter dates that precede or
     follow the active fiscal calendar but only allotments within the active fiscal calendar are
     calculated. The fiscal calendar is defined in the Company Profile (see [Edit the Company Profile)](edit-company-profile.htm "(Opens in a new tab or window)"). For
     months within the active fiscal calendar, but not within in the set date range, the Apptio planning
     application will zero out the resource allotments.
   - Description - Enter a text description for this labor resource. This is
     the same Description value displayed in the OpEx Line Items table.
   - Labor Activity Rate - This field is applicable if you are using Labor
     Activity Planning in Project Financial Planning (PFP) module. In the
     Configuration > Schema and .csv export the
     corresponding column name is Labor Rate. The value for Labor Rate gets automatically set according
     to Department Labor Activity Rate reference data. In case the value is not configured in the
     reference data this field will appear blank. The value in this field can be overridden with user
     entered value. This value indicates hourly labor rate charged for the Project when the corresponding
     resource is allocated to project.
6. Add the labor compensation adjustments, as described [here](https://help.apptio.com/en-us/it-planning/planning/plan-labor-compensation.htm "(Opens in a new tab or window)").

## Contour labor allotments per month

The monthly timeline at the right of the Labor Line Items table shows per-month tallies of
resource allotments per labor line. At the bottom, you see labor resource headcount totals per
month, and at the right column of the table, you see total labor costs per labor line, and at the
lower right, the all-up labor cost total.

The initial resource allotments per labor line are calculated by the Quantity value per month for
each month within the Start Date and End Date range. You can edit or manually contour the monthly
resource allotments.

Enter the resource allotment per general ledger line item per calendar month you want. As you do
so, the Total resource cost for the selected line item and the per-month tally will update.

Tip:

- As with other line-item views, you can add or remove columns. Place the mouse cursor in the
  column heading, click the arrow button that appears, and select an option.
- To add new line items, place the mouse cursor in the left-most column of a row, click the arrow
  button that appears, and select an option.

## View delegated project costs

If Project Financial Planning Project Financial Planningis enabled, Project Owners can delegate
project costs to department and service owners. All of these owners can show or hide delegated costs
from their financials. See [Delegate project costs](pfp/delegate-project-costs.htm "(Opens in a new tab or window)").

## View demand for labor

If Project Financial Planning or Service Demand Planning is enabled, you can make labor available
for project or service work through labor resource pools and allocations. Department Owners can
allocate to a project, service, or labor pool. These departmental allocations also appear in the
labor allocation tables of your projects and services. See [Allocate department
labor](allocate-department-labor.htm "(Opens in a new tab or window)").

## View Fully Burdened Labor Cost

Budget owners can now easily view the fully burdened labor cost directly in the Expenses > Labor
> FY total columns, eliminating the need to navigate to the Expenses > Summary section for this
information. Previously, this column only displayed Base Compensation x Quantity.

For example, in the Labor tab, you can see a labor line with a FY24 total of USD 196,888. This
amount represents the fully burdened labor cost calculated based on the configured Labor Allocation
Rules.

![](../../resources/images/it%20planning_images/3.71-1.png)

The fully burdened labor cost is the sum of the general ledger accounts generated from Labor
Allocation Rules in the Summary tab. As shown, the FY24 total in the Summary tab matches the FY24
total in the Labor tab.

![](../../resources/images/it%20planning_images/3.71-2.png)
