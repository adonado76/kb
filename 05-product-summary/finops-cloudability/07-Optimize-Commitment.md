---
source_system: "apptio-cloudability-standard"
practice: "finops"
language: "en"
doc_type: "cloudability-standard"
consolidated_file: "07-Optimize-Commitment"
source_files_count: 16
last_updated: "2026-07-13"
---

# 07-Optimize-Commitment

## Guide to Commitment Management

<!-- sub-header -->
- **breadcrumb:** Optimize > Guide to Commitment Management
- **source_path:** SSVCLNQ/product/guide_to_commitment_management.html
- **original_file:** optimize-guide-commitment-management.md
- **images:** []

This section provides a comprehensive guide to managing cloud commitments effectively using Cloudability’s bespoke commitment functionality. From aligning cross-functional teams on commitment strategy to monitoring performance and configuring alerts, Cloudability empowers FinOps, finance, and engineering teams to make informed, collaborative decisions. Together with native reporting, FinOps and IT Finance professionals should have everything they need to take full advantage of commitment-based discounts.

In this guide, you will learn how to interpret key metrics, navigate the commitment pages, Manager, Portfolio, Recommendations, and Preferences, while leveraging automated alerts to stay ahead of expiration dates and underutilization risk. Additionally, Cloudability’s recommendation engine, which supports preference configuration to surface target recommendations based on known business constraints, helps organizations build tailored financial plans. Finally, with this baseline knowledge, we will explore how our dynamic recommendation algorithm can be leveraged to perform what-if and sensitivity analysis to model a business case and execute on a holistic rate optimization strategy.

---

## Data Freshness

<!-- sub-header -->
- **breadcrumb:** Optimize > Guide to Commitment Management > Data Freshness
- **source_path:** SSVCLNQ/product/data_freshness.html
- **original_file:** management-data-freshness.md
- **images:** []

## Data Freshness

---

## Guide to Commitment Management FAQ

<!-- sub-header -->
- **breadcrumb:** Optimize > Guide to Commitment Management > Guide to Commitment Management FAQ
- **source_path:** SSVCLNQ/product/guide_to_commitment_management_faq.html
- **original_file:** management-guide-commitment-faq.md
- **images:** []

### Commitment Manager

### Commitment Portfolio

What is the difference between units and counts?

Counts refers to the number of instances in a reservation, while Units refers to normalized instance hours. This is relevant for RIs that applied to multiple instance sizes within a family. This also helps you decide on the overall size of an RI, so that a reservation of 5 instances of m4.large (Count of 5, Units of 20) not appear larger than a reservation of instances of 4 m4.16xlarge (Count of 4, Units of 512).

Why does my savings decrease when I look at Adjusted cost?

Custom pricing often shifts the savings from an RI to custom pricing. To use a simple example, if an instance cost $1/hour and the reservation costs $0.80/hour, a fully-utilized reservation of 10 instances would provide $48 of savings per day (10 x 24 x $0.2).

If you have a custom pricing agreement that gives you 10% discount for compute instances, your savings for this would effectively drop to $43.20 per day (10 x 24 x $0.18).

Why does savings/utilization change when I select a view?

The portfolio supports account group based views. However, when you select a view, filter to both where a reservation is owned as well as where a reservation is applied. If your team purchases RIs within a linked account and want to see how much of the RI was consumed by your team, you can do that with a view.

To view RIs owned in a particular account, use the Account filter on the main page.

In Azure reserved instances, does the savings rate percent and savings over term KPIs incorporate custom Azure rates?

If you have custom pricing calibrated in the application, you can also tease your savings net of custom pricing discounts.

My Commitment portfolio is missing commitments, where are they?

Cloudability commitments can only see commitments that the user account can see. Using AWS as an example, a consolidated billing parent account cannot see the activity of the child account that occurred before it entered into the consolidated billing relationship. This means that the parent account cannot see commitments belonging to the child that were purchased before the consolidated billing relationship began.

The suggested workaround is to add an IAM credential for the child account to Cloudability, in addition to the consolidated billing parent account. Cloudability Commitments will then be able to see the commitments that were purchased by the child account. Cloudability will automatically de-duplicate any overlapping data.

### Commitment Recommendations

- The commit value in savings plan is on higher end when compared to RI for EC2. Do you recommend to buy both? In Cloudability , It is possible that the commitment amount in a saving plan is higher than the Reserved instance for AWS EC2. The reserved instances provide a discount when you reserve a certain amount of computing power (measured per hour) for a one- or three-year term while savings plans provide a discount when you commit to spending a certain amount (measured in dollars per hour) for a one-or three-year period. The decision to purchase a resource or spend based commitment is up the FinOps leader in the organization. Eligible usage may be covered by multiple commitment types. Currently, we provide these recommendations in a vacuum from one another. For example, it is not recommended that all reserved instances and savings plans for AWS EC2 be purchased.
- What is the best strategy to use commitments? What are best practices? Are you expecting to consider and act on all the recommendations at once? The strategy chosen when using commitment-based discounts to save on cloud spend will vary depending on the organization, vendor, and commitment type. There is no universally best approach. Since commitments usually involve one- or three-year contracts, it is crucial to consider future plans carefully. Generally, it is advisable to make smaller, frequent purchases over time until the desired coverage percentage is achieved. Once this threshold is reached, additional commitments may be purchased as usage grows or as existing commitments expire. It is also important not to renew commitments if a decrease in usage is anticipated. In Cloudability's support for commitments, the commitment recommendations provide what commitments should be purchased to maximize net savings, given the selected usage range. Individual recommendations are provided for each permutation of the criteria necessary for each commitment type where coverage usage is detected. In affect, Cloudability Commitment Recommendations provide you the optimal commitment. Organizations should strive to this coverage level to achieve optimal savings, however, as best practices call for small incremental purchases, the optimal recommendation should rarely be acted upon directly.

### GCP Specific FAQ

How far back can I go in historical usage for analysis?

A maximum of 2 months: The entire previous months usage, up until the previous day of the current month.

What dimensions can I use to filter the usage for analysis?

You can use any configured Cloudability dimension: Tags & Labels, Account Groups, or Business Mappings. Some dimensions may not be available if the data variability is high – for example: “server name”. Only dimensions with a low-moderate amount of variability will be available, for example: “environment: production/staging”, “cost center: abc123”.

How many dimensions can I use to filter my usage for analysis?

You can select up to 10 Cloudability dimensions to apply to your usage.

When will the selected dimensions be applied to my usage?

Dimensions are applied when the next billing data ingestion occurs. It can take up to a maximum of 24 hrs for the dimensions to be applied to your usage, and be available to be used as filters. When GCP processing starts, it will take the currently configured preferences at that point in time, and apply them.

Can I change my selected dimensions multiple times?

Yes, you can change the dimensions multiple times. When the billing data ingestion occurs, it will take the currently configured dimensions and apply them to the data.

Can different users have different dimensions configured for their usage?

No, the dimensions are configured for the entire organization.

How is the usage on the graphs displayed?

The graphs show hourly data, with multiple hours being averaged into a single point if required to fit into the graph.

How is the default recommendation calculated?

This is the propriety Cloudability algorithm which looks to maximize savings while balancing risk.

Are SUDs incorporated into the recommendation?

Yes, if a resource received a SUD previously, the Cloudability recommendation savings will show the increase from the SUD rate, not the on-demand rate.

The SUD discount level changes throughout a month, what SUD discount level is used?

The average of the entire previous months discount is used and applied to the modelled usage for any resource that received a discount.

How are Cloudability 's recommendations different from the GCP recommendations?

There are 5 features that will result in different results from the native GCP recommendations:

1. Included data: Cloudability includes any resource running for any amount of time, it does not need to be running consistently for 30 days/1 mont
1. Usage period: selecting a specific usage period
1. Filtering the data: Cloudability allows you to remove usage from analysis at a very granular level
1. SUDs: Cloudability incorporates SUD discounts in the calculations if they were previously received
1. Risk: Cloudability users can analyze different commitment levels based on risk

How are values in the console rounded ?

Values are rounded to the closest whole number.

---

## Guide to Legacy Commitment Manager

