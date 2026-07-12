---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "What's new in Cloudability"
breadcrumb:
  - "What's new in Cloudability"
  - "What's new in Cloudability"
source_path: "SSVCLNQ/release-notes-standard/whats-new.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# What's new in Cloudability

## Cloudability Governance Adds Azure Support – July 1, 2026

Today we're excited to reach General Availability in Azure support for Cloudability Governance.

Customers who predominantly or partially operate on Microsoft Azure cloud can now experience the power of Cloudability Governance.

This capability extends our proactive cost insights and policy enforcement directly into the engineering workflow for Azure customers, ensuring that infrastructure changes are both cost-efficient and compliant before they are deployed

## Configurable Anomaly Detection- All Alerts Tab – June 29, 2026

Today, Cloudability Anomaly Detection introduces the All Alerts tab, enabling Cloudability Admins to view all anomaly alert subscriptions across their organization from a single, self-service location. This provides a centralized, read-only view of every alert subscription, including the subscriber, alert threshold, notification method, share type, and creation details, eliminating the need to raise a support ticket.

## Cloudability container insights supports OpenShift version 4.21 - June 25, 2026

Cloudability Container Insights now supports OpenShift 4.21. This update ensures continued compatibility with the latest OpenShift releases across major cloud providers, enabling customers to maintain full container cost visibility as they adopt newer versions of OpenShift.

## Cloudability Advanced Containers - Container Allocation and Assets Experience within Cloudability User Experience - June 24, 2026

Cloudability has released an enhanced containers insights experience by providing the powerful container allocations experience of Cloudability Advanced Containers (powered by Kubecost), now directly available in the Cloudability experience for customers with both Cloudability and Cloudability Advanced Containers.

This release includes support for dashboard, multiple/single aggregation, shared cost configuration, and moreIn addition, Kubecost's assets experience is also available within Cloudability. Users can use this to view and drill down into assets such as Node, Disk, Network, LoadBalancer, ClusterManagement, etc. This brings more of Cloudability Advanced Containers (powered by Kubecost) natively into Cloudability, eliminating the need to switch applications and streamlining workflows.

## Configurable Anomaly Detection – June 23, 2026

Today, Cloudability Anomaly Detection delivers Configurable Anomaly Dimensions, enabling Admins to select up to 4 Tags and Business Mapping dimensions most relevant to their organization. This ensures cost spikes are surfaced against dimensions that matter to their teams, rather than system-defined defaults. Configurable Anomaly Dimensions are scoped to Admin-level configuration only.

## Vendor Credentials - Granular GCS Bucket Permissions – June 3, 2026

As part of IAM improvements in GCP, we have refined the Cloudability GCP onboarding script to use bucket-specific Google Cloud Storage permissions instead of broader project-level storage permissions.

With this update, GCP Storage permissions are being moved from CloudabilityRole_Billing to a new custom project-level role, CloudabilityRole_Bucket. This role is designed to support access only to the required GCS bucket resources.

This change improves security by limiting storage access to specific buckets rather than allowing broader project-wide bucket access, in line with the principle of least privilege.

The below permissions have been redistributed to the new CloudabilityRole_Bucket.

- storage.buckets.get
- storage.buckets.getIamPolicy
- storage.multipartUploads.abort
- storage.multipartUploads.create
- storage.multipartUploads.list
- storage.multipartUploads.listParts
- storage.objects.create
- storage.objects.delete
- storage.objects.get
- storage.objects.list
- storage.objects.update

## Cloudability Advanced Containers Announces Partial View Support - June 2, 2026

Today, Cloudability Advanced Containers delivers Partial View Support, enabling organizations to scope the Advanced Containers experience to a specific subset of cloud accounts. This supports multi-tenant deployments and access-controlled environments where different users or teams should only see cost data relevant to their accounts.

Partial View Support is scoped to account-based views only . Views must be defined by cloud account membership using AccountGroups, Account IDs/Names, or vendor — other view types such as label- or tag-based views are not supported in this release.

With this release:

- A View Picker is now available in the Advanced Containers UI, allowing users to select and switch between configured views. The selected view persists in the URL and browser storage, making it easy to bookmark and share scoped views.
- All cost data — allocations, assets, and autocomplete results — is automatically filtered to the accounts associated with the active view.
- The active view is preserved when navigating between the embedded and standalone Advanced Containers experiences.
- Pages and widgets that do not support view-based filtering display a clear message rather than showing unscoped data.

## Cloudability Advanced Containers Announces Shared Credentials - June 2, 2026

Today, Cloudability Advanced Containers (CAC) delivers Shared Credentials, eliminating the need to configure cloud billing integrations separately within the Kubecost experience. Cloud cost credentials managed in Cloudability are now automatically recognized by Advanced Containers, giving customers a single place to manage their cloud integrations.

With this release:

- Cloud integrations configured in Cloudability are automatically reflected in Advanced Containers — no duplicate setup required.
- The Cloud Integrations settings page now shows credentials sourced from Cloudability, with a direct link to the Cloudability Credentials Service for any credential management.
- Cloud cost data is ingested automatically by the Cloudability pipeline, ensuring accuracy in CAC.
- Updated Cloud Cost Status API provides real-time visibility into the state of cloud cost ingestion per configured account.
- When Cloudability Advanced Containers is in use, cloud costs are handled by Cloudability and duplicate areas in Advanced Containers standalone such as cloud costs, cloud cost reports, cloud cost budgets, and collections are removed.

## CFP Intelligent Forecasting BETA - June 1, 2026

Today, we released Intelligent Forecasting capability for CFP. This new experience helps teams keep CFP plans current by refreshing existing forecast lines with projections based on the latest actuals, while giving users greater visibility and control over how those projections are generated.

CFP Intelligent Forecasting brings the same model-driven forecasting experience used in the Enhanced Forecast page into CFP plans. Users can open an individual forecast line, review historical actuals, view projections from multiple forecast models, visually compare those projections against current plan values, and apply the model that best reflects expected future spend.

Key Features

