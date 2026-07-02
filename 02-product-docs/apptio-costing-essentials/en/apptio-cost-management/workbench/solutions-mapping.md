---
source_system: "apptio-costing-essentials"
practice: "tbm"
language: "en"
doc_type: "apptio-cost-management"
title: "Solution Mapping"
breadcrumb:
  - "Costing Essentials"
  - "Workbench"
source_path: "apptio-cost-management/workbench/solutions-mapping.html"
images:
  - "resources/images/studio_images/sm-1_1145x703.png"
  - "resources/images/studio_images/sm-2_1088x621.png"
  - "resources/images/studio_images/sm-3_932x541.png"
  - "resources/images/studio_images/sm-5_937x255.png"
  - "resources/images/studio_images/sm-6_849x499.png"
capability_ids: []
last_updated: "2026-02-27"
summary: ""
---
# Solution Mapping

Use the Editable Tables in Solution Mapping to drive the allocations of OpEx/CapEx cost
Business Units.​

## Business Category Mappings

Provides ability to define the allocations of Service costs to Business Consumers, at the level
of Solution Types and Solution Categories.

- Child Service Offerings within each source Solution Type + Solution Category combination, will
  be allocated to specified target Organization(s) based on the weighting defined
- Organization Id represents the Unique ID of each Business Consumer
- Business Consumer will either represent
- A Business Unit Or
- A Department with a Business Unit
- Weighting
- Maybe 100% allocation (insert ‘1’), or split across multiple Consumers (Business
  Units/Departments)

![solution business category mapping](../../../../../03-media/apptio-costing-essentials/resources/images/studio_images/sm-1_1145x703.png)

## Offerings

Provides ability to Manage the list of applications, products and/or service offerings available
within your service catalogue, for subsequent cost allocations.

IDP users should verify/update key meta data for your service offerings, including: Allocation
Method, Delivery, Estimated Infra Usage, Offering Type, Investment Objective, IT Owner, Business
Owner, Primary Business Unit, Target Avg Unit Cost and Purpose.

Offering’s Estimated Infra Usage will be used to define the Percentage (%) split between
Infrastructure and Platform. Each Offering row should only be provided with Estimated Infra Usage to
define the Percentage (%) split to Infrastructure. Estimated Platform Usage will be derived from the
defined Estimated Infra Usage.

For example: If Estimated Infra Usage has been defined as 0.6 (60%) for the offering Acme.com,
then Estimated Platform Usage will be defined as 0.4(40%) with the difference between Estimated
Infra Usage 0.6 (60%) and Total 1 (100%)

## Allocation Methods

- Direct Allocation method enables Direct Allocation column which will be 1 by default and should
  only have one row.
- The Percent Split method enables Percent Split column and should have 2 or more rows with
  relative weighting assigned.
- Volume Split method enables Volume Split column and should have 2 or more rows with volumes
  assigned.
- Weighted Estimated Usage method enables the % Headcount Usage and User Weighting columns and
  should have 2 or more rows.

![solution offerings tab](../../../../../03-media/apptio-costing-essentials/resources/images/studio_images/sm-2_1088x621.png)

## Offering Mappings

Offerings represent the applications, products or services used by the organization and may be
directly or indirectly allocated based on the allocation method and entries in this table. Map each
Solution Offering row to one or more Organization IDs and set the Allocation method.

![solutions offerings mapping tab](../../../../../03-media/apptio-costing-essentials/resources/images/studio_images/sm-3_932x541.png)

## Missed Mappings

Use this table to verify if any offering rows are missing assignments to Solutions.
Alternatively, select (Blank) in the Cost Center Name slicer in the Solution Mappings tab.

![missed mapping tab](../../../../../03-media/apptio-costing-essentials/resources/images/studio_images/sm-5_937x255.png)

## Volumes

Provides ability to specific the estimated or actual volumes of each Offering ID (if applicable),
based on available (consumption) information.

An example of utilizing this table could be for your End User Device Solution Offerings, where
you would enter the Unit of Measure (eg: Laptop) and set the number expected in each period. Based
on the costs in the model, you would then be able to obtain a Unit Cost and compare the Planned
Volume to Actual Volume.

![solution mapping tab](../../../../../03-media/apptio-costing-essentials/resources/images/studio_images/sm-6_849x499.png)
