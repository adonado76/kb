---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "model_studio"
title: "Recursion allocations"
breadcrumb: []
source_path: "model_studio/recursion-allocations.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Recursion allocations

Applies to: TBM Studio 12.0 and later

The basic premise of Recursive allocation is that some value remains in one or more of the target
units after each iteration. With each iteration, the value in the target units increases and the
value remaining in the source units decreases until there is a minimum amount left in the source
units.

In a recursion allocation, the source and target objects must have identical units.

When you define a Recursive allocation, you set three parameters:

- Precision - Specifies the minimum value that must exist in the source
  table for a Recursive allocation to be executed. If the value goes below the minimum, no more
  iterations will be performed. The value is the total amount moved for the iteration, not a per-row
  amount.
- Maximum iterations - Specifies the maximum number of times the allocation
  will be repeated. If the precision value is reached before the maximum number of iterations has been
  performed, the remaining iterations will not be performed.
- Use incremental mode - When checked, the source value for each iteration
  is the total of the original value plus the value allocated to the target from the previous
  iteration. When checked at the end of the recursion, the total value of both objects will be greater
  than the original source value.

## Unique source and target tables required

You can have multiple Recursive allocations in a model, but each Recursive allocation must have
unique source and target tables and must not overlap. For example, assume you have five tables in a
model:

> A -> B -> C -> D -> E -> F

You could create Recursive allocations between tables A and C and tables D and F, but you could
not create a third Recursive allocation between tables B and E. The third allocation would overlap
the first two allocations.

## How Recursive allocation works

The basic premise of Recursive allocation is that some value remains in one or more of the target
units after each iteration. With each iteration, the value in the target units increases and the
value remaining in the source units decreases until there is a minimum amount left in the source
units.

For example, assume you have a source table and a target table each with the following units:

- Western Region
- Central Region
- Eastern Region

  -----------------------------------
- Help Desk Service
- Servers Service
- Telephone Service

The Western, Central, and Eastern regions allocate 100% of their value to themselves. The Help
Desk, Servers, and Telephone services allocate their value to the three regions, as well as to each
other. Assume that 10% of the service costs are allocated to the three regions with each iteration.
The remaining 90% of the service costs are cross-allocated among the services.

After the first iteration, 10% of the services cost has been allocated to the regions, leaving
90% of the cost in the services. After iteration two, slightly less than 20% of the cost has been
allocated to the regions, leaving a little more than 80% of the cost in the services. The iterations
continue until the specified number of iterations have been completed, or the amount left in the
services has dropped below the value entered in the Precision field. With each iteration, the
total value in the regions increases and the total value in the services decreases.

## Requirements

The following are the requirements for a Recursive allocation:

- The source table and target table must have identical units
- Some value must remain in one or more of the target units after each iteration

## Guidelines

Recursive allocations require significantly more processing power than standard allocations. To
keep processing times within reason:

- Use a limited number of Recursive allocations in a given model
- Use as few iterations as possible
- Set the precision value as high as is practical

## Distribution options

There are three distribution options:

- Even
- Weight By
- Data Relationship

## Even

The Even option is the default option and is in effect when the Weight By and
Data Relationship options are not selected.

![](../../resources/images/studio_images/studioimages/studio_distributing_evenly.png)

It distributes the allocation evenly across all units identified in the target table by the
To property. For example, if there is an Applications Target table with five applications and
$100,000 is being allocated, $20,000 will be allocated to each application.

## Weight By

The Weight By option distributes the allocation based on the ratio (relative size) of the
values in a column you select.

For example, assume there are five applications with various numbers of users as shown in the
table below, and $100,000 is being allocated. You want to weight the distribution by the number of
users. The $100,000 would be distributed as shown below in the Allocation column:

![](../../resources/images/studio_images/studioimages/studio/stu594.png)

Note: If you try to weight an allocation by a numeric column that contains at least one non-numeric
value, the weighting will be ignored. To correct the problem, remove the non-numeric values from the
column.

## Data Relationship

The Data Relationship option distributes the allocation evenly across the units that match
the values in a column in the source table with the values in a column in the target table. For
example, assume the source table includes information about applications. Both the source and
destination tables include an Application Category column. One of the categories is
identified as Databases, but there are two database applications: Oracle and SAP. The value
from the Database entries in the source table would be aggregated and allocated evenly to the
Database entries in the target table. If $20,000 was being allocated, it would be divided into
$10,000 for Oracle and $10,000 for SAP.

You can specify more than one relationship. If you specify more than one relationship, all the
relationships must match for the value to be allocated.
