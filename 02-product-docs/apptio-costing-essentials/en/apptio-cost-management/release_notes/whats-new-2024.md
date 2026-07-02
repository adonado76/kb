---
source_system: "apptio-costing-essentials"
practice: "tbm"
language: "en"
doc_type: "apptio-cost-management"
title: "2024 Release Notes"
breadcrumb:
  - "Costing Essentials"
  - "Release Notes"
source_path: "apptio-cost-management/release_notes/whats-new-2024.html"
images:
  - "resources/images/studio_images/compound-filter.jpg"
  - "resources/images/studio_images/config-filter.jpg"
  - "resources/images/studio_images/null-value-filter.jpg"
  - "resources/images/studio_images/r-notes/cp1.jpg"
  - "resources/images/studio_images/r-notes/cp2.jpg"
  - "resources/images/studio_images/r-notes/eud-1.jpg"
  - "resources/images/studio_images/r-notes/eud-2.jpg"
  - "resources/images/studio_images/report-filter.jpg"
capability_ids: []
last_updated: "2026-02-27"
summary: ""
---
# 2024 Release Notes

## Costing Essentials enhancements (v200) - November 22, 2024

The following two new components have been introduced in this release.

- End User Devices components (GA)  : A new End
  User Devices component is available in Template v200. It provides insights for IT Asset
  manager/Desktop Support Manager to make data driven decisions around fleet optimization
  and consolidation to help decide overall fleet size and associated costs. It will also
  assist with the planning and forecasting of estimated refresh costs for end of life and
  non-compliant devices.

  ![Image](../../../../../03-media/apptio-costing-essentials/resources/images/studio_images/r-notes/eud-1.jpg)

  ![Image](../../../../../03-media/apptio-costing-essentials/resources/images/studio_images/r-notes/eud-2.jpg)

  To know more, see  [End User Devices](../getting_started/eud-intro.htm "(Opens in a new tab or window)")  .
- Cost Pool Benchmark component (BETA)  : Cost Pool Benchmark
  provides insights for IT Leadership and IT Finance in support of strategic investment
  decisions regarding the role of IT in the business and the current IT operating model and
  sourcing strategies. Benchmarks can be used to understand cost structure of current
  strategy and to justify or adjust current investment and sourcing approaches. Compare IT
  spend to industry benchmarks (e.g. IT Spend as a % of Revenue)

  ![Image](../../../../../03-media/apptio-costing-essentials/resources/images/studio_images/r-notes/cp1.jpg)

  ![Image](../../../../../03-media/apptio-costing-essentials/resources/images/studio_images/r-notes/cp2.jpg)

  To know more, see  [Cost Pool Benchmarks](../admin/setup-be.html)  .

## Apptio Community Transition to IBM TechXchange - November 1, 2024

Today, Apptio Community has fully transitioned to IBM TechXchange

## Apptio Costing Essentials Now Available in Japanese - August 16, 2024

The Costing Essentials (ACE) application is now fully localized in
Japanese, enhancing usability for Japanese-speaking users. All strings used in ACE have been
translated into Japanese and integrated into our system. The content has been resized and
re-aligned content within the application to improve the overall fit and finish. These
changes ensure a more polished and visually appealing user experience.

## IBM Apptio Costing Essentials GA - July 5, 2024

IBM ApptioCosting Essentials has launched Template v200, which is
designed to streamline and simplify costing solutions for our users. It is a prescriptive
costing solution authored in R12, tailored for smaller and less complex customers. It is
implemented through CS Delivery for initial configuration and TAS for ongoing support. It
utilizes standard components to facilitate ease of use and consistency across
implementations.

Admins can create new projects using the Project Type “Costing
Essentials”. These projects consist of components authored directly in R12. It is an
upgradeable framework that supports future components, extending functionality to Costing Standard. It utilizes editable tables for data entry and
maintenance, including mappings that drive pre-defined allocation methods.

![Image](../../resources/images/studio_images/r-notes/rn-12117-1_662x386.png)

![Image](../../resources/images/studio_images/r-notes/rn-12117-2_1372x764.png)

![Image](../../resources/images/studio_images/r-notes/rn-12117-3_1377x754.png)

## Costing Essentials release 12.11.4 - March 1, 2024

Filtering enhancements for Costing Essentials customers using Apptio BI

Starting today, users can quickly and easily filter out data to get to the most important
information. Before this release, Costing Essentials users were not
able to filter out information in such an effective way.

Enhancements 

- Report-level filters,
- Compound filtering with pre and post aggregation options,
- Null value filtering.

Feature 1: Report-level filters

This enhancement allows users to configure filters on the report level and apply them to
all the visualizations belonging to this report. Once created the report level filters are
visible at the top of the report.

Steps to create a report-level filter:

1. In the top right corner of a report, select and go to  Mange Report Filters
    .
2. From the  Data Source  list, select the required data source.
3. Select  Add Dimensions  and then select the dimension you want
   the filter to be based on.
4. Select  Apply .

![Image](../../../../../03-media/apptio-costing-essentials/resources/images/studio_images/config-filter.jpg)

![Image](../../../../../03-media/apptio-costing-essentials/resources/images/studio_images/report-filter.jpg)

For more information, see  [Report-level filters](../../apptio_bi/self-service-reporting_user_guide/bi-create-and-manage-report-filters.htm "(Opens in a new tab or window)")  .

Feature 2: Compound filtering with pre and post aggregation options

This enhancement allows users to create complex queries to filter out the most important
information. It is available in edit mode and allows users to define statements with
multiple AND and OR operations which can be applied pre or post aggregation. Pre-aggregation
will apply the filter to each individual line of the dataset, while post-aggregation will
apply the filter after the data has been aggregated.

Steps to create a report-level filter:

In edit mode scroll down through the left side navigation panel till you get to
 Filters  .

1. Select if the filter should be applied pre or post aggregation.
2. Define the query which you want to be processed by selecting appropriate measures,
   operators and values.
3. Combine the queries using AND and OR junctions if required.

![Image](../../../../../03-media/apptio-costing-essentials/resources/images/studio_images/compound-filter.jpg)

Feature 3: Null value filtering

This enhancement allows users to easily filter out null values and focus on the most
relevant information.

Steps to apply null value filtering:

In edit mode scroll down through the left side navigation panel till you get to Filters.

1. Select if the filter should be applied pre or post aggregation.
2. Choose the measure you want to filter.
3. As the  Operator  select: “is null” or “is not null” depending
   on the information you want to see.
4. Select  OK  .

![Image](../../../../../03-media/apptio-costing-essentials/resources/images/studio_images/null-value-filter.jpg)
