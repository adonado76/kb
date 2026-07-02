---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Data Export"
breadcrumb:
  - "TBM Studio"
  - "How-To Guides (Task-Based)"
  - "Work with Data"
source_path: "studio/new-uc/howtoguides/work-with-data/data-export.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Data Export

**Content Type:** How-To Guide

**Target Audience:** IT Finance Teams, Administrators, Developers

**Time to Complete:** 30-45 minutes (varies by method)

**Prerequisites:** Access to TBM Studio with appropriate permissions; familiarity with
Data Studio basics (see Section 3.1.1)

## Overview

TBM Studio provides robust capabilities for getting your cost data out of the system and
into external tools such as data warehouses, business intelligence platforms, and custom
applications. This section covers two primary methods for data export:

- [Published Tables](htg-config-pt.html): Pre-configured, schema-stable
  datasets designed for scheduled extraction by external systems
- [API Access](htg-api.html): Programmatic data retrieval for custom
  integrations and automation

Understanding when to use each method ensures you implement the most efficient and
maintainable data export strategy for your organization.

## Choosing Your Export Method

Before diving into configuration, determine which export method best fits your use case.
The decision depends on your data consumers, refresh requirements, and technical
capabilities.

## Decision Guide: Published Tables vs. API

Use this guide to determine the right approach for your scenario:

**Choose Published Tables when:**

- You need to feed data to external BI tools like Power BI or Tableau
- Data consumers require a stable, predictable schema that doesn't change frequently
- You want data automatically refreshed after each calculation cycle
- Multiple downstream systems need the same curated dataset
- You're replacing ad-hoc manual report exports with controlled automation
- Your BI team prefers connecting to a known endpoint rather than building custom
  queries

**Choose API access when:**

- You need flexibility to query different tables or reports on demand
- Your integration requires custom logic or conditional data retrieval
- You're building a custom application that consumes TBM Studio data
- You need one-time or irregular data extractions
- Your ETL pipeline already handles data transformation and scheduling
- You require data from multiple tables combined in custom ways

**Choose both when:**

- Published Tables feed your primary BI dashboards (stable, scheduled)
- API supplements with ad-hoc queries or pulls from tables not worth publishing

## Quick Reference: Method Comparison

|  |  |  |
| --- | --- | --- |
| **Characteristic** | **Published Tables** | **API** |
| **Primary Use** | Scheduled feeds to BI tools and data warehouses | Programmatic, on-demand data retrieval |
| **Schema Stability** | Fixed until explicitly modified | Depends on source table/report |
| **Data Freshness** | Updates after each calculation | Real-time (queries current data) |
| **Configuration** | UI-based setup | Script or application code |
| **Maintenance** | Low (set and forget) | Medium (code maintenance required) |
| **Best For** | Power BI, Tableau, Snowflake feeds | Custom apps, ETL tools, automation |

## Related Tasks

- [Import data](data-import-mgmt.html): Import Data from Files
- [Transform data](transform-enrich-data.html): Transform and Clean Data
- [Build reports](../create-reports/report-basic.html): See Section 3.3
  (Create Reports)
- Detailed API reference: See Section 5.5 (API Reference)

- **[How-To Guide: Configure Published Tables](../../../../studio/new-uc/howtoguides/work-with-data/htg-config-pt.html)**
- **[How-To Guide: Export Data via API](../../../../studio/new-uc/howtoguides/work-with-data/htg-api.html)**
