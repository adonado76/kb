---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Guide to Legacy Commitment Manager"
breadcrumb:
  - "Optimize"
  - "Guide to Commitment Management"
  - "Guide to Legacy Commitment Manager"
source_path: "SSVCLNQ/product/commitment-manager.html"
images:
  - "03-media/apptio-cloudability-standard/details.jpg"
  - "03-media/apptio-cloudability-standard/commit_manager_cred_detail.jpg"
  - "03-media/apptio-cloudability-standard/commit_manager_subnav.jpg"
  - "03-media/apptio-cloudability-standard/commit_manager_usage_analysis.jpg"
  - "03-media/apptio-cloudability-standard/commit_manager_range.jpg"
  - "03-media/apptio-cloudability-standard/commit_manager_acct_sel.jpg"
  - "03-media/apptio-cloudability-standard/commit_manager_serv_sel.jpg"
  - "03-media/apptio-cloudability-standard/commit_manager_rec_opt.jpg"
  - "03-media/apptio-cloudability-standard/commit_manager_def_rec.jpg"
  - "03-media/apptio-cloudability-standard/commit_manager_rec_applied.jpg"
  - "03-media/apptio-cloudability-standard/commit_manager_savings.jpg"
  - "03-media/apptio-cloudability-standard/commit_manager_click_2_nav.jpg"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Guide to Legacy Commitment Manager

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