- Interactive forecast review – view an inline mini-graph showing actual spend history and updated projections directly within the forecast line table
- Improved forecast accuracy – use the Intelligent Forecasting engine to evaluate multiple models and recommend the best fit for each forecast line
- Model comparison and control – compare alternate model results and apply a different model when the recommended model does not reflect expected future spend
- Plan-value comparison – visually compare model-generated projections against existing plan amounts
- Re-forecast support – apply selected model results to update historical periods with actuals and future periods with new forecast estimates

Scope

This release supports interactive re-forecasting for individual forecast lines within CFP plans. Users can access Intelligent Forecasting from a forecast line (by clicking the expand icon to reveal the forecast mini-chart), review the latest actuals and projections, compare recommended and alternate model outputs, compare projected values against current plan values, and apply a selected model to update forecast values in the plan.

What’s Coming Next

At GA, CFP Intelligent Forecasting will add support for saving model selections and bulk re-forecasting making it easier for users to update forecasts based on latest actuals as part of a regular monthly update cycle.

Availability and Enablement

The CFP Intelligent Forecasting is available to all CFP customers. Intelligent Forecasting requires Update Actuals functionality, so the Update Actuals feature must be enabled before Intelligent Forecasting can be used.

Both Update Actuals and Intelligent Forecasting can be enabled from the Advanced tab on the Plan Preferences page, located under Settings in the Cloudability left navigation panel. Intelligent Forecasting is automatically enabled for customers that had enabled Update Actuals during the initial rollout period.

Intelligent Forecasting

## Cloudability Commitments Announces AWS Support for the Enhanced Commitment Manager Overview Page – June 1, 2026

On Monday June 1st, the Cloudability Commitments team released the Enhanced Commitment Manager Overview Page. This new page replaces the existing Commitment Manager through delivering parity functionality and enhancing it to work seamlessly as the landing page across Cloudability Commitment functionality. With this release, the new overview page, simply called Commitment Manager in the left-hand navigation menu, supports AWS services where we support a commitment type: All Compute, RDS, Redshift, Elasticache, and OpenSearch.

- · Chart look and feel is similar to the recommendation details page chart. This chart was recently enhanced with the AWS Support for Commitment Management 2.0 release.
- Enhanced KPIs, including Savings Rate and Coverage. KPIs on Overview page are same as shown on Portfolio and Recommendations.
- Simplified analysis period selection.
- KPI granularity supports Week, Month, and Total.
- KPI Comparison toggle.
- Chart's Cost Type support: True Cost, On-demand Equivalent (ODE).

- Daily report granularity.
- Cost/Savings Views: The Cost/Savings toggle is now gone. This information is now represented in a single chart.
- Recommendation Toggle: Moved to the header bar under the Recommendation Type dropdown.
- Navigation links to Portfolio and Recommendations pages.

- Daily Report Selection: The reporting range across the page is now month based. This simplifies the page and tailors it toward the primary use case, which is a high level overview of your performance and opportunities.
- Chart breakout by service: Aggregate reporting across services remains supported but cost is no longer explicitly broken out by service.
- Recommendation criteria selection: The Recommendation now assumes the Optimal Recommendation.
- The previous Commitment Manager page has been deprecated in favor of this new page. The old page is no longer support and cannot be restored.

For more information please see our help documentation under Using the Commitment Manager Overview to Align the Organization on Commitment Strategy .

## Cloudability Governance Adds Azure Support (Public Preview) – May 29, 2026

Today we're excited to introduce Azure support for Cloudability Governance.

Customers who predominantly or partially operate on Microsoft Azure cloud can now experience the capability of Cloudability Governance.

This expansion allows Azure-heavy enterprises to finally utilize the automated, proactive governance and cost-prevention features of Cloudability Governance rather than relying solely on reactive post-billing tools.

## Azure MCA credentialing - Auto Assigning Billing Account Reader role – May 25, 2026

This release automates assignment of the Billing Account Reader role to the Cloudability service principal for Azure MCA accounts, helping customers onboard faster.

Before this release, customers had to assign this role manually.

## User Experience improvements in Cloudability Rightsizing - May 28, 2026

- Service selection changed from tabs to menu . As more services are added to Rightsizing, we've replaced the tab-based service selector with a more efficient menu, similar to the Commitments page.
- Removed duplicate service type label from dashboard area . The service type is now displayed only in the service picker, eliminating redundant information and freeing up valuable screen space.
- Cost Basis changed from radio buttons to . The cost basis selector has been converted to a menu, similar to the Commitment Manager interface, providing a more consistent user experience. For services that only support a single cost basis, this field is read-only.
- Timeline renamed to "Analysis Period" with selector . The timeline selector has been renamed to "Analysis Period" to align with terminology used in Commitment Manager. The selector has been changed from radio buttons to a menu to conserve screen space. For services that only support a single analysis period, this field is read-only.

## Azure MCA credentialing - Auto Assigning Billing Account Reader role – May 25, 2026

This release automates assignment of the Billing Account Reader role to the Cloudability service principal for Azure MCA accounts, helping customers onboard faster.

Before this release, customers had to assign this role manually.

## Calculated Metrics in Dashboards and Reports – May 21, 2026

We're excited to introduce Calculated Metrics for Cloudability Dashboards and Reports. This powerful capability enables you to define sophisticated unit economics and KPIs from a centralized hub, providing enhanced visibility into cloud spend and operational efficiency through custom, reusable metrics.

Centralized Metric Management: Create, edit, and delete calculated metrics from a single hub within the Business Mappings product area. Define metrics once and reuse them across all dashboards and reports, eliminating redundant configuration and ensuring consistency.

Flexible Formula Creation: Build custom formulas using numeric constants, basic arithmetic operators, and existing metrics. Support for flexible formulas enable sophisticated analysis tailored to your business needs, including unit economics like cost per Resource or cost per Cluster.

Role-Based Permissions: Enhanced access controls ensure proper governance with three permission levels: Admin (full access to create, edit, and delete all metrics), Edit (create and modify own metrics), and View (read-only access).

## Cloudability Commitments Adds Portfolio Support for Microsoft Foundry Provisioned Throughput – May 19, 2026

