---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "data_studio"
title: "Configure machine learning for cost pools"
breadcrumb: []
source_path: "data_studio/configuremachinelearning.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Configure machine learning for cost pools

Applies to: TBM Studio 12.7 and later

Apptio uses machine learning techniques to predict the applicable cost pool based on the account
information. A new pipeline step, Assign Cost Pools, is automatically added
to tables that are mapped to Chart of Accounts Master Data using Map
Columns.

Prerequisites

- Costing Standard Cost Source Component, upgraded to 12.6, or newer.
- Chart of Accounts: Account information is typically available from a financial system.
  - Required columns are Account, Account Description and Expense Type. However, columns Account
    Group and Account Subgroup are recommended.
  - Use the Map Columns step with a destination of Chart of Accounts Master
    Data.

## Map Chart of Accounts to cost pools

Complete the following tasks.

## Configure the Assign Cost Pools step

On the Chart of Accounts table for which you want to map to cost pools, add the **Map
Columns** step. Choose a destination for the Chart of Accounts Master Data. See [Map Columns](mapcolumns.htm "(Opens in a new tab or window)") for more information on how
to use Map Columns.

The Assign Cost Pools step appears.

![](../../resources/images/studio_images/studioimages/studio_charts%20of%20accounts_map%20columns.png)

## Configure reference data

1. When you first use Assign Cost Pools, you employ the Configuration tab.
   Click Configure Now to obtain the reference information on cost pools. The
   screen automatically refreshes after all information is retrieved. The ATUM Cost
   Classification Reference List and OpEx CapEx Classification
   Reference tables appear under the Reference Tables category at the left.
2. Check in these new tables and your chart of accounts table at the same time.

   ![](../../resources/images/studio_images/studioimages/studio_chart%20of%20accounts_map%20columns.png)

   If an update is available, a notification will appear on the
   Configuration tab.
3. To update the reference tables at any time, check out the table you want to update. Navigate to
   the table or click on the reference data you wish to update on the
   Configuration tab. Updates display with a yellow warning icon.
4. Click Update Reference Data.

   ![](../../resources/images/studio_images/studioimages/studio_reference%20table_update.png)

## Update the model

Machine learning relies on a model that produces predictions of cost pools based on your data.
When you initially configure your table with Assign Cost Pools, the latest published version is
identified and used to predict your data. This model will not update over time for this table unless
you take explicit action.

1. To see the model you are on, click the Configuration tab.
2. If an update is available, a notification will appear on the Configuration tab. To update to the
   latest version, click Update Now.

   Note: Reverting the document will return the
   model to the checked-in version.

## Adjust confidence

Confidence is intended only for advanced use. Adjusting the confidence upwards will generally
reduce the number of records assigned. To adjust the confidence:

1. Click the Configuration tab.
2. Edit the number in the Min Confidence % box, then press
   Enter.
3. Save the table. The mappings will update.

## Use the Tree Map and Preview pane

Use the tree map to explore the data being assigned. The following images show all available
iterations.

To the right of the tree map are KPIs that indicate how rows are assigned. When a user interacts
with the tree map, the KPIs and the following table update. Filters applied directly to the table
will not affect the tree map.

The tree map has the following elements and capabilities:

![](../../resources/images/studio_images/studioimages/studio_chart%20of%20accounts_assign%20cost%20pools.png)

(1) Tree map visualization - Click any box to filter the entire
Overview tab of this step by the value in that box.

The tree map has the following levels: **Cost Pool > Cost Sub Pool > Account Group > Account
Subgroup > Account**. If any level is unavailable due to not being mapped, the tree map will
automatically drill down to the next level.

After drilling down, the path used to filter down to the current level appears and all prior
levels become links. Click All to return to the default, unfiltered view.

The assignment status in the tree map is color-coded (see step 4) and, when there is a mix of
automatically and custom-rule assigned rows, a blend of the two colors appears:

![](../../resources/images/studio_images/studioimages/studio_assign%20cost%20pools_overview.png)

(2) Description - Hover over boxes in the tree map to see descriptions and
the row count within that box by the method of assigning it. When displaying Account, it will show
Account Description.

Note: The hover is slightly delayed to avoid blocking your ability to interact
with the table quickly.

(3) Create Rule - This button becomes enabled when you filter at least one
customer-provided value. If all columns are filled out, this occurs after you click an Account
Group. Created rules will apply to all rows in the customer-provided group, and therefore, may
impact more rows than appear on the tree map.

After you click Create Rule, navigate to the Rules
tab to finish configuring the rule.

(4) KPIs - The Key Performance Indicators (KPIs) at the right show how
many rows are assigned and by what method. The percentages are rounded normally. The colors on the
KPIs are a legend of the colors in the chart.

(5) Table - The table shows all rows that match the state of the tree map.
To further filter the table, enter text in the Search field before each header. You can also
right-click on any value in the table and choose Filter by value to add text
into the Search field.

Options include:

- By default, the table is not sorted. Click on the headers to show options to change the sort.
  Any action that changes the status of rows in the table will immediately update the table and
  reapply the sort.
- The table allows changes to individual rows. Rows are identified by all their values, so if
  there are identical rows, they will be treated as one. Click cost pool or
  sub pool to see all available mappings. Choose an option to create a rule for
  that row.
