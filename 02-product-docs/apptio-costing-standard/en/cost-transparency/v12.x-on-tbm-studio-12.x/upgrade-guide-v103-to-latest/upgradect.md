---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Upgrade Costing Standard from template v103 to the latest version"
breadcrumb: []
source_path: "cost-transparency/v12.x-on-tbm-studio-12.x/upgrade-guide-v103-to-latest/upgradect.html"
images:
  - "resources/images/ct_images/template_v103_home_page.png"
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Upgrade Costing Standard from template v103 to the latest version

Applies to: Costing Standard on TBM Studio 12.3 and later, with Template v104 and later

## Overview

This document describes the reasons behind the Costing Standard user interface (UI) upgrade and
the recommended steps for upgrading Apptio application content from
Template v103 to the latest version of the application template.

## SEE ALSO

To understand the difference between templates v103 and v104, go to [Compare v104 and v103 Cost Transparency reports](../../reports-v104/comparev103v104reports.html).

To understand how the reports map to template v104, go to [Mapping Cost Transparency reports from Template v103 to
v104](../../reports-v104/mappingctreports103to104.html).

For a spreadshseet that lists all the data sets that need to be upgraded for v104, go to [Template v103 to v104 Data
Updates](../../user-guide/template103to104dataupdates-9027.html).

## Goals

The user interface for Costing Standard was redesigned to do the following:

- Simplify the report navigation in Costing Standard
- Simplify and break apart complex reports
- Better support incremental configuration
- Segment products into top-level selections, such as separating Vendor Insights reports from Costing Standard
- Support TBM Taxonomy v2 as the default (TBM Taxonomy v1 is still supported)
- Support Section 508 compliance
- Improve performance of known "expensive" reports

## Report collections in Template v104

The Costing Standard reports have been organized under the following report collections in
Template v104:

- Applications
- Benchmarking
- Business Units
- Data Dimensions
- Data Quality
- Infrastructure and Cloud
- IT Financials
- Projects
- Resources
- Services
- TBM Overview
- Vendors

## Report types

The v104 report collections are organized around the following types of reports:

- "Review" reports provide a graphical overview of key areas, such as the 10 applications or
  categories with the largest spend.
  - Example: Financial Review
  - Example: Project Review
- "Portfolio" reports provide metrics across all items in an area.
  - Example: Project Portfolio
- "Analysis" or "List" reports provide a tabular view for each area to quickly find specific values.
  - Example: Financial Analysis
  - Example: Project List
- Other reports are added to a collection to handle "insight" use cases unique to an area.
  - Example: Projects at Risk
  - Example: Impact of Retiring Applications

## Expectations for upgrading to Template v104

Because of the breadth of changes to the UI and underlying navigation, it is important that all
existing components **MUST** be upgraded; otherwise, navigation from the landing page to the
top-level reports can potentially break. Further, links from one report to a report in another area
can potentially break (for example, a link from the Service Portfolio report to a related project
report for a specific service.)

## Identifying Template v103

You can determine whether your application is using Template v103 by looking at the Costing Standard home page or the list of Costing Standard report collections.

If the Home page looks similar to the page below, you have Template v103. Look for sections like
"IT Finance" and "IT Management," each with three links below them.

![](../../../../../../03-media/apptio-costing-standard/resources/images/ct_images/template_v103_home_page.png)

Alternatively, look at your Reports menu. Navigate to the report collections.

To understand the difference between the templates, go to [Compare v104 and v103 Cost Transparency reports](../../reports-v104/comparev103v104reports.html).

## Upgrade to the latest components

The following steps are required to upgrade the application from Template v103 to v104 and later.
Complete these steps after you have upgraded your platform from TBM Studio 12.3 or 12.4 or
later.

## Related information

- ![](../../../../../../03-media/apptio-costing-standard/sout.gif)[Send feedback about
  Help Center](productfeedback@apptio.com "(Opens in a new tab or window)")
