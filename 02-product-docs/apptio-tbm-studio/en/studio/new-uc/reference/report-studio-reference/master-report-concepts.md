---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Master Report Concepts"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Report Studio Reference"
  - "Master Reports"
source_path: "studio/new-uc/reference/report-studio-reference/master-report-concepts.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Master Report Concepts

**What is a Master Report**

A master report is a special type of report that defines reusable layout elements that can be
applied to multiple child reports like a template. The concept is similar to master slides in
presentation applications like PowerPoint. When you apply a master report to a custom report, the
master's components appear as a background layer (often referred to as "wallpaper") that provides
consistent visual structure.

Master reports can include all the components available in regular reports, such as buttons,
group boxes, action items, headers, and navigation elements. However, their primary purpose is to
establish a consistent framework within which report-specific content is placed.

**Master vs. Regular Report Differences**

|  |  |  |
| --- | --- | --- |
| **Aspect** | **Master Report** | **Regular Report** |
| **Purpose** | Template for multiple reports | Standalone report for end users |
| **Hierarchy Level** | Always top-level by default | Can be any level in hierarchy |
| **Component Editing** | Components static in child reports | All components fully editable |
| **Availability** | Listed in Masters drop-down menu | Listed in Project Explorer |
| **Deletion** | Standard masters cannot be deleted | Can be deleted (except OOTB) |

**Use Cases for Master Reports**

Master reports are ideal for scenarios where you need consistent presentation across multiple
reports:

- **Corporate branding**: Apply consistent company logos, colors, and styling across all
  reports in a project
- **Navigation frameworks**: Establish uniform navigation buttons and links that guide users
  through a report suite
- **Layout standardization**: Define consistent placement of headers, footers, and content
  areas
- **Common filter sets**: Provide shared slicers and filters that apply across related reports
- **Report collections**: Create a cohesive look and feel for a set of related analytical
  reports

**The Wallpaper Model**

Think of master reports as wallpaper. When applied to a custom report, the components in a master
report:

- Cannot be edited or modified from within the child report
- Appear as a static background layer
- Components you add to the child report sit "on top of" the master components
- Can only be modified by editing the master report directly

Tip: For example, if the master includes a group box, you can position components in the
child report so they appear inside the group box visually, yet they are not actually attached to or
grouped with the master's group box.

**Parent topic:** [Master Reports](../../../../studio/new-uc/reference/report-studio-reference/master-report.html)