<!-- sub-header -->
- **breadcrumb:** Optimize > Guide to Commitment Management > Guide to Legacy Commitment Manager
- **source_path:** SSVCLNQ/product/commitment-manager.html
- **original_file:** management-guide-legacy-commitment-manager.md
- **images:**
  - 03-media/apptio-cloudability-standard/details.jpg
  - 03-media/apptio-cloudability-standard/commit_manager_cred_detail.jpg
  - 03-media/apptio-cloudability-standard/commit_manager_subnav.jpg
  - 03-media/apptio-cloudability-standard/commit_manager_usage_analysis.jpg
  - 03-media/apptio-cloudability-standard/commit_manager_range.jpg
  - 03-media/apptio-cloudability-standard/commit_manager_acct_sel.jpg
  - 03-media/apptio-cloudability-standard/commit_manager_serv_sel.jpg
  - 03-media/apptio-cloudability-standard/commit_manager_rec_opt.jpg
  - 03-media/apptio-cloudability-standard/commit_manager_def_rec.jpg
  - 03-media/apptio-cloudability-standard/commit_manager_rec_applied.jpg
  - 03-media/apptio-cloudability-standard/commit_manager_savings.jpg
  - 03-media/apptio-cloudability-standard/commit_manager_click_2_nav.jpg

The Apptio Cloudability Commitment Manager helps you gain a global view of how committed spend instruments (e.g. Reserved Instances, Savings Plans) can help you optimize your cloud spend. This article outlines capabilities of the Commitment Manager and its capabilities to help leverage committed spend instruments as part of an overall cloud financial optimization strategy.

Getting Started

Before you begin, you will want to ensure that the necessary permissions have been enabled.

To check the status of the necessary credentials, follow the steps

1. Navigate to Settings > Vendor Credentials .
1. Within the primary accounts view for the AWS tab, any master payer or linked account that owns or that may be the intended owner of commitments (reserved instances or savings plans) should have a green box with a white check status indicator under Advanced Features .
1. or an account with any status indicators other than the green box with a white checkmark, select to inspect the individual credentials.
1. Cloudability will provide you the visibility of all your reservations for AWS, Azure or GCP. For any reason if all of your accounts are not properly credentialed then you may not be able to see all your reservation commitments in the commitment manager.
1. If permissions under the Reservations subheading have a red X, they will need to be updated (by regenerating and applying CloudFormation templates ) before all information in the Commitment Manager will display properly.

If permissions are missing for Savings Plans, projected future savings from existing plans will not be represented in the primary graph of the Commitment Manager. If permissions are missing for Reserved Instances, neither historical nor projected future savings will be visible.

Accessing the Commitment Manager

To access the Commitment Manager, navigate to Optimize > Commitment Manager .

Viewing and Recommendation Options

The sub navigation bar of the Commitment Manager displays the options for customizing viewing of owned commitments as well as how recommendations are generated.

Usage Analysis

The usage analysis setting determines how much of the usage history should be taken into account when generating recommendations.

From the pulldown menu select 7, 30 or 60 days of previous usage and the graph will adjust to display the resulting projected usage and associated recommendations.

Timeline

The timeline setting allows users to determine the desired visible date range of the graph in to the past and future.

To adjust the timeline, select the Timeline section of the sub navigation to expose the date range selector. Select the desired range of time and then update. The viewable graph area will automatically adjust to show only the selected date range.

Selecting a date range inclusive of today’s date is not required but selecting a date range only in the past will produce a graph without any recommendations even though they are still being generated. Likewise, selecting a date range of only future dates will show only projected future utilization of existing commitments.

Account

The Account setting allows a user to view and generate recommendations at the master account level. To maximize utilization and savings, recommendations are made at the master payer level by default. Only master payer account selections are permitted in the Commitment Manager. If you want to restrict usage to and view at individual linked accounts then you can do so in the Reserved Instance Planner and Savings Plans "Recommended" tabs. Usage, recommendations and the graph are automatically updated for the account selected.

Learn about AWS Savings Plans

The Account selection should not be used as a filter of recommendations. It restricts the usage the recommendation service considers to only that of the selected account when generating purchase and modification recommendations assuming that the user wants recommendations to only cover that account’s usage. For this reason, recommendations generated in this way will not necessarily be a subset of those made when the master payer is selected. They will likely be entirely different recommendations.

Cloud Services

By default, the Commitment Manager generates a global view of usage and coverage of committed spend across all AWS services credentialed in the Apptio Cloudability platform, but the cloud services selection allows users to view individual or groups of services as preferred by individual users.

Under the Cloud Services selection in the sub navigation, checking and unchecking services will add and remove them from the graph for both past usage/coverage as well as future predicted usage, coverage and recommendations.

At least one service must be selected. If Savings Plans are selected in Recommendation Options and some of the services selected are not applicable to Savings Plans, the Commitment Manager will continue to generate Reserved Instance recommendations for those particular services.

Recommendation Options

Recommendation options provide users the ability to tailor purchase recommendation preferences including, commitment instrument (i.e. Savings Plans or Reserved Instances), type (e.g. EC2 or Compute for Savings Plans), term and payment model. Reserved instance exchange and modification recommendations will keep the same terms as the original commitment as required by AWS.

For AWS, not all services can be covered by Savings Plans. If Savings Plans are selected, the Commitment Manager will continue to generate Reserved Instance recommendations for services that can not be covered by Savings Plans.

Using The Commitment Manager’s Main Graph

Cost Basis

The default configuration of the Commitment Manager is one presenting on-demand usage, commitment coverage and recommendations by cost without applying available recommendations. In this view the blue shaded area represents on-demand usage layered on top of the green shaded area representing usage covered by commitments.

A red vertical line represents the most recent day of actual usage reported with the area to the left of the red line representing historical usage/commitment coverage and the area to the right of the red line projecting future usage with existing owned commitment coverage. In this view, recommendations are represented by diagonal line shading overlaying the projected future on-demand usage.

Projected Cost with Recommendations Applied

To view projected costs with the recommendations applied, move the slider control in the upper left of the graph area to the ‘Apply Recommendations’ position and the graph will adjust to display the projected costs after implementing recommendations.

Savings

In addition to viewing historical and projected coverage in terms of cost users can select to view their graphed coverage in terms of savings. To view by savings, select ‘Savings’ from the toggle selector located above the center of the graph. When selected the Savings view shows only the historical savings delivered by owned commitments in the past and the expected future savings from both owned and recommended commitments.

Viewing Owned and Commitment Recommendation Details

To view detail of existing owned Commitments, select/click the green shaded area to be directed to the Reservation Portfolio or Savings Plan inventory.

To view detail of recommendations based on the defined preferences, select click within the diagonal line shaded blue area to the right of the red line on the graph to be directed to the Reservation Planner or Savings Plan Recommendations.

Reference

- Understanding How AWS Savings Plans Affect Your Bill
- What AWS Savings Plans Mean For You
- Reserved Instances

---

## Setting Commitment Alerts

<!-- sub-header -->
- **breadcrumb:** Optimize > Guide to Commitment Management > Setting Commitment Alerts
- **source_path:** SSVCLNQ/product/setting_commitment_alerts.html
- **original_file:** management-setting-commitment-alerts.md
- **images:** []

### Purpose

Commitment Alerts reduce manual monitoring by notifying you when commitments are approaching expiration or when utilization falls below a threshold you define. This document explains how to configure, interpret, and act on alerts, plus vendor specific nuances.

### Alert Basics

We support two types of commitment alerts:

Expiration - Notifies users of upcoming expiring commitments. On your chosen 'expiring within' frequency, Cloudability will determine if a commitment is expiring over the specified time frame.

Utilization Threshold - Notifies users of commitments that exhibit a utilization below a specified threshold. On your chosen 'lookback period' and 'threshold', Cloudability runs the Commitment Portfolio utilization algorithm to determine if any existing commitments meet the specified criteria.

To configure alerts navigate to the commitment portfolio and select the alerts button in the top right corner. Alerts are facilitated through an email notification. Note that there is a separate tailored email report for each of the two alert types. Alerts evaluate your entire portfolio of supported types with valid credentials; they are not segmented by the vendor tab or type selected when you open the panel. (Setting an alert while on the AWS tab for example will apply the alert across Azure and GCP).

