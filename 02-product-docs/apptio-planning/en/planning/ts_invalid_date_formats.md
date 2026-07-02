---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "planning"
title: "Troubleshoot invalid date formats in Planning"
breadcrumb: []
source_path: "planning/ts_invalid_date_formats.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Troubleshoot invalid date formats in Planning

## Symptom

You are unable to import date values into Planning due to invalid formatting, and are unsure of
which date formats are correct.

## What's going on

Planning has stringent requirements for date formatting that are more specific than other Apptio
products.

## Solution: Syntax

You can use the following date formats:

| North America | International | East Asia |
| --- | --- | --- |
| MM-DD-YYYY | DD-MM-YYYY | YYYY-MM-DD |
| MM/DD/YYYY | DD/MM/YYYY | YYYY/MM/DD |

You must use one date format consistently across your entire Planning project.

Date formats must meet the following syntax requirements:

- Month must be represented by numeric integers. Text is invalid. For example, for the month of
  August, 10 is valid but August or AUG is not.
- Month and Day must contain one or two digits.
- Year must use all 4 digits: YYYY.
- May use "-" or "/" to separate numbers in date, as long as the selected punctuation is
  consistent.
- The order of Month and Day depends on your regional settings.

## Solution: Browser Language Settings

Planning pulls date format support from your browser or system settings. Find your browser in the
following section, and ensure the browser settings are configured correctly.

## Google Chrome

Google Chrome uses date formatting defined by the browser settings.

1. In the Google Chrome browser, open the Chrome Menu in the upper-right corner then select
   Settings.
2. Select Advanced > Languages > Language.
3. Change your language settings so that your preferred language is at the top of the language
   order.

Your settings are saved automatically.

For more information, visit [Google Chrome Help Center](https://support.google.com/chrome/?p=help "(Opens in a new tab or window)").

## Microsoft Edge

Microsoft browsers use the date format defined in the regional settings of Windows.

1. Open the Control Panel and select Change date, time or number formats.
2. In the Region dialog in the Formats tab, select your preferred date and time settings, then
   select Apply and OK.
3. Clear your browser cookies and cache.
