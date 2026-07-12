---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Decimal Number Display"
breadcrumb:
  - "Planning"
  - "Configuration and Administration"
source_path: "it-planning/planning/decimal-number-display.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Decimal Number Display

Decimal Number Display controls how numeric values are formatted and shown across
Apptio Planning. This setting allows administrators to define the number of decimal places used
for all numeric data, ensuring consistent display across plans, reports, and exports.

Note: Only users with Admin or Budget Process Owner roles can perform these tasks.

## What Decimal Number Display Controls

When enabled, the decimal display setting applies to **all numeric columns**, including:

- Fiscal year and period values (monthly, quarterly, yearly amounts)
- Integer and numeric attributes
- Quantities such as headcount, FTE, hours, and percentages

This setting affects **display only**—calculations always retain full precision in the
system.

**How to Enable Decimal Number Display**

1. Navigate to **Settings (Gear icon)** → **Company Profile**.
2. In the **Number Format** section, enable **Decimal Number Display**.
3. Select the number of decimal places to display (for example, 0–8).
4. Select **Save & Exit** to apply the setting.

## Default Behavior When Decimal Number Display Is Disabled

When **Decimal Number Display is turned off (default)**, numeric values are displayed
using view-specific defaults. These defaults vary by module and use case to balance
readability and precision.

**Views That Default to 0 Decimal Places**

- Summary views
- Contracts
- Assets
- Other non-labor tabs
- Spend Management
- Comparisons (comparison views)

**Views That Default to 2 Decimal Places**

- Labor
- Labor Activity (FTE values)

**Decimal Display in Variance Analysis**

- **Actuals** are displayed with **0 decimal places**
- **Totals and Variance amounts** are displayed with **2 decimal places**