Today, we delivered support for Microsoft Foundry Provisioned Throughput (PTU) . The thirteenth Azure commitment type supported, Foundry PTUs provide a discount on AI services in exchange for a one-month or one-year commitment to hourly usage. This commitment type is categorized as a resource-based commitment, and as such, requires selection specific usage parameters: Region, Deployment Type, and Payment Option. With this release, only the portfolio supports this commitment type. We will consider building recommendations in the future.

For more information, visit the commitment management help documentation. (edited)

## Import and Export Business Mapping Definitions via UI – May 15, 2026

- Export: Users can now export individual Business Mapping definition directly from the UI into a JSON file, allowing easy sharing or backup of BM configuration.
- Import: Users can now also import BM definition into an existing BM. The imported JSON file populates the UI with new values, allowing users to review and validate the changes.

## Cloudability Commitments Announces AWS Support for Commitment Management 2.0 – May 13, 2026

- Enhanced KPIs, including Savings Rate and Coverage
- Aggregate ‘all’ pages when applicable across the portfolio
- Coverage modal support
- Revamped recommendation details page
- Custom recommendation adjustment feature

This release helps users build a business case for a commitment strategy aligned with best practice. Specifically users can now customize Cloudability's recommendation to support sensitivity analysis for both long term strategy and the next incremental purchase. This allows users to mix term, leverage spend and resource based commitment types, and ladder up and down based on future usage assumptions.

Additionally, this functionality begins to connect the bespoke commitment pages to reporting which provides the transparency our customers require to leverage our application across commitment management chargeback/show back use cases.

How do I get Help?

Our help content was rewritten to support these major enhancements. The content starts with Cloud Cost Optimization in Cloudability . Tactically, Using Commitment Portfolio to Understand Historical Performance and Using Commitment Recommendations to Analyze Savings Opportunities provide directions for how to leverage the new portfolio and recommendations pages.

What’s Next?

This functionality was previously completed for GCP commitments at the end of 2024. We will now turn our attention to providing parity capabilities for Azure.

## Cloudability Commitments Announces AWS Commitment Recommendation Improvements – May 13, 2026

Today, the Cloudability Commitments team delivered significant enhancements our AWS Commitment Recommendations. This release can be viewed as a sub-release to Cloudability Commitments Announces AWS Support for Commitment Management 2.0 – May 13, 2026 . We are calling it out separately to bring attention to the nuance around the recommendation improvements. Users can expect the following improvements:

Introduction of Cost-based Coverage Approach - With the introduction of the Coverage KPI to AWS, we are using actual cost data rather than allocated usage hours. This will differ from the reserved coverage rate metric in reporting as coverage there is derived via usage hours. Across Commitment Portfolio and Recommendations, coverage is driven directly by cost, specifically, the portion of your on-demand equivalent spend that was covered by a commitment in a given period.This change makes coverage more meaningful for financial decision-making. Usage hours are difficult to compare across instance types and don't directly correspond to what you're spending or saving. Cost-based coverage does. With AWS Cost Explorer calculating Reserved Instance coverage in usage hours, Cloudability's cost-based approach gives you a more financially accurate view, one that reflects the actual dollar impact of your commitments rather than an hours-based proxy that can vary significantly across instance families and sizes. For Savings Plans, we believe we are now aligned with how AWS natively calculates coverage.

Recommendation driven by existing commitments across analysis period - Previously, Commitment Recommendations considered only today's commitment coverage when generating our recommendations. We now will use whatever coverage was present across the analysis period selected. While this does have the drawback of potentially being less accurate, for example if a commitment was purchased or expired during the analysis period, it now makes how the recommendation is created more straightforward. When you go to the recommendation details page, you will now see a chart that is simply in terms of cost. The proper way to now use this is feature is to view usage over the analysis period and re-select an analysis period that best represents the future. In many cases, this would require users to adjust the analysis period down to just a week or two, down from the default full month. This change is expected to have a minor impact on customers' recommended amounts post release. We believe this is an improvement because the chart now accurately represents, "What if I had owned this recommendation overt the course of the analysis period selected."

Include / Exclude Existing Saving Plans for Reserved Instance Recommendations - We now include the ability to ignore existing Savings Plans for EC2 Reserved Instance Recommendations. Due to the fungible nature of Savings Plans, they are often variably allocated by AWS. As a result, hours where savings plans were allocated to a given Instance Family/Region/Account/OS combination would cause significant variability to our recommendations given minor difference in analysis period. This feature allows you to ignore the Savings Plans since if variable usage would potentially be applied elsewhere in the event the Reserved Instance existed. This provides our users flexibility to continue to take advantage of the higher commitment savings rate of Reserved Instances.

Include / Exclude Linked Accounts - We now support the ability to generate individual recommendations per linked account across a payer. When sharing is turned on, we continue to aggregate all linked accounts within a payer account when analyzing usage. This represents how AWS distributes RIs and will offer the best savings. What is different is when sharing is off, and the user selects a payer account, they will now see a recommendation for each account rather than only a recommendation for the usage under the payer account.

How do I get Help?

Our help content was rewritten to support this enhancements. The content starts with Cloud Cost Optimization in Cloudability .

## Dashboard Tabs in Cloudability Dashboards – May 12, 2026

- Users can drag&drop Tabs to change their order
- Users can duplicate entire Tabs to copy them between Dashboards
- Users can drag&drop a Widget to move it to a different Tab
- When copying Widgets, users can choose which Tab to copy to

## Cloudability Commitments Announces Support for Column Preference Across Commitments– May 12, 2026

Today, the Cloudability Commitments team delivered a minor improvement to it's table. For tables across portfolio and recommendations for AWS and GCP, we now persist the show/Hide column selection in your machine's local storage. As a result your column selection will now persist across sessions. Notably, each commitment page has a different set of columns and order saved as the default. For more information, please view Commitment Table Basics in our Help Center.

## Commitment Recommendations Details Chart Enhancements – May 11, 2026

Today, the Cloudability Commitments team formally announces a handful of improvements to the recommendations details page. This is formally part of the Commitment Management 2.0 release. It is getting a standalone post here because this change is applicable to both AWS and GCP.

