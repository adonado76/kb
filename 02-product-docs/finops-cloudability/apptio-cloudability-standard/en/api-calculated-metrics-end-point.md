---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Calculated Metrics End Point"
breadcrumb:
  - "Cloudability API"
  - "Calculated Metrics End Point"
source_path: "SSVCLNQ/api-v3/calculated_metrics_end_point.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Calculated Metrics End Point

Summary

Calculated Metrics introduce a new, reusable metric within Cloudability Dashboards and Reports. This capability enables customers to define custom metrics using cloud cost data, utilization metrics, constants, and operators to create standardized business KPIs and unit economics measurements.

This feature empowers organizations to measure cloud efficiency using metrics tailored to their business needs, such as application unit economics, shared service allocation metrics, utilization-to-cost ratio metrics, time-window based optimization analysis, and operational efficiency measurements.

For organizations practicing FinOps and cloud financial management, Calculated Metrics provide a scalable method to standardize reporting and improve decision-making around cloud spend and operational efficiency.

How Calculated Metrics Work

Calculated Metrics are evaluated dynamically using formulas defined by users. These formulas can combine native cloud cost metrics, utilization metrics, constants, and arithmetic operators.

Users create and manage Calculated Metrics through a centralized management hub located within the Business Mappings area. Once defined, Calculated Metrics become reusable across Cloudability Dashboards and Cloudability Reports .

This ensures that all stakeholders across the organization use the same KPI definitions and business logic.

End point particulars

/v3/calculated-metrics for Calculated Metric CRUD operations

The Calculated Metric Object

name ( string, required ): Unique name for the Calculated Metric within your organization. Cannot match existing base measure names.

expression ( string, required ): The mathematical formula used to calculate the metric value. Supports operators: +, -, *, / and parentheses.

source_type ( string, required ): The data source on which the metric is built. Must be either cost or usage . All measures in the expression must match this type.

description ( string, optional ): Human-readable description explaining the purpose and usage of the metric.

number_format ( string, optional ): Display format for your metric. Options: number (default), amount , or percentage .

Create Calculated Metric

Create a new Calculated Metric in your organization.

```
curl 'https://api.cloudability.com/v3/calculated-metrics' \
  -X POST \
  -H 'accept: application/json' \
  -H 'authorization: {{JWT_TOKEN}}' \
  -H 'content-type: application/json' \
  --data-raw '{
    "name": "50 Percent Discount",
    "description": "Applies discount to unblended cost",
    "expression": "unblended_cost*0.8",
    "source_type": "cost",
    "number_format": "amount"
  }'

```

Expected Output

```
{
    "result": {
        "id": 431,
        "organization_id": 108194,
        "name": "50 Percent Discount",
        "description": "Applies discount to unblended cost",
        "number_format": "amount",
        "source_type": "cost",
        "expression": "unblended_cost*0.8",
        "created_by": "Vidyashri Hugar",
        "updated_by": "Vidyashri Hugar",
        "created_at": "2026-05-20T09:59:47.652470726Z",
        "updated_at": "2026-05-20T09:59:47.652470726Z"
    }
}
```

Response Code: 201 (Created)

Error Responses:

- 400 - Validation error (duplicate name, invalid expression, empty required fields, invalid source_type, etc.)
- 403 - Permission denied or feature not enabled
- 502 - Service failure

List All Calculated Metrics

Retrieve a list of all Calculated Metrics in your organization.

```
curl 'https://api.cloudability.com/v3/calculated-metrics' \
  -H 'accept: application/json' \
  -H 'authorization: {{JWT_TOKEN}}'
```

Expected Output

```
{
  "result": [
    {
      "id": 391,
      "organization_id": 108194,
      "name": "CPU Util Buffer",
      "description": "CPU Util Buffer description",
      "number_format": "amount",
      "source_type": "usage",
      "expression": "(avg_cpu_utilization*1.1)",
      "created_by": "Madhavi H N",
      "updated_by": "Vidyashri Hugar",
      "created_at": "2026-05-08T11:30:30Z",
      "updated_at": "2026-05-11T11:29:57Z"
    },
    {
      "id": 405,
      "organization_id": 108194,
      "name": "20 Percent Discount",
      "description": "20 Percent Discount on Cost (Total)",
      "number_format": "amount",
      "source_type": "cost",
      "expression": "(unblended_cost*0.8)",
      "created_by": "Komal Dhuri",
      "updated_by": "Komal Dhuri",
      "created_at": "2026-05-13T09:19:18Z",
      "updated_at": "2026-05-13T09:19:18Z"
    }
  ]
}
```

