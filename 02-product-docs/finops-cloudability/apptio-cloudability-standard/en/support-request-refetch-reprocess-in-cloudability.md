---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Request Refetch and Reprocess in Cloudability"
breadcrumb:
  - "Technical Support"
  - "Request Refetch and Reprocess in Cloudability"
source_path: "SSVCLNQ/chatbot/reprocess-refetch.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Request Refetch and Reprocess in Cloudability

Cloudability offers the ability to request a Refetch or Reprocess to update your data and metrics, if you want to update your historical cloud data or refresh your business metrics, mappings, tags, or account groups.

- Refetch is used to update your historical cloud data from cloud service providers into Cloudability. Note: For N and N-1 months, Cloudability does not trigger a refetch as these months are automatically run by the BAU jobs. If data already loaded into Cloudability is later corrected by the CSPs and a refetch is triggered to import the updated information, the system may not be able to retrieve the corresponding AWS account-level tags, Azure subscription-level tags, or Azure resource group tags if the account has already been decommissioned from the CSP.
- Reprocess is used to update your Business Metrics, Business Mappings, Tags & Labels, and Account Groups to apply these changes. This is the most common type of update request.

To complete a refetch or reprocess, provide IBM Support with the following information:

- Company Name/ Account Name : Provide the name of your company or account to identify your Cloudability instance.
- Time period for update : Provide which month/year or time period you want updated (e.g. Feb 2023, Feb-2023 through April 2023).

A GCP refetch will incur a cost to you for pulling the data from Google, Azure, AWS.

Cloudability will start processing your refetch or reprocess request once you provide these information to IBM Support. You will be notified when the update is complete.

For more information about refetch or reprocess in Cloudability , contact IBM Support.

The IBM support team can also investigate specific slowdowns in your environment with the help of HAR files. To learn how to collect a HAR file, visit IBM Community page.
