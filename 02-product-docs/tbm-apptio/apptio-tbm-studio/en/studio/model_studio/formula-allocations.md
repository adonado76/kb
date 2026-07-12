---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Formula allocations"
breadcrumb: []
source_path: "studio/model_studio/formula-allocations.html"
images:
  - "resources/images/studio_images/studioimages/studio_diagram_example_allocation.jpg"
  - "resources/images/studio_images/studioimages/studio_diagram_fictional_tables.jpg"
  - "resources/images/studio_images/studioimages/studio_diagram_from_to_tables.jpg"
  - "resources/images/studio_images/studioimages/studio_formula_alloc_source_and_size_table.jpg"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Formula allocations

**Applies to**: TBM Studio 12.0 and later

Use the Formula option to enter a custom formula to control the allocation. This formula will run
on the table that receives money from the allocation. The formula has two special concepts not used
by other formulas within Apptio: these concepts are SOURCE keyword and the ~ operation.

The SOURCE keyword represents the amount of money that is being allocated from the source object.
The job of an advanced allocation formula is to take the SOURCE currency amount and determine how
much should go to each matching row for the destination object. Therefore, the formula must include
the SOURCE keyword to have a useful result.

The ~ operation allows you to modify a column reference to get its total value against matching
rows, instead of the value for the current row. When your formula is evaluated against the target
table's receiving row, you can reference any column in that table to get the value of that column
for your current row. However, the SOURCE money is typically allocated across multiple rows. The ~
operator, combined with a column name, gives you the total of a column for all other rows that match
the same SOURCE money that is being distributed to your row.

For a simple allocation with no data relationship and no filters, this is the same as the total
of the column. As you add filters, you filter out rows from the set included in the ~ operator.
Similarly, if you have a data relationship defined, the only rows included in the ~ operation will
be rows with the same values in the columns used for the data relationship as the current row. This
operator symbol can be thought of as having a similar meaning to the Sum or SumIF functions.

## Example

Imagine you have no filters, no data relationship, and the following formula:

> `=SOURCE*({Servers.Size}/~{Servers.Size})`

Since there are no filters and no data relationship, SOURCE represents all money in the source
object. Similarly the ~ operator is equivalent to the SUM operator. So, in this simplified case, the
above formula is equivalent to:

> `=SOURCE*({Servers.Size}/SUM({Servers.Size}))`

This formula computes the percent of a column that exists in the target row. This percentage of
the SOURCE value is then allocated.

Note: When you add filters and data relationships, the ~ operator and SUM function provide different
results.

For some fictional tables, we can compute SOURCE and ~Size as follows:

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio_diagram_from_to_tables.jpg)

In this case, every row in the To table will compute its cost as being $1300/210 \* Size. This
example will get more interesting in later sections.

This is similar to how weighting behaves in Apptio when using the Weighting distribution option.
If you leverage the Ratio function, then you will get the same behavior. The Ratio function ensures
that when the Servers.Size column is **0** for all rows, then they receive an even distribution.
This gives the following formula:

> `=SOURCE*Ratio({Servers.Size},~{Servers.Size})`

Advanced allocation formulas can be combined with filters on the From table. When you define a
filter on the From table within your allocation, the SOURCE value in your advanced allocation will
simply filter out a set of rows, and not include the costs from those rows in the value of the
SOURCE keyword.

## Example

Imagine we take our earlier formula:

> `=SOURCE*({Servers.Size}/~{Servers.Size})`

and put it on an allocation line with a From filter of Data Center != SEA. We change our SOURCE
VALUE as follows:

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio_formula_alloc_source_and_size_table.jpg)

Notice that the allocations behavior modifies the SOURCE value only, and now allocates $1200
dollars instead of $1300.

Advanced allocation formulas can be combined with filters on the To table. When you define a
filter on the To table within your allocation, your formula will simply not be run on rows that do
not match the filter. Those rows will receive $0 from the allocation. These rows will also not be
included when computing the ~ value for a column.

## Example

Imagine we take our earlier formula of:

> `=SOURCE*({Servers.Size}/~{Servers.Size})`

and put it on an allocation line with a To filter of Data Center != SEA. We change the Value of
~Size as follows:

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio_diagram_example_allocation.jpg)

Notice that the allocations' behavior modifies the ~ values only, and now has a ~Size value of
160 instead of 210.

## Data relationship

You could create an allocation with a From filter of SEA a To filter of SEA and allocate money
only from the SEA Data Center to only servers in that datacenter. However, we do not recommend doing
this. It creates an allocation line per datacenter, and every time you add a datacenter, you would
need to add a new allocation line. The **Data Relationship** option allows you to create a single
allocation line that mimics this set of allocation lines in a maintainable manner. The Data
Relationship option allows you to constrain the rows used by the SOURCE and ~ keywords to represent
subsets of the From and To tables. These constrained subsets of cost compute their allocations
independently from one another, exactly as if they were the above independent allocations.

Each unique value in your data relationship column will result in a separate SOURCE value, and a
set of To rows. The To rows with that value in their data relationship column will receive the total
value from other rows that have the same value. This effectively slices the allocation up into
buckets for each unique value in the column. Each bucket has a source value, and a ~ value.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio_diagram_fictional_tables.jpg)

When the formula runs on a row, it uses the SOURCE and ~ values that correspond to that rows
bucket.

You can specify more than one relationship. If you specify more than one relationship, all the
relationships must match for the value to be allocated.

## Advanced allocation formulas

This section provides Advanced allocation formulas that mimic the standard distribution methods
that are available without advanced allocations formulas. These can sometimes be useful for
reference when authoring a new advanced allocation formula.

## Weighted Value allocations

> `=SOURCE*Ratio({Servers.Size},~{Servers.Size})`

**SEE ALSO**

- [Weighted Value
  allocations](weighted-value-allocations.html "Applies to: TBM Studio 12.0 and later")
- [About
  weighting and negative numbers](about-weighting-and-negative-numbers.html "◆ Applies to: TBM Studio 11.8.3.1 and later; TBM Studio 12.0 and later. The purpose of a weighting is to allocate the source number where the sum is the same in the target.")

## Standard value allocations

> `=Servers.Size`

This allocation does not reference the source currency but merely allocates a value from a column
on the receiving object.

See also [Standard Value
allocations.](standard-value-allocations.html "Applies to: TBM Studio 12.0 and later")

## Non-Standard allocations

The following distribution methods cannot be replicated using an advanced allocation formula:

- Consumption
- Recursive allocations