The email notification will occur according to the specified send frequency and time selected. Note that the time is in UTC. Note that for both alert types, you can decide to send the alert on the specified frequency, even if no commitments meet the specified criteria.

### Vendor Nuance

- Azure Saving Plans do not support a 90-day lookback. Instead, the alert defaults to the longest available period, 30-days.
- GCP does not provide the data granularity to determine utilization of an individual commitment. Instead, we provide utilization threshold alerts on the commitment group. For more information on GCP commitment groups, see the commitment portfolio documentation.

### Step-by-Step Alerts Configuration

1. Navigate to Optimize → Commitment Portfolio .
1. Click Alerts (upper right).
1. In Commitment Alerts: Expiration Toggle ON/OFF Set Expiring Within (e.g., 7, 14, 30, 60, 90 days) (Optional) Check Send even if none expiring Utilization Threshold Toggle ON/OFF Set Lookback Period (rolling N days) (Optional) Check Send even if none below threshold Frequency Choose how often to evaluate and what time to send the email
1. Click Submit to subscribe.
1. To disable, open the panel and click Unsubscribe for the relevant alert.

### Interpreting the Email Alerts

Expiration Email

What you’ll see:

Commitment(s) that are expiring within your selected window, along with identifiers and timing details.

Recommended actions:

- Validate coverage and utilization in Commitment Portfolio.
- Understand current and future workload consideration to evaluate renewal.
- Immediately upon expiration, evaluate your recommendations to determine if new commitment purchases are appropriate.

Utilization Threshold Email

What you’ll see:

Commitments below the utilization threshold, along with their evaluated usage details.

Recommended actions:

- Investigate scope (zonal vs. regional), sharing settings, and workload shifts
- Consider exchanges/convertibles or reducing future purchase sizes/terms
- Reevaluate commitment strategy to understand why frequent under utilization occurred and how to avoid it moving forward.

### Best Practices

- Threshold selection : Start at 90–95% and refine per type’s breakeven and historical volatility.
- Lookback window : 7–14 days balances noise vs. responsiveness. Use 30–90 days for steadier usage.
- Operate to signal, not noise : Investigate low utilization over an extended period of time. Single day dips may reflect benign or seasonal usage changes that may still be worth covering with a commitment.
- Pair with dashboards : Track coverage, utilization, savings rate, and remaining cost to contextualize alert spikes.

### Key Takeaways

- Configure Expiration and Utilization Threshold alerts in Commitment Portfolio → Alerts.
- Set a lookback and threshold aligned to breakeven and volatility; choose frequency and send time.
- Use emails as a signal to investigate.
- Be aware of Azure lookback limits and GCP group level evaluations.

---

## Using Commitment Portfolio to Understand Historical Performance

<!-- sub-header -->
- **breadcrumb:** Optimize > Guide to Commitment Management > Using Commitment Portfolio to Understand Historical Performance
- **source_path:** SSVCLNQ/product/using_commitment_portfolio_to_understand_historical_performance.html
- **original_file:** management-using-commitment-portfolio-understand-historical-performance.md
- **images:** []

### Purpose

The purpose of this document is to give a broad overview of how to use the Commitment Portfolio. At a summary level, you use the Commitment Portfolio to understand how your existing commitments have performed over time, where risk exists moving forward, and to provide a starting point to begin the conversation around where opportunities remain. When fully utilized, this page blends tactical insights with strategic interpretation, allowing FinOps practitioners to quickly move from signals (KPIs) to actions (alerts, reporting, recommendations).

### How to Access and Use

The Commitment Portfolio page is located under the Optimize section in the left-hand navigation menu and is organized by vendor. Each tab shares a common structure so you can compare across clouds without switching mental models. The header toolbar lets you build a focused portfolio view

Commitment Type

This selection is organized by vendor (AWS), to service (EC2), to commitment type (EC2 Reserved Instances). Note that the intermediate service page is not required where there is a single commitment type that covers the service.

- All level (vendor-based landing page): Shows all supported services/types for the selected vendor.
- Service level : Shows all supported commitment types for the selected service.
- Type level : Showed all commitment types for the various types.

Account

The account picker controls which accounts’ usage you’re analyzing and automatically pulls in any commitments that affected that usage, even if those commitments were purchased elsewhere. For example, if Account A’s commitment covers usage in Account B, selecting Account B alone will still reflect the impact of A’s commitment on B’s usage. As a best practice, choose accounts that align with your vendor console sharing settings so analysis mirrors how commitments are actually shared. The picker represents hierarchical nature of your accounts and is multi-select.

- Selecting a payer account(s) (Management, Subscription, Billing) selects all linked accounts beneath it.
- Selecting specific linked account(s) (Member, Subscription, Project) shows a partial‑selection state on the payer account.

You can narrow by the billed account using table filters. For provider hierarchies and sharing scopes, see Account Structure by Vendor .

Cost Basis

Choosing List or Adjusted pricing allows users to understand their recommendations from list or negotiated on‑demand and commitment rates. The KPIs and tables reflect the basis you select. Note that Azure commitment pages may not expose a toggle yet. When present, values reflect Custom where applicable. For more information, see How Custom Pricing Factors Across Commitments

Analysis Period

This selection drives all KPIs and table meta data on the page. The default is last month and times are in UTC. Our suggestion is to avoid reporting on the most recent 24 hours to allow data to complete processing in our pipeline. For more information, see Data Freshness .

### Interpreting the Portfolio KPIs

- Net Savings and Remaining Commitment Cost are dollar KPIs scoped to the analysis period.
- Savings Rate, Utilization, and Coverage are rate KPIs scoped to the analysis period.
- Portfolio Savings Rate (PSR) = Commitment Net Savings ÷ Committable Spend (under the selected basis). PSR isolates the effect of commitment discounts from negotiated on‑demand pricing, making it a cleaner portfolio metric than Effective Savings Rate (ESR) when negotiated rates are in play. When Cost Basis = List, PSR equals ESR since all values are in terms of list rate and there is no savings due to negotiated rates. For more information, see Commitment Key Performance Indicators .
- Utilization is weighted by the relative impact/size of commitments in the table.
- The KPI details modals are available for Net Savings and Coverage. These modals provide additional information in support of understanding how the KPI is calculated. For more information, see Commitment Net Savings and Coverage Modals .

### Per‑Type Summary & Details Panel

- All available metadata for the commitment.
- KPIs scoped to this commitment (same definitions as the header KPIs).
- Trend visuals for daily net savings and utilization for the selected analysis period. We include a lifetime toggle to snap the chart to the entire life of the commitment regardless of the current analysis period.

Table Operations & Filters

- Sort : Click a column header to sort descending, click again for ascending, a third time to reset.
- Show/Hide Columns : Use the columns control to choose which fields to display.
- Pagination : Standard pagination controls appear below the table.
- Export : The Export button produces a CSV in what‑you‑see‑is‑what‑you‑get format for the current scope and visible columns.

Add Filter & Inline Filtering

- Use add filter (below the header tool bar) to filter by any supported field.
- Cells that are hyperlinked are available for filtering, selecting a linked cell will filter the table by that attribute and add a chip to the filter bar.

Alerts & Views

- Alerts : The top‑right alerts button opens Commitment Alerts to configure Expiration and Utilization Threshold emails.
- Views support : The Portfolio supports account and vendor scoped views. Other business mappings aren’t supported here because per‑commitment metrics can’t be computed reliably under arbitrary remaps.

GCP’s Grouped vs. Ungrouped Tables

For GCP, the Portfolio supports two complementary perspectives, driven by how GCP reports commitments (credits without per‑usage commitment IDs and multi‑dimensional resource CUDs). In exports, Reservation ID is typically not set.

- Grouped View: Aggregates commitments at the applicable scope (e.g., Billing Account/region for GCE CUDs). In this view, the app can show performance metrics per group.
- Ungrouped View: Mirrors AWS/Azure with a row per commitment. Some per‑item performance metrics are omitted when underlying data lacks per‑commitment granularity. The grouped Details Panel lists the CUDs comprising the group.

### Using this page to implement best practice

