---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "planning"
title: "Configure cross-charge"
breadcrumb: []
source_path: "planning/iip/configure-cross-charge.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Configure cross-charge

When project uses labor resources from the Resource Cost Center, on the Project Cost Center side
of accounting the labor activity expense is charge or debit amount. To avoid double counting of the
expense, the Resource Cost Center owner should receive the cross-charge or credit for the same
activity.

You can configure cross-charge support in Integrated Investment Planning by setting up Labor
Activity Account reference data.

For more information, see [Manage Labor Activity Type data](manage-labor-activity-type-data-ref.htm "(Opens in a new tab or window)")

When the Activity Type is set on the Labor Activity line, the financials are generated to
allocate charge (debit) on the Charge Account and cross-charge (credit) on the Resource Cost Center
Account.

If you are allocating resources from Vendor in which case the labor activity expense is accounted
for the project using those resources but there isn’t a need to cross-charge that expense, you can
implement this use case by configuring Activity Type such that it has Charge Account but no
Cross-Charge Account.

You are able to view charge and cross-charge amount generated under respective cost centers and
accounts on the Expenses > Summary view.
