---
source_system: "apptio-billing"
practice: "tbm"
language: "en"
doc_type: "boit"
title: "Set Billing Standard user permissions in Frontdoor"
breadcrumb: []
source_path: "boit/set-permissions-frontdoor.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Set Billing Standard user permissions in Frontdoor

Billing Standard on TBM Studio 12 users the Frontdoor Admin Console for user
management. For more information, see About Frontdoor, the Apptio Access
Administration page.

To perform the following actions, Billing Standard users require the following Frontdoor
permissions:

- **ViewDataQualityAndMonthlyProcessReports** - Enables the user to access the
  Billing Quality Collection.
- **ViewBusinessRelationshipReports** - Enables the user to access everything
  EXCEPT the Billing Quality collection.
- **ManageAndSendInvoices** - Enables the user to configure and send email
  bills.
- **ViewServiceProviderReports** - Enables the user to access the IT Service
  Provider Report collection.
- **ViewBusinessUserReports** - Enables the user to access the Service Charges
  report collection.

The following out-of-the-box roles provide access to the Billing Standard application, but
restrict access to TBM Studio:

- **Business Consumer** - Provides access to the Service Charges report
  collection and Cost Transparency.
- **Business Owner** - Provides access to view all of Billing Standard , with
  the exception of Data Quality and Bill Distribution.
- **Service Manager** - Provides access to the IT Service Provider and Service
  Charges report collections in Billing Standard .
