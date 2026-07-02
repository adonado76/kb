---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Summarize Labor Financials"
breadcrumb:
  - "Planning"
  - "Labor Planning"
source_path: "it-planning/planning/labor-summarization.html"
images:
  - "resources/images/it_planning_images/config1.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Summarize Labor Financials

The Summarize Labor Financials feature enables you to determine how your labor cost data
is aggregated and presented in the Summary tab. It controls which dimensions (e.g., Cost Center,
Account, Location) are used to group and roll up labor cost lines, ensuring you get the right
level of visibility and confidentiality for labor financials.

Note: Admin or Budget Process Owner roles are required to configure labor summarization.

## How It Works

- When labor line items are entered in the Labor tab, the system uses your defined Labor
  Allocation Rules to generate financial entries by account.
- The **Labor Summarization Settings** specify which dimensions are used to group and
  aggregate those financial entries in the Summary tab.
- This allows you to maintain summarized labor costs (e.g., by Cost Center or Account)
  instead of seeing each labor entry individually.
- Choosing summarization dimensions also helps protect sensitive data, as aggregation
  hides individual-level compensation details.

## Default Summarization Dimensions

By default, the following dimensions are available to summarize by:

- **Account**
- **Cost Center**
- **Cost Object**
- **Comment**
- **Location**
- **Project**
- **Vendor**
- **Description**
- **Employee Name**

**Cost Center, Cost Object,** and **Account** are *always selected* and cannot
be removed, as they are required for aggregation. If Integrated Investment Planning is
enabled, Project is also selected and cannot be removed.

In addition to these standard fields, **custom dimensions** that exist in both the
Financials and Labor schemas will also appear in this list and can be selected for
summarization.

## Configuration Steps

1. Navigate to **Settings (Gear icon) → Company Profile**
2. Under the **Labor Headcount** section, enable **Labor Summarization**
3. Select the dimensions you want to use for summarization.
4. Click **Save and Exit** to apply changes.

Newly created plans will automatically use these summarization settings. For existing
plans, re-creating the plan is required to apply the updated settings.

![image of configuration steps](../../../../../03-media/apptio-planning/resources/images/it_planning_images/config1.png)

## Best Practices

- Choose broad dimensions for summarization (like Cost Center or Account) when you need
  confidentiality and high-level roll-up.
- Include more granular dimensions (like Location or Description) only when detailed
  visibility is required—and make sure data access controls are in place. Refer to [Hide Sensitive Labor Data](hide-sensitive-labor-data.html "Administrators can restrict visibility of specific columns in the Labor tab—such as employee name, salary, or other compensation details—so that users without the required permission can view labor entries without seeing sensitive fields.") for more details.
