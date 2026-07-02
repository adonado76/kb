---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "admin"
title: "Calc Management Settings"
breadcrumb: []
source_path: "admin/cacl-mgmt-settings.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Calc Management Settings

Applies to: 12.11.0 and later. Customers can now disable/enable staging calculations at a
project level, so that they can control which projects get calculated and in turn, reduce the number
of total calculations.

Calc Management is not active by default. To enable it, navigate to Project > **Enable
Features**, and then select Project Calc Management.

![](../../resources/images/studio_images/proj-calc-mgmt.png)

## Navigation

Navigate to Build tab on the TBM Studio Ribbon and select Calc Management

![](../../resources/images/studio_images/cm-ribbon.png)

The Project Calculation Management popup appears with three tabs - Calc Settings, Dev Queue, and
Staging Queue

![](../../resources/images/studio_images/pcm-popup.png)

## Calc Settings

This tab shows the list of projects with their priority along with the state of the staging
environment(enabled/disabled). You can update the priority by dragging the row or entering the
desired value in the priority input box. Additionally you can update the state of any project from
this tab by toggle button. If you want to enable/disable all the projects in one go, you can use
Enable All/ Disable All Button at the top of the table. \*\*

Once done, enter a Reason to document the purpose for the change and click Submit
button.

## Dev Queue & Staging Queue

There is no change in the functionality of Dev Queue and Staging Queue. To know
more, see [Calc
Prioritization](default-calc-prioritization.htm "(Opens in a new tab or window)").

## Multi-Tenant Scenario

There are two scenarios in a multi-tenant system:

- With limited access: If a user has access to all or few tenants, they can update the
  state of the projects which they have access for but cannot update the priority of any project. The
  Stage Queue and Dev Queue would be disabled for a user with limited access.
- With full access: If a user has access to all tenants, they can update the state or
  priority of any project listed in the tab.
