---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Tab Visibility Rules"
breadcrumb:
  - "How-To Guides (Task-Based)"
  - "IBM Apptio Report Studio (New)"
  - "Components"
  - "Tabs"
  - "Tab Visibility Rules"
source_path: "SSWRJM/studio/report-studio/components/tab-visible.html"
images:
  - "03-media/apptio-tbm-studio/tvr1.png"
  - "03-media/apptio-tbm-studio/tbr2.png"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Tab Visibility Rules

You can control whether a tab is visible or hidden to report viewers by defining a Visibility Rule.

Setting a Visibility Rule

Each tab in a Tabbed Group (Tabs) includes an overflow menu that provides additional configuration options.

To define a visibility rule:

1. Open the overflow menu for the tab.
1. Select Visibility Rule .
1. Enter the expression that determines whether the tab should be visible.

The tab will be shown or hidden to users in the report viewer based on the result of the visibility expression.

Default Behaviour

- The first tab in a Tabbed Group always remains visible.
- For this reason, the Visibility Rule option is disabled for the first tab.
- Visibility rules can only be configured for subsequent tabs.

Visibility States

A tab can have one of the following states:

- Visible – The tab appears to users when viewing the report.
- Hidden – The tab does not appear to users when viewing the report.

The visibility state is determined by the result of the configured expression .

Example

You can create a visibility rule that allows administrators to see a tab while keeping it hidden from end users.

Visibility Rule: <%=IF(eval({$CurrentUser}: {Users.Role})=Admin,enabled,hidden)%>

This allows report admins to display specific information only to certain user roles.