- Time horizon : Trend by month/quarter for portfolio‑level signals; use week/day to confirm seasonality.
- Basis discipline : Keep price source and recognition basis consistent across comparisons. For more information see Cloudability Commitment’s Approach to Cost and How Negotiated Pricing Factors Across Commitments
- Showback/Chargeback : Use portfolio filters plus Coverage links to break out covered vs. uncovered by team/app for accountability.
- Renewal readiness : Compare Net Savings and Utilization for items nearing expiration; decide to renew, exchange (if applicable), or simply let them expire.
- Waste control : Persistent red in Net Savings often indicates scope mis‑alignment, over‑buying, or seasonality—adjust term, scope, or category mix.

### Key Takeaways

- The portfolio is your single view of owned commitments and historical performance.
- Read aggregate KPIs first, then use details panel and modals ( Coverage / Net Savings ) to understand drivers.
- Use filters, grouped/ungrouped toggles, and vendor context to go from signal to action.
- Use Alerts and Recommendations to operationalize findings.
- Treat the portfolio as your system of record; review weekly for trend checks and monthly for renewal planning.

---

## Using Commitment Preferences to Build a Business Case

<!-- sub-header -->
- **breadcrumb:** Optimize > Guide to Commitment Management > Using Commitment Preferences to Build a Business Case
- **source_path:** SSVCLNQ/product/using_commitment_preferences_to_build_a_business_case.html
- **original_file:** management-using-commitment-preferences-build-business-case.md
- **images:** []

### Configuring Recommendation Usage Filters (GCP Support Only)

To setup your organization, go to Settings and select Commitment Preferences . Here you will be able to configure up to 10 Cloudability dimensions to apply to your usage. Select dimensions from your configured Tags & Labels, Business Mappings, or Account Groups.

For best performance, choose dimensions that provide a moderate level of variability – such as business units or application names. Dimensions that have a large amount of variability such as resource name will lead to significant performance degradation. If a configured dimension is not available – it is likely due to excessive variability.

Any changes to your preferences will be implemented in the next processing cycle, allow up to 24 hours for any changes to take effect, and be available in the CUD recommendations page.

Dimensions are regularly checked for variability and will be added/removed from the list of available dimensions. If a dimension becomes too variable it will be removed and no longer available in your data set.

---

## Using Commitment Recommendations to Analyze Savings Opportunities

<!-- sub-header -->
- **breadcrumb:** Optimize > Guide to Commitment Management > Using Commitment Recommendations to Analyze Savings Opportunities
- **source_path:** SSVCLNQ/product/using_commitment_recommendations_to_analyze_savings_opportunities.html
- **original_file:** management-using-commitment-recommendations-analyze-savings-opportunities.md
- **images:** []

### Purpose

The purpose of this document is to give a broad overview of how to use Commitment Recommendations. At a summary level, you use Commitment Recommendations to understand where savings opportunities exist based on your current cloud spend and the commitments you already own. Recommendations are generated by a proprietary model that applies your preferences and business constraints. The details page then lets you run sensitivity and what‑if analyses to build a business case for incremental purchases and shape an optimized commitment strategy for your organization.

### How to Access and Use

The Commitment Recommendations page is located under the Optimize section in the left-hand navigation menu and similar to portfolio, is organized by vendor. Each tab shares a common structure so you can compare across clouds without switching mental models. The header toolbar lets you build a focused recommendation view:

Commitment Type

This selection is organized by vendor (AWS), to service (EC2), to commitment type (EC2 Reserved Instances). Note that the intermediate service page is not required where there is a single commitment type that covers the service.

- All level (vendor-based landing page): Shows all supported services/types for the selected vendor.
- Service level : Shows all supported commitment types for the selected service.
- Type level : Showed all commitment types for the various types.

Notably, the aggregate pages at the vendor and service level ensure that the recommendations provided are mutually exclusive from each other. For more information on this behavior, see the recommendation type section below.

Account

The account picker chooses which accounts’ usage our model will analyze for a recommendation. It is generally best practice to choose an account selection that corresponds with your sharing preferences configured in the vendor console. Because we do not have a systematic to query this information, we provide the option to configure this in the application. The picker represents hierarchical nature of your accounts and is multi-select.

- Selecting a payer account(s) (Management, Subscription, Billing) selects all linked accounts beneath it.
- Selecting specific linked account(s) (Member, Subscription, Project) shows a partial‑selection state on the payer account. For more information about account terminology, see Account Structure by Vendor

Action

Relevant only to AWS at this time, this selection allows you to choose whether you are looking to evaluate Buy, Exchange, or Under Utilized recommendations. This is particularly relevant to AWS EC2 where convertible reserved instances offer more flexibility to achieve higher levels of coverage.

Term

This selection tells our model which term length to analyze in the provided recommendations. For optimal and target recommendation types, this dropdown will display Mix when multiple term recommendations are shown on the page.

Cost Basis

Choosing List or Adjusted pricing allows users to understand their recommendations from list or negotiated on‑demand and commitment rates. The KPIs and tables reflect the basis you select. Note that Azure commitment pages may not expose a toggle yet. When present, values reflect Custom where applicable. For more information, see How Negotiated Pricing Factors Across Commitments .

Analysis Period

This selection drives all KPIs and table meta data on the page. The default usage profile, the preference name of the default analysis period across the recommendations page, is last previous month and times are in UTC. Our suggestion is to avoid reporting on the most recent 24 hours to allow data to complete processing in our pipeline. For more information, see Data Freshness .

Importantly, our model today is driven solely off the analysis period selected. For more information about selecting an appropriate analysis range for your use case, see the Usage Profile.

Payment Option

Specific to AWS and Azure, this selection determines how the selected recommendations would be paid for. Often an additional discount when paying in advance.

Offering Class

Specific to AWS EC2 Reserved Instances, this selection determines whether to provide standard or convertible recommendations.

Region Preference

Specific to AWS EC2 Reserved Instances, this selection determines whether to provide recommendations scoped to a region or availability zone.

Account Sharing

This selection determines whether to provide recommendations scoped to individual accounts or aggregated at the payer.

Rate Thresholds

This selection acts as a simple filter to specify which utilization and savings rate thresholds are relevant when calculating recommendations.

### Interpreting the Recommendation KPIs

All KPIs are expected based on our recommendation model. They are formally driven off the analysis period selected.

- Net Savings is defined as the expected gross savings minus expected waste from the proposed purchases in scope.
- PSR (expected), CSR (expected), and CDR (known) are all used to help interpret recommendations.
- We show current and future coverage to convey how coverage would change given the specified recommendations were purchased.
- Utilization is weighted by the relative impact/size of recommendations in the table.

### Per‑Type Summary & Details Page

Beneath the header is the table. Each row summarizes a recommendation. Columns adapt to the selected commitment type. Unlike portfolio’s drawer, the details action opens a dedicated Details Page for that recommendation. From here the scope is focused to this recommendation, providing a chart and adjustment capability.

Table Operations & Filters

- Sort : Click a column header to sort descending, click again for ascending, a third time to reset.
- Show/Hide Columns : Use the Columns control to choose which fields to display.
- Pagination : Standard pagination controls appear below the table.
- Export : The Export button produces a CSV in what‑you‑see‑is‑what‑you‑get format for the current scope and visible columns.

Add Filter & Inline Filtering

- Use Add Filter (below the header) to filter by any supported field.
- Cells that are hyperlinked are available for filtering, selecting a linked cell will filter the table by that attribute and add a chip to the filter bar.

Alerts & Views

- Views support : The Recommendation Page supports account and vendor scoped views. Other business mappings aren’t supported here because per‑commitment metrics can’t be computed reliably under arbitrary remaps.

Recommendation Details Page

- Modeled KPIs : Net Savings, Savings Rate, Coverage, Utilization for the currently selected recommendations.
- Analysis Chart : Mirrors the Commitment Manager structure with current commitment cost overlaid with the proposed recommendation’s cost and resulting on-demand cost.
- Details Summary Card : Shows the specifics of the recommendation and additional information needed to assess the recommendation.
- Recommendation Adjustment : The Adjust action button allows users to use our model to adjust the recommendation. Here we support three adjustment methods. See the Recommendation Type section below for more information.
- Reporting Links : We provide links to reporting to provide some understanding of the committable spend backing the recommendation. We will improve this in the future by adding the coverage modal to the recommendations page.

