---
source_system: "apptio-costing-essentials"
practice: "tbm"
language: "en"
doc_type: "apptio-cost-management"
title: "Fallout"
breadcrumb:
  - "Costing Essentials"
  - "Workbench"
source_path: "apptio-cost-management/workbench/fallout.html"
images:
  - "resources/images/studio_images/fall-labor.png"
  - "resources/images/studio_images/fall-oth_958x601.png"
  - "resources/images/studio_images/fall-sol.png"
  - "resources/images/studio_images/fall-vendor.png"
  - "resources/images/studio_images/fallout-1_1202x762.png"
  - "resources/images/studio_images/fallout-2_1017x447.png"
capability_ids: []
last_updated: "2026-02-27"
summary: ""
---
# Fallout

The Fallout Dashboard readily highlights the costs – both OpEx and CapEx – in your
Costing Essentials model that have fully allocated or not allocated (fallout).

## KPIs

Provides an overview of the full cost at each level in the model. A fully allocated model will
show the same total cost in each KPI.

Example:

- Cost Source – Total Spend YTD = $100
- Solutions – Total Spend YTD = $80
- Business Unit – Total Spend YTD = $50

## Cost Source

Use this report to view the OpEx Distribution (Labor, Vendors, Other) by period and ensure that
your GL Transactions match with the Cost Source object within ACM.

![image](../../../../../03-media/apptio-costing-essentials/resources/images/studio_images/fallout-1_1202x762.png)

As per design, there is an allocation sending all remaining cost into Other – i.e. cost which has
not been allocated to Vendor or Labor –. Therefore, there is no fallout from Cost Source, and to
ensure the cost flowing via Other is legitimate, we display the misallocated cost in a table below
the chart. “Misallocated” means that this cost sent to Other, should have been sent to Vendor or
Labor, but was failing due to unmatching Relationship.

Examples:

- On a given GL Actual, Cost Pool is Internal Labor for the Account, but we cannot find any Labor
  HC associated to the same Cost Center in Labor Data.
- On a given GL Actuals, a Vendor ID has been mapped, but we cannot find this Vendor ID in the
  Vendors Master List (which could be the case if the Vendor has been removed from the Vendors Master
  List used for the Month selected)

![image](../../../../../03-media/apptio-costing-essentials/resources/images/studio_images/fallout-2_1017x447.png)

## Labor

Use this report to view any unallocated labor costs that are expected to allocate to Solutions.
To fix any fallout, user should utilize the ‘Labor Mapping’ tables to allocate a Labor resource to
individual Solution Offerings.

![image](../../../../../03-media/apptio-costing-essentials/resources/images/studio_images/fall-labor.png)

## Vendors

Use this report to view any unallocated vendor costs that are expected to allocate to Solutions.
To fix any fallout, user should utilize the ‘Vendor Mapping’ tables.

![image](../../../../../03-media/apptio-costing-essentials/resources/images/studio_images/fall-vendor.png)

Note: when Lookup columns [In Catalogue Type], [In Catalogue Category], [In Catalogue Offering
ID] are highlighted in red, it means the data mapped in the Workbench is not found anymore in the
Service Catalogue. This can occur when the Service Catalogue is updated without updating the
Resource mappings to align to the new Service Catalogue.

## Solutions

Use this report to view any unallocated Solution costs that are expected to allocate to
Organizations (Consumers). To fix any fallout, user should utilize the ‘Solution Mapping’ or
‘Organization Mappings’ tables as per advised in column “Fallout Fix Action”.

![image](../../../../../03-media/apptio-costing-essentials/resources/images/studio_images/fall-sol.png)

## Others

Cost out of Other is always allocating since it works as “Send Remaining” cost allocation. The
below snapshot indicates details of this allocated cost.

![image](../../../../../03-media/apptio-costing-essentials/resources/images/studio_images/fall-oth_958x601.png)
