---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Connect to Cloudability Financial Planning"
breadcrumb:
  - "Planning"
  - "Integrations"
source_path: "it-planning/planning/connect-cfp.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Connect to Cloudability Financial Planning

Important: Available with the ***Apptio Planning Standard****subscription*

Remember: The New View is enabled.

The Cloud Financial Planning (CFP) integration enables Apptio Planning to incorporate cloud
budgets and forecasts directly from IBM Cloudability into planning workflows.

With this integration, organizations can align cloud financial plans created in CFP with
departmental budgets and forecasts in Apptio Planning. Cloud forecast line items imported from
CFP are automatically mapped to Planning’s financial structures, reducing duplication of
effort and improving consistency across cloud and enterprise financial planning.

The integration is optional. Customers can use the Cloud tab in Apptio Planning to manage
cloud-specific spend independently of CFP. When CFP is connected, imported cloud budgets and
forecasts can coexist with cloud expenses entered directly in Planning, providing flexibility
to supplement CFP data where needed.

This feature supports more accurate, streamlined, and connected cloud financial planning
across systems.

**Key Features:**

**Cloud Tab**

- Customers can enable a new **Cloud tab** in the Expenses New View to manage cloud costs
  directly within Apptio Budgets and Forecasts.
- The Cloud tab can be enabled independently and does not require CFP integration.

**CFP Integration**

- Customers can connect Apptio Planning with Cloud Financial Planning (CFP) to import cloud
  budgets and forecasts from CFP in a single action.
- Imported cloud expenses are automatically mapped to Planning’s financial structure.

## Prerequisites

Before enabling Cloud Planning or CFP Integration:

1. Apptio Planning Standard license required.
2. CFP Integration supports **Gregorian fiscal calendars only** (445 & 13‑Period not
   supported). Cloud tab works with all supported fiscal calendars
3. **New Expenses Page Experience (Beta)** must be enabled.

## Enabling Cloud Planning and CFP Integration

***Note:*** *Admin or Budget Process Owner roles are required to perform these
tasks.*

1. Navigate to **Settings**
   **(Gear icon)** → **Company Profile**.
2. Ensure **New Expenses Page Experience (Beta)** is enabled first—Cloud tab can’t be
   used without it. To enable the feature, follow these steps:
   - **General Configuration** → **Access & Permissions** → Select **Enable
     New Expenses Page Experience (Beta)**
3. Select **Cloud Planning** → **Enable Cloud Planning.** This step enables the Cloud
   tab under Expenses.
4. To connect to IBM Cloudability’s Cloud Financial Planning (CFP) select **Cloud Planning**→ **Enable Cloud Financial Planning Integration.**
5. Click **Save and Exit** button

## Permissions

You can control who can view or edit cloud expenses:

- **ViewCloud -** Allows viewing and editing lines in the Cloud tab.
- **CanImportFromCloudability -** Provides access to import data from CFP and delete
  the imported lines.
- By default, both these permissions are granted to **Admin** and **Budget Process
  Owner** roles, and **Cost Center Owner** has **ViewCloud** permission only.

- **[Manage Cloud Expenses (without CFP Integration)](../../it-planning/planning/manage-cfp-wo-int.html)**
- **[Set Up and Manage Cloud Financial Planning Integration](../../it-planning/planning/cfp-integration.html)**
