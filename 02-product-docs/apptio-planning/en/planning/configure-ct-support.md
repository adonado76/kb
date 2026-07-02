---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "planning"
title: "Configure Cost Transparency"
breadcrumb: []
source_path: "planning/configure-ct-support.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Configure Cost Transparency

Complete the following tasks to configure Costing Standard to support Planning. The tasks below
can only be performed by users assigned to the Admin or Budget Process Owner roles. For additional
information on roles, see Frontdoor permissions and roles.

1. Edit your reference data as needed. See [Manage reference data](manage-reference-data.html "(Opens in a new tab or window)").
2. Import reference data from Costing Standard. See [Integrate with Cost Transparency](integrate-ct.htm "(Opens in a new tab or window)").
3. Configure Costing Standard. To learn more, see [Costing Standard Foundation Module configuration](../../cost-transparency/configuration/moduleconfig.html "(Opens in a new tab or window)"). You will need to create a Costing Standard
   project, configure time for the project, and upload and map Costing Standard data.
4. Install the Apptio ITPF Integration and CTF-Labor components in Costing
   Standard.
5. Ensure you set up data integration with Costing Standard. See [Integrate with Cost Transparency](integrate-ct.htm "(Opens in a new tab or window)"). Apptio recommends that you
   carefully consider cadence for updates and naming conventions when integrating with Costing
   Standard.
6. Use the following instructions to configure your data sets, master data, and models.

The following table describes all the reference data required to support Planning. Each data set
includes a unique template used to map data from your raw source files into the master.

| Data set | Description |
| --- | --- |
| Account Master | Typically derived from Accounts reference data, this data includes cost pool mapping for future import updates. |
| Cost Center Master | Typically derived from the hierarchical structure of your business. This can be the same as the department list. |
| Department Master | Typically derived from the hierarchical structure of your business. |
| Location Master | (Optional) List of company operating locations used to leverage labor planning capabilities. This can be office locations, geographical regions, etc. |
| Vendor Master | (Optional) List of vendors your company contracts with to provide the services or supplies necessary to enhance labor and contract planning capabilities. |
| Asset Class Master | Used for asset planning. Contains the information needed to determine depreciation types, calculation methods, and mappings between asset class and OpEx or CapEx accounts. If you need to load the asset class master, create and load it separately. |
| Contract Type Master | Used for contract planning. Contains the information needed to determine mappings between contract types and OpEx or CapEx accounts. If you need to load the contract type master, create and load it separately. |
| Labor Role Master | Used for labor planning. Contains information for each unique labor role. |
| Labor Rate Master | Used for labor planning. Contains information needed to determine mapping between labor roles and compensation rates. |
| Labor Allocation Rules Master | Identifies allocation rules for internal and external employees used to determine their cost to the business (for example, taxes and bonuses). This data is updated in your Apptio planning application. |
| Actuals Master | Used for budgeting and forecasting. Translates general ledger actuals into the Planning template. |
| Transfer Account Type Master | Used to determine the correct allocation of money for consuming or supporting various departments or labor pools. |
| Cost Objects Permissions Master | Used to determine which users can view, edit, or approve a Cost Object. |

## Configure data sets

## Actuals data

Append general ledger actuals data to the Cost Source Master with the appropriate mappings.

![](../../resources/planning_images/studio_cost-source-master-data_append-actuals.png)

## Plan data

When installing the Planning Integration component, a series of transforms are installed.

If you experience an issue during the Date Partition step, modify the plan data format (rows or
columns).

![](../../resources/planning_images/studio_itpf-budget-transform_date-partition.png)

The following table provides the mappings and formulas required as part of appending to the Cost
Source Master. These steps address the following but additional mappings may be required:

- ITPF Labor Budget
- ITPF Labor Forecast

There are several taxonomical differences between Planning and Costing Standard, including the
translation between a Cost Center and Cost Object. For example, a Cost Object is used to define
either a department, project, service, or business unit. The translation from Cost Objects to Cost
Center must be completed for Planning to function correctly.

You must add several formulas to translate the data between the two systems. Complete the
following mapping:

1. In the ITPF Labor Budget table, add a step between the Date Partition and
   Table steps:

   ![](../../resources/planning_images/studio_itpf-labor-budget.png)
