---
source_system: "apptio-billing-standard"
practice: "tbm"
language: "en"
doc_type: "billing"
title: "Recent releases"
breadcrumb:
  - "Release Notes"
  - "Recent releases"
source_path: "SSV8ML/boit/billing/release-notes/whats-new.html"
images: []
capability_ids: []
last_updated: "2026-07-06"
summary: ""
---
# Recent releases

*This section describes changes to the out-of-box Billing content only, not the underlying platform. For platform-level updates such as TBM Studio and Client server behavior, readers should review TBM Studio’s Release Notes and consider applicable changes alongside what is documented here.*

Changes listed in this section are limited to updates delivered through Component Templates for Billing. Billing Essentials is exclusively associated with Component Template version 200, while Billing Standard is associated with Component Template version 120 and earlier. When reviewing a change, always confirm which Component Template version or Billing edition your environment is using to understand whether that change applies to your Billing implementation.

## Important Announcements

None

## Billing Essentials (template version 200) - February 28, 2025

- Japanese language support has been added to improve accessibility for users.
- The Rate Management report now includes a new Rate Adjustment Impact metric, providing additional insights into rate changes.
- A new “Billing Cost Model” report has been added to the “Billing” report collection to provide a summary of billing allocation flows.

## Billing Essentials (template version 200) – January 17, 2025

This release provides the following enhancements to improve the overall user experience and provide more efficient management of billing and data upload processes.

- Enhanced Reporting : The Billing Process Admin Report has been integrated into the Billing collection, with role-based access control (RBAC) permissions configured to restrict access to authorized Billing Process Owner(s).
- Journal Entry Export and Archiving : The Billing Journal Archive tab now enables users to export journal entries to an Excel file (.xlsx) and create a flattened table for audit reporting purposes, utilizing a CopyTable script to ensure data integrity.

Fig #: IBM Apptio Billing’s “Billing Process Admin” report demonstrating journal entry export feature.

- Invoice Archiving : The Bill Invoice Archive tab features a Copy Invoice Details button script, which facilitates the archiving of bill invoices by creating a duplicate copy of the original invoice, ensuring a permanent record for auditing and compliance purposes.