Assumed ODE Selection : A toggle for assumed ODE (on-demand equivalent) selection has been added to the Recommendation Details page, allowing users to ignore the assumed ODE for a simpler cost chart. Turning the toggle off shrinks the y-axis and puts more focus on cost.

Split Commitment Capability : Users can now split commitments from the Recommendation Details page, viewing current commitments either summed together or broken out individually. This benefits an analysis of a recommendation whose coverage usage could be covered by a different commitment type.

Updated Chart Tooltip : The chart tooltip has been redesigned to support scrolling and aggregates cost in a format resembling a financial statement, communicating hourly data alongside summarized totals for improved readability and at-a-glance analysis.

Total Cost Removed from Chart Type Dropdown : Total Cost is no longer available as a chart type since totals are now accessible through the updated tooltip. Toggle controls have been updated accordingly, addressing user feedback that the previous selection was confusing.

Recommendation Type Renamed : The top-level Custom recommendation type is now Modified, and the Adjusted Recommendation type is now Custom. These changes resolve naming conflicts created by the renamed cost basis list. For more information, see Using Commitment Recommendations to Analyze Savings Opportunities .

## Cloudability Commitments Announces Miscellaneous Minor GCP Commitment Enhancements – May 11, 2026

- Enhanced Account Selection for Large Number of Accounts across Portfolio and Recommendations: Customers can have thousands of accounts. We now fold the linked accounts up to the payer account. This is especially useful for commitments since they are typically bought/shared at the payer account level. Users no longer need to endlessly scroll or know exactly what account to search for.
- Analysis Period Cost on Portfolio: We now support the total cost for the analysis period alongside the remaining cost. Customers might want to compare this number with what they see in reporting. You no longer need to add this column by hand or export the table into a csv to sum.
- Portfolio (PSR) and Commitment (CSR) Savings Rates on the Portfolio: The CSR and PSR are distinctly different. The CSR is the weighted savings rate of your commitments across the analysis period. The PSR is the saving rate of your portfolio. CSR = Savings / On-Demand Equivalent of Commitment Cost. PSR = Savings / Committable Spend. Seeing these two values side by side helps draw the distinction between the two KPIs. For more information, see Commitment Key Performance Indicators .

## Cloudability adds support for Azure Blob Storage tier recommendations – May 11, 2026

Today, we added support for Azure Blob Storage tier recommendations. Cloudability users can now optimize Azure storage costs by receiving intelligent recommendations for container-level access tier configurations, including Hot, Cool, Cold, Archive, and Smart Tier options.

For each container, Cloudability analyzes storage usage, access patterns, and operational costs to identify tier misconfigurations. Recommendations calculate total monthly costs across all available tiers, including early deletion fees and retrieval costs, to suggest the optimal configuration that minimizes costs while maintaining performance requirements.

These recommendations follow the same format as existing AWS S3 and Google Cloud Storage tier optimization recommendations and are visible on the Rightsizing Explorer page. The feature supports both traditional tier transitions and Azure Smart Tier automatic optimization, providing flexibility for different storage management strategies.

For more information, see Azure Blob Storage rightsizing .

Customers must add 'Microsoft.Storage/storageAccounts/read' permissions for all elements of this feature to work as expected.

## Enhanced Forecasting - May 4, 2026

We released the Enhanced Forecast page – a new and improved cloud forecasting experience for Cloudability.

The Enhanced Forecast page is a major upgrade to the legacy Forecast experience, delivering the same core forecasting functionality with significantly more flexibility, transparency, and control. Users can choose their own forecast drivers, analyze full forecast line-item detail, benefit from more accurate Intelligent Forecasting, visually compare model results, and connect forecasts to budget workflows.

New and Enhanced Functionality (over legacy Forecast page)

- User-selectable spend drivers – choose your own dimensions, instead of the fixed drivers used by the legacy Forecast page
- Full forecast line-item detail – review all forecast line items, not just the top 20
- Improved forecast accuracy – uses the Intelligent Forecast Engine to evaluate multiple models and automatically select the best fit, instead of relying on a single fixed model
- Interactive model comparison and control – review model details, visually compare alternate model results, and apply a different model when needed
- Pivot-style detail analysis – group, summarize, sort, and filter forecast line-item details directly in the table

Learn more about Enhanced Forecast

## Logging and Monitoring in Workload Planning - April 29, 2026

This release introduces support for Logging and Monitoring services across AWS, Azure, and OCI. For GCP, Workload Planning currently supports Logging only. This is similar to how users can already create estimates for services such as Virtual Machines and Databases.

Users can select the appropriate service from the Service Type drop-down: Logging and Monitoring for AWS, Azure, and OCI, and Logging for GCP. After entering the required capacity and, optionally, defining their specific configuration, Workload Planning will generate pricing options tailored to their requirements.

## User Experience improvements in Cloudability Dashboards - April 28, 2026

- Persist widget filters configuration when switching widget types. When changing a Widget type (e.g. from a Chart to a Table), the interface will now retain the filters configuration so that the filters configuration does not need to be recreated separately for each type of Widget.
- The “Other” row in table widgets is now displayed separately from the remaining values to clearly distinct it from the actual results.
- Date-based filters can now be configured using a user-friendly calendar input . With this change, users will not need to type in the values for date format filters. Instead, users will be able to pick a date using a built-in calendar selector.
- Copy and paste filters to/from clipboard. Users will now be able to easily move a filters configuration between different Widgets and save a filter set to reuse it later.
- Export chart as a .png image. Charts can now be exported and saved as an image in PNG format.
- Search and filter in a table widget . All Table widgets can now be filtered using a single text-based search field that is applied across all visible columns.
- Export as PDF . The entire Dashboard can now be exported in PDF format to enable easier collaboration with other users.

## Subscribe to Reports with comparison date range - April 28, 2026

This release introduces an improvement to Cloudability Reports subscription functionality. With this change, users will be able to subscribe to Reports that use “Compare date” functionality, in the same way as they are currently able to subscribe to Reports with a single date.

## Cloudability Optimization Dashboard’s COIN Explorer Supports Conditional Formatting - April 20, 2026

