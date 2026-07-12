---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Business Metrics in Cloudability"
breadcrumb:
  - "Setup"
  - "Organize Your Cloud Spend"
  - "Business mapping"
  - "Business Metrics in Cloudability"
source_path: "SSVCLNQ/admin/business-metrics.html"
images:
  - "03-media/apptio-cloudability-standard/business-mappings-new1.png"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Business Metrics in Cloudability

Overview

Business Metrics allow you to organize your cloud infrastructure to match your business needs. These custom metrics enable you to create meaningful reports that align with your organization's specific financial and operational requirements.

What are Business Metrics?

Business Metrics are customizable financial calculations that you can define in Cloudability to track specific aspects of your cloud spending. Unlike standard metrics, Business Metrics allow you to:

- Create custom formulas using existing cost data
- Apply conditional logic based on dimensions like vendor, service, or account
- Transform raw cloud cost data into business-relevant financial metrics
- Set specific conditions for when metrics should be applied

Creating a Business Metric (using Cloudability UI)

To create a business metric, follow the steps below:

1. Navigate to the Business Mapping section.
1. Select the Metrics tab.
1. Click the New Business Metric button.
1. Enter a meaningful name for your metric.
1. Choose the value format (Currency or Number).
1. Set up the metric definition using either: Default Value: A simple value or metric reference Fixed Value Metric Scenario: Standard cost per employee for chargeback Metric Name: "Cost Per Employee" Type: Default Value Value: 150 Usage: Allocate $150 per employee per month for cloud infrastructure Metric Reference Calculate cost efficiency ratio Metric Name: "Cost Efficiency Ratio" Type: Default Value Formula: Total_Cost / Total_Usage_Hours Where: Total_Cost = Sum of all cloud costs Total_Usage_Hours = Sum of instance hours Prematch Expression: Conditions that determine when the metric applies Scenario: Different cost allocation rates for different environments Metric Name: "Environment Cost Multiplier" Type: Prematch Expression Prematch Expression 1: IF tag:Environment = "Production" THEN Multiplier = 1.0 Prematch Expression 2: IF tag:Environment = "Staging" THEN Multiplier = 0.5 Prematch Expression 3: IF tag:Environment = "Development" THEN Multiplier = 0.3 Default: Multiplier = 0.1

Defining Your Metric Logic

Business Metrics use statements to define their behavior. Each statement consists of:

1. Match Expression: Conditions that determine when the statement applies Example: DIMENSION['vendor'] == 'GCP' Example: DIMENSION['date'] >= '2021-12-01' && DIMENSION['date'] < '2026-12-01'
1. Value Expression: The calculation to perform when conditions match Example: METRIC['bytes_transferred'] Example: METRIC['unblended_cost'] Example: {Cost (Adjusted Amortized)} * 0.83
1. 

Multiple statements can be created for a single metric, and they will be evaluated in the order they appear in the list.

Using Business Metrics in Reports

Once created, your Business Metrics can be used in reports just like any standard metric:

1. Create or edit a report.
1. Add your custom Business Metric to the report.
1. Combine with dimensions like ATUM mappings, vendor, or service name.

Common Use Cases

- Cost Normalization: Create metrics that normalize costs across different cloud vendors
- Internal Pricing: Implement custom pricing models for internal chargeback
- Budget Tracking: Track spending against predefined budgets
- Savings Calculations: Calculate realized or potential savings from optimization efforts
- Custom Amortization: Define your own amortization rules for reserved instances or savings plans
- Unit Economics: Calculate cost per user, transaction or user to understand your economics better

Advanced Features

- Use mathematical operators (+, -, *, /) to create complex formulas
- Reference existing metrics using the {} syntax
- Apply conditional logic using && (AND) and || (OR) operators
- Filter based on specific dimension values like vendor, service name, or region

How do Business Metrics work with Business Mappings?

Business Metrics are crafted using Business Mapping statements that leverage a combination of existing billing data and customer-provided data. Users can create custom metrics related to Cloud billing concepts, populated with the specific values from the logic that best fits their reporting needs in the context of their businesses.

