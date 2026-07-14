---
source_system: "apptio-cloudability-standard"
practice: "finops"
language: "en"
doc_type: "cloudability-standard"
consolidated_file: "11-Technical-Support-cloudability"
source_files_count: 5
last_updated: "2026-07-13"
---

# 11-Technical-Support-cloudability

## Custom Discounts and Enterprise Discount Programs (EDP)

<!-- sub-header -->
- **breadcrumb:** Technical Support > Custom Discounts and Enterprise Discount Programs (EDP)
- **source_path:** SSVCLNQ/chatbot/custom-discounts-enterprise-discount.html
- **original_file:** support-custom-discounts-enterprise-discount-programs-edp.md
- **images:** []

Cloudability supports custom discounts and Enterprise Discount Programs (EDP) from Cloud Service Providers (CSP) such as AWS, Azure, GCP, and OCI. These custom discounts and pricing adjustments are reflected in several capabilities, including reporting and cost analysis, rightsizing, commitments, and workload planning.

Cloudability has two Cost Metrics for reporting considering custom pricing:

- Cost (Adjusted) built from the Cost (Total) metric.
- Cost (Adjusted Amortized) built from the Cost (Amortized) metric.

These metrics adjust the figures for pricing rules and are available to Cloudability customers with custom pricing module enabled.

Rightsizing allows you to use:

- On-Demand Cost
- Effective Cost

If your organization has enabled custom pricing in Cloudability, the relevant custom rates are applied to the cost basis calculations.

Both Effective and On-demand cost basis calculations use custom/ EDP pricing.

Workload Planning supports custom pricing by default. For organizations without an agreement with vendors, Workload Planning defaults to Retail pricing.

---

## Configure Enterprise Discount Program for AWS

<!-- sub-header -->
- **breadcrumb:** Technical Support > Custom Discounts and Enterprise Discount Programs (EDP) > Configure Enterprise Discount Program for AWS
- **source_path:** SSVCLNQ/chatbot/edp-request.html
- **original_file:** edp-configure-enterprise-discount-program-aws.md
- **images:** []

When a customer negotiates an Enterprise Discount Program (EDP) with AWS, both contractually agree upon discounts. Cloudability implements the same discounts at the resource level as well as in real time. AWS only shows these discounts at the end of the month.

Configuring custom pricing is not suitable for a customer with Automated Discount Program (ADP) deployed by AWS already.

Before submitting a request for EDP, answer the following in the AWS Private Pricing PDF form:

| Question | Description |
| --- | --- |
| Discount Term | Start and end of EDP |
| Contract Year | Defines when contract starts/stops (dates) |
| Eligible Payer Accounts | Lists payer account that EDP applies to |
| Credits Account | Lists accounts for credits |
| Cross Service Discount | Discount that applies when service specific discounts are not listed |
| Service Specific Discount | List specific AWS Services that receive discount different than Cross Service Discount |
| Service Specific Rates | List specific AWS Services that receive a specific rate rather than discount |
| Discount | Specifies which discounts apply (cross service, Service specific discount, service specific rate) |
| Service specific regions | Specifies which regions receive service specific discounts/rates |
| Spend Commitment | Good information - specifies what level of commitment they need to spend to hit discounts - not something we can programmatically use |

The EDP process takes some time to complete.

The Apptio support team can also investigate specific slowdowns in your environment with the help of HAR files. To learn how to collect a HAR file, visit the Apptio Community page.

---

## Optimize Cloudability Performance

<!-- sub-header -->
- **breadcrumb:** Technical Support > Optimize Cloudability Performance
- **source_path:** SSVCLNQ/chatbot/chatbot-performance.html
- **original_file:** support-optimize-cloudability-performance.md
- **images:** []

For system down issues, navigate to the Outage section in this document

Dashboard & Reports Best Practices

A successful dashboard or widget for Cloudability depends on best practices, such as selecting the right metrics, creating easy-to-understand visualizations, optimizing data loading, and refresh times. Reviewing factors such as the number of widgets used per dashboard, dashboard sharing and permission settings, and report/ chat configuration can help improve performance. Regularly monitoring and fine-tuning these aspects can help ensure the dashboards and widgets continue to perform optimally. See Performance - Dashboard & Widgets Best Practices .

Outage Definitions

Mass Outage: A production incident is a customer impacting event that causes disruption to or a reduction in the quality of a service necessitating an engineering response. A production incident can vary widely in severity, ranging from an entire global web service crashing to a small number of users having intermittent errors. An outage is an event where an application is down or unavailable and fully inaccessible (user can't login).

Mass Outage Process: For mass outages, visit status.cloudability.com for the most recent outage activity.

If you are experiencing an outage not related to a mass outage, submit a support case with the following information

- Is your issue related to any outage?
- Have you reviewed the Cloudability status page?
- Are multiple users impacted?
- Is it for a specific page or all pages/dashboards/reports?

The Apptio support team can also investigate specific slowdowns in your environment with the help of HAR files. To learn how to collect a HAR file, visit Apptio Community page.

---

## Request Refetch and Reprocess in Cloudability

<!-- sub-header -->
- **breadcrumb:** Technical Support > Request Refetch and Reprocess in Cloudability
- **source_path:** SSVCLNQ/chatbot/reprocess-refetch.html
- **original_file:** support-request-refetch-reprocess-in-cloudability.md
- **images:** []

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

---

## Technical Support

<!-- sub-header -->
- **breadcrumb:** Technical Support > Technical Support
- **source_path:** SSVCLNQ/chatbot/technical_support_contact_info.html
- **original_file:** support-technical.md
- **images:** []

If you need technical support you can go to IBM Support to open and view support cases.

---
