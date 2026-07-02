---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "planning"
title: "Financial Dimensions reference data"
breadcrumb: []
source_path: "planning/manage-financial-dimensions.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Financial Dimensions reference data

The tasks below can only be performed by users assigned to the Admin or Budget Process
Owner roles. For additional information on roles, see Frontdoor permissions and roles.

Dimensions are the essential data categories in budget line items. Many built-in
dimensions have dependencies on other dimensions (see [Reference data attribute and
dimensions dependencies](manage-reference-data.html) for more information). You can import dimensions reference data from
a .csv file or from Costing Standard and export dimensions reference data templates and table data
(see [Manage
dimensions](manage-reference-data.dita "(Opens in a new tab or window)")).

![](../../resources/images/it%20planning_images/icon_video.png)

Watch these videos from Apptio Education Services:

- [Configuring
  Reference Data: Financial Dimensions and Cost Object Permissions](https://community.apptio.com/videos/1991 "(Opens in a new tab or window)").
- [Understanding Data Hierarchies in Planning](https://community.apptio.com/videos/2244 "(Opens in a new tab or window)").

Or see all [Apptio planning video and training resources](https://community.apptio.com/viewdocument/apptio-products-video-catalog?CommunityKey=1bdb1f0b-9524-43d4-b987-5d2b8595eebf "(Opens in a new tab or window)").

## Manage Account reference data

After the initial import and configuring of your accounts, it is important to maintain your .csv
file of Accounts data, including cost pool mapping for future import updates.

In the Costing & Planning Plan navigation menu, select Configuration > Reference Data >
Account.

This data table includes the following:

- Code (required) - The unique identifier for a general ledger account, used to import
  actuals from the general ledger.
- Name (required) - The account's name.
- Parent Code - Represents your account's hierarchy. This is the code value of its
  immediate higher-level or parent account (if any).
- Category - General ledger account groups used for variance analysis. See the following
  section "[Manage Account Category reference data](#FinancialDimensionsreferencedata__ManageAccountCategoryreferencedata)."
- Cost Pool - The [ATUM
  category](../../atum/home.dita "(Opens in a new tab or window)") to which the account belongs.
- Expense Type (required) - Defines the general ledger account as an Operating (OpEx) or
  Capital (CapEx) account. If blank, the default value is OpEx.
- Group -

Tip:

- You cannot directly edit values other than cost pool values in the Account table. Maintain your
  chart of accounts data in an Excel workbook based on the .csv template, re-import, and then
  republish the .csv file as needed.
- It is recommended that you generate new .csv files from your Excel workbook rather than directly
  edit the .csv file. Treat the Excel workbook as editable and the .csv file as read only. Otherwise,
  Excel may strip off leading zeros when it opens a .csv file which can create problems with account
  numbers that include leading zeros.
- You can also substantially customize reference data dimensions and line-item tables (see [Manage custom reference data
  (dimensions, lists, and line-item tables).](manage-custom-reference.dita "(Opens in a new tab or window)")

## Manage Account Category reference data

This dimension groups your detailed general ledger accounts into a manageable list for variance
analysis. See [Analyze budget
variance](analyze-budget-variance.dita "(Opens in a new tab or window)"). 10-15 discrete values are recommended for this dimension. You may already have
something similar implemented as a custom attribute in your Account reference data.

Note: The Account Category dimension does not currently support importing from Costing Standard.
However, you can build the reference data in Costing Standard (see [Integrate with Cost Transparency](integrate-ct.dita "(Opens in a new tab or window)")).

1. In the Costing & Planning Plan navigation menu, select Configuration > Reference Data >
   Account Category.
2. Update the data table values as required:
   - Code (required) - The unique identifier for your account category or grouping (for example,
     ADMIN)
   - Name (required) - The name for your account category or grouping (for example, Facilities and
     Administration)

Here are some example Account Category reference data values:

| Code | Name |
| --- | --- |
| CAPITAL | Capital Investments |
| CONSULTING | Consulting |
| EXT-LABOR | Contract Labor |
| DEPRECIATION | Depreciation |
| ADMIN | Facilities and Office Admin |
| EMP-OTHER | Other Employee Costs |
| SERVICES | Outside Services |
| EMP-SALARY | Salaries and Benefits |
| TECH | Technology |
| TELECOM | Telecom |

## Manage Cost Center reference data

Cost Centers represent line-item attributes that map to Cost Objects.

1. In the Costing & Planning Plan navigation menu, select Configuration > Reference Data > Cost
   Center.
2. Update the data table values as required:
   - Code (required) - The unique identifier of the Cost Center (usually provided by your corporate
     finance system), used to import actuals from the general ledger and employed in plans to integrate
     with corporate finance systems.
   - Name (required) - The Cost Center name.
   - Parent Code - Represents your Cost Center hierarchy. This is the code value of its immediate
     higher-level or parent Cost Center (if any). Note that the Cost Center hierarchy is not related to
     the budget or forecast plan approval hierarchy in Apptio planning applications. Those are determined
     by Cost Object Permissions for your organization (see Manage Cost Object Permissions reference
     data.

## Manage Department reference data

This dimension represents your organization's structure. Specifically, Departments represent the
hierarchical structure of your IT organization (or whatever structure you prefer) for budget
planning and reporting. Departments are one type of Cost Object (Projects are another example of
Cost Objects). Cost Object Permissions reference data determines who can edit each Department and
who can approve budget plan submissions. See [Manage Cost Object Permissions reference data.](manage-cost-object.dita "(Opens in a new tab or window)")

Import and publish reference data for your Department using .csv-format files maintained outside
of your Apptio planning applications.

1. In the Costing & Planning Plan navigation menu, select Configuration > Reference Data >
   Department.
2. Update the data table values as required:
   - Code (required) - The unique identifier of the Department.
   - Name (required) - The Department's name.
   - Parent Code - Represents your Department's hierarchy.
   - Currency Code - The common currency for the Department. Required when multiple currencies are
     enabled (see Support for multiple currencies). The Department's common currency value should be the
     three letter ISO code for the currency. If no currency code is entered, the default common currency
     is used. • Price Group - Determines the price group for the Department for Region-based or
     Tiered-pricing models.
   - Default Cost Center Code - The default value unless a different Cost Center code value is
     provided.
   - Cost Center Code - The identifier for corresponding Cost Centers (see Manage Contract reference
     data). When importing actuals, they are allocated per Cost Center, then mapped to Cost Object (see
     Import and publish actuals). A Department can be associated with multiple Cost Centers and can
     include line items (volumes, labor, or expenses) recorded for more than one Cost Center. Add
     multiple Cost Centers to the table cell using a comma to separate them. NOTE: A Department can be
     associated with multiple Cost Centers, but a Cost Center can only be associated one Department.

SEE ALSO: [Update department hierarchy](update-department-hierarchy.dita "(Opens in a new tab or window)")

## Manage Location reference data

By defining Location, you can determine where costs will be incurred. Also, location helps define
other dimensions, such as value-added tax (VAT). See [Manage Contract reference data](manage-contract-configuration.dita "(Opens in a new tab or window)"))

1. In the Costing & Planning Plan navigation menu, select Configuration > Reference Data >
   Location.
2. Update the data table values as required: Name, Continent, and Country of
   the Location.

## Manage Variance Driver reference data

This dimension defines a configurable list of common variance drivers for your users. This
structured approach enables the effective roll-up reporting of variance drivers. See [Analyze budget variance](analyze-budget-variance.dita "(Opens in a new tab or window)").

NOTE: (for Costing Standard users): If you build the Account Category reference
data in Costing Standard then map to Account, the import from Costing Standard will import those
mappings into your Apptio planning application. See [Integrate with Cost Transparency](integrate-ct.dita "(Opens in a new tab or window)"). Variance Driver does not currently support
importing from Costing Standard.

1. In the Costing & Planning Plan navigation menu, select Configuration > Reference Data >
   Variance Driver.
2. Update the data table values as required:
   - Code (required) - The unique identifier for your variance driver (for example, TIMING)
   - Group - Determines the group for the variance driver (in development, leave blank)
   - Name (required) - The variance driver name (for example, Project Timing)

Example Variance Drivers reference data values:

| Code | Group | Name |
| --- | --- | --- |
| IMPACT | Accounting | Accounting Impact |
| TIMING | Accounting | Accounting Timing |
| RUNRATE | Operations | Change in Run Rate |
| PIVOT | Projects | Change in Strategic Investment |
| FOREX | Other | FX Impact |
| GROWTH | Operations | Growth |
| SERVICES | Operations | Managed Services Impact Timing |
| OTHER | Other | Other (<20%) |
| PROJECT | Projects | Project Timing |
| DEMAND | Operations | Resource Demand Variation |
| UNPLANNED | Other | Unplanned Items Spend |

## Manage Vendor reference data

By defining the vendor, budget owners can account for costs from external companies.

1. In the Costing & Planning Plan navigation menu, select Configuration > Reference Data >
   Vendor.
2. Update the data table values as required: Name and Group associated with the
   vendor.
