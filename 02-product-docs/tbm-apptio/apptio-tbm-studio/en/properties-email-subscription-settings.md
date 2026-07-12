---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Email Subscription Settings"
breadcrumb:
  - "Reference"
  - "Report Studio Reference"
  - "Report Properties"
  - "Email Subscription Settings"
source_path: "SSWRJM/studio/new-uc/reference/report-studio-reference/email-sub-settings.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Email Subscription Settings

Email subscriptions allow reports to be automatically distributed to users on a scheduled basis.

Subscription Configuration

| Setting | Description |
| --- | --- |
| Setting | Description |
| Subscription Name | Auto-populated as <Report Collection - Report Name>. Can be customized. |
| Recipients | Email addresses of users who will receive the subscription. Must be valid email addresses from authorized domains. |
| Reporting Period | Current Period uses the active period when the subscription runs. Can also specify a fixed period. |
| Include PDF in attachment | Attaches a PDF version of the report to the email |
| Filtered Views | Enables sending reports with pre-applied slicer selections |
| Bulk Upload XLS | Enables mass distribution with unique filtered views per recipient |

Security note: Emails can only be sent to authorized domains configured in the customer's environment. Row-Level Security (RLS) is not applied in email subscriptions.
