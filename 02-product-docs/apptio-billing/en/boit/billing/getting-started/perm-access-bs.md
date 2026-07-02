---
source_system: "apptio-billing"
practice: "tbm"
language: "en"
doc_type: "boit"
title: "Permissions and access types for Billing Standard"
breadcrumb:
  - "Billing"
  - "Getting started"
  - "User Roles and Permissions"
source_path: "boit/billing/getting-started/perm-access-bs.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Permissions and access types for Billing Standard

The following table lists available permissions specific to Billing Standard and their
descriptions:

|  |  |
| --- | --- |
| **Permission Name** | **Description** |
| ViewDataQualityAndMonthlyProcessReports | Enables the user to access the Billing Quality Collection. |
| ViewBusinessRelationshipReports | Enables the user to access everything EXCEPT the Billing Quality collection. |
| ManageAndSendInvoices | Enables the user to configure and send email bills. |
| ViewServiceProviderReports | Enables the user to access the IT Service Provider Report collection. |
| ViewBusinessUserReports | Enables the user to access the Service Charges report collection. |

Billing relies on a combination of front-end access and back-end access (via TBM Studio). Not
everyone needs both.

## Front-end access

**Front-end access is used to:**

- View and interact with Billing reports (invoices, detail views, unit-rate analysis,
  variance views).
- Export data for offline analysis or journal preparation.
- For some implementations, adjust rates or other configuration values that are
  intentionally exposed through editable tables and upload mechanisms.

**Common access patterns:**

- Admins and Analysts have broad access to Billing report collections.
- Service or Product Owners see views for their services or products.
- Consumers and Stakeholders see the parts of the Billing catalog that relate to their
  business units or cost centers.

## TBM Studio access

**TBM Studio access is used to:**

- Install and update Billing components.
- Adjust models, metrics, datasets, and table definitions that Billing depends on.
- Diagnose data issues that require examining upstream logic in Costing.

**Typical patterns:**

- Admins, Analysts, TAS, and Partners who design or maintain Billing logic work in TBM
  Studio.
- Service or Product Owners, Senior Leaders, and Consumers usually do not need TBM Studio
  access.