Response Code: 200

Returns an array of all Calculated Metrics. The array will be empty if no metrics exist.

Get Calculated Metric by ID

Retrieve details of a specific Calculated Metric using its ID.

```
curl 'https://api.cloudability.com/v3/calculated-metrics/{{METRIC_ID}}' \
  -H 'accept: application/json' \
  -H 'authorization: {{JWT_TOKEN}}'
```

Expected Output

```
{
  "result": {
      "id": 391,
      "organization_id": 108194,
      "name": "CPU Util Buffer",
      "description": "CPU Util Buffer description",
      "number_format": "amount",
      "source_type": "usage",
      "expression": "(avg_cpu_utilization*1.1)",
      "created_by": "Madhavi H N",
      "updated_by": "Vidyashri Hugar",
      "created_at": "2026-05-08T11:30:30Z",
      "updated_at": "2026-05-11T11:29:57Z"
    }
}
```

Response Code: 200

Error Responses:

- 404 - Calculated metric not found
- 400 - Invalid ID format
- 403 - Permission denied

Update Calculated Metric

```
curl 'https://api.cloudability.com/v3/calculated-metrics/{{METRIC_ID}}' \
  -X PUT \
  -H 'accept: application/json' \
  -H 'authorization: {{JWT_TOKEN}}' \
  -H 'content-type: application/json' \
  --data-raw '{
    "description": "Updated description",
    "number_format": "number"
  }'
```

Expected Output

```
{
  "result": {
      "id": 391,
      "organization_id": 108194,
      "name": "CPU Util Buffer",
      "description": "Updated description",
      "number_format": "number",
      "source_type": "usage",
      "expression": "(avg_cpu_utilization*1.1)",
      "created_by": "Madhavi H N",
      "updated_by": "Vidyashri Hugar",
      "created_at": "2026-05-08T11:30:30Z",
      "updated_at": "2026-05-11T11:29:57Z"
    }
}
```

Response Code: 200

The response reflects the merged state with the updated_at timestamp advanced to the current time.

Error Responses:

- 404 - Calculated metric not found
- 400 - Invalid expression, duplicate name, or validation error
- 403 - Permission denied (e.g., attempting to update another user's metric without full access)

Delete Calculated Metric

Delete a Calculated Metric. Important: A metric can only be deleted if it is not currently referenced by any saved reports, dashboards, or widgets. If the metric is in use, you must remove those references before deletion.

```
curl 'https://api.cloudability.com/v3/calculated-metrics/{{METRIC_ID}}' \
  -X DELETE \
  -H 'accept: application/json' \
  -H 'authorization: {{JWT_TOKEN}}'
```

Response Code: 204 (No Content)

After successful deletion, the response body is empty. Attempting to retrieve the deleted metric will return a 404 error.

Error Responses:

- 400 - Cannot delete: metric is currently used in reports or dashboards. Error message: "cannot delete calculated metric: it is currently used in reports or dashboards"
- 404 - Calculated metric not found
- 403 - Permission denied

Validation Rules

The following validation rules apply when creating or updating Calculated Metrics:

- Name: Must be unique within the organization and cannot match existing base measure names. Cannot be empty.
- Expression: Must use valid operators (+, -, *, /) and valid measure names for your organization. Cannot be empty.
- Source Type: Required. Must be either "cost" or "usage". All measures in the expression must match the specified source_type.
- Number Format: Optional. Must be one of: "number" (default), "amount", or "percentage".
- Operators: Only arithmetic operators are allowed: +, -, *, /
- Parentheses: Must be properly balanced in expressions.
- Measure Names: Can contain letters, digits, and underscores. All referenced measures must exist and be valid for your organization.
- Decimals: Use period (.) for decimal numbers in expressions.

Permissions and Access Control

Calculated Metrics support three permission levels.

Full Access

Permission: CalculatedMetricsFeatureFullAccess

Users can:

- View calculated metrics
- Create calculated metrics
- Update calculated metrics

Own Edit Access

Permission: CalculatedMetricsFeatureOwnEditAccess

Users can:

- View all calculated metrics
- Create calculated metrics
- Update only metrics they created

View Only Access

Permission: CalculatedMetricsFeatureViewOnlyAccess

Users can:

- View calculated metrics
- View metric definitions
- Cannot create or edit metrics