### Recommendation Type

Cloudability produces multiple recommendation modes to match different decision styles. These modes are available for comparison on both the summary and details pages.

Taking AWS as an example, EC2 can be covered by EC2 Reserved Instances, EC2 Instance Savings Plans, and Compute Savings Plans. When on the All Compute recommendations page, the optimal recommendation will look across the three applicable commitment types to recommend what is optimal across committable spend. When on the All EC2 page, the optimal recommendation will look across the two EC2 specific commitment types to recommend what is optimal across committable spend while ignoring Compute Savings Plans. Finally, on the EC2 Instance Savings Plans recommendations page, the optimal recommendation will demonstrate what’s the maximum one could save with EC2 Instance Savings Plans, ignoring EC2 Reserved Instances.

- Commitment Amount : This method simply takes in an amount you wish to commit to, either in terms of on-demand or commitment cost, and provides you the expected outcome based facilitated through the recommendation user interface.
- Coverage Percentage : This method assumes you wish to build a business case for a coverage percentage that differs from your configured target commitment strategy. Input a coverage percentage and our model will attempt to estimate what purchase would result in the desired coverage percentage for the current variant.
- Minimum Sustained Usage : This method assumes you wish to cover all of sustained usage. We provide an input to omit up to 5% of usage hours that are outliers. Note: The custom recommendation still takes into account expected utilization based on the selected analysis period.

### Using this page to implement best practice

- Understand Current Performance : Always first check the portfolio to have a strong understanding upcoming expiration's and current utilization.
- Understand current coverage level : Our recommendations do not take future commitment expiration's into account.
- Understand how usage could change : Our recommendations are based off current usage and therefore do not take into account increases or decreases in usage.
- Configure Commitment Preferences : We set your commitment preferences by default to show a target recommendation. We recommend reviewing these preferences and adjusting them to fit your business prior to using the recommendations page.
- Compare Optimal vs Target vs Custom : If optimal materially exceeds target coverage, validate your risk tolerance through adjusting your commitment preferences. You may be leaving significant savings on the table. Use custom inputs to develop a summary level understanding of how different preferences could impact your recommendations.
- Build a business case : Use the recommendations details page build a business case for a long-term coverage strategy or incremental purchase.

### Key Takeaways

- Recommendations mirror Portfolio structure but are forward‑looking and actionable.
- The details page is a full workspace: inspect assumptions, view charts, and adjust proposals.
- Use Optimal/Target/Custom/Adjusted modes to align decisions to risk, policy, and cash constraints.
- Configure preferences to configure the target recommendation; use Coverage and Net Savings on portfolio for additional context.

---

## Using the Commitment Manager Overview to Align the Organization on Commitment Strategy

<!-- sub-header -->
- **breadcrumb:** Optimize > Guide to Commitment Management > Using the Commitment Manager Overview to Align the Organization on Commitment Strategy
- **source_path:** SSVCLNQ/product/using_commitment_manager_to_align_the_organization_on_commitment_strategy.html
- **original_file:** gcm-using-commitment-manager-overview-align-organization-commitment-strategy.md
- **images:** []

### Purpose

The overview page is the orientation layer for Cloudability Commitments. It brings together current posture (historical performance) and future opportunity (modeled recommendations) into one cross-service, cross‑vendor view. From this landing page, teams can begin to align on a holistic understanding of the current impact rate optimization has on their portfolio, and where immediate opportunity might lie. The tailored chart and standardized KPIs directly align users before drilling into Portfolio or Recommendations. This document will provide instructions for how to use this page.

### Access and Basic Configuration

The Commitment Manager page is located under the Optimize section in the left-hand navigation menu, below the Optimization Dashboard, and unlike the portfolio and recommendation pages.

Service Type

To start, the service type selector is a multi-select dropdown used to select which service usage you would like to analyze. When a service is selected, only the committable usage , is analyzed and displayed in the chart. This is an overview page, so further analysis of your portfolio or opportunities at the individual commitment type level must be done on the portfolio and recommendations pages. Notably, the aggregate pages at the vendor and service level ensure that the recommendations provided are mutually exclusive from each other.

For more information on this behavior, see the Recommendation Type section below.

Account

The account picker chooses which accounts’ usage our model will analyze. The picker represents hierarchical nature of your accounts and is multi-select. When selecting a payer account(s) (Management, Subscription, Billing), the button selects/unselects all linked accounts beneath it. When selecting specific linked account(s) (Member, Subscription, Project), the button similar selects/unselects the account while displaying a partial‑selection state on the payer account. It is generally best practice to choose an account selection that corresponds with your sharing preferences configured in the vendor console.

For more information about account terminology, see Account Structure by Vendor .

Cost Basis

The overview page does not allow for the option to choose your cost basis, instead if Adjusted is configured the chart will be in terms of Adjusted.

For more information, see How Negotiated Pricing Factors Across Commitments .

Analysis Period

The analysis period selection on the overview page differs from the portfolio recommendation pages in that a user selects a range in months. Importantly, users can select into the future. By default, the analysis period is one month look back and three months look forward in relation to today. If today's current month is considered part of the look forward or "forecast", because all days for the month have not yet been completed, the analysis period selection allows for both a selection of a range in months or a single month. To understand how the KPIs function with respect to the analysis period selected, see the KPI options in the subsequent section.

Recommendation Type

This section allows for the report to include or exclude the recommendation for the service selected. Optimal refers to the optimal recommendation type. For more information about the optimal recommendation type see Recommendation Type . For service spend that can be covered by multiple commitment types, assume the recommendation applied corresponds to the spend based commitment type. As an example. for AWS compute, the recommendation used on this page corresponds to compute savings plans.

### Configuring and Interpreting the KPIs

KPI Options - Type

This selection is used to configure the KPIs. Standard, the default, provides two values per KPI that demonstrate the earliest period and latest period selected. As such, standard allows you to compare the KPIs at two moments in time. Total, simply computes the KPI across the entire analysis period selected. Average, provides you the average across the analysis period selected for the KPI granularity selected.

KPI Options - Granularity

This selection defines the KPI granularity to be week or month based. In conjunction with KPI type, the user is provided the flexibility to analyze actual and forecasted performance across time.

KPI Options - Comparison

This selection will add a comparison KPI when either standard or average KPI option type is selected. Use the adjacent toggle to configure the comparison KPI to support absolute and percent change comparison methods.

More Options - Cost Granularity

Today, we only support daily granularity on the chart. Therefore, each bar on the chart, is representative of a cost in a day

More Options - Cost Type

We support true cost and on-demand equivalent (ODE). When true cost is selected, the default, all values on the chart are in terms of the cost paid or expected to be paid. When ODE is selected, all values are in terms of ODE, therefore the recommendation and existing commitment cost are transformed into ODE terms. Note, when ODE is selected as the cost type, the bar chart equals that of the ODE usage because all cost shown are in terms of on-demand.

Here are some examples on how to configure the KPI for a specific use case.

Example 1

Use Case: "Today is July 1st 2026, I would like to understand how my portfolio has improved or declined over the course of the first half of the year."

Configuration: Select All Services and a specific payer, select an analysis period of January 2026 to June 2026, select recommendation type to be off, select KPI options type to be standard, granularity month, and comparison on.

Interpretation: The KPI marked with the yellow annotation corresponds to January. The KPI in purple corresponds to June. The comparison KPI for each individual KPI will represent the percent change between January, and June. This configuration can be used for any combination of multiple months, therefore it can compare to two months/weeks in the past, two months/weeks in the future or the past with the future. In the user interface, the past is explicitly called actual, while the future is explicitly called forecast.

Example 2

Use Case: "Today is July 1st 2026, I would like to understand my net savings and coverage across the entire year in the event I make no future purchases."

Configuration: Select All Services and a specific payer, select an analysis period of January 2026 to December 2026, select recommendation type to be off, select KPI options type to be total.

Interpretation: There will now be one single value per KPI*. The KPIs will now represent values across the entire selected period.

*The remaining cost is also included in the cost KPI.

Example 3

Use Case: "Today is July 15th 2026, I would like to understand the value of the immediate commitment opportunities for the upcoming month. I would like to see this in comparison from the previous month."