- To assign a cost pool to a row, click the Cost Pool or the
  Cost Sub Pool column. The Assign To menu appears and
  shows all the list of cost pools and cost sub pools available for selection.

(6) Status - The Status column has five possible states:

- Unassigned
- Conflicts
- Automatic
- Rule
- Verified

The colors match the KPI legend next to the tree map except for verified ones, which are dark
green. Also, you can interact with the Status column to change the status of
each row.

Options include:

- Click the Status column value icon when it is automatically assigned or
  custom rule is assigned to verify that row. Verified rows have locked values and will not change
  even if they are automatically assigned cost pool changes.
- Click on Conflicts to verify that row.
- Click on Unassigned to show the same menu available on the Cost Pool and
  Cost Sub Pool columns.

## Create and manage rules

Use rules to set the cost pool and cost sub pool for rows in the table that can be applied based
on values in rows. Rules continue to apply to all uploads in that version of the table.

The Rules table is in the upper left of the Rules tab. By default, it
contains the name of the rule and row counts that match the rule criteria, broken out by how the
rule was applied.

![](../../resources/images/studio_images/studioimages/studio_assign%20cost%20pools_rules.png)

To see options to show or hide columns, right-click on the header.

## Create a new rule

Rules apply conditions to the table and then assign a cost pool.

1. Select New Rule to create a rule with no conditions and cost pool
   assignment.Use a rule name and description to help track the decisions made in each rule.

   Use a
   rule name and description to help track the decisions made in each rule.
2. Edit the rule.

## Edit a rule

To edit a rule manually, add conditions and select the criteria on which to select.

- Right-click on a value in the table, then click Add to Rule to add
  another criterion to the rule. If no rule is selected, it will create a new rule. Then, add the
  criterion.

  Note: Before you remove a mapping in Map Columns that is used by rules, be sure to remove
  that criteria from the rules. If you remove a mapping and are unable to adjust your rules as you
  want, add the column back, remove that column from rules, then remove the mapping again.

## Apply rule conditions

Condition operators follow this logic:

| Name of operator | Description | Example |
| --- | --- | --- |
| Equals | Use for an exact match. | Expense Type *Equals* OpEx |
| Contains | Use for values that include your typed text but may also include other information. | Account *Contains* 2111 |
| Starts With | Use when you know what your value starts with. | Account Description *Starts With* Salary |
| Ends With | Use when you know what your value ends with. | Account Description *Ends With* Benefits |
| Is In | Use when your value is one of the listed comma-separated texts. | Account *Is In* 2111,2112 |
| Not Equals | Eliminates rows that don’t match the text you enter. | Expense Type *Not Equals* CapEx |
| Does Not Contain | Eliminates rows that don’t contain the text you enter. | Account Description *Does Not Contain* Maintenance |
| Does Not Start With | Eliminates rows that don’t start with the text you enter. | Account *Does Not Start With* ACCT\_ |
| Does Not End With | Eliminates rows that don’t end with the text you enter. | Account *Does Not End With* 23 |
| Is Not In | Eliminates rows that don’t match one of the lists of text strings you enter. | Account *Is Not In* 2111,2112 |
| Is Null | Use when your value is empty. | Expense Type *Is Null* |
| Is Not Null | Use when your value is not empty. | Expense Type *Is Not Null* |

NOTES:

- You can add conditions in the same column twice. However, after saving a rule, conditions will
  be condensed into an Is In or Is Not In using
  wildcards to address other permutations.
- Columns only operate either by positive matches (Is In, Equals, Contains, and so on) or by
  negative matches (Not Equals, and so on).
- When Is Null is used in a column, that column may not be used for other
  operators.
- Rules may only be created or edited in the trunk branch. Therefore, to create or edit rules,
  merge your table and then complete the edits.

## Resolve rule conflicts

When more than one rule is applicable to one or more rows and no rule is more specific than the
other, the row(s) will be set to Conflict status and no cost pool or cost sub
pool are assigned to the row(s). Conflicting rules are listed in the
Conflicts tab.

A conflicting rule can be resolved in one of two ways:

- Select the rule you want to update from Select a Rule, modify a
  condition(s), then click Update Rule.
- Right-click on the rule you want to supersede, then select Verify. This
  will cause the chosen rule to overrule the other rules in which it was in conflict.

## Verify rows

You can verify that any row assigned to a cost pool was manually reviewed. Doing so will
supersede any other way to change the row. The row may be verified regardless if the assignment was
completed through machine learning or through manual intervention using rules. Changes to the model
will not affect verified rows.

## Assign Cost Pools step and versioning

Tables containing the Assign Cost Pools step can be time versioned like any other table. For more
information, see [Version a
table](version_table.htm "(Opens in a new tab or window)").

## Branch or rollback

If you roll back a project in check in history, the rules will be returned to the state they were
in at that time. Any future-added rules will default to a higher automatic number as reflecting the
rules that have been created thus far.

Rules can only be created or edited in the trunk branch. Therefore, to create or edit rules,
first merge your table and then complete any edits.

SEE ALSO:

- [Map Columns](mapcolumns.htm "(Opens in a new tab or window)")
- [Assign cost pools with machine
  learning](assigncostpools.htm "(Opens in a new tab or window)")
- [Frequently asked questions about
  Map Columns](faqmapcolumns.htm "(Opens in a new tab or window)")