Cloudability has added support for conditional formatting in the COIN Explorer found in the Optimization Dashboard. In the Rightsizing preferences section, users can set thresholds for COIN score conditional formatting. The settings include a green/yellow threshold as well as a yellow/red threshold.

COIN (Cost Optimization Index Number) provides a standardized metric for organizations to review optimization opportunities in the context of the spend in that area of their business so they know where to focus and prioritize. Many organizations go as far as treating it like a leaderboard to compare the efficiency of teams across their organization.

Accompanying this release, several updates were made to the optimization dashboard around COIN and realized savings to improve accuracy.

## Support for Google Cloud Storage Tier Recommendations - April 14, 2026

Cloudability has added support for Google Cloud Storage tier recommendations. Cloudability users can now optimize GCS costs by receiving recommendations for bucket-level storage class configurations, including Standard, Nearline, Coldline, Archive, and Autoclass options. For each bucket, Cloudability analyzes storage usage, access patterns, and operational costs over a minimum of 30 days to identify storage class misconfigurations.

These recommendations follow the same format as existing AWS S3 tier optimization recommendations and will be visible in the Rightsizing Explorer page. Customers with Resource Level Billing enabled for GCP will automatically begin receiving these recommendations.

Customers must add 'storage.buckets.list' permissions for all elements of this feature to work as expected.

## GCP Compute Rightsizing Now Includes License Costs - April 14, 2026

Cloudability has enhanced GCP compute rightsizing recommendations to include operating system and software license costs in savings calculations. Cloudability users can now receive more accurate rightsizing recommendations that account for the full cost of running GCP instances, including Windows Server, SQL Server, Red Hat Enterprise Linux, SUSE Linux Enterprise, and Ubuntu Pro licenses.

Previously, GCP rightsizing recommendations only considered compute costs (CPU, memory, and storage), which could lead to incomplete savings estimates for instances running licensed operating systems or software. With this enhancement, recommendations now calculate both compute and license costs for source instances and recommended targets, ensuring that license requirements and minimum core counts are respected when suggesting alternative instance types.

These enhanced recommendations will be visible in the Rightsizing Explorer page and maintain the same format as existing GCP compute recommendations. Customers with GCP instances running licensed operating systems will automatically see more accurate savings estimates that reflect total cost of ownership.

## Business Mappings View Only Permission Enhancements - April 14, 2026

We released an improvement to view-only permissions in Business Mappings area. With this change, users with view-only access will no longer see action buttons (Edit, Delete, Create, etc.) in Business Dimensions, Hierarchical Dimensions, and Business Metrics. Additionally, we unified the viewing experience across all Business Mappings areas. View-only users can now consistently access details in Business Dimensions, Hierarchical Dimensions and Business Metrics.

## Ability to rename Hierarchical Business Dimension - April 9, 2026

We've launched the ability to rename Hierarchical Business Dimensions in Business Mappings. With this change, users can now edit the name of their Hierarchical Business Dimensions directly within the interface, which provides grater flexibility in organizing their structures.

## Cloudability Rightsizing Introduces Savings Thresholds for Block Storage - April 7, 2026

Cloudability Rightsizing added support for an expanded functionality in Rightsizing preferences to provide a minimum savings amount for Block Storage. This threshold, (defined for a 30-day recommendation, and prorated for 10-day recommendations), allows organizations to define the minimum savings amount for their block storage recommendations (AWS EBS, Azure Disk, and GCP Persistent Disk) and filter out any recommendations that don’t meet that threshold.

This release allows organizations to focus on the most impactful recommendations, similar to the existing functionality that was established for Compute Rightsizing recommendations.

## Cloudability Governance Support for GitHub Enterprise Server - April 7, 2026

Adding support for GitHub Enterprise Server extends Cloudability Governance into self-hosted, highly regulated environments, enabling enterprises to bring FinOps policy checks , cost estimation , and recommendations directly into their existing, on-premise GitHub-based workflows. This enhancement lets platform and FinOps teams apply the same guardrails and approval workflows they use with GitHub.com to repositories hosted on their own infrastructure, aligning cost and compliance controls with existing governance frameworks for GitHub Enterprise .

## Cloudability x ServiceNow CMDB Integration for Business Dimensions - April 1, 2026

Today, we are launching Cloudability x ServiceNow CMDB Integration for Business Dimensions .

The Cloudability x ServiceNow CMDB Integration enables automated synchronization between ServiceNow CMDB and IBM Cloudability Business Mappings, allowing organizations to use ServiceNow as the single source of truth for business structure and cost allocation logic in Cloudability.

This integration eliminates the need for manual or API-driven updates to Cloudability business mappings by automatically reflecting CMDB changes from ServiceNow into Cloudability. The integration can only be installed on certified ServiceNow versions; unsupported versions will block installation entirely.

Key Highlights:

- Automated Business Mapping: Business mappings in Cloudability are automatically created and maintained based on ServiceNow CMDB data.
- Centralized Governance: ServiceNow CMDB acts as the authoritative source for organizational, application, and cost-center data used for cloud cost allocation.
- Near Real-Time Synchronization: Updates in ServiceNow CMDB are automatically reflected in Cloudability without manual intervention.
- Native ServiceNow App: The integration is delivered as a certified application available in the ServiceNow Store.

ServiceNow integration is available in ServiceNow store under the following link: https://store.servicenow.com/store/app/c3864d3d4784fe1482f632c4f16d43c8

## Vendor Credentials - Ability to archive uncredentialed accounts - April 1, 2026

This release introduces the ability to archive uncredentialed accounts directly from the Vendor Credentials screen.

Previously, uncredentialed accounts had to be credentialed first before they could be archived. With this update, accounts in an uncredentialed status can now be archived directly using the ellipsis ( ⋯ ) menu , eliminating the need for credentialing.

Overall archive actions are now available directly from the Vendor Credentials screen for all accounts irrespective of the status.

## Anomaly Detection - Anomaly Feedback - March 30, 2026

We’ve launched Anomaly Feedback Starting today, you can provide quick feedback on detected anomalies using a simple thumbs up or thumbs down . This helps us understand whether the anomalies being flagged are actually useful. Previously, there was no direct or structured way to share feedback, which limited our ability to refine detection quality based on real user input.

