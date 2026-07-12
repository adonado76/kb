---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Master Report Best Practices"
breadcrumb:
  - "Reference"
  - "Report Studio Reference"
  - "Master Reports"
  - "Master Report Best Practices"
source_path: "SSWRJM/studio/new-uc/reference/report-studio-reference/master-report-best-practices.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Master Report Best Practices

Follow these best practices when creating and using master reports to ensure optimal results:

Design Guidelines

1. Use master reports as layout aids : Generally, create containers such as group boxes within which you will place components like charts and tables in child reports. Masters are most effective when they define structure, not content.
1. Plan tabbed component usage carefully : If you add a tabbed component to a master report, be sure to add all necessary content to each tab within the master itself. You cannot add components to individual tabs in the child report. Components placed on top of a tabbed component in the child report will display on top of all tabs.
1. Use group boxes for visual structure only : Group boxes added to a master report lose their component grouping functionality when applied to child reports. Use them as visual borders and layout containers, not as functional grouping mechanisms.
1. Configure button context appropriately : If you add a button to a master report that uses Wiki text without specifying a Data URL, the application will use the current (child) report as the context. Plan your navigation accordingly.

Maintenance Guidelines

- Document your masters : Maintain a list of which master reports exist and which child reports use each master
- Test changes thoroughly : When updating a master report, review how changes affect all child reports before deploying
- Use naming conventions : Prefix master report names with "Master -" or similar identifier to easily distinguish them from regular reports
- Limit master nesting : While you can apply master reports to other master reports, this is not recommended due to complexity and potential confusion
