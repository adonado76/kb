---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Hybrid IT TCO Impact Getting Started"
breadcrumb:
  - "Costing Standard"
  - "Other Solutions"
  - "Hybrid IT TCO Impact"
source_path: "cost-transparency/reports/hybitsol-gs.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Hybrid IT TCO Impact Getting Started

The Hybrid IT TCO Impact solution helps organizations understand the financial impact
of application migrations across on-premises, private cloud, and public cloud environments. It
enables comparison of pre- and post-migration TCO, unit costs, and volumes, and provides insight
into the cost pools and IT towers driving change. This solution supports data-driven validation
of migration business cases and ongoing financial tracking of hybrid IT
transformations.

## Components Install

To enable Hybrid IT TCO Impact, install the following components in the order listed.
Before installation, ensure **Components Version** in **Project Settings** is
temporarily set to **Version 120**. After installation, revert the version to avoid
unnecessary upgrade indicators.

1. **Applications Workbench**

   Enables enrichment of application metadata required for
   Hybrid IT TCO Impact analysis.

   Required fields include:

   **Hosted On**
   (On-Prem, Private Cloud, Public Cloud)

   **Application Investment Objective**
   (Sustain, Retire, Migrate, Invest)
2. **Hybrid IT TCO Impact**

   Installs the core framework, including migration
   workbenches, editable tables, metrics, and models. It also deploys intermediate reports
   used to capture and freeze baseline application metrics prior to migration.
3. **Hybrid IT TCO Impact Reporting**

   Installs the end-user reports ranging from
   executive-level summary views to detailed application-level analysis of migration
   benefits and cost drivers.

   Note: These components are available with templates v120
   or above

## Prerequisites

You must have the following components installed prior to configuring Hybrid IT TCO
Impact:

• CTF- Cost Source

• CTF- IT Towers

• CT Apps- Applications

## Common Sources of Data

**Application Portfolio Management (APM) tools**: Supply application metadata including
application IDs, ownership, lifecycle status, and investment objectives (sustain, migrate,
retire, invest).

## Datasets

The Hybrid IT TCO Impact solution installs and uses the following key datasets:

• Applications Master Data

• Application Migration

• Application Migration Relationships

• Applications Migrated (Raw, Cost Pool, IT Tower)

These datasets support before-and-after cost comparison, migration grouping, and variance
analysis.

## Configuration Overview

To activate Hybrid IT TCO Impact reporting, follow these high-level steps:

- **Establish Baseline TCO**
- Ensure TCO, unit costs, and usage volumes are calculated for all current applications
  using standard ATUM allocations. Populate required metadata in the Applications
  Workbench.
- **Capture Migration Metadata**
- For applications marked as **Migrate**, record migration strategy, migration status,
  target application IDs, and migration timing using the Application Migration
  Workbench.
- **Freeze Pre-Migration Metrics**
- When migration status is set to **Done**, capture a trailing twelve-month average
  snapshot of TCO, volumes, and unit costs for the migrated application using
  Apptio-to-Apptio datalink connectors.
- **Model Pre- and Post-Migration Costs**
- Configure modeled metrics for Cost Pre-Migration, Cost Post-Migration, and Application
  Count Post-Migration to enable apples-to-apples comparison across cost pools and IT
  towers.

For more details on configuring and operating Hybrid IT TCO Impact, go to[Hybrid IT TCO Impact Configuration Guide](hybrid-it-tco-config.html).
