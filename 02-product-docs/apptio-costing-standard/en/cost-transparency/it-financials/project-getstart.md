---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Projects Getting Started"
breadcrumb:
  - "Costing Standard"
  - "Financial Use Cases"
  - "Projects"
source_path: "cost-transparency/it-financials/project-getstart.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Projects Getting Started

## Getting Started

Use the Projects capability to track, analyze, and manage IT project spend across cost
centers, projects, and IT towers. The **CTF – Projects** component enables visibility
into project investments, budget adherence, and spend trends, supporting better financial
control and strategic alignment.

Before using the Projects reports, install the required component and load project cost
data into the master data table.

## Components Install

**CTF- Projects**

The CTF- Projects component provides the data structure required to analyze project spend
by type, cost center, project, and IT tower.

**Prerequisites**

- CTF- Cost Source
- CTF- Labor
- CTF- Labor Units or CTF- Time Tracking

After installing the component, you must upload project data and map it to the **Projects
Master Data** table to enable project spend reporting and analysis.

**Common Sources of Data**

Project data is typically sourced from project and portfolio management applications that
track project financials, timelines, and ownership. These systems provide details such as
project budgets, actual spend, project status, and investment classification.

Common Sources includes ServiceNow, Project Portfolio Suite, Clarity PPM, Jira Align / Jira
Advanced Roadmaps, MS Project Online / Project Server, Planview etc.

## Master Datasets

**Projects Master Data Table:** Defines the data required for project cost and budget
reporting. To populate this table, upload a project data set and map it to the appropriate
fields in the master data table. Typically, you upload a single project data set, which is
appended to and mapped into the Projects Master Data table.

**Project to Application Mapping Table:**This table is used to associate projects with
the applications they impact. This mapping enables visibility into how project investments
contribute to application cost, change, and modernization efforts.
