---
source_system: "apptio-costing-essentials"
practice: "tbm"
language: "en"
doc_type: "apptio-cost-management"
title: "Reference Tables"
breadcrumb:
  - "Costing Essentials"
  - "Workbench"
source_path: "apptio-cost-management/workbench/reference-tables.html"
images:
  - "resources/images/studio_images/rt-1_1040x601.png"
  - "resources/images/studio_images/rt-2_1058x539.png"
  - "resources/images/studio_images/rt-3_1060x491.png"
  - "resources/images/studio_images/rt-4_1059x779.png"
  - "resources/images/studio_images/rt-5_1066x807.png"
capability_ids: []
last_updated: "2026-02-27"
summary: ""
---
# Reference Tables

This section of the Workbench is to provide the customer the ability to manage the
baseline reference data to be utilized in Apptio Cost Management.

## Solution Categories

A Vertical is considered the distinction of the Solution Types & Categories used in the ACM
model. Customer may choose the ‘Common’ Vertical which is based on TBM Taxonomy v4; or they can
create their own unique Vertical.

**Solution Type** must align with the TBM Taxonomy. (See the TBM Taxonomy Reference
Table).

**Solution Category** can be customer specific.

User can select which Solution Categories to include in the model by selected ‘YES’ in the
Include column.

![](../../../../../03-media/apptio-costing-essentials/resources/images/studio_images/rt-1_1040x601.png)

## Vendor Lookups

**Vendor Type** is a classification of vendors to provide appropriate management and oversight
to optimize pricing and risk. Recommended categories are: Strategic, Preferred, Transactional and
Legacy.

**Vendor Category** is a high-level categorization of the function that the vendor
provides.

![](../../../../../03-media/apptio-costing-essentials/resources/images/studio_images/rt-2_1058x539.png)

NOTE: It is recommended that users do not delete any of the existing Vendor Types (STRATEGIC,
PREFERRED, TRANSACTIONAL) as they are linked directly to business rules, reports and KPIs.

## Solution Lookups

**Delivery** provides the ability to set a Solution as delivered by: Public Cloud, Private
Cloud, On Prem.

**Investment Objective** is the investment strategy for the solution. Used to prioritize
solution resources and investments for new and existing solutions that are aligned to the business'
imperatives and objectives.

![](../../../../../03-media/apptio-costing-essentials/resources/images/studio_images/rt-3_1060x491.png)

## Cost Center RLS

This provides the ability for the user to enter Row Level Security assignments by Cost Center.
Items entered into this table will limit the User ID to only be able to see data that relates to the
Cost Center they are assigned.

User ID should be the email address the user uses to sign into Apptio.

![](../../../../../03-media/apptio-costing-essentials/resources/images/studio_images/rt-4_1059x779.png)

## Full Access RLS

For any users allowed full access to all data reported on in Costing Essentials, should be
inserted into this table.

![](../../../../../03-media/apptio-costing-essentials/resources/images/studio_images/rt-5_1066x807.png)
