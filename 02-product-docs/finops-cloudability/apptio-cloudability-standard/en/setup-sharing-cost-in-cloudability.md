---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Sharing Cost in Cloudability"
breadcrumb:
  - "Setup"
  - "Sharing Cost in Cloudability"
source_path: "SSVCLNQ/product/cost-sharing.html"
images:
  - "03-media/apptio-cloudability-standard/cost-sharing-4.jpg"
  - "03-media/apptio-cloudability-standard/cost-sharing-6.jpg"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Sharing Cost in Cloudability

## Introduction

Sharing costs helps organizations manage spend across showback and chargeback exercises in a more efficient manner. By sharing line items across Cloudability, they are able to save cost.

Sharing of costs is the act of taking a bucket of spend (e.g. a dimensional value's direct charges) and sharing that value across a list of destination dimensional values. A simple way to think about this is every dimensional value has a direct cost within Cloudability. This cost has been derived by ingesting raw data of the resource cost, followed by tagging, and then using the conditional logic of Cloudability's business mappings feature.

Every dimensional value is associated with a direct cost, shared cost, and a total cost (direct+shared).

Cost allocation rules are done within the context of a singular business mapping. Multiple rules can be configured within a Business Mapping. However you can not configure rules across multiple business mappings..

## Benefits

The benefits of Cost Sharing are:

- Accurate Cost Attribution : Enable precise tracking of shared resources and services across teams, products, and business units.
- Defensible Chargeback Model : Create transparent, rule-based cost distribution that supports internal billing practices.
- Flexible Allocation Strategies : Choose from multiple allocation methods to match your organization's cost sharing requirements.
- Business-Aligned Cost Management : Map technology costs to business outcomes and organizational structure.
- Enhanced Cost Visibility : Gain clear insights into both direct and shared costs across your cloud environment.

## Core Concepts

Organizations allocate and share costs under varied scenarios. Keeping that in mind. we have included the most common allocation strategies for you as in the following section.

The various costs incurred are:

- Direct cost : Costs derived through raw data ingestion, synthetic tagging, or business mapping decoration
- Shared cost : Costs received through cost sharing rules from source dimensional values
- Total cost : Combined value of direct and shared costs for any dimensional value

## Allocation Strategies

The various allocation strategies are:

- Even Split defines a spread of direct costs (s) across a set of dimensional buckets at equal value. Direct costs can either be that of a single or multi dimensional bucket.
- Fixed Weighting uses fixed weights as a percentage. It is a breakout of direct costs for a single or multi dimensional bucket from a user-defined weighting.
- Proportional (By Direct Charges) uses the direct cost as the weight. This lets you dynamically weigh the allocation based off the source destination’s direct charges. Proportional weighing takes into account the source bucket's direct charges when it calculates the assignment ratio for the selected allocation.
- Telemetry/ Consumption based allocations uses telemetry data ( Usage metrics, API calls, or storage operations) to create more accurate and data-driven allocation rules and is only available for Cloudability Premium customers.

## Configure Cost Sharing rules

To configure Cost Sharing rules,

1. From the Organize section of the main menu, select Cost Sharing .
1. Select New Allocation . Alternatively, select an existing business dimension to edit the allocation rule. There is no limit on allocation rules you can set.
1. Specify a dimension for the new allocation.
1. To create a new rule, click New Rule . Select the source buckets you wish to share costs from, the destination buckets you wish to share costs to, and the allocation strategies to weigh these costs by. Existing allocation rules if any are displayed under the Rules table.
1. Click Save .
1. Navigate to the Explorer tab to view your shared costs and applied allocation rules.

The Explorer tab displays the allocation rules created with the following details:

- Reporting Range: The date range chosen starting from Yesterday to Last Year.
- Cost Metric : The cost type chosen.

Click the +Add Filter to set filters to display the list of cost allocation rules.

You can toggle the All and Shared button to display the list of all cost allocation rules or shared ones respectively.

## Reporting

We have exposed a new projection in Apptio BI for reporting on shared costs called Cloudability Cost and Usage (Allocated). This is a separate projection due to the scale and size of the data set that we work with while running all cost allocation rules. To build a report from this shared cost, follow the steps below:

1. Navigate to Apptio BI in the right hand navigation pane.
1. In the Reports tab, select Create New Report .
1. Click Add Visualization and select the Cloudability Cost and Usage (Allocated) projection.
1. Create your report with the same dimensions and cost metrics that are available in the Cloudability Cost and Usage .
1. Select from the list of Cloudability Views .

## Views

Cost sharing respects our view construct by showing shared line items under the destination bucket when that bucket is included in a view. For example: For a business dimension called Product with multiple products within titled products A, B, and C, our organization allocates A’s costs out to B and C on a proportional basis (by direct charges) resulting in B and C absorbing A’s direct cost. Now, for a view configured with C, when a report is created in Apptio BI , product C’s view would display both their direct charges as well as the cost that was shared with them from A.

## Best Practices

Some of the best practices in Cost Sharing Include aspects of Rule Configuration and Cost Management .

Rule configuration include the following:

- Start with simpler allocation rules and gradually increase complexity
- Document the business justification for each allocation rule
- Regularly review and validate allocation rules against business changes
- Consider the hierarchical impact of allocations within your organization
- Cost allocation rules operate within a single business mapping

Cost management include the following:

- Monitor both direct and shared costs to identify trends and anomalies
- Validate allocation results monthly to ensure accuracy
- Maintain clear documentation of allocation decisions and methodologies
- Consider seasonal variations when setting up allocation rules

## Import and Export Functionality for Cost Allocation Rules

- CSV Import : You can upload cost allocation rules via CSV, removing the need to configure them manually in the user interface or programmatically through the API. This is ideal for bulk generation of allocation rules . A CSV template is available at the bottom of this document that provides a sample template that can be used when importing rules. Alternatively, if you have a set of rules already, they will export with the correct column headers and values supported for upload. The list of columns that we require are as follows: Rule ID : A unique identifier of the rule in question. If you are building multiple statements in a given rule, (For example: You are splitting out multiple source buckets across multiple destinations) you will need to include the same rule ID for all statements Allocation Method (this needs to be one of the following): Even_split, proportional_fixed_weighting, proportional_metric, or telemetry_consumption. Note that telemetry is only supported in Cloudability Standard and Premium. Source : The set of source buckets you wish to allocate the cost from Destination : The set of destination buckets you wish to allocate the cost to Destination Weight : This should be the weight of the allocation to this specific destination Telemetry Identifier : This should be set to custom Telemetry Metric Name : The name of the metric that is used to weight the allocation. This can be the number of API calls as an example.
- Export Existing Rules : You can export their current set of cost allocation rules within a business dimension.

## Cost Allocation Rules Template

| Rule ID | Allocation Method | Source | Destination | Destination Weight | Identifier Telemetry | Metric Name |
| --- | --- | --- | --- | --- | --- | --- |
| 2310fe9f-6535-474b-a153-27719a485168 | even_split | cloud | billing | 0.5 |  |  |
| 2310fe9f-6535-474b-a153-27719a485168 | even_split | cloud | acme | 0.5 |  |  |
| 2 | telemetry_consumption | compute |  | 0 | custom | Number of SQS Requests |
| 3 | proportional_metric | data | vanguard | 0 |  |  |
| 3 | proportional_metric | data | nimbus | 0 |  |  |
| 3 | proportional_metric | data | billmx | 0 |  |  |
| 3 | proportional_metric | pipeline | vanguard | 0 |  |  |
| 3 | proportional_metric | pipeline | nimbus | 0 |  |  |
| 3 | proportional_metric | pipeline | billmx | 0 |  |  |
| 4 | proportional_fixed_weighting | billingdata | ccm | 0.4 |  |  |
| 4 | proportional_fixed_weighting | billingdata | infosec | 0.6 |  |  |
| 4 | proportional_fixed_weighting | datalake | ccm | 0.4 |  |  |
| 4 | proportional_fixed_weighting | datalake | infosec | 0.6 |  |  |
| 4 | proportional_fixed_weighting | techops | ccm | 0.4 |  |  |
| 4 | proportional_fixed_weighting | techops | infosec | 0.6 |  |  |
| 5 | even_split | operations | ccm | 0.5 |  |  |
| 5 | even_split | operations | vedas | 0.5 |  |  |

## Explorer Page Data Export

- Direct costs
- Shared costs
- Total costs

## Cost Sharing by Business Metrics

We are expanding the power and precision of Cost Sharing with new support for custom Business Metrics.

Share Costs Across Any Currency-Based Business Metric

Previously, Cloudability supported cost sharing only across a predefined set of default cost metrics. With this update, you can now allocate shared costs across any currency-based Business Metric in their environment .

- More contextually relevant cost allocations tailored to your business’s unique financial model
- Stronger defensibility of shared cost distribution by aligning it with metrics that matter most to your teams
- Expanded reporting capabilities using metrics beyond the defaults

Currently, only currency-based Business Metrics are being supported.

- Explorer Page : When setting up or reviewing cost sharing rules, you will see all eligible Business Metrics available for selection
- Apptio BI : You can also select from the full set of supported metrics when creating reports, enabling deeper insights and alignment across stakeholders

This update is available to all Cloudability customers and requires no additional configuration to begin using.

User Configuration Guide: Lineage in ApptioBI Reporting

This guide helps users include the Allocation Source dimension in their Apptio BI reports to gain detailed insights into the origins of shared costs.

Prerequisites:

- Access to Apptio BI and the Cloudability Cost and Usage (Allocated) projection
- Rules set up in Cloudability Cost Sharing

Step-by-step Configuration

1. Open Apptio BI: Log in to your Cloudability account and navigate to Apptio BI.
1. Select Projection: Navigate to a dashboard and New Widget to create a new widget. Choose the Cost and Usage (Allocated) projection.
1. Add Allocation Source Dimension: In the widget configuration pane, click on Dimensions. Search for and select Allocation Source. Drag or click to add the Allocation Source dimension into your widget.
1. Customize Your Widget: Add any additional required dimensions or metrics. Confirm and apply your widget settings.
1. Validate and Publish: Preview the widget to ensure data accuracy and clarity. Click Save to finalize and publish your report.

- Allocation Source provides row-level detail of shared costs and will increase the number of rows in your reports.
- Avoid using Allocation Source with multiple business dimensions simultaneously enabled for cost sharing, as this will generate errors.

## Troubleshooting Known Issues

- Error: "Unable to display Allocation Source": Cause: Allocation Source is being used with multiple dimensions having cost sharing. Resolution: Ensure Allocation Source is only combined with one shared dimension at a time in each widget.
