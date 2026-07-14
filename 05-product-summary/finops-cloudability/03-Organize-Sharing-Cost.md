---
source_system: "apptio-cloudability-standard"
practice: "finops"
language: "en"
doc_type: "cloudability-standard"
consolidated_file: "03-Organize-Sharing-Cost"
source_files_count: 3
last_updated: "2026-07-13"
---

# 03-Organize-Sharing-Cost

## Sharing Cost in Cloudability

<!-- sub-header -->
- **breadcrumb:** Setup > Sharing Cost in Cloudability
- **source_path:** SSVCLNQ/product/cost-sharing.html
- **original_file:** setup-sharing-cost-in-cloudability.md
- **images:**
  - 03-media/apptio-cloudability-standard/cost-sharing-4.jpg
  - 03-media/apptio-cloudability-standard/cost-sharing-6.jpg

## Sharing Cost in Cloudability

### Introduction

Sharing costs helps organizations manage spend across showback and chargeback exercises in a more efficient manner. By sharing line items across Cloudability, they are able to save cost.

Sharing of costs is the act of taking a bucket of spend (e.g. a dimensional value's direct charges) and sharing that value across a list of destination dimensional values. A simple way to think about this is every dimensional value has a direct cost within Cloudability. This cost has been derived by ingesting raw data of the resource cost, followed by tagging, and then using the conditional logic of Cloudability's business mappings feature.

Every dimensional value is associated with a direct cost, shared cost, and a total cost (direct+shared).

Cost allocation rules are done within the context of a singular business mapping. Multiple rules can be configured within a Business Mapping. However you can not configure rules across multiple business mappings..

### Benefits

The benefits of Cost Sharing are:

- Accurate Cost Attribution : Enable precise tracking of shared resources and services across teams, products, and business units.
- Defensible Chargeback Model : Create transparent, rule-based cost distribution that supports internal billing practices.
- Flexible Allocation Strategies : Choose from multiple allocation methods to match your organization's cost sharing requirements.
- Business-Aligned Cost Management : Map technology costs to business outcomes and organizational structure.
- Enhanced Cost Visibility : Gain clear insights into both direct and shared costs across your cloud environment.

### Core Concepts

Organizations allocate and share costs under varied scenarios. Keeping that in mind. we have included the most common allocation strategies for you as in the following section.

The various costs incurred are:

- Direct cost : Costs derived through raw data ingestion, synthetic tagging, or business mapping decoration
- Shared cost : Costs received through cost sharing rules from source dimensional values
- Total cost : Combined value of direct and shared costs for any dimensional value

### Allocation Strategies

The various allocation strategies are:

- Even Split defines a spread of direct costs (s) across a set of dimensional buckets at equal value. Direct costs can either be that of a single or multi dimensional bucket.
- Fixed Weighting uses fixed weights as a percentage. It is a breakout of direct costs for a single or multi dimensional bucket from a user-defined weighting.
- Proportional (By Direct Charges) uses the direct cost as the weight. This lets you dynamically weigh the allocation based off the source destination’s direct charges. Proportional weighing takes into account the source bucket's direct charges when it calculates the assignment ratio for the selected allocation.
- Telemetry/ Consumption based allocations uses telemetry data ( Usage metrics, API calls, or storage operations) to create more accurate and data-driven allocation rules and is only available for Cloudability Premium customers.

### Configure Cost Sharing rules

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

### Reporting

We have exposed a new projection in Apptio BI for reporting on shared costs called Cloudability Cost and Usage (Allocated). This is a separate projection due to the scale and size of the data set that we work with while running all cost allocation rules. To build a report from this shared cost, follow the steps below:

1. Navigate to Apptio BI in the right hand navigation pane.
1. In the Reports tab, select Create New Report .
1. Click Add Visualization and select the Cloudability Cost and Usage (Allocated) projection.
1. Create your report with the same dimensions and cost metrics that are available in the Cloudability Cost and Usage .
1. Select from the list of Cloudability Views .

### Views

Cost sharing respects our view construct by showing shared line items under the destination bucket when that bucket is included in a view. For example: For a business dimension called Product with multiple products within titled products A, B, and C, our organization allocates A’s costs out to B and C on a proportional basis (by direct charges) resulting in B and C absorbing A’s direct cost. Now, for a view configured with C, when a report is created in Apptio BI , product C’s view would display both their direct charges as well as the cost that was shared with them from A.

### Best Practices

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

### Import and Export Functionality for Cost Allocation Rules

- CSV Import : You can upload cost allocation rules via CSV, removing the need to configure them manually in the user interface or programmatically through the API. This is ideal for bulk generation of allocation rules . A CSV template is available at the bottom of this document that provides a sample template that can be used when importing rules. Alternatively, if you have a set of rules already, they will export with the correct column headers and values supported for upload. The list of columns that we require are as follows: Rule ID : A unique identifier of the rule in question. If you are building multiple statements in a given rule, (For example: You are splitting out multiple source buckets across multiple destinations) you will need to include the same rule ID for all statements Allocation Method (this needs to be one of the following): Even_split, proportional_fixed_weighting, proportional_metric, or telemetry_consumption. Note that telemetry is only supported in Cloudability Standard and Premium. Source : The set of source buckets you wish to allocate the cost from Destination : The set of destination buckets you wish to allocate the cost to Destination Weight : This should be the weight of the allocation to this specific destination Telemetry Identifier : This should be set to custom Telemetry Metric Name : The name of the metric that is used to weight the allocation. This can be the number of API calls as an example.
- Export Existing Rules : You can export their current set of cost allocation rules within a business dimension.

### Cost Allocation Rules Template

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

### Explorer Page Data Export

- Direct costs
- Shared costs
- Total costs

### Cost Sharing by Business Metrics

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

### Troubleshooting Known Issues

- Error: "Unable to display Allocation Source": Cause: Allocation Source is being used with multiple dimensions having cost sharing. Resolution: Ensure Allocation Source is only combined with one shared dimension at a time in each widget.

---

## Cost Sharing -Telemetry and Consumption Based Allocations

<!-- sub-header -->
- **breadcrumb:** Setup > Sharing Cost in Cloudability > Cost Sharing -Telemetry and Consumption Based Allocations
- **source_path:** SSVCLNQ/product/cost-sharing-telemetry.html
- **original_file:** cloudability-cost-sharing-telemetry-consumption-based-allocations.md
- **images:** []

## Cost Sharing -Telemetry and Consumption Based Allocations

Overview

Telemetry Based Allocations enables you to distribute shared costs across your cloud environment using actual usage metrics from your systems. By uploading telemetry data, you can create more accurate and data-driven allocation rules within Cost Sharing.

Benefits

Using telemetry data for cost allocation provides several key advantages, as in:

- Usage-Based Cost Distribution : Allocate costs based on actual system usage rather than static percentages or estimated metrics
- Improved Cost Accuracy : Create a direct correlation between resource consumption and cost distribution
- Defensible Allocation Model : Support cost allocations with concrete usage data, making it easier to justify charge-back models
- Flexible Metric Support : Use any measurable metric (API calls, compute usage, storage operations) to drive allocation decisions

Before you begin

The file used for uploading your telemetry data should be a CSV file with the following required fields:

- Date: The time stamp for the metric measurement
- Category: Maps to your business dimension category
- Value: The metric measurement (e.g., number_of_api_requests, compute_hours)

The following example displays a CSV file format.

| Date | Category | Number of API requests |
| --- | --- | --- |
| 2025-01-01 | Team A | 15000 |
| 2025-01-01 | Team B | 8500 |
| 2025-01-01 | Team C | 12000 |

Using Telemetry in Cost Sharing

Follow the steps below to use Telemetry and consumption based allocations:

1. Select Organize/Cost Sharing in the left-hand navigation Pane
1. Select the New Allocation button
1. Select a Dimension in the New Allocation modal dialog and then select the Create button
1. Select the Telemetry Data tab
1. Select the Upload Telemetry File button and upload the CSV file
1. The CSV file will appear in the Telemetry table in the Telemetry Data tab
1. Select the Rules tab
1. Select the New Rule button
1. Select Telemetry / Consumption in the Allocation Method drop down
1. Select at least one option in the Source (from) list
1. The destination values appear disabled because the destination values are defined in the CSV that was uploaded
1. Save your Allocation Rule

The system will automatically compute allocation ratios based on your telemetry data and apply them to your shared costs.

Best Practices

Follow the best practices in Telemetry as below:

- Ensure your telemetry data covers the same time period as your cost allocation periods.
- Validate that your Category field values align with your existing business dimension categories.
- Regular updates to telemetry data will provide the most accurate cost distribution.
- Consider seasonality and usage patterns when selecting appropriate metrics for allocation.

---

## Cost Sharing for Reports and Dashboards

<!-- sub-header -->
- **breadcrumb:** Setup > Sharing Cost in Cloudability > Cost Sharing for Reports and Dashboards
- **source_path:** SSVCLNQ/product/cost-sharing-for-reports-and-dashboards.html
- **original_file:** cloudability-cost-sharing-reports-dashboards.md
- **images:**
  - 03-media/apptio-cloudability-standard/costsharing14.png
  - 03-media/apptio-cloudability-standard/costsharing15.png
  - 03-media/apptio-cloudability-standard/costsharing16.png
  - 03-media/apptio-cloudability-standard/costsharing1.png
  - 03-media/apptio-cloudability-standard/costsharing2.png
  - 03-media/apptio-cloudability-standard/costsharing3.png
  - 03-media/apptio-cloudability-standard/costsharing4.png
  - 03-media/apptio-cloudability-standard/costsharing5.png
  - 03-media/apptio-cloudability-standard/costsharing6.png
  - 03-media/apptio-cloudability-standard/costsharing7.png
  - 03-media/apptio-cloudability-standard/costsharing8.png
  - 03-media/apptio-cloudability-standard/costsharing10.png
  - 03-media/apptio-cloudability-standard/costsharing11.png
  - 03-media/apptio-cloudability-standard/costsharing12.png
  - 03-media/apptio-cloudability-standard/costsharing13.png

## Cost Sharing for Reports and Dashboards

### Overview

A new Cost Sharing toggle in the Cloudability Reports and Dashboard Widget Editor lets users generate data visualizations from report data with allocated (shared) costs applied. When enabled on a report or widget, results reflect allocated costs according to rules configured in Cloudability → Cost Sharing .

1. Open any report or widget editor.
1. Look for the Cost Sharing button in the header section.
1. Toggle the button to see your data with allocated costs.
1. Explore the new Cost Type and Allocation Source measures.
1. Save your widget and watch for the allocation badge on the title.

- Users can toggle Cost Sharing on/off per report or supporting widget.
- Previewing or saving a report or widget shows how data changes with Cost Sharing applied.
- Additional measures are now available which are only supported when Cost Sharing is enabled.

- Allocation rules are created and managed in the Cost Sharing feature.
- Rules apply only to Business Dimensions . (Non-business dimensions are not allocation targets.)

- Each supported widget type has a Cost Sharing toggle (Applied / Not Applied) in the header portion of the Create/Edit report and widget drawer.
- Toggling updates the query parameters used for Widget preview and save.
- The widget title displays an allocation badge when Cost Sharing is applied, so users can see at a glance that allocation rules affected the result set.
- Business Dimensions that have allocations applied to them show an allocation icon in all dimension selection components.

Measures Available with Cost Sharing

When Cost Sharing is Applied , the following new measures are now supported:

- Cost Type Indicates whether a dimension value has Direct or Shared cost.
- Allocation Source Breaks down where shared costs are attributed across business dimensions.

Dimension & Metric Support

- Some dimensions/metrics are supported only when Cost Sharing is Applied .
- Conversely, others are not supported in that state.

Behavior in the editor:

- Supported items remain selectable and usable.
- Unsupported items are: Marked with an error icon if previously selected and the user toggles Cost Sharing into a state where they’re invalid. Disabled in selectors to prevent new selection.

Preview/Save Request Sanitization

To prevent backend errors when Cost Sharing is toggled:

- On Preview or Save , any unsupported dimensions/metrics/filters (given the current toggle state) are removed from the request .
- This avoids failed requests due to invalid combinations and ensures the visualization renders successfully with supported fields.
- A user is notified on creation of Report or Dashboard Widget of the unsupported measures that have been removed in the process of saving.

Report Creation from Chart Widget

- A Chart Widget tooltip can navigate a user to a Report. In Widget Preview, we ensure only supported measures are included in the Report generated from Chart Widget data.

Filters

- Filters cannot target unsupported dimensions.
- If a user previously set such a filter and then toggles to an unsupported state: The filter shows an error icon in the editor. Unselected options are disabled. The filter is omitted from Preview/Save requests.

Validation & Notifications

- Reports require at least one dimension and one metric .
- If toggling Cost Sharing makes the configuration invalid (e.g., the sole dimension becomes unsupported), the user cannot produce a valid report. The UI shows a toast error notification explaining the configuration is unsupported with the current Cost Sharing state.

If a user is attempting to use the new ‘Allocation Source’ measure, the supported config for this request is to include with ‘Allocation Source’ at least one Business Dimension, and one other dimension.

- The UI shows a toast error notification explaining the configuration is unsupported if these conditions are not met.

State Persistence Rules

- While editing, the UI retains unsupported selections visually (marked with errors) so users can quickly toggle Cost Sharing on/off and compare results with the same intended configuration .
- On Save : Unsupported items are not persisted to the widget definition (because such a configuration cannot produce a valid report). Users keep the ability to toggle and preview while editing, but saved widgets never include invalid fields.

Cost Sharing in Reports

- All functionality is consistent across CLDY Reports and Dashboards. Widgets can be configured with Cost Sharing applied directly from a Report and copied to a user dashboard.
- Reports and Widgets can be exported and shared using existing Report Export functionality.
- A Report with Cost Sharing applied can also be subscribed to via the Report subscription drawer.
- A Report can be copied to Dashboard, persisting the Shared Cost value applied in the created widget.

Summary of Expected User Experience

1. User opens a widget, chooses dimensions/metrics, and optionally enables Cost Sharing .
1. Editor shows: Allocation icons on applicable Business Dimensions. Error icons on any fields that become unsupported when toggling the Cost Sharing state.
1. On Preview/Save: Unsupported fields/filters are automatically removed from the request. If removal makes the configuration invalid, an error toast informs the user.
1. After saving: The widget title shows an allocation badge if Cost Sharing is applied. The saved widget contains only supported fields for its Cost Sharing state.

Example Widgets:

1. Table showing the Business Dimension w/ allocated rule applied and the Allocation Category of this metric’s values:

Stacked Bar Chart showing the Cost Type of the values of a Business Dimension w/ allocated rule applied, stacked, showing cost(total) and cost(amortized) metrics:

Comparison of two Pie Charts rending the same Business Dimension, showing how the cost(total) metric varies when shared cost is applied or not applied:

![costsharing13](../images/costsharing13.png)

---
