---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "admin"
title: "Lineage Demonstration"
breadcrumb: []
source_path: "admin/lineage-demo.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Lineage Demonstration

The Lineage feature is not active by default. An Administrator can enable it by
navigating to Project tab > Enable Features, and then select Show Lineage. It
can then be accessed from different entities, like Tables, Columns in Tables, Editable Tables and
Metrics Reports.

Let us walk through an example to demonstrate the power of lineage : Take Apptio One Cost project
(historically called as Cost Transparency) and pull up a simple data set in a simple model just to
get started.

Consider the Apptio Value Explorer >>Value Master data set. Here, in the data pipeline, you have
append step with a couple of tables connected, a formula step including one lookup to another table.
You also see Join step which show multiple relationships between tables. These are some of the
relationships you can quickly identify here.

![](../../resources/images/studio_images/r-notes/demo-lineage-1.png)

To explore lineage for this table, navigate to the project explorer, right-click and select
Trace Lineage for this document. A new tab for lineage appears with a fairly complex
diagram.

Blue color represents model related objects(AVE) and Tan represents reports.

The initial view is limited to a depth of 1 and will show downstream dependencies as we are
starting from a table which can be increased, based on the complexity of the relationships of your
selected entity. As the project gets very complex, accordingly you can get more depth to drill down
the relationships. You can also switch between downstream dependencies which is default if you pick
a table, or upstream dependencies which are default if you pick a report.

You can also include or exclude the sub-components or subtypes associated to the tables, model
object or reports. Select the checkbox for the subtype you want to see in your lineage diagram.
Numbers with each subtypes denotes the total count of entities present in the diagram. You can also
Select all/Deselect all subtypes using toggle subtypes.

Additional information for any entity is available by hovering over them. If you click on the
Upside Red arrow, it will show the list of entities to addon above the selected object in the
graph.

![](../../resources/images/studio_images/demo-lineage-2.png)

![](../../resources/images/studio_images/demo-lineage-3.png)

![](../../resources/images/studio_images/demo-lineage-4.png)

Similarly, click the Downside Red arrow to see the downstream entities.

Now, remove all the subtypes and select Apply. You can see a table at the top level going
into a model. Now increase the depth and apply to see more information with these two entities in
focus.

![](../../resources/images/studio_images/demo-lineage-5.png)

![](../../resources/images/studio_images/demo-lineage-6.png)

Here, a solid line means there is a direct dependency between the two entities and you can
see what that dependency is by hovering over the line. The dotted line means there is an
indirect dependency: likely other intermediate entities in between the two on the diagram. You can
double click on the dotted line to see what those intermediate dependencies are.

You will also notice that the depth to choose is increased up to level 5, which means we
increment just a couple of layers at a time. This is done to retain the same performance with each
iteration and return more information. On choosing the maximum depth, you will notice that the table
is associated with two different models, which are providing information to multiple reports.

Now with each entity right click, you get options to:

- Show Direct Dependencies: which brings the focus to the selected entities to see direct
  dependencies.
- Hide This: will remove the entity from the graph.
- Open Document: will open the document in a different tab.

![](../../resources/images/studio_images/demo-lineage-7.png)

Now that you have some understanding how Lineage works, lets go to another use case where you
wanted to look at a column and understand the impact if we change it.

Let us take Benchmark Tower Spend Transform table, and assume we are interested in a particular
column % Tower Spend. You can right click on the column and click on **Trace Lineage for this
column**.

![](../../resources/images/studio_images/demo-lineage-8.png)

In the downstream dependency, it is clear that this metric column is associated with the table
and the report known as Benchmarking Summary. On increasing the depth to maximum, we see the
following:

![](../../resources/images/studio_images/demo-lineage-9.png)

Hence, this view gives us information about what all reports and tables the column is associated
with. You may also want to see what are the entities his column is dependant on (upstream) and can
switch to "The focused entity depends on" in the right panel. Overall, this will help you to
identify the impact to get rid of this column.

## Lineage through a Report

This is another use case of lineage. Navigate to Reports , select **Vendor Insights
Spends without POs**, right-click and then choose Trace Lineage for this document. The
lineage graph appears as shown. Now, toggle subtypes and increment depth, to see that there are more
tables and relationships, and you can see the account payable table and master data set, with some
reports associated with it.

![](../../resources/images/studio_images/demo-lineage-10.png)

If you go even deeper, you will see there are more tables and relationships. The chart of
accounts is feeding the purchase order, due to the account that is associated with the purchase
order. Organizational mapping is likely due to cost centers and organizational responsibilities
associated with this table and ultimately in the reports. Again you have the ability to navigate to
both the tables, a column a calculated metric or a report.

![](../../resources/images/studio_images/demo-lineage-11.png)