## Bulk Import in WLP - March 30, 2026

This release introduces a major enhancement to the Bulk Import feature in Workload Planning (WLP). It allows customers to upload a structured file with up to 500 resources in a single operation across all service types, regions, and CSPs.

This feature helps customers perform workload planning more efficiently by eliminating the need to add resources manually or in smaller batches. Users can now import up to 500 resources at once, receive recommendations instantly, and accelerate their cloud planning process.

## Export the Accounts status in Vendor Credentials - March 19, 2026

This release adds support for exporting the vendor credentials status in csv format. This feature helps our customers to quickly review the status of accounts when the number of accounts are large in number.

Each of the credentialed data sources with account status can be exported in cs format. Each datasource will have its individual export.

## Snowflake Warehouse Cost Insights & Tag Support - March 19, 2026

With this update, teams can attribute costs more precisely, and surface key cost drivers using Cloudability’s dashboards and Business Dimensions. Previously, Cloudability provided visibility only at the service level, meaning customers could not see the cost of individual warehouses nor use Snowflake tags for cost allocation. Cloudability now delivers deeper insights directly within existing workflows, enabling more effective cost governance and informed decision making.

How does it work?

- For customers with existing access: No action is required.
- For customers already using Snowflake credentials in Cloudability:
- Organizations that did not previously recredential will need to do so to activate these enhancements. The process remains unchanged: simply follow the steps in our Help Center and run the updated template provided in the UI.
- For customers new to Snowflake in Cloudability:
- Complete the standard credentialing process described in the Connect Snowflake

## Resource Inventory Saved Reports: Improved date range handling - March 17, 2026

Previously, opening a Resource Inventory (RIS) saved report with a non-rolling date range and exceeding the supported three-month window failed to load and displayed an error message.

With this update, such reports load successfully instead of failing. If the saved date range exceeds the supported limit, Cloudability automatically resets it to the default 7-day range and displays a flash notification informing users that the date range was adjusted.

This improvement ensures saved reports remain accessible even when their stored date ranges fall outside the supported limit.

## Dashboards 2.0 - March 16, 2026

Today, we are launching Dashboards 2.0 - a major front-end revamp of the entire Cloudability Dashboards experience. This upgrade aims to modernize the technology used in Dashboards, unlock new Dashboards functionality and accelerate the future feature development. Dashboards 2.0 address several usability issues and optimize the overall design of the Dashboards framework.

- There are no functional changes between Dashboards 2.0 and previous version of Dashboards. All the functionality will remain the same.
- There will be slight visual differences that do not impact the product behavior.

Dashboards v2 is now enabled in all regions.

## Support for OCI in Resource Inventory - March 16, 2026

We’re excited to announce support for Oracle Cloud Infrastructure (OCI) in the Resource Inventory feature. With this release, you can now view cost, utilization, and resource-level metadata for OCI Compute (Virtual Machine) services in the same single-pane-of-glass experience you already use for other hyperscalers.

OCI Compute service support includes all the existing capabilities available in Resource Inventory today. To enable this feature for your Cloudability organization, please contact your TAM, CSM, or Apptio account representative. Within 3–4 business days of enablement, complete OCI inventory data for Compute resources will be available in Cloudability.

For more details, see OCI Resource Inventory .

## Cloudability Adds Support for Dynamic COIN Reporting - March 6, 2026

Cloudability added a new tab to the Optimization Dashboard allowing users to report on resource optimization opportunities and contextualize those opportunities with the underlying spend in the form of a COIN Score (Cost Optimization Index Number).

COIN scores can be leveraged to better understand and contextualize opportunities as well as to normalize optimization opportunities across different teams and organizations to act as a leaderboard or way of measuring efficiency.

In the newly released COIN Explorer, users can add or remove fields to understand COIN scores at the desired granularity as well as export this data as needed.

## Cloudability Rightsizing Adds Support for Azure Available Memory Bytes Metric – March 4, 2026

Today, we delivered enhanced memory metrics for Azure compute rightsizing recommendations. Cloudability now leverages Azure's standard Available Memory Bytes metric as a fallback when custom memory utilization data is unavailable. This enhancement ensures more Azure instances receive comprehensive rightsizing recommendations without requiring customers to configure custom metrics.

Previously, Azure instances without custom memory metrics could not receive memory-based rightsizing recommendations, limiting optimization opportunities. With this release, Cloudability automatically calculates memory utilization from Azure's built-in Available Memory Bytes metric, expanding the coverage of rightsizing recommendations across your Azure compute resources.

This improvement may result in updated recommendations and savings estimates for Azure instances that previously lacked memory data. No action is required from customers—the enhancement automatically applies to all Azure compute recommendations. Customers who already have custom memory metrics configured will see no change in their recommendations.

For more information, visit the rightsizing recommendations help documentation .

## Cloudability Commitments Adds Support for Azure App Service Reserved Instances – February 23, 2026

Today, we delivered support for Azure App Service Reserved Instances . The twelfth Azure commitment type supported, Azure App Service Reserved Stances provide a discount on compute in exchange for a one- or three-year commitment to hourly usage. This commitment type is categorized as resource-based commitments, and as such, requires selection specific usage parameters: Tier, Instance, and Region. With this release, we support this commitment type across both the commitment portfolio and recommendations.

For more information, visit the commitment management help documentation.

## User-friendly Business Mapping names in data exports - February 19, 2026

With this release, Cloudability Dashboards and Reports launched a new functionality, that will return the user-friendly names of Business Metrics, Business Dimensions, Account Groups and Tags&Labels when exporting CSV data from a Report, Dashboard or Explore. Previously, Business Metrics and Dimensions were exported using a column ID (e.g. "category12"), instead of the user-friendly label. The default behavior of API-based exports will NOT change . However, users will be able to add "useDimensionNames=true" option in the request to opt-in to this feature when using API. Existing API integrations will NOT be impacted, and users will be able to use the user-friendly names of Business Mappings if they want by adding the flag to their API requests.

