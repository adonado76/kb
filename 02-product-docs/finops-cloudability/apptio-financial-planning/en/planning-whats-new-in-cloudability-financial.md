---
source_system: "apptio-financial-planning"
practice: "tbm"
language: "en"
doc_type: "financial-planning"
title: "What's new in Cloudability Financial Planning"
breadcrumb:
  - "What's New in Cloudability Financial Planning"
  - "What's new in Cloudability Financial Planning"
source_path: "SSVWBC/cloud-financial-planning/release-notes/whats-new.html"
images: []
capability_ids: []
last_updated: "2026-07-10"
summary: ""
---
# What's new in Cloudability Financial Planning

## CFP Intelligent Forecasting BETA - June 1, 2026

We released a Beta of our upcoming Intelligent Forecasting capability for CFP. This new experience helps teams keep CFP plans current by refreshing existing forecast lines with projections based on the latest actuals, while giving users greater visibility and control over how those projections are generated.

CFP Intelligent Forecasting brings the same model-driven forecasting experience used in the Enhanced Forecast page into CFP plans. Users can open an individual forecast line, review historical actuals, view projections from multiple forecast models, visually compare those projections against current plan values, and apply the model that best reflects expected future spend.

Key Features

- Interactive forecast review – view an inline mini-graph showing actual spend history and updated projections directly within the forecast line table
- Improved forecast accuracy – use the Intelligent Forecasting engine to evaluate multiple models and recommend the best fit for each forecast line
- Model comparison and control – compare alternate model results and apply a different model when the recommended model does not reflect expected future spend
- Plan-value comparison – visually compare model-generated projections against existing plan amounts
- Re-forecast support – apply selected model results to update historical periods with actuals and future periods with new forecast estimates

Beta Scope

This Beta release supports interactive re-forecasting for individual forecast lines within CFP plans. Users can access Intelligent Forecasting from a forecast line (by clicking the expand icon to reveal the forecast mini-chart), review the latest actuals and projections, compare recommended and alternate model outputs, compare projected values against current plan values, and apply a selected model to update forecast values in the plan.

What’s Coming Next

At GA, CFP Intelligent Forecasting will add support for saving model selections and bulk re-forecasting making it easier for users to update forecasts based on latest actuals as part of a regular monthly update cycle.

Availability and Enablement

The CFP Intelligent Forecasting Beta is available to all CFP customers. Intelligent Forecasting requires Update Actuals functionality, so the Update Actuals feature must be enabled before Intelligent Forecasting can be used.

Both Update Actuals and Intelligent Forecasting can be enabled from the Advanced tab on the Plan Preferences page, located under Settings in the Cloudability left navigation panel. Intelligent Forecasting is automatically enabled for customers that had enabled Update Actuals prior to the Beta release.

Learn more about Intelligent Forecasting

## Forecast Model settings, Improved large-plan performance, async Plan creation - Mar 5, 2026

This release includes enhancements that add forecast model preferences, improve discoverability of plan and forecast settings, and enhance performance for larger plans.

What's New

- Plan Preferences changes In our February 23rd release, we introduced a new global Plan Preferences page. Plan Preferences provides a single home for all planning-related preferences. By locating it under the Settings menu alongside preferences for other Cloudability features, users can more intuitively find and manage settings for both basic and advanced CFP planning. In this release, we are deprecating the existing Plan Dimensions page and relocating its functionality to Plan Preferences for Cloudability Dimensions and to the Plan overflow (3-dot) menu for Plan-only Dimensions - placing these settings in locations that are more intuitive and easier to discover. To support a smooth transition, the existing Plan Dimensions page will remain in the product for now with a message explaining that its functionality has moved and providing a navigation link to the new location.
- Forecast model settings We added a new Forecasts tab to Plan Preferences. This tab lets you control which forecast models are used by the Intelligent Forecasting engine. For example, you can now disable specific models so they are not considered by the engine. These selections apply both to the Enhanced Forecast page and to the forecasts generated during CFP plan creation.
- Large plan performance improvements To better support the creation and use of large plans - those with more than 10,000 rows - we made architectural changes to improve data isolation and reduce the impact of long-running, compute-intensive operations such as plan creation, forecast updates, and report refreshes on neighboring tenants. This reduces slowdowns and UI timeout errors that some customers have experienced. We also significantly improved plan publish performance, reducing the time it takes for plan changes to become available in Apptio BI reporting.
- Asynchronous plan creation We updated the plan creation experience to an asynchronous model, similar to the current Duplicate Plan experience. When you create a plan, it now appears immediately on the Plan Listing page with an in progress indicator. While creation is still in progress, the plan cannot be opened. The user receives a toast notification when creation completes.

