---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Tab Visibility Rules"
breadcrumb:
  - "TBM Studio"
  - "How-To Guides (Task-Based)"
  - "IBM Apptio Report Studio (New)"
  - "Components"
  - "Tabs"
source_path: "studio/report-studio/components/tab-visible.html"
images:
  - "resources/images/studio_images/tbr2.png"
  - "resources/images/studio_images/tvr1.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Tab Visibility Rules

You can control whether a tab is visible or hidden to report viewers by defining a Visibility
Rule.

**Setting a Visibility Rule**

![image of tab visibility rule option](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/tvr1.png)

![image of tab visibility popup with visibility rule](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/tbr2.png)

Each tab in a Tabbed Group (Tabs) includes an **overflow menu** that provides additional
configuration options.

To define a visibility rule:

1. Open the **overflow menu** for the tab.
2. Select **Visibility Rule**.
3. Enter the expression that determines whether the tab should be visible.

The tab will be shown or hidden to users in the report viewer based on the result of the
visibility expression.

**Default Behaviour**

- The first tab in a Tabbed Group always remains visible.
- For this reason, the Visibility Rule option is disabled for the first tab.
- Visibility rules can only be configured for subsequent tabs.

**Visibility States**

A tab can have one of the following states:

- **Visible** – The tab appears to users when viewing the report.
- **Hidden** – The tab does not appear to users when viewing the report.

The visibility state is determined by the **result of the configured expression**.

**Example**

You can create a visibility rule that allows administrators to see a tab while keeping it
hidden from end users.

Visibility Rule: `<%=IF(eval({$CurrentUser}:
{Users.Role})=Admin,enabled,hidden)%>`

This allows report admins to display specific information only to certain user roles.

**Parent topic:** [Tabs](../../../studio/report-studio/components/rs-tabs.html "The Tabs component lets you organize report content into multiple tabs within a single report. Each tab can contain its own layout of components and visualizations, helping structure complex reports into clear, navigable sections.")
