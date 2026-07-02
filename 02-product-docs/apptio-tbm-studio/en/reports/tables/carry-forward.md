---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "reports"
title: "Carry Forward"
breadcrumb: []
source_path: "reports/tables/carry-forward.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Carry Forward

This function allows the user to carry forward the numeric values in a editable table (ET)
report.

To enable this feature, navigate to the [Advanced Properties](set-table-properties.htm "(Opens in a new tab or window)") popup.

![](../../../resources/images/studio_images/cf-dataedit_463x489.png)

Select the **Data Edit** checkbox to enable the carry forward feature. The **Disable Carry
Forward** button appears below the report component.

![](../../../resources/images/studio_images/cf-disable.png)

Note: The carry forward is applicable only for numeric value and consecutive columns. If there is a
non-numeric column in between, the carry forward will not apply thereafter.

If the user selects **Disable Carry Forward**, then carry forward will be deactivated and the
button will appear as **Enable Carry Forward**.

![](../../../resources/images/studio_images/cf-enable.png)

The carry forward behavior is applicable only for the local session and does not persist. Hence,
every time the user returns, it will be in the default carry forward enabled state.