Configuration: Select All Services and a specific payer, select an analysis period of June 2026 to August 2026, select recommendation type to be optimal, select KPI options type to be standard, granularity month, and comparison on.

Interpretation: The KPI marked with the yellow annotation corresponds to actual observed performance in June. The KPI in purple corresponds to the forecasted performance net of the optimal recommendation in August. The comparison KPI for each individual KPI will represent the percent change between June and August.

---

## Understanding Commitment Management Basics in Cloudability

<!-- sub-header -->
- **breadcrumb:** Optimize > Understanding Commitment Management Basics in Cloudability
- **source_path:** SSVCLNQ/product/commitment_management_basics.html
- **original_file:** optimize-understanding-commitment-management-basics-in-cloudability.md
- **images:** []

Summary

Commitment Management Basics introduces the foundational concepts behind how Cloudability models, measures, and reports cloud commitment data. It provides a clear framework for interpreting key financial and operational metrics—such as cost, savings, utilization, and coverage—across cloud service providers. By standardizing terminology and aligning with FinOps best practices, Cloudability Commitments helps users make informed decisions about cloud spend, optimize pricing strategies, and manage commitment portfolios with confidence.

Whether navigating cost structures, evaluating performance indicators, or exploring account hierarchies, this documentation equips you with the knowledge needed to fully leverage Cloudability’s commitment management capabilities. Dive into the following sections to understand how to read commitment tables, configure account sharing, and interpret savings metrics across AWS, Azure, and GCP.

---

## Account Structure by Vendor

<!-- sub-header -->
- **breadcrumb:** Optimize > Understanding Commitment Management Basics in Cloudability > Account Structure by Vendor
- **source_path:** SSVCLNQ/product/commitments_vendor_account_structure.html
- **original_file:** cloudability-account-structure-by-vendor.md
- **images:** []

### Purpose

The purpose of this document is to bring cloud account hierarchy to the practical level. It is crucial to understand how account structure impacts commitment sharing, visibility, and reporting across Cloudability Commitments. If you have not already, review the formal account definitions in How Commitment Management Differs Across Cloud Service Providers .

### Why Account Structure Matters to Commitments

Commitment benefits flow according to provider specific scopes (org, billing profile, project, region/AZ). Cloudability maps these hierarchies to:

- Compute KPIs correctly at the different levels of relevance.
- Recommend purchases at the correct sharing boundary based on preferences.
- Provide our users the ability to properly credential their accounts to systematically pull the appropriate data necessary.

Failure to properly credential and set up preferences may result in incorrect assumptions and recommendations that could lead to a incorrect reporting or worse, an erroneous purchase. Further, public APIs rarely provide sharing preferences systematically. This requires manual input to ensure both the portfolio and recommendations align with how discounts are actually applied.

### How Cloudability Maps Your Account Hierarchies

Cloudability ingests provider metadata and normalizes it to a few core ideas used across the app.

Payer Account - The invoice owner and common place where commitments are often formally billed. Note that often the commitment can be purchased at either the payer or linked account level. If sharing is turned on, the commitment will typically be shared across linked accounts on the payer.

Linked Account - Where resources run and usage occurs.

In product, our goal is to deliver a hierarchical and multi-select account selection across all pages. While at the time of writing this, we haven't fully supported this functionality, our plans are to make do on this commitment. For now, the pages address as follows:

Commitment Manager - Aggregates data across vendor accounts. Allows for multi-select. For, both the actual (historical) and forecasted (future) data, the account selection acts as a usage picker.

Commitment Portfolio - Shows per type summaries and details by account/subscription/project.

Commitment Recommendations - Respects your sharing intent (org wide vs. scoped) and account filters.

### AWS

Account Structure

Management (payer) account - Receives the consolidated bill; often the purchasing account for RIs/Savings Plans.

Member accounts (linked) - Where resources run and costs are generated.

Organizational Units (OUs) - Hierarchical “folders” for policy and governance (not billing containers). Not of particular interest for commitments.

Sharing behavior

Commitment sharing is an organization level setting. When enabled, discounts can automatically apply across member accounts, regardless of OU placement.

Region sharing is relevant to commitments where workloads and be deployed and commitment purchased at the region or availability zone.

### Azure

Account Structure

Billing Account (EA/MCA) - Top-level contract construct.

Billing Profile (MCA) - Invoice owner; often your primary sharing boundary.

Invoice Section (MCA) - Sub invoice buckets used for allocations/show back.

Subscription - Resource container and unit of billing.

Sharing behavior

Shared scope applies benefits across a billing context (e.g., EA Enrollment or MCA Billing Profile / Invoice Section)

Single Subscription or Single Resource Group limits benefits to that scope

### GCP

Account Structure

Billing Account - Where commitments and credits are managed; invoice owner.

Project - Resource container where workloads run and costs are generated.

Sharing behavior

Sharing must be turned on in the GCP console. It is managed at the Billing Account level.

Region is relevant to GCE Resource CUDs and some Spend CUDs such as Cloud SQL CUDs.

### Tips

1. Credential the right payer accounts first; confirm linked accounts and review any special permissions per service.
1. Set your account sharing settings per payer in commitment preferences to ensure correct sharing settings are defaulted to in recommendations.
1. Verify sharing is enabled at the payer level before trusting org wide coverage in Portfolio.
1. Confirm sharing settings and set them in the commitment preferences.
1. Periodically verify these settings.

### Takeaways

Account structure is crucial for proper function on Cloudability Commitments. Ensure accounts are correctly credentialed and sharing preferences set such that commitment functionality works properly.

---

## Cloudability Commitment’s Approach to Cost

<!-- sub-header -->
- **breadcrumb:** Optimize > Understanding Commitment Management Basics in Cloudability > Cloudability Commitment’s Approach to Cost
- **source_path:** SSVCLNQ/product/commitment_approach_to_cost.html
- **original_file:** cloudability-commitments-approach-cost.md
- **images:** []

### Purpose

Crucial to understanding how to use these features, the purpose of this document is to explore cost definitions across Cloudability Commitments.

### Cost Terminology

There are several cost related definitions that are crucial to using Cloudability Commitment functionality. Across these pages, we use strive to standardize terminology ensure consistent interpretation.

On ‑ Demand Equivalent (ODE) — Baseline cost had you paid on‑demand for the same usage. Can be any combination of on-demand and commitment cost.

On-Demand — Costs that received no discount from commitments.

Cost — Actual billed cost. Can be any combination of commitment cost and on-demand cost. Our charts across these pages are displayed in terms of this cost metric.

Amount — Generally speaking, amount is synonymous to ODE. We use this term where it it may be ambiguous to what combination of on-demand and cost a metric could represent.

Covered Amount — Portion of total usage billed under discounted rates. The ODE of a commitment.

Covered Cost — Explicitly the cost of the commitment or commitments.

Uncovered Cost — Not formally used as this term by definition is the same at on-demand cost. We prefer the term on-demand.

Uncovered Amount — Yet another term for on-demand cost. We use this to keep the terminology consistent on the coverage modal.

Cost Basis — A cross-feature term used across Cloudability to align the information on a given page with the appropriate cost metric. For Cloudability Commitments, the Cost Basis is dictated by the list vs. negotiated price on both on-demand and commitment discount.

List — Uses list prices for both the on-demand and commitment costs. Performance and recommendations are driven off of these values.

Adjusted — Uses negotiated prices for both the on-demand and commitment costs. Performance and recommendations are driven off of these values.

Lifetime Cost — The total cost of a commitment, including any upfront costs.

Remaining Cost — The cost remaining of a commitment from today, regardless of the reporting range selected.

---

## Commitment Key Performance Indicators

<!-- sub-header -->
- **breadcrumb:** Optimize > Understanding Commitment Management Basics in Cloudability > Commitment Key Performance Indicators
- **source_path:** SSVCLNQ/product/commitments_key_performance_indicators.html
- **original_file:** cloudability-commitment-key-performance-indicators.md
- **images:** []

### Purpose

Establish foundational understanding of common KPIs used across Cloudability Commitments. Across the commitment manager, portfolio, and recommendations, we leverage common KPIs that quantify savings and risk after accounting for all cost and pricing adjustments.

