---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "CTF - Labor component: install and configure"
breadcrumb: []
source_path: "cost-transparency/configuration/ctf-labor-component.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# CTF - Labor component: install and configure

Use the CTF - Labor component to import project costs. This component is not installed
automatically with the standard Costing Standard project. The Labor component provides insights into
project spend by type, cost center, projects, and IT towers.

Applies to: Costing Standard on TBM Studio 12.4 and later

## Introduction

The Labor Master Data table defines the data required to populate the cost and budget related
reports. The data provides an in-depth analysis of labor costs for both FTE and contract employees,
including comparisons of actual costs and headcount against plan. To populate the Labor Master Data
table, upload a labor data table and map it to the Labor Master Data table.

## Uses

Use the CTF - Labor component reports to do the following:

- Manage expense to budget
- Identify spend levers
- Align spend with business objectives
- Align spend to strategy
- Confirm value or cancel projects

## Install the component

The CTF - Labor component is not installed with the standard Costing Standard project.

To install the components:

1. Open the Costing Standard project.
2. In the Project tab, click **Components**.
3. Click the **CTF - Labor** component.
4. Click **Install**.

The Labor Master Data table defines the data required to populate the cost and budget related
reports. The data provides an in-depth analysis of labor costs for both FTE and contract employees,
including comparisons of actual costs and headcount against plan. To populate the Labor Master Data
table, upload a labor data table and map it to the Labor Master Data table.

## Typical data sources

Labor figures usually are pulled from HR applications such as Oracle EBS, PeopleSoft, Workday,
and SAP. The data should include a list of employees and time tracking information.

The application requires employees or employee activities to be mapped to the ATUM
Tower/Sub-tower taxonomy. A common approach is to create a mapping table outside of the application
and then to upload the table.

## One upload

Typically you upload a single labor data table that is appended to the Labor Master Data table.
The data table must contain fields that can be mapped to the appropriate fields in the Labor Master
Data table.

## Master data

For a description of the fields in the master data table, see the information on the CTF - Labor
component page in the product. To display the page:

1. Click the **Project** tab.
2. Click **Components**.
3. Click the **CTF - Labor** component.

## Required and recommended fields

The required and recommended fields needed to light up the standard Costing Standard labor
reports are listed below.

- Compensation Type (required)
- Cost Center (required)
- Cost Center Name (required)
- Cost Pool (required)
- Cost Sub Pool (recommended)
- Employee Type (required)
- IT Resource Sub-Tower (required)
- IT Resource Tower (required)
- Labor Headcount (required)
- Labor ID (required)
- Labor Name (required)
- Location (required)
- Planned Headcount (required)
- Position (required)
- Project ID (recommended)
- Region (required)
- Unique Identifier (required)

## Related information

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Send feedback about
  Help Center](productfeedback@apptio.com "(Opens in a new tab or window)")