## Cloudability Anomaly Ignore Alerts - February 19, 2026

Today we launched Anomaly Ignore Alerts. Starting today, users can temporarily ignore anomaly alerts directly from the alert configuration page to reduce noise during expected cost events and ensure only meaningful, actionable alerts are surfaced.

Key capabilities include:

1. Ignore alerts at the individual anomaly alert level
1. Support ignore functionality for shared alerts
1. Select preset ignore duration (7, 14, or 30 days)
1. Define a custom date range for ignoring alerts.
1. Edit the ignore duration (extend or shorten as needed)
1. Schedule ignore for a future time period
1. Ignore alerts in bulk using the Bulk Anomaly Alert Ignore option
1. Automatically resume alerts once the ignore period ends

## Cloudability Commitments Announces Support for GCP’s New Spend CUD Program – February 16, 2026

Today, IBM Cloudability announces support for GCP’s New Spend CUD Program.

Background

In early 2025, GCP announced significant changes to how their spend-based commitments would be billed, impacting 13 of their 17 commitment types .

On July 15, 2025, GCP enabled early migration to the new spend-based CUDs program. Between July 2025 and early February 2026, users could voluntarily opt into the new billing model. During the first week of February, GCP began force-migrating customers, completing the process on Friday, February 6. A brief overview of the program is available here: Simpler billing, clearer savings: A FinOps guide to updated spend-based CUDs .

We had been recommending that users delay migration because it was a breaking change across reporting, commitment portfolio, and commitment recommendations.

Support for the new billing paradigm

With this announcement, the new billing paradigm is now supported across both reporting and commitment functionality. Commitment portfolio and recommendations have been restored to near parity with the previous billing model. For reporting, we've delivered an improved experience compared to what existed prior.

At a high level, reporting on commitment cost and waste is now more straightforward and follows the paradigm already established for AWS and Azure. Additionally, we can now report on this data at a per-CUD level. Under the previous paradigm, this was not possible and represented a common pain point for users looking to apply granular chargeback or showback logic.

These changes are live in production for all users. For users who voluntarily migrated prior to the forced migration in February, a refetch of previous month data may be required. For more information, see Supplemental Guide to GCP CUD

## Cloudability Support for Azure Foundry (Brand Update) – February 13, 2026

With this release, we have updated the Service Name dimension in Cloudability to align with Microsoft’s rebranding of Azure Cognitive Services to Azure Foundry.

The existing Service Name “Azure Cognitive Services” will now be represented as two distinct Service Names:

| Before | After |
| --- | --- |
| Azure Cognitive Services | Azure Foundry Models Azure |
|  | Azure Foundry Tools |

- Foundry Models – Core inferencing engines (Azure OpenAI, Phi, DeepSeek, Llama)
- Foundry Tools – Pre-built AI capabilities (Speech, Language, Document Intelligence)

- All new data will automatically reflect the updated Service Names
- Historical data will reflect the new names upon reprocessing

## View assignment visibility for User and Entra ID Groups – February 11, 2026

We’ve improved group management by adding visibility into where User Groups and Entra ID Groups are used across Views. Previously, if a Group was used in View assignment, the system blocked it's deletion and admins had no easy way to identify which Views were using the Group. This often required manually checking multiple Views.

With this enhancement, admins can now see a read-only list of all Views where a group is assigned, directly from the User Group or Entra ID Group definition page. The list displays the View names and clearly indicates when a group is not used in any View, helping streamline group cleanup and reduce manual effort.

For more information, visit the Manage User Groups and Manage Entra ID Groups help documentation.

## Auto Sync scheduling for Entra ID Groups – February 5, 2026

Today, we’ve added auto-sync scheduling for Entra ID Groups to improve usability and reduce administrative effort. Previously, Cloudability admins had to manually sync Entra ID Groups using the “Sync Entra ID Group” action, which could result in missed updates as Entra ID group memberships change frequently.

With this enhancement, Cloudability admins can now configure daily, weekly, or monthly auto-sync schedule using defined filter criteria. Entra ID Groups are automatically synced based on the selected schedule and criteria, ensuring Cloudability remains consistently aligned with Entra ID, without manual intervention.

For more information, visit the Manage Entra ID Groups help documentation.

## Cloudability Optimization Dashboard adds Effective Cost Basis for Resource Recommendations - February 2, 2026

Today, Cloudability added the effective cost basis as an option for the recommendations surfaced in the Optimization Dashboard (Beta). The effective cost basis allows for a more meaningful COIN calculation by comparing the amortized cost of the services to the effective cost savings calculated by Cloudability’s Rightsizing recommendations. This preference can be found in the Rightsizing Preferences > Dashboard section along with the other preferences and settings that impact the Optimization Dashboard.

## Cloudability Commitments Update Surrounding Upcoming Support for GCP’s New Spend CUD Program - January 30, 2026

On January 16th, we provide an initial announcement about GCP's mandatory migration to the New Spend CUD Program. The following information is an update on what we can share at this time.

- If you have not voluntarily migrated, GCP will migrate it's customers to the new billing model next week:February 2nd - 5th, 2026.

- We plan to release iterative support as we become confident in our release. Cloudability Reporting, Commitment Portfolio, and Commitment Recommendations will likely be released in a staged manner.
- We expect to release support during the week of February 9th - 13th, 2026. We are hopeful that customers can expect full functionality starting Monday, February 16th.
- No action is required from you—we expect to support the new program automatically when your migration occurs.

- For customers who have already migrated, we need to re-fetch data dating back to the month you had voluntarily opted into the new program. We request that you reach out to your account teams to provide that month in preparation for our backend release.
- For customers who will undergo the mandatory migration next week, we may require a re-fetch of February to have complete history. We will provide an update next week.
- Note that for both cohorts, we will support the new program moving forward post our infrastructure release. This re-fetch is a one time requirement and only necessary for the months between when we release backend support and the migration occurred.

## Commitment Support for Azure Database for MySQL Reserved Capacity – January 23, 2026