## Update Actuals Automation - February 23, 2026

This release adds Update Actuals Automation – a new Plan Owner–initiated capability that replaces forecast values in closed periods with actual spend. The result is a spend-adjusted forecast that reflects actuals to date while preserving forecast values in future periods.

New Capabilities

- Update Actuals action for Plan Owners A new plan action, Update Plan with Actuals , is available in the plan overflow menu (3-dot button in the plan header). Plan Owners can run this action to replace forecast values with actual spend in closed periods across all forecast lines in the plan.
- Locked periods with distinct Actuals visualization Periods updated with actuals are locked to prevent further edits and are visually distinguished from future forecast periods with column highlighting. This makes it clear which months contain read-only actuals versus editable forecast values.
- Smart forecast updates Update Actuals replaces forecast values in historical periods with actuals. If multiple forecast line items share the same forecast-dimension key (for example, a baseline line item plus manually added line items for the same dimension values), Update Actuals distributes the actual amount across all line items that share the same key using the allocation method selected when initiating the operation – proportional or even spread.
- New Plan Preferences page A new Plan Preferences page, located under Cloudability Settings, centralizes Forecast and other CFP plan-specific settings.

Benefits

- Accurate, decision-ready spend-adjusted forecasts By ensuring closed periods reflect actual spend, forecasts become a more reliable control mechanism for variance analysis, year-end projection, and identifying over- or under-spend early enough to take action.
- Automation of a high-volume monthly process While Plan Owners can manually update past periods with actuals, doing so at scale is inefficient and error-prone. Update Actuals automates this monthly reconciliation, reduces administrative burden, and ensures updates are applied consistently across all forecast line items.

How to Access

Use Update Plan with Actuals from the plan overflow menu (3-dot button in the plan header). Only Plan Owners can access this action. Selecting it opens the Update Actuals page, where you can configure and run the operation and monitor completion status.

- Admin enablement is required. An Admin must enable Update Actuals in Settings > Plan Preferences . Until enabled, the Update Plan with Actuals action and related functionality are not available
- Enablement is irreversible. Once enabled, the Forecast line item table permanently uses Inline Edit mode and Summary/Detail mode is removed (the toggle is removed from the UI). This change applies to all plans - existing and future - and cannot be undone

## Enhanced Budgets with Forecast-Level Granularity - December 10, 2025

This release adds support for creating budgets at multiple levels of detail, including the forecast line level, giving you the flexibility to build budgets that more closely align with your organization’s planning needs. It includes the following enhancements:

Flexible Budget Granularity

Select which forecast dimensions to include when creating a budget. You can budget at:

- Cost Object Only
- Cost Object + Shared Budget Categories such as Vendor, Region, or Environment
- Full Forecast-Level Detail , matching the granularity of individual forecast line-items

On-Demand Budget Creation

Plans are now created with forecast data only. You can add a budget whenever you're ready, and initial budget values are automatically summarized from the forecast based on the dimensions you select.

Improved Budget Workflow

Plan Owners can:

- Create or delete budgets
- Refresh budget values using the latest forecast data
- Add budget rows for forecast items introduced after the budget was created

