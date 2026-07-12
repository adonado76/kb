---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "data_studio"
title: "Apply row-level security"
breadcrumb: []
source_path: "data_studio/apply-row-level-security.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Apply row-level security

◆ Applies to: TBM Studio 12.2 and later

To provide data security at the row level, you can filter tables and reports based on the current
user. Rows that are not associated with the current user are hidden. Row-level security is available
on tables. Filtering at the row level was called "View Filters" in TBM Studio 11.

Watch this demo video: [Row-level Security in R12](https://community.apptio.com/videos/2248 "(Opens in a new tab or window)"). Or, browse [all Apptio
videos](https://community.apptio.com/docs/DOC-7714 "(Opens in a new tab or window)").

For information using DataLink to load row-level security data, see [Load data into the
Row-Level Security project using Datalink](load-low-level-security-data-datalink.htm "(Opens in a new tab or window)").

While all tables that can be built with Ad Hoc Query are redacted, certain legacy tables are
not.

Note: Row-Level security affects all users. Do not rely on row-level security to secure data for
Admin users, since they have access to Studio mode and ultimately can author reports that bypass it,
add themselves to the Row-Level security tables, and disable Row-Level Security entirely.

The items each user can see are specified in a separate project called Row-Level Security.
The Row-Level Security project is installed automatically when a new Apptio instance is
created. The project is used for row-level security in all projects in a domain.

To access the project, open the Settings menu ![](../../resources/images/studio_images/studioimages/icons/setting-icon.png) and click
Configure Row-Level Security.

## Configure row-level security

There are two main steps for configuring row-level security:

- Step 1: In the Row-Level Security project, create
  one or more mapping tables that identify the items (rows in a table) that each user will be able to
  view.
- Step 2: Define the view filters for the tables that will be secured by
  adding a Row-Level Security step to the transform pipeline.

We will explore configuration with an example covered in the following sections. In this example,
we configure Row-Level Security on the Cost Source and the IT Resource Towers in a simplified model.
Settings will limit visibility to business unit data based on the user. We then examine effects on
reporting from the perspective of our test user "[bob@acme.com](mailto:bob@acme.com "(Opens in a new tab or window)")" to see how the limitation to drillTo tables noted above comes
into play.

## Create the mapping tables

The mapping tables identify the items that each user can view. A mapping table must have two columns:

- ID: The user ID. The ID must match a user name in the Users table in the
  redaction project.
- Item: The name of the item a user can access as it appears in the table
  in the working project. For example, if you had a table with information about data centers, you
  would enter the name of the data center.

Note that you do not need to be concerned with the name of the table or of the name of the column
in the mapping table that contains the item. The table name and column name will be provided when
you define the filters.

You can create one or more mapping tables. If you have only one rule to control row-level
security, one table will probably be all you need. If you have more than one rule, for example users
who should be able to access all data centers, you may want to create more than one table to help
you organize the items.

In general, you will create the mapping tables outside of the Apptio application and then upload
the tables.

The mapping table shown below defines access to business units for four users. Note that
bob@acme.com is configured to have access to BU 2 alone. Also, note that rachel@acme.com has access
to two BUs.

![](../../resources/images/studio_images/studioimages/studio_bu-access_table_sui.jpg)

While it would be possible to give users who should have access to all BU's three entries (one
for each of BU 1, BU 2, and BU 3), in this example, if additional BUs were added, we would need to
keep adding entries for those users. So, in this example, we also create the BU Full Access table so
that we can give sally@acme.com access to all BU data regardless of whether additional BUs are
added.

Note that the word Admin is used in columns in this table and filters further on in this example.
This is different from the Admin's role permissions mentioned in the limitations section
above.

![](../../resources/images/studio_images/studioimages/studio_bu%20full%20access_table_sui.jpg)

## Configure the row-level security filters

To apply row-level security to a table, you must add a Row-Level Security step to the
table transform pipeline. The filter will reference the mapping tables you created in the previous
step. A filtered transform table can be added to a report and the row-level security will be in
effect for the table.

To define row-level security for a table:

1. Open the table from the Project Explorer.
2. Insert a Row-Level Security step ([How?](transform-workspace.htm "(Opens in a new tab or window)")).
3. Add entries to the filter. You can add more than one entry. Entries typically use "or" logic. If
   any one of the entries is true, the user will be able to see the entry.
   - First field: Select the column in the table that contains the items to be
     filtered.
   - Second field (intersects): Select the mapping table that contains the
     row-level security information. This is the table you uploaded in Step 1.
   - Third field: The name of the column in the mapping table that contains
     the items that a user has permission to view.
   - Fourth field (where user is): The name of the column in the mapping table
     that contains user IDs.

     Tip: Adding a Row-Level Security pipeline step will automatically add a modeling step.
     Only Modeled Tables and Editable Tables can have Row-Level Security applied to them.

Here, we see the filter for Cost Source configured with a rule that covers the regular users in
the BU Access table. The rule provides access to rows in the table where the Cost Source.BU column
values match the BU Access.BU column values where the BU Access.User ID column is equal to the user
ID of the logged in user viewing the table.

![](../../resources/images/studio_images/studioimages/studio_cost%20source_looking%20at%20row-level%20security_sui.jpg)

Now, we want to test our filter to make sure it's working. Here we see the preview filter being
used to view what rows Bob would be able to see:

![](../../resources/images/studio_images/studioimages/studio_cost%20source_row-level%20security_sui.jpg)

Now, we want to add access for Sally. To do that, we must add a formula column to the table which
has the value that appears in the "BU Full Access.Is Admin" column. That value is "Yes," so we do
this:

![](../../resources/images/studio_images/studioimages/studio_cost%20source_formulas_sui.jpg)

At this point, we modify the Row-Level Security pipeline step to use OR logic so that if the user
appears in the "BU Full Access.Is Admin" table, they have access to all rows. The following screen
shot shows this additional filter and the result of putting sally@acme.com into the preview
filter.

![](../../resources/images/studio_images/studioimages/studio_row-level%20security_cost%20source%20admin_sui.jpg)

## Row-level security in reporting

Now that we have configured Row-Level Security for our modeled tables, we want to see the effects
on reports and understand the limitation listed above. To that end, we have created a report which
has a summary of the IT Resource Towers object, a drill from IT Resource Towers to Cost Source, and
a summary of the Cost Source object. Here is a screenshot of that report being viewed via the Admin
role. Note that the drill table shows data for all Business Units.

![](../../resources/images/studio_images/studioimages/studio_demo%20reports_row%20level%20security%20demo_sui.jpg)

Before we look at what Bob would see, note that the allocations in this example include an
allocation from BU 3 to BU 2:

![](../../resources/images/studio_images/studioimages/studio_it%20resource%20towers_model_sui.jpg)

Now, we impersonate ([How?)](https://community.apptio.com/docs/DOC-6891 "(Opens in a new tab or window)") bob@acme.com to see what Bob would see. The following screen shot
shows this.

![](../../resources/images/studio_images/studioimages/studio_demo%20reports_cost%20source%20bu_sui.jpg)

## Row-level security in model overview reports

In a model overview report, a tier reflects row-level security if row-level security has been
applied to the table. However, the values in the tiers will apply only the row-level security
applied to the specific tier. In the example below, row-level security has been applied only to the
Cost Center tier. Note that the values in that tier add up to less than the $5,097,741 shown for IT
Resource Towers.

![](../../resources/images/studio_images/studioimages/studio_row-level%20security_model%20overview%20reports_sui.png)
