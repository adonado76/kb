---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Project Administration"
breadcrumb:
  - "TBM Studio"
  - "Administration"
source_path: "studio/new-uc/admin/project-admin.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Project Administration

**Content Type:** Conceptual / How-To

**Target Audience:** Administrators, Power Users

**Prerequisites:** Admin or Power User role, access to Project tab

Project administration encompasses all activities related to setting up, configuring, and
maintaining TBM Studio projects. This includes creating projects, configuring time settings,
managing domain-wide settings, and establishing governance policies.

## Understanding Projects

Projects are the foundational organizational unit in TBM Studio. A project groups together
data sets, metrics, models, and reports into a cohesive workspace. Each project has its own
configuration, time settings, and user permissions.

**Key project characteristics:**

- Projects contain all data tables, transforms, model objects, metrics, and reports
- Each project has independent time settings, defining the fiscal calendar and active
  periods
- Projects can be based on standard templates (Costing Standard) or custom
  configurations
- Multiple projects can exist within a single domain
- Only one project can be open at a time in the application

**Note:** *Only system administrators can create or delete projects. Contact your
Apptio system admin if you need a new project created or an existing project
removed.*

## Configuring Project Settings

Project settings control project-level behavior for calculations, formatting, and
presentation. Access project settings from the Project tab by clicking Project Settings in
the Project Setup group.

**Key Project Settings:**

|  |  |
| --- | --- |
| **Setting** | **Description** |
| **Base Currency** | Default currency for displaying values in reports. Users can override this in their profile. |
| **Locale** | Determines number, currency, and date formats used throughout the project. |
| **Number Compaction** | Abbreviations for thousands (K), millions (M), billions (B), and trillions (T). |
| **Components Version** | Specifies which content version to use for component upgrades and installations. |
| **Auto-calculate** | When enabled, the application automatically updates documents after check-in. Disable this for large projects to improve performance. |
| **Mandatory Check-in Descriptions** | Requires users to enter a description with each check-in. Recommended for audit trails. |

**Tip:** *For projects with large databases that take significant time to calculate,
disable auto-calculate and let users manually trigger updates when needed.*

## Configuring Time Settings

Time settings define your fiscal calendar, control which periods are active, and determine
what data periods users see by default. Properly configuring time settings is critical for
accurate reporting and optimal performance.

**To configure time settings:**

1. Navigate to **Project > Time Settings**.
2. Configure the Fiscal Year Definition (Gregorian, 13-period, or custom 4-5-4
   variant).
3. Set the Project Start and End dates to define the calculation window.
4. Configure the Default Time Period that users will see when opening reports.
5. Define Closed Periods to prevent data modifications to finalized periods.

**Warning:** *Once you enable time for a project, you cannot disable it. The project
start date cannot be changed after initial configuration. Plan your time settings
carefully before committing.*

**Time Settings Best Practices**

- Set the default period to the most recently fully closed month to ensure users see
  validated data.
- Close periods once data is validated to prevent accidental changes.
- Limit the project start and end dates to only necessary periods to improve calculation
  performance.
- Update the default period after each month-end close completes.

## Domain Settings

Domain settings control environment-wide configurations that apply across all projects in
your Apptio instance. Access domain settings from the Project tab by clicking Domain
Settings.

**Key domain settings include:**

- **Default Project** - The project that opens when users log in without specifying a
  project
- **Multi-Currency Service** - Centralized currency exchange management across Apptio
  products
- **Fiscal Calendar Service** - Shared fiscal calendar definitions across products

## Enabling Optional Features

TBM Studio provides several optional features that can be enabled based on your
organization's needs. Access these from the Project tab by clicking Enable Features.

|  |  |
| --- | --- |
| **Feature** | **Description** |
| Calc Priority Management | Prioritize calculations across projects based on importance or urgency |
| Calc Management | Enable/disable staging calculations at project level |
| Recurring Publish | Schedule automatic publishing of editable table data to transforms |
| Show Unused Documents | Identify tables, metrics, and reports not used anywhere in the project |
| Show Anomalies Panel | Display anomaly detection for unusual calculation patterns |
| Apex UI | Enable the modernized user interface experience |