These enhancements give you greater control over how budgets are structured and help ensure they remain accurate and aligned with evolving forecasts.

## Forecast Inline Edit mode - October 31, 2025

This release introduces a new, streamlined inline editing experience for Forecasts. This enhancement replaces the previous “Summary–Detail” model with a single, Excel-like table that makes navigation and editing faster and more intuitive. Users can now view, group, insert, and edit forecast line items directly within one unified table – no need to open a separate panel to view or modify details.

In the current experience, editing a forecast line item requires two steps: opening the cost object’s summary row to display the Details panel, then locating the line item to edit. Inline Edit Mode eliminates that extra step by presenting all forecast line items in a single, editable table.

Benefits

- Faster editing – update values directly in the table with a click or keystroke.
- Simplified workflow – view and edit all forecast details in one place.
- Familiar experience – Excel-like navigation and controls for quick adoption.
- Full keyboard support – navigate, select, and edit forecast dimension and metric data entirely using the keyboard.
- Organize, analyze and edit sort, filter, group, and summarize forecast data with powerful table operations — all while retaining full inline editing capabilities.

Usage

Inline Edit Mode is launching as an opt-in experience. Users can enable it by toggling “ Try Inline Edit Mode ” on the Forecast table. The toggle can be turned off at any time to return to the current Summary–Detail model.

## Enhanced Forecast Accuracy - July 1, 2025

This release announces an upgraded forecasting engine in Cloudability Financial Planning (CFP) powered by IBM watsonx™.

The forecasting service generates automated predictions based on your historical cloud spend. It selects the best-fit model for each forecast line item from a range of proven techniques.

You can attain improved accuracy by switching to daily granularity. This ensures consistency across all product areas including KPIs, Forecast Summary, and Forecast Variance pages.

## Hierarchical Planning - July 1, 2025

This release introduces Hierarchical Plans. This new capability works together with Hierarchical Business Mappings (HBM) and Hierarchical Views (HV) support to drive better insights to your cloud spends.

Key Features

- Multi-level cost ownership and budgets - Plans including up to five levels of cost ownership with more granular budgeting and accountability across your organization.
- Automatic cost rollups by hierarchy - Forecast and budget line items are displayed according to the cost ownership hierarchy using a toggle.
- Simplified setup - Creating plans within an hierarchical view structure automatically makes the plan hierarchical.
- View-based filtering and access control - Filtering contents and control display of data for authorized viewers only within the HV structure of the plans.
- Easy hierarchy updates - Managing organizational changes to update hierarchy.
- Hierarchical permissions - Assigning budgets or forecast ownership at all levels.
- Multi-level alerts - Setting alerts at all levels within the hierarchy.

For more information, see Organize Views using Hierarchical Views .

## Line Item table upgrade & other minor UX enhancements - May 14, 2025

We released an update to CFP focused on improving usability and performance in line item tables and selection picklists.

Summary of the key enhancements:

- Line Item Table enhancements Improved Usability: Column action menus always visible (No hover required) Sorting and filtering controls clearly labeled and always accessible Filter and sort states easier to see and understand Apply or clear filters and sorts with a single click Full Keyboard Support: Navigate, edit, and select values—Text, numbers, dropdowns, and date entirely with the keyboard Use standard keyboard shortcuts to copy and paste values Multi-Level Sorting: Sort by multiple columns at once by holding the Shift key while clicking column headers

- Picklist Improvements Performance Boost optimized for large lists with faster load times, infinite scroll, and responsive search New “Only” Option: in multi-select picklists, enabling quick isolation and selection of single values in a click Streamlined “Search & Add”: Use Search along with the “Only” option to quickly find and add items to your selection

- Plan Listing enhancements Faster Deletion: Significantly improved performance when deleting large sets of plans Select All: Now supports “Select All,” especially useful when working with filtered subsets of plans
