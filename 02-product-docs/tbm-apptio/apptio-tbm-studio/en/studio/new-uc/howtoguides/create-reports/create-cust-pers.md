---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Create Custom Perspectives"
breadcrumb:
  - "TBM Studio"
  - "How-To Guides (Task-Based)"
  - "Create Reports"
  - "Report Customization"
source_path: "studio/new-uc/howtoguides/create-reports/create-cust-pers.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Create Custom Perspectives

**Objective:** Create a custom perspective that organizes selected fields for business
users, making reports easier to build and more consistent.

**When to use:** Use custom perspectives when you want to:

- Provide analysts with a curated set of commonly-used fields
- Add fields from multiple tables into a single, easy-to-access location
- Lock fields to specific tables for predictable results in production reports
- Hide technical complexity from business users who build reports

**Prerequisites:**

- Power User or Admin role (or custom role with Edit Models permission)
- Access to Report Studio in edit mode
- Understanding of which fields your analysts need most frequently

**Time estimate:** 15-30 minutes per perspective

## Understanding Custom Perspectives

The Project Explorer in Report Studio displays several standard sections: Tables, Metrics,
and Time. While these sections provide access to all available data, they can be
overwhelming—especially business analysts who only need a subset of fields.

Custom perspectives solve this problem by letting you create curated groups of fields.
Think of a custom perspective as a "favorites" list that contains exactly what your users
need. An advantage is that you can add fields from several different tables and lock each
field to its source table. This makes it possible to build reports that contain data from
several tables at different levels in your model.

**Key concepts:**

- **Power Users** see all sections: Tables, Metrics, Time, and Perspectives
- **Analysts** see only custom perspectives and the Time section, simplifying their
  view
- All analysts see all custom perspectives—you cannot create different perspective sets
  for different analyst groups
- Custom perspectives appear in alphabetical order at the top of the Perspectives
  area

## Step-by-Step: Create a Custom Perspective

1. In the **Project Explorer**, locate the **Perspectives** section.
2. Right-click in the **Perspectives** section and select **Add New
   Perspective**.
3. In the **Create Perspective** dialog, enter a descriptive name for the perspective
   (for example, "IT Finance Analytics" or "Monthly Cost Review") and click **OK**.

**Tip:** *Choose names that clearly communicate the perspective's purpose to your
analysts.*

## Step-by-Step: Add Fields to a Custom Perspective

You can add fields to a perspective using any of these methods:

**Method 1: Drag from Project Explorer**

1. Locate a field in the **Tables**, **Metrics**, or **Time** section of the
   **Project Explorer**.
2. Drag the field to the **Perspectives** header in the **Project Explorer**.
3. When prompted, select the target perspective and click **OK**.
4. Complete the **Publish Field** dialog (see field options below).
5. Click **Publish**.

**Method 2: Drag from Component Configuration**

1. While configuring a report component, locate a useful field in the **Component
   Configuration** panel.
2. Drag the field to the Perspectives section title bar.
3. Complete the **Publish Field** dialog and click **Publish**.

**Method 3: Right-click in Component Configuration**

1. Right-click a field in the **Component Configuration** panel.
2. Select **Publish**.
3. Complete the **Publish Field** dialog and click **Publish**.

## Publish Field Dialog Options

When you publish a field, you configure several important options:

|  |  |
| --- | --- |
| **Field** | **Description** |
| Name | The display name for the field. If locking to an object, consider including the object name for clarity. |
| Data Type | Controls basic formatting. Select from Currency, Number, Percentage, etc. |
| Lock to object | When checked, ensures the field applies only to the specific object selected when publishing. Best practice: Always lock fields in production reports. |
| Represents a hierarchy code | Applies only to slicers. When checked, the field creates hierarchical groupings based on search characters. |
| Show all rows in time-based query | When checked, displays all rows in time-based tables even if some periods have zero values. Required for calculations using PreviousYear, YearToDate, and similar time functions. |
| Description | Displayed as a tooltip when users hover over the field. Provide clear explanations to help analysts understand the data. |
| Notes | Information visible only to other Power Users in this dialog—useful for documenting field configuration decisions. |

## Step-by-Step: Organize Fields with Groups

Group related fields within a perspective for better organization:

1. Right-click within a custom perspective and select **Add New Group**.
2. Enter a name for the group (for example, "Cost Metrics" or "Business Unit
   Dimensions").
3. Drag fields from elsewhere in the perspective into the group.

To remove a field from a group, drag it to a blank area within the custom perspective.

Tip: Groups are especially useful for hierarchical slicers. The order of fields
within a group determines the slicer hierarchy.

## Step-by-Step: Create an Admin-Only Perspective

Sometimes you need perspectives for Power Users and Admins that analysts shouldn't see:

1. Create a new perspective as described above.
2. When naming the perspective, enclose the name in parentheses—for example, **(Admin
   Fields)** or **(Technical Metrics)**.
3. Click **OK**.

Perspectives with parentheses around their names are visible only to users with Admin
roles.

## Managing Custom Perspectives

**Rename a perspective:** Right-click the perspective name and select **Rename**.

**Delete a field:** Right-click the field within the perspective and select **Delete
Field**.

**Delete a perspective:** Right-click the perspective title bar and select
**Delete**.

**Edit a published field:** Right-click the field and select **Edit** to modify its
properties.

## Common Pitfalls

- **Unlocked fields produce inconsistent results:** If you don't lock a field to its
  object, it may apply to whatever object is currently selected in the report, leading to
  unexpected data.
- **Missing descriptions confuse analysts:** Take time to write helpful
  descriptions—analysts may not know your data model.
- **Too many fields defeat the purpose:** Be selective. A perspective with 100 fields
  isn't much better than the raw Tables view.
- **Forgetting time-based query option:** If you're publishing calculated metrics that
  reference other time periods, check "Show all rows in time-based query" to ensure complete
  data displays.

**Parent topic:** [Report Customization](../../../../studio/new-uc/howtoguides/create-reports/report-cust.html)
