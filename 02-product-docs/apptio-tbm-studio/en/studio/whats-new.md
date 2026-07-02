---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Recent releases"
breadcrumb:
  - "TBM Studio"
  - "Release Notes"
source_path: "studio/whats-new.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Recent releases

## Server 12.11.22 - May 29, 2026

- This release introduces several enhancements to the New Report Studio, including:
  - [Theme Engine](report-studio/theme-engine.html) for a more
    customizable and consistent report appearance
  - Support for adding descriptions to custom formulas to improve readability and maintainability
  - Export to Excel functionality for table visualizations in the Report Designer
  - Enhanced Editable Tables with configurable row limits
  - Support for displaying formatted data in Editable Tables
  - “Add to Filter” support for custom formulas in Editable Tables
  - Zero-value filtering support for charts to provide greater flexibility in data analysis
  - A new option to disable drill-through interactions through the Data Panel configuration
- Support has been added for running [recurring
  publish](formulas-and-functions/functions/ApptioScript-function.html "Applies to: TBM Studio 12.11.22 and later") schedules for editable tables using ApptioScript.
- **Costing Standard (templates v120)** 
  - [Data Center TCO](/docs/SSI71A/cost-transparency/infra-use-cases/dc-overview.html) is now generally available to customers with an IBM Apptio
    Costing Standard license. This solution pack helps organizations analyze the total cost of operating
    data center facilities, evaluate capacity and utilization across power, cooling, space, and racks,
    and compare sites using unit economics such as cost per kilowatt, cost per rack, and cost per square
    foot. It also helps allocate data center costs to the infrastructure, applications, and solutions
    they support, improving visibility into cost drivers, capacity constraints, and investment
    decisions. Highlight Video [Link](https://www.youtube.com/watch?v=RT6brXfajcc "(Opens in a new tab or window)")
  - [Mainframe TCO](/docs/SSI71A/cost-transparency/infra-use-cases/mf-overview.html) Enhancements:
    - Cost Pool tab updated to understand cost composition, track trends, compare against benchmarks,
      and review period-over-period detail in a single, coherent view.
    - New Mainframe Storage use case added to provide visibility into mainframe storage costs,
      consumption, and allocation as part of the overall Mainframe TCO analysis.
  - [Out-of-the-box reports](report-studio/ootb-report-pp.html "This document outlines the steps required to enable Modernized OOTB (New Experience (NX)) reports on a client instance. These reports provide enhanced visibility, better insights, and a more user-friendly‑ experience while continuing to use the same datasets as Classic TBM Studio.") based
    on the new Report Studio are now available as GA for Financials, Vendors, Applications, Labor,
    Public Cloud TCO, Mainframe TCO, AI TCO, Services components.
  - Costing Standard Legacy out-of-the-box Reports are now available in Polish language

**Fixed in this release**

- Fixed security vulnerabilities

## Client 2.22 - May 29, 2026

- Support has been added for running [recurring
  publish](formulas-and-functions/functions/ApptioScript-function.html "Applies to: TBM Studio 12.11.22 and later") schedules for editable tables using ApptioScript.
- All other features require upgrade to server version 12.11.22. Please refer to the server
  updates.

## Server 12.11.21.1 - May 8, 2026

- Quarterly Java update.

## Client 2.21.1 - May 8, 2026

- Quarterly Java update.

## Studio UI 1.21.2 - May 8, 2026

**Release 1.21.2 is now GA**

This release includes the following set of minor feature enhancements and fit-and-finish
improvements focused on usability and overall product experience of the **New Report Studio.**

- UI padding fixes for improved visual consistency
- General fit-and-finish improvements across the New Report Studio experience

## Studio UI 1.21.1 - April 17, 2026

The following improvements have been introduced in the new IBM Apptio Report Studio:

- Fixed accessibility violations to improve compliance.
- Introduced an Active/Inactive flag for reports. The calculation engine now excludes inactive
  reports.
- Enhanced multi-line tooltip rendering for improved readability.
- Fixed Japanese localization issues
- Added clear separation of legacy reports in the check-in panel.

## Server 12.11.21 - April 10, 2026

- The new [IBM Apptio Report Studio](report-studio/getting-started/intro.html "The new IBM Apptio Report Studio, which is carbon-designed, delivers a modernized, intuitive, and more powerful reporting experience. It is designed to help TBMAs, and business users build reports faster, with less complexity and a shorter learning curve. Compared to the Classic Report Studio, this version brings:") is
  now GA, offering a modern experience for creating, customizing, and consuming reports - enabling
  end-to-end adoption across creation, migration, and sharing workflows. With new report studio you
  can
  - Create reports from scratch
  - View and learn from Pre-Built Standard Reports
  - Edit and Customize Reports
  - Consume and Share Reports
- In this release new IBM Apportion Report Studio enhancements include: button component for
  actions, tab visibility rules, shared axis in overlay charts, auto-wrapping in tables, saved views,
  email sharing from report viewer, and a [migration assistant](report-studio/migration-assistant.html) for moving reports from classic TBM Studio.
- Introduced a new self-service capability within Automated Data Management (ADM) to enable
  integration between Cloudability and Costing, replacing the existing Cloudability DataLink
  connector. Additional details and migration guidance will be shared by your CSM.
- IBM Help documentation has been refreshed for TBM Studio, Billing, and Benchmarking.
- Costing Standard (templates v120)
  - A new standalone project type for Mainframe TCO has been introduced, enabling dedicated analysis
    and management of mainframe costs.
  - [Modernized out-of-box
    reports](report-studio/ootb-report-pp.html "This document outlines the steps required to enable Modernized OOTB (New Experience (NX)) reports on a client instance. These reports provide enhanced visibility, better insights, and a more user-friendly‑ experience while continuing to use the same datasets as Classic TBM Studio.") based on the new Report Studio are now available (Public Preview).
  - A new solution, Data Center TCO (Public Preview), is now available, providing comprehensive
    visibility into data center costs, capacity utilization, and cost allocation.
  - Data Advisor has been updated with the latest enhancements.

**Fixed in this release**

- Fixed security vulnerabilities

## Client 2.21 - April 10, 2026

- Added a checkbox in the Unused Reports workflow to enable visibility into Partner Admin usage
  data.
- Upgraded the graphing library; minor visual changes in charts may be observed.
- All other features require upgrade to server version 12.11.21. Please refer to the server
  updates.

## Server 12.11.20 - February 27, 2026

- The new [IBM Apptio Report Studio](report-studio/recent-releases.html) is now
  available for Public Preview. If you would like to participate and aren't already registered, please
  reach out to your Customer Success Manager (Require server 12.11.19/2.19+). New features includes
  - Tree View for Tables
  - Export Reports to PDF
  - Export Tables to Excel
  - Multi-currency Support
- deleteAllrows functionality for Editable table will delete only the currently filtered set of
  rows when filters are applied. If no filters are applied, all rows in the editable table will be
  deleted.
- From Q2, 2026, support for [grouping on numeric dimensions](troubleshooting/numeric-grouping-tables-reports.html) will be fully disabled. Customers are advised to
  proactively identify and resolve any related configurations.
- [Email Subscriptions](reports/email-subscription.html) now
  support Row Level Security
- Costing Standard (templates v120)
  - **Product TCO Solution:** Added App ID drilldowns, CapEx & Total Spend metrics in [Product detail
    report](/docs/SSI71A/cost-transparency/solution-uc/product-reports.html), and budget metrics in [Product list report](/docs/SSI71A/cost-transparency/solution-uc/product-reports.html#prorep__plist).
  - **Mainframe TCO Solution:** Introduced a dedicated [Mainframe Applications report](/docs/SSI71A/cost-transparency/infra-use-cases/mf-reports.html#mfrep__mainframe-apps) (previously part of Mainframe TCO).
- Costing Essentials (templates v200)
  - Updated the allocations to assign External Labor to Vendors first, before allocating to Labor.
  - Updated the column pickers in the [Labor Analysis](/docs/SSU3U2H/apptio-cost-management/out_of_the_box_reports/labor-review.html#LaborReview__lanalysis) .

## Client 2.20 - February 27, 2026

- The new [IBM Apptio Report Studio](report-studio/recent-releases.html) is now
  available for Public Preview. If you would like to participate and aren't already registered, please
  reach out to your Customer Success Manager (Require server 12.11.19/2.19+).
- Fixed vulnerability issues.
- All new features require upgrade to server version 12.11.20. Please refer to the server
  updates.

## Server 12.11.19.1 - February 06, 2026

- Quarterly Java update.
- Fixed an issue in the new Report Designer where the Object column dimension ID incorrectly
  included the table name

## Client 2.19.1 - February 06, 2026

- Quarterly Java update.

## Server 12.11.19 - January 16, 2026

- The new [IBM Apptio Report Studio](report-studio/prev-releases.html) is now
  available for Public Preview. If you would like to participate and aren't already registered, please
  reach out to your Customer Success Manager. Access to the new IBM Apptio Report Studio will be
  enabled on the release 12.11.19/ 2.19.
- From Q2, 2026, support for [grouping on numeric dimensions](troubleshooting/numeric-grouping-tables-reports.html) will be fully disabled. Customers are advised to
  proactively identify and resolve any related configurations.
- Costing Standard (templates v120)
  - Added a new drill report to focus on product hierarchy.
  - Added Product TCO to reference project.
  - Product TCO is available in Japanese language.
  - Created a new component for TBM v5 Reference Files.
- Costing Essentials (templates v200)
  - Created a new component for TBM v5 Reference Files.

## Client 2.19 - January 16, 2026

- Fixed vulnerability issues.
- All new features require upgrade to server version 12.11.19. Please refer to the server
  updates.
