---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Business Mappings End Point"
breadcrumb:
  - "Cloudability API"
  - "Business Mappings End Point"
source_path: "SSVCLNQ/api-v3/business_mappings_endpoint.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Business Mappings End Point

Summary

Business Mapping is an activity that allows you to map your cloud cost and usage to custom dimensions and custom metrics that are important to report on within your organization.

Business Mapping represents an Admin feature within Cloudability that delivers a special category of 'synthetic' dimensions called Business Dimensions and synthetic metrics called Business Metrics which can be utilized by all users throughout the platform.

Business Dimensions provide a means to allocate your cloud cost and usage data beyond what you can with native cloud mechanisms. You can think of them as having similar properties to vendor tags but with far more flexibility - indeed there's a good chance that some of your Business Dimensions will partially rely on vendor tags.

The native Cloudability metrics are a set of useful, powerful measures for users to gain insight into their cloud spend and efficiency. However, for bespoke customer use cases, users need to contextualize and customize Cloud spending against business specific KPIs to visualise trends; this will enable stakeholders to make decisions based on data that is meaningful to them and their business. Business Metrics are crafted using Business Mapping statements that leverage a combination of existing billing data and customer provided data

The Business Mappings expression language has a remarkable amount of inbuilt dexterity and therefore our customers will find a myriad of uses for Business Dimensions and Business Metrics.

For more information about Business Dimensions please see this page .

For more information about Business Metrics please see this page .

How business mapping works