2. Update the Labor Budget table with the following formula columns:

   | Master Data field | Value |
   | --- | --- |
   | Cost Center | =Cost Object |
   | Cost Center Name | =Cost Object Name |
   | Cost Center Owner | =lookup(Cost Object, Department Master, Code, Cost Center Owner) |
   | Owner | =lookup(Cost Object, Department Master, Code, Owner) |
3. Repeat the previous steps for ITPF Labor Forecast data.

## Configure Master data sets

## Cost Source Master Data data set

A budget or forecast is considered a financial plan. Each type of plan must be appended to the
Cost Source Master Data for Planning to function properly.

![](../../resources/planning_images/studio_cost-source-master-data_append.png)

## Plan data

The following table provides the mappings and formulas required as part of appending to the Cost
Source Master Data. These steps address the following but additional mappings may be required:

- ITPF Budget Transform
- ITPF Forecast Transform

Required data mappings:

| Master Data field | Value |
| --- | --- |
| Account | =Account |
| Account Description | =Account Description |
| Account Group | =lookup(Account, Account Master, Code, Account Group) |
| Account Subgroup | =lookup(Account, Account Master, Code, Account Subgroup) |
| Amount | =Amount |
| Cost Center | =Cost Center |
| Cost Center Name | =Cost Center Description |
| Cost Center Owner | =Lookup(Cost Center, Department Master, Code, Cost Center Owner) |
| Cost Pool | =Lookup(Account, Account Master, Code, Cost Pool) |
| Cost Sub Pool | =Lookup(Account, Account Master, Code, {Cost Sub-Pool}) |
| Discretionary/Non-Discretionary | =Lookup(Account, Account Master, Code, {Discretionary/Non-Discretionary}) |
| Expense Type | =Expense Type |
| Fixed Variable | =Lookup(Account, Account Master, Code, {Fixed/Variable}) |
| Is Labor | =IF(Cost Pool IN ("Internal Labor", "External Labor"), "Yes", "No") |
| Is Project | =IF(Project ID="", "No", "Yes") |
| Is Vendor | =IF(Vendor ID="", "No", "Yes") |
| Journal ID | =Journal ID |
| Journal Line | =Line Description |
| Journal Line ID | =Journal ID |
| Owner | =Lookup(Cost Center, Department Master, Code, IT Owner) |
| Project ID | =Project ID |
| Project Name | =Project Name |
| Vendor ID | =Vendor ID |
| Vendor Name | =Vendor Name |

## Labor Master Data

The following table provides the mappings and formulas required as part of appending to the Cost
Source Master Data. These steps address the following but additional mappings may be required:

- ITPF Labor Budget to Labor Master Data
- ITPF Labor Forecast to Labor Master Data

Required data mappings:

| Master Data field | Value |
| --- | --- |
| Cost Center | =Cost Center |
| Cost Center Name | =Cost Center Name |
| Cost Center Owner | =Cost Center Owner |
| Cost Pool | =IF(Employee Type=”Internal”, ”Internal Labor”, “External Labor”) |
| Cost Center Name | =Cost Center Description |
| Cost Center Owner | =Lookup(Cost Center, Department Master, Code, Cost Center Owner) |
| Cost Pool | =Lookup(Account, Account Master, Code, Cost Pool) |
| Cost Sub Pool | =”Expense” |
| Employee Type | =Employee Type |
| Expense Type | =Expense Type |
| Hours | =720 |
| Labor Headcount | =1 |
| Labor ID | =Cost Center&&Role&&Location&&Employee Type&&Employee Name |
| Labor Name | =Employee Name |
| Location | =Location |
| Owner | =Lookup(Cost Center, Department Master, Code, IT Owner) |
| Planned Headcount | =Value |
| Position | =Role |
| Region | =Lookup(Location, Location Master, Location, Region) |
| Role Type | =Role |
| Title | =Role |
| Vendor | =Vendor |
| Weighting Factor | =1 |

## Configure models

Configure the Labor Cost, Budget, and Forecast models so that the labor plan and spend are
allocated from Cost Source to Labor, weighted by headcount.

![](../../resources/planning_images/studio_model_configure.png)

Labor financial values (such as dollars) should be allocated 100% from Cost Source to Labor.

![](../../resources/planning_images/studio_model_cost-source-to-labor.png)