Evaluated at ingestion

When Cloudability ingests the detailed billing data from cloud vendors, we evaluate each cost line item against the Business Mapping statements for your configured Business Metrics. For those of you with a programming background, you can think of the list of statements as similar to a case statement. As soon as there is a match, then the name of the statement itself is evaluated and the resultant value is arithmetically calculated and used to populate the Business Metric for that item. This custom metric name can simply be a meaningful string that you provide. When cloud vendors post new billing data, we'll automatically pick up any changes or additions you make to your Business Mapping statements. To have historic months reflect the updated rules, you can reach out to support or your TAM for this to be actioned.

The custom metric name

Every Business Metric you create requires a name. Think deeply about the business context that you're trying to share and choose a name that people will quickly make sense of. You're giving a name to the custom metric as it will appear in Cloudability reports and dashboards.

The custom metric format

As well as a name, you must decide if this custom metric will surface data formatted as currency or a regular number. The use case driving this custom metric will help you decide on the appropriate format.

For example: If your use case is to provide a surcharge for management fees, then the custom metric format will be currency.

The default value

Once you've decided on a name and a format, you need to set a default value. This is the value the Business Metric will inherit if none of the statements you declare match.

For example: an option here would be to use the cost amount already in the billing data. As you build your Business Metrics, each use case will help you with determining a good default value.

It's about matching with statements

Every statement has two components:

An expression for what to match against. This expression can involve complex boolean logic, a time frame, and has a very comprehensive list of operators that can be applied against all the important attributes of the cost items.

An expression to evaluate, resulting in the value for the Business Metric if the criteria in #1 happens to match.

Below is a simple example:

```
"statements": [{
	"matchExpression": "DIMENSION['vendor'] == 'Amazon'
		|| DIMENSION['vendor'] == 'Azure' ",
	"valueExpression": "METRIC['unblended_cost'] * 1.15"
}]
```

Why do you use business metrics?

Use cases

Business Metrics can help address several use cases where, in addition to Cloudability 's native metrics, you may need custom metrics for your business' reporting requirements. Below are examples of a few of the more popular customer use cases:

| Unit Economics | Also known as Cost per X. A customer can contextualize their Cloud spend as a unit cost in a single in-app metric. For example: cost per ride, cost per active user, cost per subscription, etc. |
| --- | --- |
| Unit Economics | Also known as Cost per X. A customer can contextualize their Cloud spend as a unit cost in a single in-app metric. For example: cost per ride, cost per active user, cost per subscription, etc. |
| KPI Driven Cost | Cost in the context of a business-specific KPI. For example, a customer can contextualize cost in terms of full-time engineers (cost in FTEs) to understand their cloud spend in terms of the number of dev ops engineers needed to support a deployed application. |
| Surcharge/ Markup | A surcharge or markup for Cloud spend can be built in and surface costs inclusive of management fees, license costs, or other surcharges using a single in-app metric. |

The rules engine that drives this feature is equipped with sophisticated logic capabilities, and individual rules can be based on pretty much all of the important attributes that vendors supply with the billing and usage data. These attributes include vendor-supplied dimensions and metrics like cost tags, account names, Unblended Cost but also include enhanced dimensions and metrics provided by Cloudability like Usage Family, Lease Type, and Adjusted Cost.

Creating a Business Metric (using Cloudability API)

Business Metrics can be created using API by leveraging the Business Mapping expression language. Rules are defined through JSON-formatted expressions and statements which are arithmetically evaluated, resulting in a custom metric and corresponding value.

Working with Business Metrics

From the Business Mappings End Point , you can see a feature overview, including the Business Metrics endpoints with corresponding descriptions and examples available for you to work with Business Metrics. Additionally, you'll find templates that you can use to help kickstart your custom metric setup and other helpful resources.

You can set up a maximum of five Business Metrics.

Below are quick references and examples for (i) listing a Business Metric you've already created, (ii) creating a new Business Metric, and (iii) updating an existing Business Metric.

Listing Business Metric

