---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "CTF - IT Towers component: install and configure"
breadcrumb: []
source_path: "cost-transparency/configuration/ctf-ittowers-component.html"
images:
  - "resources/images/ct_images/gear_icon.png"
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# CTF - IT Towers component: install and configure

The CTF - IT (Resource) Towers component is part of the Costing Standard Foundation
module. The component provides insights into the costs of IT resource towers and sub-towers, and
compares IT tower and sub-tower spending to budget in support of monthly, quarterly, and annual
operational and strategic reviews.

Applies to: TBM Studio 12.4 and later, with Template v103 and later

## Uses

You must install the CTF - Cost Source component before you install the IT Towers component. The
component installs the IT Resource Towers Master Data.

- Identify the top IT tower changes in month-to-month and quarter-to-quarter spend
- Identify the top IT tower variances against budget
- Manage IT tower spend to budget
- Identify top cost sources

## Install the component

To install the component:

1. Open the Costing Standard project.
2. In the Project tab, click **Components**.
3. Click the **CTF - IT Tower** component.
4. Click **Install**.

## Common source systems

The structure (or taxonomy) of IT towers and sub-towers is defined in Apptio's TBM Unified Model
(ATUM). The taxonomy is loaded with your Costing Standard project in the IT Resource Towers Resource
List.

Some of the values required for the IT towers and sub-towers are not automatically allocated via
the other CTF components (that is, the Labor, Fixed Assets, and Vendors components). As a result,
you need to do the following to extract the proper data from your source systems and load it into
Apptio:

- Map your cost centers to IT towers and sub-towers
- Define an actual allocation percentage for cost centers that are mapped to multiple IT towers and sub-towers
- Define a budgeted allocation percentage for cost centers that are mapped to multiple IT towers and sub-towers

Your Success Management team will work with you to determine how to map your cost centers and
account codes and how to define the allocation percentages that work best for your organization.

## Master data

For a description of the fields in the master data table, see the information on the CTF - IT
Towers component page in the product. To display the page:

1. In the Project tab, click **Components**.
2. Click the **CTF - IT Towers** component.

## Required and optional fields

The following fields are required for the standard IT Tower reports:

- IT Resource Sub-Tower Name
- IT Resource Tower Name
- IT Resource Tower Owner
- IT Resource Tower Quantity
- Unit of Measure

|  |  |  |
| --- | --- | --- |
|  |  |  |

The following fields are optional:

- Annual Unit Cost Target
- Asset Routing Flag
- Asset)Resource Key Metafield
- Deliver
- Fixed Asset\_ITRT Key
- Fixed Asset\_ITRT Key Metafield
- ITRT\_Cloud\_Key Metafield
- ITRT\_LPARs Key
- ITRT\_SaaS Key
- Labor\_ITRT Key Metafield
- Mapped Benchmark
- Service Provider\_ITRT Key
- Service Type Mapping
- Sub-Tower Tablematch
- Time Tracking\_ITRT Key Metafield
- Unit Cost Target
- Vendor\_ITRT Key Metafield

For more information, see the Data Advisor. To open the Data Advisor, open an active instance of
Apptio, click the Settings icon (![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/gear_icon.png)),
then click **Data Advisor > IT Towers**.

In addition, there are columns for a tower owner, quantity, and unit cost target. If you are
implementing Benchmarking, you will need to complete the Quantity column. You can download the IT
Resource Towers Reference List, update the data, and upload the file as a new data set. You can then
map the new reference list to the IT Towers Master Data set. As long as you do not change the list
of IT resource towers and sub-towers, you will be compliant with the ATUM taxonomy.

## IT resource tower identifiers

The Other Cost Pools object identifier includes the cost center, IT resource tower, and
sub-tower.

The IT Resource Towers object identifier includes the IT resource tower and sub-tower.

## Columns required to link data sets

You will also need to consider how to link to the IT Resource Towers Master Data from other data
sets. The following list highlights some specific data elements needed for linking data sets
together:

- Cost Source Master Data:
  - Cost Center
  - IT Resource Tower
  - IT Resource Sub-Tower
- Labor Master Data:
  - IT Resource Tower
  - IT Resource Sub-Tower
- Fixed Assets Master Data
  - IT Resource Tower
  - IT Resource Sub-Tower
- Public Cloud Master Data
  - IT Resource Tower
  - IT Resource Sub-Tower
- Vendor Master Data
  - IT Resource Tower
  - IT Resource Sub-Tower

If you do not have sufficient data for allocating between Cost Source and Other Cost Pools, leave
those costs in the Cost Source object and do not allocate without appropriate mapping.

For additional information about allocations, see [Allocating costs
between Projects and IT Resource Towers on the Cost model](https://community.apptio.com/docs/DOC-4330 "(Opens in a new tab or window)").

## Related information

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Send feedback about
  Help Center](productfeedback@apptio.com "(Opens in a new tab or window)")
