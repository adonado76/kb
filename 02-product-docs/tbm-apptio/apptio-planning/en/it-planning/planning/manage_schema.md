---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Schemas"
breadcrumb:
  - "Planning"
  - "Configuration and Administration"
source_path: "it-planning/planning/manage_schema.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Schemas

Schemas define the structure of data in Apptio Planning. They specify the tables,
fields, and relationships that determine how information is stored, linked, and surfaced across
Expense tabs such as Labor, Contracts, Assets, and Financials.

Note: Admin or Budget Process Owner roles are required to manage schemas.

From the **Schemas** page, administrators can manage:

- **Line Item Schemas** – Define data structures for Financials, Actuals, Labor,
  Contracts, Assets, and Labor Activity line items.
- **Standard Dimensions** – Out-of-the-box dimensions such as **Department**,
  **Account**, or **Cost Center** used across all Line Item Schemas. =
- **Custom Dimensions** – User-created dimensions (up to 40 for release 5.12) for
  organization-specific data.

Schemas ensure consistency between dimensions and line items, enabling users to analyze data
seamlessly across plans.

## Managing Line Item Schemas

Apptio Planning supports multiple schema types, each corresponding to a key planning area:

|  |  |
| --- | --- |
| **Line Item Type** | **Description** |
| Financials | Captures operational and capital expenses (OpEx/CapEx). Data from this schema is displayed in the **Summary** and **Other** tabs. |
| Assets | Tracks asset purchases, depreciation, and financial impact over time. Data from this schema is displayed in the **Assets** tab. |
| Contracts | Used for managing vendor agreements and applying amortization schedules. Data from this schema is displayed in the **Contracts** tab. |
| Labor | Defines headcount, compensation, and allocation rules for labor cost planning. Data from this schema is displayed in the **Labor** tab. |
| Labor Activity | Used for tracking project labor hours and cross-charges. Data from this schema is displayed in the **Labor Activity** tab. |
| Actuals | Stores actual transactional data for forecasting and variance analysis. Data from this schema is displayed in **Spend Management**. |

## Standard and Custom Dimensions

**Dimensions** are shared reference data used to categorize and group information across
schemas.

Apptio Planning supports two types:

- **Standard Dimensions** – Provided out-of-the-box, such as **Department**,
  **Account**, and **Cost Center**. These are linked automatically to related
  schemas.
- **Custom Dimensions** – User-created dimensions that allow you to extend the data model to
  match your business needs. You can add **up to 40 custom dimensions for release 5.12.**

Each dimension can include **attributes** (columns) that add context and detail — such as
“Region,” “Manager,” or “Business Unit.” These attributes are available for filtering,
grouping, and reporting.

Note: When a dimension is shared across multiple schema types (for
example, “PO Number” appears in both Contracts and Financials), data from those schemas
automatically carries through from the **Contracts tab** to the **Summary tab**.

Create a Custom Dimension 

1. Navigate to **Planning** > **Configuration** > **Schema.**
2. Select the **Custom Dimensions** tab.
3. Click the **+**(Add) button.
4. Complete the following fields:
   - **Name** – Enter a name for the new dimension.
   - **Description** – Provide a brief description of the dimension’s purpose.
   - **Add To** – Select the Line Item Schemas where this dimension should be
     available.
5. Click **Add** to create the custom dimension.

Edit or Delete a Custom Dimension

To **edit**:

1. Navigate to **Planning > Configuration > Schema**.
2. Select the **Custom Dimensions** tab.
3. Click the dimension name or right-click → **Edit**.
4. Update the available attributes.

To **delete**:

1. Right-click the dimension name.
2. Select **Delete**.

Important: Deleting an attribute permanently removes all data stored in that
field across all plans.

## Custom Attributes

Custom attributes allow you to extend built-in or custom dimensions with additional fields
to capture metadata relevant to your organization.

For example, you might add:

- **“Program”** or **“WBS Code”** to a **Project** dimension.
- **“Region”** to a **Department** dimension.
- **“PO Number”** to a **Contract** schema.

You can add **up to 60 custom attributes per dimension**, and they will appear as
additional columns in the related reference data tables.

Supported Attribute Types

|  |  |
| --- | --- |
| **Type** | **Description** |
| String | Stores text values such as names, descriptions, or codes. Supports a maximum of 255 characters. |
| Date | Captures a specific calendar date (e.g., contract start date or hire date). |
| Integer | Stores whole numbers without decimals (e.g., headcount, number of licenses). |
| Numeric | Stores numeric values, including decimals, for financial or quantitative data (e.g., cost, rate). |
| Percentage | Represents numeric values as percentages (e.g., allocation rate, utilization). |
| Memo | Used for long-form text or notes, such as comments or detailed descriptions. Supports a maximum of 1024 characters. |
| List | Provides a predefined set of selectable values (e.g., region, department type). |
| User | References a user within Apptio Planning, allowing assignment of ownership or responsibility. |
| Boolean | Stores true/false values, used for toggles or binary indicators (e.g., active/inactive, yes/no). |
| Link | Stores clickable URLs that open in a new browser tab. Useful for referencing external resources such as Jira tickets, documentation, or dashboards. |

Add a Custom Attribute

1. Navigate to **Planning** > **Configuration** > **Schema**.
2. Select the appropriate tab — **Line Items**, **Standard Dimensions**, or **Custom
   Dimensions** — depending on where you want to add the attribute.
3. Click the specific **line item type** or **dimension** to open its details.
4. On the **Available Attributes** page, click **Add**.
5. Complete the following fields:
   - **Field Name** – Enter a name for the new attribute.
   - **Data Type** – Choose from the supported attribute types.
   - **Default Value** – Optionally define a default value for the field.
   - **Mandatory for Data Entry** *(Line Item Schemas only)* – Require users to
     complete this field when entering data.
   - **Sensitive Data***(Labor Line Item Schema only)* – Restrict visibility to
     authorized users (controlled by **[Cost Object
     Permissions](manage-cost-object.html)**).
   - **Restricted Access***(Line Item Schemas only)* – Limit editing rights to Admins or
     users with the ***EditRestrictedDimensions*** permission.
6. Click **Add** to save the custom attribute.

Edit or Delete a Custom Attribute

To **edit**:

1. Navigate to **Planning > Configuration > Schema**.
2. Select the dimension or line item type.
3. Open the **Available Attributes** dialog.
4. Click the attribute name or right-click → **Edit**.
5. Update the name or default value and click **Save**.

To **delete**:

1. Right-click the attribute name.
2. Select **Delete**.

   Important: Deleting an attribute permanently removes all
   data stored in that field across all plans.
