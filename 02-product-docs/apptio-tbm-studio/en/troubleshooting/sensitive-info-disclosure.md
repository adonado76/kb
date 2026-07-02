---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "troubleshooting"
title: "TBM Studio Workspace State Management Changes"
breadcrumb: []
source_path: "troubleshooting/sensitive-info-disclosure.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# TBM Studio Workspace State Management Changes

Applies to: Server 12.11.8/ BFF-2.8.0

This functionality allows users to efficiently restore their workspace after the user returns
back to TBM studio again.

## Background

TBM Studio currently stores workspace state information locally in the browser. This information
includes:

- Last accessed documents
- Open folders
- Open documents
- Last selected application (CT or TBM Studio)
- Project details (if TBM Studio was last used)

## Security Concerns and Changes Implemented

A recent security audit identified the storage of sensitive data in the browser as a
vulnerability. To address this concern, the following changes have been implemented:

- Users will have the option to disable browser storage of workspace state information.
- Disabling browser storage will prevent the automatic restoration of the previous workspace upon
  login.

## Impact on Users

## TBM Studio Users

By default, users will now land on the calculation page instead of their last project upon
opening TBM Studio.

Previously saved workspace state like active project, explorer sections, tabs, and check-out
document state will no longer be automatically restored.

![](../../resources/images/studio_images/ts-1.png)

## CT - Bill of IT Users

No impact on end users.

## Frequently Asked Questions (FAQ)

Is disabling browser storage mandatory?

No, it's an optional feature available to all customers in all regions.

Government Customers: Browser storage is disabled by default for government customers. They
cannot restore the previous state unless storage is enabled via the `/data` setting.

Can users have both security and workspace restoration?

Currently, this is not possible. However, users can set a default project in TBM Studio to ensure
they land on that project instead of the calculation page. This approach won't restore other
workspace settings.

How to disable browser storage?

This information is not intended for public release notes. Government customers can contact their
CSM to enable storage via `/data`.

## Additional Notes

This change affects Server version 12.11.8 and BFF version 2.8.0.

While this change may cause inconvenience, we are exploring alternative solutions to restore
workspace state information securely in the future. It is recommended that all users carefully
consider the trade-off between security and convenience when deciding whether to disable browser
storage.