### Savings Performance Indicators

Net Savings — Savings minus waste. Reflects the true value realized/expected by your portfolio, commitment, or recommendations. Used at both individual commitment and aggregate levels.

Example - If a set of commitments cost $10k over a specific time period which equated to $15k in on-demand equivalent spend. The gross savings of the commitments would be $15k - $10k = $5k. If 5% of these commitments when unutilized, waste would equal $10k*5% = $500. Thus, the Net Savings = $5k - $500 = $4.5k.

Savings Rate — We have several saving rates surfaced in our application. Their definitions are as follows:

Generically — Savings Rate = Savings / Spend

Effective Savings Rate (ESR ) — Committable Spend is explicitly in terms of on-demand price. Therefore, a List cost basis means that neither the negotiated rates on on-demand nor commitments are included, ESR is based solely on list pricing. For an Adjusted cost basis, the list on-demand rate is used in conjunction with the negotiated commitment rate. While a bit nuanced, this definition is aligned with the FinOps Foundation and makes sense when negotiated pricing is included as a component of Rate Optimization. We only use this term on the Optimizations Dashboard since in is crucial to isolate commitment performance from negotiated pricing at the commitment feature level.

ESR = (Commitment Savings + Custom Rate Savings) / Committable Spend.

Negotiated Savings Rate (NSR) — While not explicitly used in Cloudability, the NSR is a term that can be used to isolate your negotiated on-demand rates. The numerator is simply the savings attributed to this negotiated rate while the denominator, Committable Spend, carries the same definition as with ESR.

NSR = Custom Rate Savings / Committable Spend.

Portfolio Savings Rate (PSR) — PSR is the core metric Cloudability Commitments uses to communicate the performance of a portfolio or set of recommendations. Notably, committable spend here is fully aligned with the cost basis. A List cost basis therefore implies the savings and spend is driven off of List rates while Adjusted implies the KPI is calculated off negotiated rates.

PSR = Commitment Saving / Committable Spend.

Commitment Savings Rate (CSR) — The realized (portfolio) or expected (recommendations) savings rate of a commitment. Can be compared directly with CDR to understand the impact of utilization. Notably, this KPI appears alongside PSR on the portfolio when applicable. Another way to describe this KPI when surfaced on portfolio is the weighted average of multiple commitment's savings rates.

CSR = Commitment Saving / ODE of Commitment Cost

Commitment Discount Rate (CDR) — The saving rate given that the commitment was fully utilized. We surface this alongside CSR to demonstrate maximum savings rate achievable by a given commitment.

CDR = 𝑆𝑎𝑣𝑖𝑛𝑔𝑠 𝑅𝑎𝑡𝑒 @ 100% 𝑈𝑡𝑖𝑙𝑖𝑧𝑎𝑡𝑖𝑜𝑛.

Subsequent help documents will dive further into this terminology and explain where it is relevant to fully understand commitment performance and evaluate opportunities.

### Strategy and Risk Indicators

Utilization — The extent to which purchased commitments were actually consumed; weighted and aggregated when displayed as a KPI. This metric is realized for portfolio but expected as a result of the usage range selected in recommendations.

Coverage — The portion of eligible usage covered by commitments (vs. on‑demand), shown as a percentage and extensively supported by a coverage modal.

Example - 75% coverage means three‑quarters of eligible usage benefited from discounted pricing.

Remaining Commitment Cost — What you owe from today until all active commitments expire, independent of the reporting range.

Importantly, commitment KPIs and meta data cannot often be derived across business metrics and therefore, the commitment pages only support account and vendor-based views. We strive to continue to improve this portion of our application and encourage you to flag requests on the IBM Ideas Portal . Leverage the "Rate Optimization" category.

---

## Commitment Management Basics FAQ

<!-- sub-header -->
- **breadcrumb:** Optimize > Understanding Commitment Management Basics in Cloudability > Commitment Management Basics FAQ
- **source_path:** SSVCLNQ/product/understanding_commitment_management_basics_faq.html
- **original_file:** cloudability-commitment-management-basics-faq.md
- **images:** []

## Commitment Management Basics FAQ

---

## Commitment Table Basics

<!-- sub-header -->
- **breadcrumb:** Optimize > Understanding Commitment Management Basics in Cloudability > Commitment Table Basics
- **source_path:** SSVCLNQ/product/commitment_table_basics.html
- **original_file:** cloudability-commitment-table-basics.md
- **images:** []

### Purpose

The purpose of this document is to introduce how meta data is displayed across the commitment pages expectation and explain the data shown in Cloudability’s commitment tables and how to read, filter, and export it consistently across pages (Manager, Portfolio, Recommendations). This is a practical reference for columns, sorting, and interpretation.

### Information Architecture

Metadata for commitments, recommendations, and groups appears in three UI patterns across the app:

Table — A tabular grid with columns and column groups (headers) that organize related fields for easy comparison.

Details Panel (Right Drawer) — A slide out panel that displays field level properties and contextual actions for the selected row or card.

Summary Card — A page level card that surfaces key metrics or attributes relevant to the current view (commonly used on the Recommendations page).

Why this is important: Standardized display patterns make information scannable, align Help Center terminology with the product UI, and ensure consistent reporting and analysis across providers.

### Where You’ll See UI Components

Commitment Manager — Aggregate level overview with a time series chart of commitment costs and savings. In the future, we will add a Monthly Rollup table to summarize the periodized costs shown in the chart.

Commitment Portfolio — A tabular inventory of commitments. Each row includes a Details action (right aligned) that opens the Details Panel (Right Drawer) to show fields not present in the table.

Commitment Recommendations — A summary view that mirrors Portfolio interactions. The Details action opens a dedicated Details Page (instead of the drawer). A Summary Card highlights recommendation assumptions (term, scope, sharing, payment) and modeled KPIs such as cost and net savings.

Why this is important: We're defining consistent naming for these UI components (Table, Details Panel, Summary Card, Details Page) to more effectively explain concepts later in this documentation.

### Data Reference

The following table provides a reference for each field shown across the commitment pages.

Commitment Details

| Field | AWS | GCP | AZURE | Notes |
| --- | --- | --- | --- | --- |
| Field | AWS | GCP | AZURE | Notes |
| Commitment ID | ID | ID | — | Unique identifier for the commitment record. |
| Category | Category | Category | — | Vendor agnostic category (e.g., Resource vs. Spend). |
| Service | Service | Service | — | Service or Product family (e.g., EC2, GCE, RDS). |
| Region | Region / Availability Zone | Region | — | Location of a resource. |
| Term | Term | Term | — | Typically, 1 or 3year. |
| Payment Option / Billing Frequency | Payment Option | — | — | AWS: No/Partial/All Upfront. GCP: effectively no upfront for most commitments. |
| Upfront Cost | Upfront Cost | — | — | Recognized by basis (cash vs. adjusted). |
| Hourly Commitment Amount | Hourly Amount | Hourly Amount | — | Contextual to the commitment e.g., GCP Resource CUDs show vCPU/Memory/SSD/GPU quantities; AWS EC2 RI shows count/quantity. |
| Commitment List Discount Rate | — | List Savings Rate | — | Published discount rate for the item. |
| OS | OS | — | — | Applicable to some compute commitments. |
| Tenancy | Tenancy | — | — | Dedicated vs. shared tenancy (AWS). |
| Class | Class | — | — | Standard vs. convertible (where applicable). |
| Sharing | ISF | — | — | Instance Size Flexibility / sharing indicator (AWS). |
| Units (deprecated) | Units | — | — | No longer required. |
| Region Sharing Bool | MultAZ | — | — | Indicates multiAZ/region sharing behavior (AWS). |
| Engine Type | Engine Type | — | — | Applicable to certain database/search products. |

Account & Ownership

| Field | AWS | GCP | AZURE | Notes |
| --- | --- | --- | --- | --- |
| Field | AWS | GCP | AZURE | Notes |
| Payer Account Name | Payer Account | Billing Account | — | Invoice owner / billing context. |
| Payer Account ID | — | Billing Account ID | — | Identifier for the billing account (GCP). |
| Linked Account Name | Linked Account | Project | — | Consuming account/project. |
| Linked Account ID | — | Project ID | — | Identifier for the project (GCP). |

