---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "admin"
title: "Implementing Cost Source Detail with performance in mind"
breadcrumb: []
source_path: "admin/configurecostsource.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Implementing Cost Source Detail with performance in mind

We frequently configure Cost Source to be as granular as possible, and forget to
determine whether or not we use or need that granularity. Most standard reports and allocation
strategies do not require or reference the full range of elements we typically see in general ledger
type files that back our Cost Source Master Data table. Increased granularity often does not improve
our reporting, but it always decreases its performance.

The purpose of this article is to discuss ways to reduce unnecessary granularity.

## Architectural considerations

Before reviewing options, first determine the following:

- Which columns and what level of granularity do I need to support allocations? For example,
  columns used in drivers, filters, and data relationships in allocations out of Cost Source.
- Which columns and what level of granularity do I need to support reporting?

While columns are the simplest way to think of granularity in Cost Source or other modeled
tables, required granularity may in some cases be a subset of values within those columns. In such
cases, it may be possible to create a column which omits superfluous values.

## Group rows to eliminate unnecessary data elements

If the granularity needed to support allocations and reporting is substantially less than the
granularity in the Cost Source already, then this is the best option.

A common example of excessive granularity is the transaction date, or other transaction-level
information. Consider the following scenario to visualize this. If we want to see how much a given
Cost Center is spending in each Account, we do not need the full 6-row table ([High-granularity table](#ImplementingCostSourceDetailwithperformanceinmind__High-granularity_table)). Grouping on the data elements we
need does not leave us with any less information to make our decision, but it reduced our row count
by almost 50% ([Low-granularity table](#ImplementingCostSourceDetailwithperformanceinmind__Low-granularity)). The performance
benefit is even larger when working with the tens of thousands of rows often present in the
financial data we consume.

## High-granularity table

| Cost Center | Account | Amount | Transaction Date |
| --- | --- | --- | --- |
| CC123 | 80001 | $400 | 4/2/17 |
| CC123 | 80001 | $585 | 4/3/17 |
| CC123 | 90001 | $500 | 4/2/17 |
| CC456 | 80001 | $450 | 4/2/17 |
| CC456 | 80001 | $400 | 4/3/17 |
| CC789 | 90001 | $500 | 4/2/17 |

## Low-granularity table

| Cost Center | Account | Amount | Transaction Date |
| --- | --- | --- | --- |
| CC123 | 80001 | $985 | {Various} |
| CC123 | 90001 | $500 | 4/2/17 |
| CC456 | 80001 | $850 | {Various} |
| CC789 | 90001 | $500 | 4/2/17 |

## Use stand-alone tables for full-granularity reporting

Note: This is an advanced option that requires the creation of custom reports, or the modification
of out-of-the-box reports. This option is recommended only when granular, line-level reporting is
necessary.

When there is a business requirement to report on detail beyond what is necessary to support
allocations, then the best option is a stand-alone *detail* table. This is the simplest
solution, and it prevents mistakes in the future, such as creating a report that is overly
detailed.

In more complex scenarios where granular line-level reporting may be necessary, we can still
satisfy these use cases without severely impacting model performance. One way to achieve this is to
create a full granularity *reporting* modeled table that is not used for allocations and keeps
the standard Cost Source-modeled table grouped to only what is strictly necessary for allocation
logic. This means the data is easily available for reporting and we can use standard and custom
metrics with it as well, but our calculation time and report drills are only minimally impacted.

![](../../resources/images/studio_images/studio_cs_modeled_table_750x394.png)

![](../../resources/images/studio_images/studio_full-granularity_report_modeled_table_750x386.png)

## Use a *Cost Source Detail* table to support allocations

If you need granularity in Cost Source to support allocations to modeled tables above Cost
Source, then you can insert a *Cost Source Detail* table between Cost Source and those
objects.

Note: If you create new reports with tables showing the relationship between Cost Source Detail and
other modeled tables higher in the model, this can erode the calculation benefits.

You can create a Cost Source Detail table by using a transformation of Cost Source.

To transform Cost Source:

1. In the Home tab, select New > Table.
2. Enter the Name and Category for the new table, and then select OK.
3. When the Source step opens, select Existing Table.
4. From the Input Table drop-down, select Cost Source Master Data as the source.

The processes below summarize creating a Cost Source Detail table:

- To set the object identifier for Cost Source Detail, select the columns that make the original
  identifier. These contain the necessary granularity.
- Cost Source Detail is the base of the model and allocates into Cost Source.
- To set the object identifier for Cost Source, select the columns to make an *optimized
  identifier*. The optimized identifier is a reduced version of the original identifier, and
  contains only the necessary fields to allocate to Cost Source Detail.
- Cost Source allocates into the financial layer.

After you have set identifiers, drivers and allocations need to be adjusted to pass costs from
Cost Source, through Cost Source Detail, and from there to the remainder of the financial layer. The
process of adjusting drivers and allocations varies between implementations, so specific steps are
difficult to outline in this article. In summary, drivers and allocations that are being allocated
out of Cost Source Detail should have the exact same currency amounts in the object's metric that
they had when they were being allocated from the Cost Source object.

![](../../resources/images/studio_images/studio_cs_base_of_the_model_750x276.png)

![](../../resources/images/studio_images/studio_csd_allocates_to_financial_750x438.png)

By allocating through Cost Source Detail, users can keep the extra granularity in the detail
object while preventing Cost Source from being too granular.

## Use a *Cost Source Detail* table below Cost Source

If the Cost Source granularity needed to support specific reporting requirements exceeds what is
needed to support allocations to objects, then creating a Cost Source Detail table below Cost Source
is an option. Reports which need the extra granularity must be changed to point to Cost Source
Detail instead of Cost Source.

The process is similar to [Use a Cost Source Detail table to support allocations](#ImplementingCostSourceDetailwithperformanceinmind__UseaCostSourceDetailtabletosupportallocations), but simpler in that there is
typically less labor required to implement the changes if all the allocations between Cost Source
and objects in the financial layer do not change.

Depending on the status of a project, we recommend you use a configuration where Cost Source
Detail falls below Cost Source. This is because the farther a project is in development, the more
time it takes to make changes to put Cost Source Detail above Cost Source. If a project is new,
design the model so that Cost Source feeds into Cost Source Detail. If you configure the model so
that Cost Source Detail is the bottom object, keep in mind the following risks.

Note:

- If users create new reports with tables showing the relationship between Cost Source Detail and
  other modeled tables higher in the model, this can erode the calculation benefits.
- If the requirements change and you need to use additional detail to support allocations, then
  you may need to move Cost Source Detail above Cost Source.

  ![](../../resources/images/studio_images/studio_csd_base_of_the_model_750x354.png)

  ![](../../resources/images/studio_images/studio_cs_allocates_to_financial_750x432.png)

## How to report on detail

By design, the use of Cost Source Detail on the reporting surface should be limited to a summary
table. This allows users to take advantage of the extra granularity within the object, without
experiencing reduced performance caused by a drill into the object. If business requirements change
and the need to drill into the Cost Source Detail object arises, we recommend that you reach out to
your CSM to further review possible options.

## Summary

For an easy reference as to what approach to take when discussing Cost Source Detail, refer to
the following chart:

[![](../../resources/images/studio_images/studio_cs_or_csd_approach_diagram_thumb_720_0.png)](../../resources/images/studio_images/studio_cs_or_csd_approach_diagram.png "(Opens in a new tab or window)")

To learn more about creating custom objects, drivers, and reports, visit TBM Studio's R12 [Knowledge base](https://community.apptio.com/community/apptio/product-central/cost-transparency "(Opens in a new tab or window)").

Note:

- Remember that the purpose of the data in Apptio is to populate reports that help drive
  decisions. If a data element cannot help you make a decision or allocate costs, then it is not a
  good candidate for inclusion in an identifier.
- Seeing *{various}* is not necessarily a sign of bad configuration, especially when
  configuring to improve performance.
- When making exceptions to standard granularity recommendations, or adding new objects and
  reports, pursue the least invasive options first. From there, you can increase granularity to the
  desired level.
- Keep in mind that Costing Standard is not an accounting system. Most analysts who could make use
  of extremely granular transaction-level data already have access to that information. The level of
  detail needed for cost modeling, allocations, and strategic business decisions is often much
  less.