```
 curl -X GET 'https://api.cloudability.com/v3/business-mappings/metrics/' -u '[auth_token]:' 
```

Create a Business Metric

```
 curl -X POST 'https://api.cloudability.com/v3/internal/business-mappings/metrics/' \
  -H 'Content-Type: application/json' \
  -u '[auth_token]:' \
  -d @- >> EOF
{
  "name": "Cost (Surcharge)",
  "numberFormat": "number",
  "defaultValueExpression": "METRIC['unblended_cost']",
  "statements": [
    {
      "matchExpression": "DIMENSION['vendor'] == 'Amazon' || DIMENSION['vendor'] == 'Azure' ",
      "valueExpression": "METRIC['unblended_cost'] * 1.15"
    }
  ]
}
EOF 
```

Expected Output

```
{
  "result": {
    "name": "Cost (Surcharge)",
    "index": 1,
    "kind": "BUSINESS_METRIC",
    "defaultValue": "METRIC['unblended_cost']",
    "numberFormat": "number",
    "updatedAt": "2025-11-12T07:29:27.182Z",
    "statements": [
      {
        "matchExpression": "DIMENSION['vendor'] == 'Amazon' || DIMENSION['vendor'] == 'Azure' ",
        "valueExpression": "METRIC['unblended_cost'] * 1.15"
      }
    ]
  }
}
```

Update a Business Metric

```
curl -X PUT 'https://api.cloudability.com/v3/internal/business-mappings/1/metrics/' \
  -H 'Content-Type: application/json' \
  -u '[auth_token]:' \
  -d @- >> EOF
{
  "name": "Cost (Surcharge)",
  "numberFormat": "number",
  "defaultValueExpression": "METRIC['unblended_cost']",
  "statements": [
    {
      "matchExpression": "DIMENSION['vendor'] == 'Amazon' || DIMENSION['vendor'] == 'Azure' ",
      "valueExpression": "METRIC['unblended_cost'] * 1.25"
    }
  ]
}
EOF
```

Expected Output

```
 {
  "result": {
    "name": "Cost (Surcharge)",
    "index": 1,
    "kind": "BUSINESS_METRIC",
    "defaultValue": "METRIC['unblended_cost']",
    "numberFormat": "number",
    "updatedAt": "2025-11-12T07:32:16.858Z",
    "statements": [
      {
        "matchExpression": "DIMENSION['vendor'] == 'Amazon' || DIMENSION['vendor'] == 'Azure' ",
        "valueExpression": "METRIC['unblended_cost'] * 1.25"
      }
    ]
  }
} 
```

Operators

Using the Business Mappings expression language, you'll have a vast array of operators to test the logic of your statements. Some examples of operators available for you to use include greater than which can be handy for testing against things like dates. Choose an operator which makes your statement as straightforward as possible. By using our API, you'll have additional options, including regular expressions.

For example, timeboxing a business metric value between two dates :

```
 {
  "name": "Cost (Surcharge)",
  "numberFormat": "number",
  "defaultValueExpression": "METRIC['unblended_cost']",
  "statements": [
    {
      "matchExpression": "DIMENSION['date'] >= '2019-01-01T00:00' && DIMENSION['date'] <= '2019-01-31T23:59'",
      "valueExpression": "METRIC['unblended_cost'] * 1.25"
    }
  ]
} 
```

Boolean Logic

Within an individual statement, you can group expressions together using OR operators and combine with AND operators to get the exact logical outcome to match your business rules.

Below is a very basic example:

```
{
  "name": "Cost (in FTEs)",
  "numberFormat": "number",
  "defaultValueExpression": "METRIC['unblended_cost']",
  "statements": [
    {
      "matchExpression": "DIMENSION['date'] >= '2019-01-01T00:00:00' && DIMENSION['date'] <= '2019-01-31T23:59:59' && (DIMENSION['transaction_type'] == 'usage' || DIMENSION['transaction_type'] == 'recurring')",
      "valueExpression": "METRIC['unblended_cost']  / 115000"
    }
  ]
}

```

For additional guidance on using Business Metrics effectively, please contact your account representative or submit a support ticket.
