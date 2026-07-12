---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Weighted Value allocations"
breadcrumb: []
source_path: "studio/model_studio/weighted-value-allocations.html"
images:
  - "resources/images/studio_images/neg-wa.png"
  - "resources/images/studio_images/studioimages/studio/stu588.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Weighted Value allocations

**Applies to**: TBM Studio 12.0 and later

A **Weighted Value** allocation distributes value based on the ratio (relative size) of the
values in a column you select from the target table. This is one of the most common types of
allocations ([Learn
more](allocate-value-in-model.html "Applies to: TBM Studio 12.0 and later")). For example, you might distribute the allocation based on the number of employees in a
business unit, the number users of an application, the number of servers in a data center, or the
number of square feet in a data center.

The following is an example weighted value by allocation:

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu588.png)

## Distribution options

There are three distribution options:

- Even
- Weight By
- Data Relationship

## Even distribution

The **Even** distribution option is the default option and is in effect when the **Weight
By** and **Data Relationship** options are not selected.

![](../../resources/images/studio_images/studioimages/studio_weighted%20value_distributing.png)

This option distributes the allocation evenly across all units identified in the target table by
the **To** property. For example, if there is an **Applications Target** table with five
applications and $100,000 is being allocated, $20,000 will be allocated to each application.

## Weight By distribution

Adding a weighting to an allocation imposes an uneven distribution of currency by referencing a
field or metric that captures the desired distribution across records in the destination object of
the allocation. Allocation weightings are used in two distinct situations:

- When there is a column in a data set that more accurately captures how units (usually dollars)
  should distribute across the records in a data set. An example of this is using depreciation dollars
  from the fixed asset ledger to weight allocations into Fixed Assets.
- When there is a lack of relevant data points by which to accurately allocate. In this case,
  weightings are used to make allocations more accurate than they otherwise would be by using data
  relationships.

## Example

Assume there are five applications with various numbers of users as shown in the table below and
$100,000 to be allocated. If no weighting is used and the dollars are evenly distributed, then each
application gets an even share of the $100,000.

![](../../resources/images/studio_images/studioimages/studio_diagram_weight%20by%20distribution.png)

In this next case, however, you want to weight the distribution by the number of users. Then, the
$100,000 would be distributed as shown below in the **Allocation** column:

![](../../resources/images/studio_images/studioimages/studio_diagram_weighted%20value%20allocation%20example.png)

Note: There are two common issues when weighting allocations:

- **Weight by non-numeric**: If you try to weight an allocation by a numeric column that
  contains at least one non-numeric value, the weighting will be ignored. To correct the problem,
  remove the non-numeric values from the column.
- **Weight by negative**: If you try to weight an allocation by a negative value, the
  allocation will fail due to a guardrail put in place to prevent calculation issues arising from
  weighing by negative values. For more information, see [About weighting and
  negative numbers](about-weighting-and-negative-numbers.html "◆ Applies to: TBM Studio 11.8.3.1 and later; TBM Studio 12.0 and later. The purpose of a weighting is to allocate the source number where the sum is the same in the target.").

There are three options by which to weight allocations:

| Weighting option | Summary | Example |
| --- | --- | --- |
| Table | Distributes the allocation based on the ratio of the values in a column from the data set backing the destination object in the allocation. | You could use the Depreciation column from your Fixed Asset Ledger to weigh your Cost allocation from the Cost Source to Fixed Assets. |
| Metric | Distributes the allocation based on the ratio of the values in the same destination object, but for a different metric.  **NOTE**: This is available only in TBM Studio 12.5 and later. | You could use the Cost allocation distribution to weigh a Budget allocation. |
| Other Driver | Distributes the allocation based on the ratio of the values in a specific driver or set of drivers into the destination object.  **NOTE**: This is available only in TBM Studio 12.5 and later. | You could use your Labor allocation into IT Resource Towers to weigh the Project allocation into IT Resource Towers |

**Ignore Insignificant Weights**

![image of ignore insignificant weights checkbox](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/neg-wa.png)

For weighting columns on an
allocation, if small weights fall outside a configurable range, then treat them as
zero.

to disable: -Ddisable.allocation.weighing.range=true

to set range:
-Dallocation.weighing.range=1000000000

This can be read as weights that are 1
billion times smaller than the biggest weight, per allocation key, are treated as
zero.

## Data Relationship

The **Data Relationship** option distributes the allocation evenly across the units that match
the values in a column in the source table with the values in a column in the target table. For
example, assume the source table includes information about applications. Both the source and
destination tables include an **Application Category** column. One of the categories is
identified as **Databases**, but there are two database applications: Oracle and SAP. The value
from the Database entries in the source table would be aggregated and allocated evenly to the
Database entries in the target table. If $20,000 was being allocated, it would be divided into
$10,000 for Oracle and $10,000 for SAP.

Finally, you can specify more than one relationship. If you specify more than one relationship,
all the relationships must match for the value to be allocated.
