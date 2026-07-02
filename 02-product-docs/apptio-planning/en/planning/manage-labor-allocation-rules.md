---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "planning"
title: "Labor Allocation Rules"
breadcrumb: []
source_path: "planning/manage-labor-allocation-rules.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Labor Allocation Rules

The tasks below can only be performed by users assigned to the Admin or Budget Process
Owner roles. For additional information on roles, see Frontdoor permissions and roles.

Dimensions are the essential data categories in budget line items. Many built-in
dimensions have dependencies on other dimensions (see [Reference data attribute and
dimensions dependencies](manage-reference-data.html) for more information). You can import dimensions reference data from
a .csv file or from Costing Standard and export dimensions reference data templates and table data
(see [Manage
dimensions](manage-reference-data.dital "(Opens in a new tab or window)")).

![](../../resources/images/it%20planning_images/icon_video.png)

Watch this video from Apptio Education Services: [Configuring Reference
Data: Labor Dimensions](https://community.apptio.com/videos/1993 "(Opens in a new tab or window)").

Or see all [Apptio planning video and training resources](https://community.apptio.com/viewdocument/apptio-products-video-catalog?CommunityKey=1bdb1f0b-9524-43d4-b987-5d2b8595eebf "(Opens in a new tab or window)").

## Manage Labor Allocation Rules

Labor planning supports a rules model with which you can define conditional criteria to charge
labor expenses to specific general ledger accounts.

Tip: You must charge 100% of a labor resource's base compensation to your Salaries and
Wages general ledger code (or your organization's equivalent code). Set up this rule first. If you
want to calculate labor amortization using working days, [configure your working day calendar](configure-working-days.dita "(Opens in a new tab or window)") first.

1. Enable labor planning features (see [Edit the Company Profile](https://help.apptio.com/en-us/it-planning/planning/edit-company-profile.htm "(Opens in a new tab or window)")).
2. In the left navigation menu, select Configuration > Labor Allocation Rules.
3. Select Export > Export All on the top-right area of the page.
4. Open the downloaded .csv file and update the data values as required:
   - Account - The general ledger account code to charge for this rule. Options available are
     provided by the Accounts reference data (see [Manage Financial Dimensions reference data](https://help.apptio.com/en-us/it-planning/planning/manage-financial-dimensions.htm "(Opens in a new tab or window)")).
   - Output Value Type - A rule based on one of the following options:
     - Percent of Base Rate - Enter a percentage value.
     - Flat Value - The annual fixed amount.
   - Currency - The common currency for the labor allocation. Required when support for multiple
     currencies is enabled (see [Support for multiple currencies](https://help.apptio.com/en-us/it-planning/planning/support-multiple-currencies.htm "(Opens in a new tab or window)")). The department's common
     currency value should be the three-letter ISO code for the currency. If no currency code is entered,
     the default common currency is used.
   - Value - Percentage to allocate to the account.
   - Labor Amortization Method - Choose one of the following options:
     - Straight Line Even Period -Select this option to amortize evenly across each months.
     - Straight Line Using Calendar Days - Select this option to amortize according to the number of
       days in a given month.
     - Straight Line Using Working Days - Select this option to amortize by calculating a weighted
       average of actual work days per month. See the [examples](https://help.apptio.com/en-us/it-planning/planning/manage-labor-allocation-rules.htm#Labor "(Opens in a new tab or window)") in the following section.
   - Exclude from Labor Calculation –
     - - By default, rules are included from the Labor FY Total calculation. To exclude a rule, check the
         corresponding checkbox.
       - When a rule is marked for exclusion, it will not impact the FY Total displayed in the Labor tab
         but will continue to generate a financial line item on the Summary tab.
       - When importing or exporting Labor Allocation Rules data using a .csv file, set "Exclude from
         Labor Calculation" to FALSE to include the rule in the fully burdened labor calculation, or TRUE to
         exclude the rule.
5. Optionally, click in the Advanced Rules cell to add advanced logic to your rule. Add additional
   clauses you want to subsequent rows in the Advanced Rules table, then click Done. This data table
   includes the following:
   - Employee Type - Determines whether this rule applies to internal or external (such as vendors or
     contractors) labor resources. • Role - Available options for this dimension are provided by Roles
     reference data.
   - Location - Available options for this dimension are provided by Location reference data.
   - Vendor - Available options for this dimension are provided by Vendor reference data.
   - Currency Code - The common currency for labor allocation. Required when support for multiple
     currencies is enabled. The department's common currency value should be the three-letter ISO code
     for the currency. If no currency code is entered, the default common currency is used.
   - Value - The default annual labor compensation adjustment to apply. If the Rate Type value of the
     rule is Percentage, you must enter a percentage value here. If the value is Fixed, you must enter a
     specific amount here.
   - Click Publish to make the labor allocation rules available in planning and spend
     management.
6. Now, Configuration > Labor Allocation Rules, and then import the updated .csv file.

## Labor Allocation Rules and Advanced Rules examples

A basic rule sets the default general ledger charge, and an advanced rule, when its criteria are
met by a specific labor resource, supersedes the basic rule's general ledger charge. Accounts with
advanced rules appear with number in the Advanced Rules column.

The following are basic rule examples:

- Charge 10% of an employee’s annual base compensation amount to a Payroll Tax Charge general
  ledger code.
- Charge a fixed $250 per year per employee to a Training and Development general ledger
  code.

You can define advanced rules. These rules apply labor dimension conditions to determine how
costs get charged to specific general ledger accounts. For example, charge a fixed $250 per year per
employee to a Training and Development general ledger code. Then, add two clauses to make it
an advanced rule:

- If the labor resource's Location is Seattle, increase the Training and Development
  amount to $300.
- If the labor resource's Location is Boston, increase the Training and Development
  amount to $400.

The previous examples describe rules as they apply to a single labor resource (or a full-time
equivalent), but they also apply in the cases of fractional (part-time) or multiple (fungible) labor
resource. For example, charge a fixed $250 per year per employee to a Training and
Development general ledger code. Then, add a clause to make it an advanced rule.

For example:

- When the rule is run against a labor resource who works half-time, the resulting charge will be
  $250 x 0.5, or $125.
- When the rule is run against a labor resource that represents a team of 3 FTE members, the
  resulting charge will be $250 x 3, or $750.

The Apptio planning application calculates the general ledger charges per month. The sum of the
monthly values produces the cost value of the annual labor resource. Although you work with the cost
amounts per year of labor resources when managing rules and viewing current and planned labor
resources, the general ledger charges are calculated per month.

## Labor Amortization Method example

The following example assumes a 365 day calendar year:

| Amortization method | Base annual rate | Jan. | Feb. | Mar. |
| --- | --- | --- | --- | --- |
| Straight Line Even Period | $100,000 | $8,333 | $8,333 | $8,333 |
| Straight Line Using Calendar Days | $100,000 | $8,493 | $7,671 | $8,493 |

The following example assumes a custom work day calendar was used to calculate the amortized
expense. January and July have three pay periods while the remaining months have two:

| Amortization method | Base annual rate | Jan. | Feb. | Mar. |
| --- | --- | --- | --- | --- |
| Straight Line Using Working Days | $100,000 | $11,538 | $7,692 | $7,692 |
