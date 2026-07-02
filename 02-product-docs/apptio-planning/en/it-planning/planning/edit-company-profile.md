---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Company Profile Settings"
breadcrumb:
  - "Planning"
  - "Configuration and Administration"
source_path: "it-planning/planning/edit-company-profile.html"
images:
  - "resources/images/studio_images/studioimages/icons/setting-icon.jpg"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Company Profile Settings

The Company Profile allows Admin and Budget Process Owner users to configure
application-wide settings that customize the display, enable or disable features, and define
workflow behavior across Apptio Planning.

Note: Admin or Budget Process Owner roles are required to manage Company Profile Settings.

## Accessing the Company Profile

1. Select the **Settings** button (![img](../../../../../03-media/apptio-planning/resources/images/studio_images/studioimages/icons/setting-icon.jpg)) from the top-right corner and choose
   **Company Profile**.
2. Enter or edit the information as needed.
3. Select **Save and Exit**to apply the changes.

## General Configuration

|  |  |  |
| --- | --- | --- |
| **Section** | **Feature** | **Description** |
| Currency | Default Currency | Sets the primary currency used across all plans. All monetary values default to this currency unless multi-currency is enabled. |
| Currency | Enable multi-currency | Allows users to plan in multiple currencies. Currency conversion rules apply when enabled. |
| Currency | Display ISO currency codes instead of currency symbols. | Replaces currency symbols (e.g., $, £) with ISO codes (e.g., USD, GBP). |
| Number Format | Enable Decimal Number Precision | Control the number of decimal places shown in numeric fields in plans. |
| Number Format | Decimal Places | Specifies the number of decimal places (e.g., 1–8) that will be used when decimal precision is enabled. |
| Access & Permissions | Enable Enforce View Permissions | Restricts Department visibility based on user permissions. Users only see cost objects they are authorized to access. |
| Access & Permissions | Enable New Expenses Page Experience (Beta) | Enables the redesigned Expenses page, offering improved performance, filtering, and navigation. |
| Access & Permissions | Enable Plan Level Cost Object Permissions | Enables the User Permissions page at the individual plan level to manage permissions per plan. |
| Approval Workflows & Notifications | Approval Workflow | Defines how plan submissions move through the approval process.    Choose between Multilevel Approval (sequential approvers) or Hierarchical Approval (organizational reporting structure).    For Hierarchical Approvals, optionally choose to disable Group Department submissions. |
| Approval Workflows & Notifications | Send Email Notifications for Planning Process Events | Sends email alerts when plans are submitted, approved, or returned. |
| Variance Analysis | Enable Variance Analysis | Enables Variance Analysis, allowing users to capture variance drivers and add commentary. |
| Forecasting | Summarize Actuals | Selects the attributes used to roll up and summarize actual transaction data for forecasting. |
| Data Management | Enable External Code | Allows storing external system identifiers for plan line items. |
| Data Management | Disable Update Reference Data Restrictions | Permits updating Reference Data values even when changes may delete existing plan data. The system generates a backup before applying the update. |
| Data Management | Enable Automated Data Management Integration | Enables data imports and synchronization through ADM. |
| Upgrades & Maintenance | Upgrade Day | Specifies the day your environment receives product updates. |
| Show Period Date Ranges | Display date range for period columns | Displays start date and end date for the period columns in the Expenses table. Dates are formatted according to user’s configured locale. Note – Available only in the Expenses > New View |
| Data Spread Settings for Other Expenses | Set Calendar Days Spread as Default | When enabled, amounts entered in the **quarterly** or **annual** columns are automatically distributed across months based on the number of calendar days in each month.  Users can override this default at the Expenses table level and select either **Even Spread or** **Calendar Days Spread** |

## Labor Planning

|  |  |  |
| --- | --- | --- |
| **Section** | **Feature** | **Description** |
| Labor Headcount Planning | Labor Headcount | Enables labor headcount planning, allowing users to plan staffing levels, positions, and associated costs within the Labor tab. |
| Labor Headcount Planning | Headcount Summarization Method | Determines how multiple labor records are consolidated (e.g., by averaging or selecting the starting or ending period value). |
| Labor Headcount Planning | Default Labor Start Date | Sets a default start date for new labor entries. |
| Labor Headcount Planning | Disable Base Compensation Warning | Turns off system warnings triggered when base compensation values are blank. |
| Compensation Adjustment | Variable Compensation Adjustment | Enables modeling of variable compensation adjustments. |
| Compensation Adjustment | Adjustment Cycles | Defines the default frequency and timing for compensation adjustments. These settings can be overridden at the plan level. |
| Labor Summarization | Labor Summarization | Select the dimensions used to aggregate financial line items generated from the Labor tab when displayed in the Summary tab. |

## Contract Planning

|  |  |  |
| --- | --- | --- |
| **Section** | **Feature** | **Description** |
| Contract Planning | Contracts | Enables contract-level planning, allowing users to model new and existing contracts within the Contracts tab. |
| Contract Planning | Auto Update Contract Total | Automatically recalculates the contract total when periodic amounts change, ensuring the contract value always reflects the sum of scheduled payments. |
| Contract Planning | Include Value-Added Tax (VAT) | Allows VAT to be applied to contract payments. When enabled, VAT is calculated based on the defined tax rate. |

## Asset Planning

|  |  |  |
| --- | --- | --- |
| **Section** | **Feature** | **Description** |
| Asset Planning | Enable Asset Planning | Enables asset-level, allowing users to model capital assets and calculate depreciation and capital expenses within the Asset tab. |

## Investment Planning

|  |  |  |
| --- | --- | --- |
| **Section** | **Feature** | **Description** |
| Project Planning | Enable Integrated Investment Planning | Enables project-based planning, allowing users to define investments and link expenses to projects. |
| Labor Activity Planning | Enable Labor Activity | Enables users to allocate labor effort (hours or FTE) to projects and generate cross-charge financials based on activity types within the Labor Activity tab. |
| Labor Activity Planning | Labor Allocation | Allows configuration of over- and under-allocation rules for labor resources. When enabled, define thresholds for when a resource is allocated beyond or below its available capacity. |
