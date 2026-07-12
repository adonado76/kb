---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Workforce Getting Started"
breadcrumb:
  - "Costing Standard"
  - "Financial Use Cases"
  - "Workforce"
source_path: "cost-transparency/it-financials/wf-getstart.html"
images:
  - "resources/images/ct_images/wf-gs.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Workforce Getting Started

Use Workforce & Time Tracking components to load, allocate, and analyze labor cost
and headcount data across internal employees and external contractors. These components enable
labor spend reporting, headcount tracking, workforce allocation, and project-level labor
analysis.

Depending on your operating model (waterfall, agile, or hybrid), you may install one or more
labor-related components to support workforce reporting and allocation requirements.

## Components Install

**CTF- Labor**

- The CTF- Labor component enables reporting and analysis of labor cost and headcount
  for both FTE and contract employees. It supports comparisons of actual costs and
  headcount against plan and budget.
- Track labor cost and headcount by cost center, role, project, and IT tower
- Analyze labor budget variances
- Support workforce cost accountability
- After installing this component, you must upload labor data and map it to the **Labor
  Master Data** table to populate cost and budget-related labor reports

**CTF- Labor Units**

The CTF- Labor Units component enables accurate allocation of labor headcount across
Projects, Applications, and Products in waterfall, agile, or hybrid operating models.

- Allocate labor headcount across multiple IT Resource Sub-Towers
- Support Agile, Project, or Hybrid IT operating models
- Report accurate headcount per application, product, or project

This component uses Labor Master Data as its source and introduces additional allocation
logic and metrics, including Internal Headcount, External Headcount, and Labor Units.

- Review and adjust allocations (Labor → Other Labor Allocations → IT Resource
  Towers)
- Apply **Internal Headcount**, **External Headcount**, and **Labor Units**
  metrics to custom allocations
- Use **Labor ID** and **Weighting Factor** for allocation logic
- Review the diagram below for recommended model

**CTF- Labor NX Reports (Additional Component)**

This component provides predefined NX reports based on Labor data for analysis across cost
centers, roles, and time periods.

Use this component when:

- You need standard labor cost reports
- You want to compare actuals and budgets
- You require consistent Labor reporting

## Common Sources of Data

Labor data is typically sourced from HR and workforce management systems that maintain
employee, contractor, and time-tracking information. Common systems include **SAP, Oracle
E-Business Suite, PeopleSoft, and Workday**.

The data should include employee or contractor identifiers, employment type, role
attributes, organizational alignment, and, where applicable, time or activity information.
If the customer follows the standard model allocations, labor data will need to be mapped to
the Apptio TBM Unified Model (ATUM) Tower and Sub-Tower taxonomy to ensure consistent
reporting.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/wf-gs.png)

## Master Datasets

You may have to upload multiple tables and map to the master tables provided with the
components. Tables are:

- **Labor Master Data**
- Contains labor cost, budget, and headcount information for internal and external
  workforce. This dataset is populated by uploading and mapping a labor data table.
- **Other Labor Allocations Master Data**
- Installed with the Labor Units component and used to allocate labor across IT
  Resource Towers, Sub-Towers, projects, and applications using weighting factors.
- **Time Tracking Master Data**
- Used by the Time Tracking component to allocate labor costs and effort to projects
  and operational activities