Today, we delivered support for Azure Database for MySQL Reserved Capacity . The eleventh Azure commitment type supported, Azure Database for MySQL commitments provide a discount on compute in exchange for a one- or three-year commitment to hourly usage. This commitment type is categorized as resource-based commitments, and as such, requires selection specific usage parameters: Deployment Option, Instance, and Region. With this release, we support this commitment type across both the commitment portfolio and recommendations.

For more information, visit the commitment management help documentation.

## Cloudability Rightsizing Support for Azure Virtual Machine Scale Sets - January 22, 2026

Cloudability has added Azure Virtual Machine Scale Sets support in Rightsizing. Cloudability users can now receive recommendations to rightsize their scaling behavior by modifying the types of instances used in the ScaleSet to achieve a better cost outcome without impacting the performance of the application.

Customers may need to update their permissions to leverage this release, including the management:Reader permission or following three permissions:

1. Microsoft.Compute/virtualMachineScaleSets/read
1. Microsoft.Compute/virtualMachineScaleSets/virtualMachines/read
1. Microsoft.Compute/virtualMachineScaleSets/extensions/read

Prior to this release, users with Azure compute recommendations may have seen individual instance recommendations for instances that were part of scale sets. These instances will now be treated as part of the scale set instead of individually, so some customers may see their recommendations for Azure Compute instances change with this release to avoid double counting.

These recommendations will also be visible in the Rightsizing Explorer page and can also be linked to Rightsizing ROI tickets like other recommendation types.

## Advanced Containers Powered By Kubecost – January 22, 2026

Advanced Containers powered by Kubecost is a paid add-on for Cloudability that provides access to the full Kubecost feature set directly within the Cloudability experience.

Advanced Containers extends existing Cloudability container insights with advanced Kubernetes cost visibility, optimization, and automation capabilities.

With Advanced Containers, you can:

- Access the full power of Kubecost, including granular Kubernetes cost allocation down to the pod and container level.
- Monitor and optimize GPU workloads, including GPU cost visibility and rightsizing insights.
- Enable automated Kubernetes optimization, including actionable and automated CPU and memory rightsizing.
- View real-time Kubernetes costs, rather than delayed or batch-processed container spend.
- Monitor and allocate costs for on-premises Kubernetes clusters, in addition to cloud-hosted environments.

Advanced Containers is available as a paid add-on to Cloudability and requires deploying the Kubecost agent to monitored Kubernetes clusters.

For setup instructions and additional details, see the Cloudability Advanced Containers documentation.

## Cloudability Commitments Announces Upcoming Support for GCP’s New Spend CUD Program - January 16, 2026

Google Cloud Platform (GCP) has shifted the mandatory migration date for the New Spend CUD Program from January 26th to a multi-day window: February 2nd - 5th, 2026.

- During the migration day, GCP has communicated that users will not be able to purchase new CUDs for at least a short time as the migration to the new billing program completes.
- When Cloudability begins to support the Spend CUD program, it will require at least a day, but no longer than 48 hours for our systems to refresh.
- No action is required from you—we expect to support the new program automatically when your migration occurs

GCP sent a Mandatory Service Announcement (MSA) on December 11th, 2025 with your specific migration date. You can also find this date on the Billing Overview page in your GCP Console. Note that Cloudability does not have access to individual customer migration dates.

Already migrated to the new Spend CUD program? If you opted into the new Spend CUD program early, we apologize for the delay in support. Full functionality will be restored when the formal migration window begins in early February. For any further questions or concerns, please reach out to your account team.

## Cloudability Governance is now Generally Available – January 15, 2026

This new capability brings proactive cost insights and policy enforcement directly into the engineering workflow, ensuring that infrastructure changes are both cost efficient and compliant before they are deployed.

Cloudability Governance is now available for DevOps engineers , Platform Admins , and FinOps teams who manage AWS resources and use Terraform - whether through Terraform Community , HCP Terraform or Terraform Enterprise – for their infrastructure as code solution. This feature is designed for teams that host their code repositories on GitHub.com , including GitHub Enterprise Cloud .

Previously, FinOps practices were often introduced too late in the development lifecycle, leading to misalignment between Finance and Engineering. This delay forced costly rework, as teams relied on manual reviews or post-deployment audits to catch cost inefficiencies and policy violations– resulting in overspending, compliance risks, and unexpected remediation tasks for engineers.

Cloudability Governance integrates with GitHub and Terraform to bring FinOps policy enforcement and cost visibility into the CI/CD pipeline. Key capabilities include:

- Pre-deployment Cost Estimation : Real-time AWS cost estimates, including custom pricing and EA discounts, directly in GitHub and Terraform workflows.

- Get Cost Optimized Resource Selection : Recommendations for lower-cost EC2 and RDS alternatives with similar configurations.

- Policy Enforcement at IaC Level : Enforce mandatory tags, block legacy resources, and set budget thresholds.

- Compliance Monitoring : Centralized dashboard to track adherence to FinOps policies.

- PR Management : Identify and review non-compliant pull requests with built-in approval workflows.

- Run Task Integration with HCP Terraform : Seamlessly integrate Cloudability Governance as a Run Task in HCP Terraform workspaces. This allows policy checks to be automatically triggered during the plan phase of a Terraform run, enabling advisory or mandatory enforcement before infrastructure is provisioned.

This feature shifts cloud cost management from reactive to proactive—helping teams prevent overspending and policy violations before infrastructure is deployed.

For more information about the feature, please review Cloudability Governance documentation .

## Support for Effective Cost Basis in Rightsizing Explorer - January 14, 2026

Cloudability has added support for effective cost basis in Rightsizing Explorer. Cloudability users can now view rightsizing recommendations by either on-demand or effective cost when reviewing rightsizing opportunities in Explorer.

## Cloudability Rightsizing Adds Support for AWS Unattached ElasticIP Addresses - January 9, 2026

Cloudability has added AWS ElasticIP addresses support in Rightsizing. Cloudability users can now receive recommendations to terminate unattached ElasticIP addresses as part of their broader workload and resource optimization initiatives

No new permissions are needed for these recommendations, customers may begin to see these recommendations populated immediately. These recommendations will also be visible in the Rightsizing Explorer page and can also be linked to Rightsizing ROI tickets like other recommendation types.
