---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Configuration and Customization"
breadcrumb:
  - "TBM Studio"
  - "How-To Guides (Task-Based)"
  - "IBM Apptio Report Studio (New)"
source_path: "studio/report-studio/config-custom.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Configuration and Customization

## Accessibility Compliance

The New Report Studio is designed to support accessibility and adheres to section 508
accessibility standards. The experience includes support for keyboard navigation, screen
readers, and accessible UI patterns to ensure reports can be created and viewed by users
with diverse accessibility needs.

## Localization

The new Report Studio now includes localization support, allowing users across regions to
experience a seamless and consistent interface in their preferred language and format.

The section below explains how localization works across various aspects of the Report
Studio.

- Static Text Localization: All static text elements (labels, buttons, menu items, and
  messages) within the new Report Studio are now localizable.
  - Currently, Japanese translation is supported.
  - When you switch your application language to Japanese, all static text in the
    Report Studio will automatically appear in Japanese.
- Data and Configuration: The new Report Studio fully supports non-English data and
  configurations.
  - You can use non-English characters in report names, filters, or data fields.
  - Configurations such as column names, filters, or custom labels can include
    localized text without affecting report functionality.
- Locale-Specific Formatting: Formatting of numbers, dates, and other locale-sensitive
  data automatically follows the conventions of the user’s selected locale.
  - For example, users with the Japanese locale will see numbers formatted with commas
    and decimal markers as per Japanese conventions.
- Currency Handling: The new Report Studio supports non-USD single-currency projects.
  - Projects configured with a specific base currency will display all monetary values
    using the corresponding currency symbol and formatting.
  - Example: A project set to Japanese Yen will display all currency values with the
    Yen symbol across reports.

## Multi-Currency Settings

If multi-currency is enabled for your project, reports can be viewed and tested in
different currencies and rate types (Actual or Plan).

**Multi-Currency in Report Studio (Admin)**

Admins can test reports in
different currencies directly within the Report Studio before publishing or
sharing.

How to change currency in Report Studio?

1. Open the report in Report Studio.
2. Click the Advanced menu.
3. Select multi-Currency Settings.
4. Choose:
   1. A Currency
   2. A Rate Type (Actual vs Plan)

Each enabled currency supports both Actual and Plan rate types.

The report
will re-render immediately based on the selected currency and rate type.

**When to
use this**

- Validate report accuracy across currencies
- Test plan vs actual rate scenarios
- Preview in alternate currencies
- Ensure formatting and totals display correctly

**Multi-Currency in Report Viewer (End Users)**

If the project has
multi-currency enabled, a currency selector appears on the report in the Report
Viewer.

**Default Behaviour**

- Reports open in the user’s preferred currency and rate type.
- The report renders automatically using those settings.

**Changing currency in the Viewer**

1. Use the currency selector dropdown on the report
2. Choose any enabled currency
3. Select the desired rate type (Actual or Plan)

The report re-renders instantly using the selected settings.

**Session
Persistence**

- The selected currency and rate type persist for the duration of the user’s currency
  viewing session.

**Export Behaviour**

The selected currency and rate type apply to
exports:

- **Export to PDF** reflects the currently selected currency.
- **Export to Excel** (individual components) reflects the currently selected currency.

- **[Steps to Enable Modernized OOTB (NX) Reports in Client Instance](../../studio/report-studio/ootb-report-pp.html)**  
  This document outlines the **steps required to enable Modernized OOTB (New Experience (NX)) reports** on a client instance. These reports provide enhanced visibility, better insights, and a more user-friendly‑ experience while continuing to use the **same datasets as Classic TBM Studio**.
- **[IBM Apptio Report Migration Assistant Guide](../../studio/report-studio/migration-assistant.html)**
