---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "configuration"
title: "Populate the Cost Source to IT Resource Master Data table"
breadcrumb: []
source_path: "configuration/populatecostsource2.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Populate the Cost Source to IT Resource Master Data table

To populate the Cost Source to IT Resource Master Data table, upload a data table that
defines the percentage of the other costs to allocate to each cost center. After creating the table,
map it to the Cost Source to IT Resource Master Data table.

Applies to: Costing Standard on TBM Studio 12.0 and later

## Introduction

Use the Other Cost Pools table to allocate any values not allocated to Labor or Fixed Assets to
the IT Resource Towers and Sub-Towers. To do this, you will need to:

- Map your cost centers to the IT Towers and Sub-Towers.
- Define an actual percent allocation if a cost center maps to multiple IT Towers and
  Sub-Towers.
- Define a budgeted percent allocation if a cost center maps to multiple IT Towers and
  Sub-Towers.

The Cost Source to IT Resource Master Data table defines the data required to "light-up" the cost
and budget related reports. To populate the table, you must upload a data set that defines the
percentage of the other costs to allocate to each cost center. After creating the table, map it to
the Cost Source to IT Resource Master Data table. An example table is shown below.

![](../../resources/images/ct_images/6869_1.png)

## Typical data sources

Cost center figures usually are pulled from applications such as Oracle, SAP, Lawson, and Cognos
Financial Statement Reporting. The data you use will determine the level of detail available and the
columns that you will map to the Cost Source to IT Resource Master Data table.

## One upload

Typically, you upload a single data table that is appended to the Cost Source to IT Resource
Master Data table and the IT Resource Towers Master Data table. The data table must contain fields
that can be mapped to the appropriate fields in the master data tables.

## Required and recommended fields

The required and recommended fields needed to light up the master data tables listed below.

Cost Source to IT Resource Master Data

- % Allocated (required)
- Cost Center (required)
- IT Resource Tower and Sub-Tower (required)
- Planned % Allocated (recommended)

IT Resource Towers Master Data

- IT Resource Sub-Tower Name (required)
- IT Resource Tower Name (required)
- IT Resource Tower Owner (required)
- IT Resource Tower Quantity (required)
- Unit of Measure (required)

**Parent topic:** [Costing Standard](../home.html)

## Related information

- ![](../../../../03-media/apptio-costing-standard/sout.gif)[Send feedback about
  Help Center](productfeedback@apptio.com "(Opens in a new tab or window)")