When Cloudability ingests the detailed billing data from cloud vendors we evaluate each and every line item against the " matchExpressions " within the Business Mapping for each configured Business Dimension and Business Metric. You can think of the list of statements as similar to a case statement, as soon as there is a match then the " valueExpression " attribute is evaluated and the resultant value used to populate the Business Dimension or Business Metric for that item. This expression could simply be a string or involve a range of operations based on other attributes of the line item itself (such as it's vendor tag values).

More information about Business Dimensions and Business Metrics

We have plenty of material to help you make the most out of Business Mapping.

- Read more about the structure of a Business Mapping here
- Read more about the Business Mappings expression language that backs Business Dimensions and Business Metrics here .

End point particulars

/business-mappings for all RESTful CRUD interactions

Filtering operators quick reference

| Argument | Description |
| --- | --- |
| == | equals |
| != | not equals |
| > | greater than |
| < | less than |
| >= | greater than or equal to |
| <= | less than or equal to |
| CONTAINS | contains |
| !CONTAINS | does not contain |
| EXISTS | check for existence |
| !EXISTS | check for non-existence |

For additional filtering operators and corresponding examples, see business_mapping_expression.html#business_mapping_expression__operators .

Business Dimensions

Popular Uses

- Implementing complex grouping rules for allocation
- Allocating untaggable resources
- Fall back mechanisms allowing for issues with your tagging implementation
- Categorizing shared costs such as support charges
- Compliance - For example identify each cost item as compliant or not based on attributes like tags, location or type

The Business Dimension Object

name ( string ): Name for the Business Dimension

index ( integer ): An integer value between 1 and 10 representing the ID for the Business Dimension.

kind ( string ): The kind attribute represents the declaration that we are defining a Business Metric versus a Business Dimension for our Business Mapping construct

defaultValue ( string ): the string value used. If there are no rule matches then this is the fall back value. optionally: defaultValueExpression ( string ): the string expression used If no rule matches then take the value resolved by this expression as the fall back value.

statements ( array ): List of statement objects. Each billing item will run through the statements until a hit on matchExpression

matchExpression ( string ): The expression to match against

valueExpression ( string ): If matched then take the value resolved by this expression.

Business Dimension Object JSON

```
{
  "result":[{
      "name": "Business Unit",
      "index": 1,
      "kind": "BUSINESS_DIMENSION",
      "defaultValue": "Unallocated",
      "statements": [
        {
           "matchExpression": "EXISTS TAG['Business_Unit']",
           "valueExpression": "TAG['Business_Unit']"
        },
        {
          "matchExpression": "DIMENSION['vendor_account_identifier'] == '999999999999'",
          "valueExpression": "'Mergers and Acquisitions'"
        },
        {
          "matchExpression": "DIMENSION['vendor_account_identifier'] == '888888888888'",
          "valueExpression": "'Consulting Services'"
        },
        {
          "matchExpression": "DIMENSION['vendor_account_identifier'] == '777777777777'",
          "valueExpression": "'Shared Services'"
        }
    ]
  }]
}
```

Create a Business Dimension

```
curl -X POST https://api.cloudability.com/v3/business-mappings \\
     -H 'Content-Type: application/json' \\
     -u ‘[auth_token]:’ \\
     -d @- << EOF
{
  "name": "Business Unit",
  "defaultValue": "Unallocated",
  "statements": [
    {
      "matchExpression": "EXISTS TAG['Business_Unit']",
      "valueExpression": "TAG['Business_Unit']"
    },
    {
      "matchExpression": "DIMENSION['vendor_account_identifier'] == '999999999999'",
      "valueExpression": "'Mergers and Acquisitions'"
    }
  ]
}
EOF
```

Retrieve a Business Dimension

```
 curl https://api.cloudability.com/v3/business-mappings/1 \\
     -u ‘[auth_token]:’
```

Update a Business Dimension

```
curl -X PUT https://api.cloudability.com/v3/business-mappings/1 \\
     -H 'Content-Type: application/json' \\
     -u ‘[auth_token]:’ \\
     -d @- << EOF
{
  "name": "Business Unit",
  "defaultValue": "Shared Services",
  "statements": [
    {
      "matchExpression": "EXISTS TAG['Business_Unit']",
      "valueExpression": "TAG['Business_Unit']"
    },
    {
      "matchExpression": "DIMENSION['vendor_account_identifier'] == '999999999999'",
      "valueExpression": "'Mergers and Acquisitions'"
    },
    {
      "matchExpression": "DIMENSION['vendor_account_identifier'] == '777777777777'",
      "valueExpression": "'Finance Operations'"
    }
  ]
}
EOF
```

Delete a Business Dimension

```
curl -X DELETE https://api.cloudability.com/v3/business-mappings/1 \\
     -u ‘[auth_token]:’
```

List All Business Dimensions

```
curl https://api.cloudability.com/v3/business-mappings/dimensions \\
     -u ‘[auth_token]:’
```

Business Metrics

Popular Uses

Business Metrics can help address a number of use cases where, in addition to Cloudability 's native metrics, you may need custom metrics for your business' reporting requirements; below are examples of a few of the more popular customer use cases:

Unit Economics

also known as "Cost per X". a customer can contextualize their Cloud spend as a unit cost in a single in-app metric. for example: "cost per ride share", "cost per active user", "cost per subscription", etc...

KPI Driven Cost

cost in the context of a business specific KPI. for example: a customer can contextualize "cost" in terms of full time engineers (cost in FTEs) to understand their Cloud spend in terms of the number of DevOps Engineers needed to support a deployed application.

Surcharge / Markup

a surcharge or markup for Cloud spend can be built in and surface costs inclusive of management fees, license costs or other surcharges using a single in-app metric.

The Business Metric Object

name ( string ): The name field indicates the unique identifier for the Business Metric values generated by the Business Mapping statement rules you have defined.

numberFormat ( string ): In addition to a name, the custom metric you create will be evaluated to a number and surfaced as " currency " or a regular decimal " number ".

index ( integer ): An integer value representing the ID for the Business Metric

kind ( string ): The kind attribute represents the declaration that we are defining a Business Metric versus a Business Dimension for our Business Mapping construct

defaultValueExpression ( string ): If there are no matches for the statements defined, this is the fall back value

preMatchExpression ( string ): The preMatchExpression represents a centralized/global expression which is evaluated before all other defined expressions contained within statements section; It can be left empty (without a defined expression) when creating a Business Metric; if left empty, it will be omitted from the response.

statements ( array ): List of statements. Each billing item will be evaluated against the statements until a match is found for the defined matchExpression

matchExpression ( string ): The expression to match against

valueExpression ( string ): If match is found then take the value resolved by this expression.

Business Metric Object JSON

```
{
  "result": [{
    "index": 1,
    "name": "Cost (Storage Backup 10% Surcharge)",
    "kind": "BUSINESS_METRIC",
    "numberFormat": "currency",
    "preMatchExpression": "(DIMENSION['vendor'] == 'amazon' || DIMENSION['vendor'] == 'azure') && DIMENSION['usage_family'] == 'storage'",
    "defaultValueExpression": "METRIC['unblended_cost']",
    "statements": [{
      "matchExpression": "DIMENSION['invoice_date'] == '2019-09-01' && DIMENSION['transaction_type'] == 'usage' && (DIMENSION['usage_type'] CONTAINS 'backup' || DIMENSION['usage_type'] CONTAINS 'snapshot')",
      "valueExpression": "METRIC['unblended_cost'] * 1.10"
    },
    {
      "matchExpression": "DIMENSION['invoice_date'] == '2019-10-01' && DIMENSION['transaction_type'] == 'usage' && (DIMENSION['usage_type'] CONTAINS 'backup' || DIMENSION['usage_type'] CONTAINS 'snapshot')",
      "valueExpression": "METRIC['unblended_cost'] * 1.10"
    },
    {
      "matchExpression": "DIMENSION['invoice_date'] == '2019-11-01' && DIMENSION['transaction_type'] == 'usage' && (DIMENSION['usage_type'] CONTAINS 'backup' || DIMENSION['usage_type'] CONTAINS 'snapshot')",
      "valueExpression": "METRIC['unblended_cost'] * 1.10"
    }]
  }]
}
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

Retrieve a Business Metric

```
 curl -X GET 'https://api.cloudability.com/v3/internal/business-mappings/1/metrics' -u ‘[auth_token]:’
```

Update Business Metric

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

Delete Business Metric

```
curl -X DELETE 'https://api.cloudability.com/v3/internal/business-mappings/1/metrics' -u ‘[auth_token]:’
```

List Business Metric

```
 curl -X GET 'https://api.cloudability.com/v3/business-mappings/metrics/' -u '[auth_token]:' 
```
