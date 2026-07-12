---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Inheritance"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Report Studio Reference"
  - "Master Reports"
source_path: "studio/new-uc/reference/report-studio-reference/inheritance.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Inheritance

**How Child Reports Inherit from Master**

When you apply a master report to a custom (child) report, the master's content appears as a
background layer. The child report inherits the visual appearance and any interactive elements
defined in the master, but the inheritance model follows the "wallpaper" concept:

- Master components render first, forming the base layer
- Child report components render on top of the master layer
- The two layers are visually combined but remain functionally separate

**What is Inherited**

- **Layout structure**: Group boxes, visual containers, and spatial organization
- **Static components**: Buttons, notes, logos, and branding elements
- **Interactive elements**: Tabbed components (tabs function when master is applied)
- **Navigation**: Links and buttons that navigate between reports

**What is NOT Inherited**

- **Editability**: Master components cannot be modified from the child report
- **Component grouping**: Group boxes lose their grouping functionality in child reports
- **Tab component content areas**: You cannot add components to individual tabs within the
  child report
- **Data bindings**: Report-specific data configurations remain unique to each report

**Parent topic:** [Master Reports](../../../../studio/new-uc/reference/report-studio-reference/master-report.html)
