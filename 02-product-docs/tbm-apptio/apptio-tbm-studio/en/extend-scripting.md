---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Scripting"
breadcrumb:
  - "How-To Guides (Task-Based)"
  - "Integrate and Extend"
  - "Scripting"
source_path: "SSWRJM/studio/new-uc/howtoguides/integrate-extend/scripting.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Scripting

| Content Type | How-To Guide |
| --- | --- |
| Content Type | How-To Guide |
| Target Audience | Business Analysts, Developers |
| Prerequisites | Basic TBM Studio familiarity, understanding of editable tables |

ApptioScript is TBM Studio's scripting language for building interactive business applications. It allows you to automate data operations, implement business logic, and create workflow-driven processes that extend beyond TBM Studio's built-in capabilities.

This section contains two how-to guides: the first introduces ApptioScript fundamentals and shows you how to write your first scripts , while the second covers common patterns you can adapt to for your business scenarios. For complete function documentation, see Section 5.6: ApptioScript Reference.

What You Can Do with ApptioScript

- Automate data entry and updates — Add, edit, or delete rows in editable tables programmatically
- Implement business workflows — Create approval processes, status transitions, and automated notifications
- Control user experience — Make cells required or read-only based on conditions, implement cascading dropdowns
- Create audit trails — Automatically track who edited data and when
- Copy and transform data — Move data between tables, projects, or time periods
- Send notifications — Trigger emails when specific conditions are met

## When to Use ApptioScript vs. Built-in Features

TBM Studio provides many built-in capabilities. Use ApptioScript when you need behavior that goes beyond standard configuration.

| Scenario | Built-in Feature | When to Use ApptioScript |
| --- | --- | --- |
| Scenario | Built-in Feature | When to Use ApptioScript |
| Simple dropdown lists | Column Possible Values | Use script for cascading dropdowns with complex logic |
| Data validation | Validation rules in column config | Use script for cross-field validation |
| Calculated values | Calculated metrics | Use script for row-level calculations in editable tables |
| User notifications | Not available | Use SendEmail() function |
| Workflow status changes | Not available | Use EditRows() with button actions |
| Audit trails | System audit log | Use script for user-visible edit tracking in tables |