Performance (NonKPI Fields)

| Field | AWS | GCP | AZURE | Notes |
| --- | --- | --- | --- | --- |
| Field | AWS | GCP | AZURE | Notes |
| [Reported] Commitment Cost | Cost | Cost | — | Sum cost of commitments within the selected scope/period. |
| [Paid] Commitment Cost | Paid Cost | Paid Cost | — | Recognized per basis (cash vs. adjusted). |
| [Lifetime] Commitment Cost | Lifetime Cost | Lifetime Cost | — | Cumulative cost over the commitment’s life. |
| Reported Commitment Net Savings | Net Savings | Lifetime Net Savings | — | May differ in naming; reflects period vs. lifetime on GCP. |
| Reported Commitment Savings Rate | Savings Rate | Savings Rate | — | Current savings rate for the row’s scope (not a portfolio KPI). |
| Reported Commitment Utilization | Utilization | Utilization | — | Blended utilization for the row (not a portfolio KPI). |
| [Remaining] Commitment Cost | Remaining Cost | Remaining Cost | — | Forward exposure until expiration. |
| Reported Unrealized Net Savings | Unrealized Net Savings | — | — | Potential savings not yet realized due to under utilization. |
| Hourly OnDemand Commitment | — | OnDemand commitment | — | GCP reference value for comparison (where available). |
| Hourly Net Savings | — | Net Savings (Hourly) | — | Where exposed at hourly granularity. |
| Breakeven | — | Breakeven (Months) | — | Months to break even given current usage. |

SubQuantities (GCP Resource CUDs)

| Field | AWS | GCP | AZURE | Notes |
| --- | --- | --- | --- | --- |
| Field | AWS | GCP | AZURE | Notes |
| Hourly Commitment Amount — Cores | — | Hourly Commitment Amount (Cores) | — | vCPU quantity committed. |
| Utilization — Cores | — | Utilization (Cores) | — | vCPU utilization of the committed quantity. |
| Hourly Commitment Amount — Memory | — | Hourly Commitment Amount (Memory) | — | Memory (GiB) quantity committed. |
| Utilization — Memory | — | Utilization (Memory) | — | Memory utilization of the committed quantity. |
| Hourly Commitment Amount — SSD | — | Hourly Commitment Amount (SSD) | — | SSD quantity committed. |
| Hourly Commitment Amount — GPU | — | Hourly Commitment Amount (GPU) | — | GPU quantity committed. |

Recommendation Details (Where Applicable)

| Field | AWS | GCP | AZURE | Notes |
| --- | --- | --- | --- | --- |
| Field | AWS | GCP | AZURE | Notes |
| Recommendation SubType | Instance Family / Node / Instance Type | Machine Type | — | Proposed shape/family for the recommendation. |
| Monthly Recommendation SUD Credit | — | Recommendation Sustained Use Discount Credit (Estimated Monthly) | — | GCP specific estimate. |
| Lifetime Recommendation SUD Credit | — | Recommendation Sustained Use Discount Credit (Estimated Lifetime) | — | GCP specific estimate. |

Status & UI

| Field | AWS | GCP | AZURE | Notes |
| --- | --- | --- | --- | --- |
| Field | AWS | GCP | AZURE | Notes |
| State | State | — | — | Current state (active, retired, etc.). |
| Start Date | Start Date | — | — | Effective start. |
| End Date | Expiration | — | — | Effective end / expiration. |
| Details Button | Details Icon | Details Icon | — | UI control to open the drawer/details page. |
| Total Number of Commitments | Commitments | — | — | Label above the table next to the export icon (UI label). |

### Working With the Table

Filter Bar — Manual filter across meta data by using the common filter toolbar.

Filter Hyperlink — Hyperlinked cells in the table are immediately available to filter as 'equals'. Select a hyperlink to filter the table by this value. The filter chip will appear in the filters toolbar above.

Show/Hide Columns — Use the Show/hide columns bar on the right side of the table to select which columns you wish to view. (Coming soon)

Sort & MultiSort — Click a header to sort descending. Click again to sort ascending. Click a third time to return to the default state.

Export — The export button provides a CSV of the data in the table in a what you see is what you get format. Note that all meta data is included in this export.

### Takeaway

Getting fluent in the tables, labels, and layouts used across Commitment Manager, Portfolio, and Recommendations is foundational. With a consistent vocabulary (Table, Details Panel, Summary Card, Details Page) and a clear mapping of field names across providers, you’ll:

- Read rows in context (scope, term, payment), avoiding misinterpretation.
- Trace ownership and sharing correctly (payer/billing account vs. linked account/project).
- Compare apples-to-apples across clouds using normalized fields.
- Move faster from what you see (table) to why it matters (details, sub quantities, performance fields) and what to do next (filters, export, and Recommendations).

With this foundational information, subsequent documentation will dive deeper into the application and how it’s used to optimize cloud spend.

---

## How Negotiated Pricing Factors Across Commitments

<!-- sub-header -->
- **breadcrumb:** Optimize > Understanding Commitment Management Basics in Cloudability > How Negotiated Pricing Factors Across Commitments
- **source_path:** SSVCLNQ/product/custom_pricing_factors_across_commitments.html
- **original_file:** cloudability-how-negotiated-pricing-factors-across-commitments.md
- **images:** []

### Purpose

Explain how negotiated pricing interacts with commitment programs and KPIs so teams read results consistently across pages and providers.

Negotiated pricing may also be referred to as custom pricing for commitments we will use them interchangeably

### Pricing Basics

Negotiated Pricing Changes the Baseline - Committable spend, provided in terms of on-demand equivalent (ODE) reflects list or adjusted rates depending on your selected cost basis. That choice flows into each of the 5 key performance indicators.

Negotiated Pricing Changes the Commitment Discount Rate - In addition to negotiating on-demand rates, CSPs allow for the negotiation of commitment discounts, often varying across commitment type, region, instance, term, etc.

Stacking Matters - Negotiated pricing may stack with commitments (additive) or supersede certain line items (non stacking). Always confirm how your contract interacts with the commitment program for the affected services. As Cloudability Commitments pulls this pricing from your public APIs, we are able to formally determine the real result/expectation for a given commitment or recommendation.

### Cost Basis — List vs. Adjusted

Cost basis determines what prices are used for ODE and cost calculations.

List - Uses public/list rates for both on-demand and commitment pricing.

Adjusted - Uses your negotiated/custom rates for both on-demand and commitment pricing. One caveat as mentioned in the introduction to savings rate section, ESR uses a mix of negotiated commitment pricing and list on-demand rates when the adjusted basis is selected. As such, this ensures that negotiated pricing is included when assessing Rate Optimization at the highest level.

Implication - With adjusted cost basis, often on-demand, commitment discount, and thus ODE are all lower than when list. As a result, magnitude of Net Savings and Commitment Cost are likely to be lower since the discount on a commitment is less, the cost applicable to the commitment is less, or a combination of both.

### Stacking Rules

Negotiated pricing contracts differ wildly across customer size and CSP. The largest cloud service users naturally have leverage in negotiating discounts relative smaller customers. At a high level, there are no hard and fast rules. Treat the following as patterns to verify against your agreements.

Additive Stacking - Negotiated discounts reduce the on-demand rate; commitment discounts apply on top, resulting in lower effective rates.

Superseding Terms - Negotiated pricing may establish a floor that replaces list discounts for certain SKUs/services.

Program Priority - Some programs apply credits after commitments, others reduce the base used to calculate commitment value.

While Cloudability can systematically help expose negotiated pricing implications, it is prudent for FinOps practitioners to understand the negotiated terms inside and out. Confirm stacking order for your services. Misunderstanding stacking can lead to double counting expected savings.

### Practical Guidance

- Isolate list based KPIs from negotiated based KPIs. Mixing them could give the wrong interpretation of performance.
- Pay attention to your cost basis across commitment pages. Ensure adjusted is set as default. Document your basis on shared dashboards and exports outside of the application.
- Validate stacking per service family before proceeding with purchases.
- Explore the list cost basis to better understand the impact of your negotiated terms. Leverage this knowledge in future negotiated pricing conversations.

---
