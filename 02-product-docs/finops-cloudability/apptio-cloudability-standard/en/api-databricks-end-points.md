---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Databricks End Points"
breadcrumb:
  - "Cloudability API"
  - "Databricks End Points"
source_path: "SSVCLNQ/api-v3/databricks_public_api.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Databricks End Points

Summary

These end point are used to manage Databricks integration within Cloudability that support the creation, updating and deletion of Databricks credentials within Cloudability.

With Cloudability being available in multiple regions, all references to api.cloudability.com in this API documentation should be referred to as mentioned in Getting started with Cloudability API V3 .

End Point Particulars

end point : /v3/vendors/databricks/accounts for RESTful CRUD interactions

end point : /v3/vendors/databricks/accounts?include=permissions&viewId=0

end point : /v3/vendors/databricks/accounts/<account_id>?include=permissions&viewId=0

end point : /v3/vendors/databricks/accounts/<account_id>?viewId=0

end point : /v3/vendors/databricks/accounts/<account_id>/verification?include=permissions,associatedAccounts&viewId=0

end point : /v3/vendors/databricks/template

end point : /v3/vendors/databricks/accounts/<account_id>/archive?viewId=0

end point : /v3/vendors/databricks/permissions/accounts/<account_id>

Parameters

- orgId (string) : Organisation Id
- accountId (string) : Databricks Account Id
- secret (string) - Secret created for the Service Principal User
- clientId (string) - Client Id created for the Service Principal User
- endpoint (string) - Databricks account endpoint
- workspace(string) - Workspace URL
- warehouseId(string) - Warehouse ID
- dependentCsp(string) - “AWS” | “GCP”
- activePaymentModel(string) - "Committed Contract" | "Pay as you go" (current active payment model)
- paymentModel(string) - "Committed Contract" | "Pay as you go"
- rateLimit (int) - This rate limit is fixed for the type of endpoints in Databricks

List Accounts

Example Request

```
curl 'https://api.cloudability.com/v3/vendors/databricks/accounts?viewId=0' \\ 
 -u ‘[auth_token]:’ 
```

```
{ 
"result": [ 
{ 
"id": "a11a1a1a-1a11-1aaa-11a1-a1111a11a11a", 
"vendorAccountName": "a11a1a1a-1a11-1aaa-11a1-a1111a11a11a", 
"vendorAccountId": "a11a1a1a-1a11-1aaa-11a1-a1111a11a11a", 
"vendorKey": "databricks", 
"verification": { 
"state": "verified", 
"lastVerificationAttemptedAt": "2026-02-09T10:14:20Z" 
}, 
"authorization": { 
"type": "databricks_user", 
"clientId": "b22222b2-b2b2-2222-b222-b2b22b2b2bb2", 
"subscriptionModel": "Direct", 
"dependentCsp": "AWS", 
"activePaymentModel": "Pay as you go", 
"contractDetails": [ 
{ 
"startDate": "2024-02-01", 
"endDate": "2024-03-31", 
"discount": 10, 
"paymentModel": "Committed Contract" 
}, 
{ 
"startDate": "2024-04-01", 
"endDate": "2024-04-30", 
"discount": 5, 
"paymentModel": "Committed Contract" 
}, 
{ 
"startDate": "2024-06-01", 
"endDate": "2024-10-31", 
"discount": 15, 
"paymentModel": "Committed Contract" 
}, 
{ 
"startDate": "2024-11-01", 
"endDate": "", 
"discount": 0, 
"paymentModel": "Pay as you go" 
} 
], 
"workspace": "workspace.cloud.databricks.com", 
"warehouseId": "1aa11111a111a11a" 
}, 
"createdAt": "2024-08-14T08:13:42Z", 
"consumerOrgId": "", 
"byodVendor": "ABSENT" 
} 
] 
} 
```

Create account

POST /v3/vendors/databricks/accounts?viewId=0

Example Request

```
curl -X POST 'https://api.cloudability.com/v3/vendors/databricks/accounts?viewId=0\\ 
-H 'Content-Type: application/json' \\ 
-u ‘[auth_token]:’ \\ 
-d @- << EOF 
{ 
"vendorAccountId": "a11a1a1a-1a11-1aaa-11a1-a1111a11a11a", 
"clientId": "b22222b2-b2b2-2222-b222-b2b22b2b2bb2", 
"secret": "secret", 
"workspace": "<Workspace-URL>", 
"warehouseId": "workspace.cloud.databricks.com", 
"subscriptionModel": "Direct", 
"dependentCsp": "AWS", 
"activePaymentModel": "Pay as you go", 
"contractDetails": [ 
{ 
"startDate": "2026-02-09", 
"endDate": null, 
"discount": null, 
"paymentModel": "Pay as you go" 
} 
], 
"type": "databricks_user" 
} 
```

Upon successful creation the API will return the credentials object.

Update account

PUT /v3/vendors/databricks/accounts/<account_id>?include=permissions&viewId=0

Example Request

```
curl -X PUT 'https://api.cloudability.com/v3/vendors/databricks/accounts/<account_id>?viewId=0\\ 
-H 'Content-Type: application/json' \\ 
-u ‘[auth_token]:’ \\ 
-d @- << EOF 
{ 
"vendorAccountId": "a11a1a1a-1a11-1aaa-11a1-a1111a11a11a", 
"clientId": "b22222b2-b2b2-2222-b222-b2b22b2b2bb2", 
"secret": "secret-2", 
"workspace": "<Workspace-URL>", 
"warehouseId": "workspace.cloud.databricks.com", 
"subscriptionModel": "Direct", 
"dependentCsp": "AWS", 
"activePaymentModel": "Pay as you go", 
"contractDetails": [ 
{ 
"startDate": "2026-02-09", 
"endDate": null, 
"discount": null, 
"paymentModel": "Pay as you go" 
} 
], 
"type": "databricks_user" 
} 
```

Retrieve Account

GET /v3/vendors/databricks/accounts/<account_id>?viewId=0

Example Request

```
curl 
'https://api.cloudability.com/v3/vendors/databricks/accounts/<account_id>’\\ 
-u ‘[auth_token]:’ 
```

Delete Credential for Account

DELETE /v3/vendors/databricks/accounts/<account_id>?viewId=0

Example Request

```
curl -X DELETE 
'https://api.cloudability.com/v3/vendors/databricks/accounts/<account_id>?viewId=0\\ 
-u ‘[auth_token]:’ 
```

Verify Credential for Account

POST v3/vendors/databricks/accounts/<account_id>/verification?include=permissions,associatedAccounts&viewId=0

Example Request

```
curl --X POST 
'https://api.cloudability.com/v3/vendors/databricks/accounts/<account_id>/verification?include=permissions,associatedAccounts&viewId=0’\\ 
-u ‘[auth_token]:’ 
```

Archive Account

POST /v3/vendors/databricks/accounts/<account_id>/archive?viewId=0

Example Request

```
curl --X POST 
'https://api.cloudability.com/v3/vendors/databricks/accounts/<account_id>archive?viewId=0’\\ 
-u ‘[auth_token]:’ 
```

Get Permissions for Account

GET /v3/vendors/databricks/permissions/accounts/<account_id>

Example Request

```
curl --X GET 
'https://api.cloudability.com/v3/vendors/databricks/permissions/accounts/<account_id>’ 
\\ 
-u ‘[auth_token]:’ 
```

Databricks Template - This API is used to get the template notebook.

Example Request

```
curl 'https://api.cloudability.com/v3/vendors/databricks/template' \\ 
 -u ‘[auth_token]:’ 
```

Example Response

```
{ 
"result": { 
"scripts": "{\n \"cells\": [\n {\n \"cell_type\": \"code\",\n \"execution_count\": 0,\n \"metadata\": {\n \"application/vnd.databricks.v1+cell\": {\n \"cellMetadata\": {\n \"byteLimit\": 2048000,\n \"rowLimit\": 10000\n },\n \"inputWidgets\": {},\n \"nuid\": \"84259o57-91oo-476d-80c2-oo558oo4d0oo\",\n \"showTitle\": false,\n \"title\": \"\"\n }\n },\n \"outputs\": [],\n \"source\": [\n \"spark.conf.set('spark.databricks.delta.schema.autoMerge.enabled', 'true')\"\n ]\n },\n {\n \"cell_type\": \"code\",\n \"execution_count\": 0,\n \"metadata\": {\n \"application/vnd.databricks.v1+cell\": {\n \"cellMetadata\": {},\n \"inputWidgets\": {},\n \"nuid\": \"o52oo419-o40o-490o-8240-ooo40747oo9o\",\n \"showTitle\": false,\n \"title\": \"\"\n }\n },\n \"outputs\": [],\n \"source\": [\n \"%sql\\n\",\n \"DESCRIBE system.billing.list_prices;\"\n ]\n },\n {\n \"cell_type\": \"code\",\n \"execution_count\": 0,\n \"metadata\": {\n \"application/vnd.databricks.v1+cell\": {\n \"cellMetadata\": {},\n \"inputWidgets\": {},\n \"nuid\": \"o4119o19-oo23-4o9o-o206-634o75324oo4\",\n \"showTitle\": false,\n \"title\": \"\"\n }\n },\n \"outputs\": [],\n \"source\": [\n \"%sql\\n\",\n \"DESCRIBE system.billing.usage;\"\n ]\n },\n {\n \"cell_type\": \"code\",\n \"execution_count\": 0,\n \"metadata\": {\n \"application/vnd.databricks.v1+cell\": {\n \"cellMetadata\": {},\n \"inputWidgets\": {},\n \"nuid\": \"468oo531-498o-41oo-oooo-o1o813oo6o14\",\n \"showTitle\": false,\n \"title\": \"\"\n }\n },\n \"outputs\": [],\n \"source\": [\n \"%sql\\n\",\n \"CREATE CATALOG IF NOT EXISTS billing_data;\"\n ]\n },\n {\n \"cell_type\": \"code\",\n \"execution_count\": 0,\n \"metadata\": {\n \"application/vnd.databricks.v1+cell\": {\n \"cellMetadata\": {},\n \"inputWidgets\": {},\n \"nuid\": \"2oo2o5o0-89o3-4ooo-o482-14o632oo6o1o\",\n \"showTitle\": false,\n \"title\": \"\"\n }\n },\n \"outputs\": [],\n \"source\": [\n \"%sql\\n\",\n \"CREATE SCHEMA IF NOT EXISTS billing_data.billing_data_schema;\"\n ]\n },\n {\n \"cell_type\": \"code\",\n \"execution_count\": 0,\n \"metadata\": {\n \"application/vnd.databricks.v1+cell\": {\n \"cellMetadata\": {},\n \"inputWidgets\": {},\n \"nuid\": \"833oooo4-oo95-45oo-o5o8-94oo445o8o50\",\n \"showTitle\": false,\n \"title\": \"\"\n }\n },\n \"outputs\": [],\n \"source\": [\n \"%sql\\n\",\n \"CREATE TABLE IF NOT EXISTS billing_data.billing_data_schema.billing_materialized_view (\\n\",\n \" account_id STRING,\\n\",\n \" workspace_id STRING,\\n\",\n \" record_id STRING,\\n\",\n \" sku_name STRING,\\n\",\n \" cloud STRING,\\n\",\n \" usage_start_time TIMESTAMP,\\n\",\n \" usage_end_time TIMESTAMP,\\n\",\n \" usage_date DATE,\\n\",\n \" custom_tags MAP\u003cSTRING, STRING\u003e,\\n\",\n \" usage_unit STRING,\\n\",\n \" usage_quantity DECIMAL(38,18),\\n\",\n \" usage_metadata STRUCT\u003c\\n\",\n \" cluster_id: STRING,\\n\",\n \" job_id: STRING,\\n\",\n \" warehouse_id: STRING,\\n\",\n \" instance_pool_id: STRING,\\n\",\n \" node_type: STRING,\\n\",\n \" job_run_id: STRING,\\n\",\n \" notebook_id: STRING,\\n\",\n \" dlt_pipeline_id: STRING,\\n\",\n \" endpoint_name: STRING,\\n\",\n \" endpoint_id: STRING,\\n\",\n \" dlt_update_id: STRING,\\n\",\n \" dlt_maintenance_id: STRING,\\n\",\n \" run_name: STRING\\n\",\n \" \u003e,\\n\",\n \" identity_metadata STRUCT\u003crun_as: STRING\u003e,\\n\",\n \" record_type STRING,\\n\",\n \" ingestion_date DATE,\\n\",\n \" billing_origin_product STRING,\\n\",\n \" product_features STRUCT\u003c\\n\",\n \" jobs_tier: STRING,\\n\",\n \" sql_tier: STRING,\\n\",\n \" dlt_tier: STRING,\\n\",\n \" is_serverless: BOOLEAN,\\n\",\n \" is_photon: BOOLEAN,\\n\",\n \" serving_type: STRING\\n\",\n \" \u003e,\\n\",\n \" usage_type STRING,\\n\",\n \" report_period STRING,\\n\",\n \" unit_cost DECIMAL(38,18),\\n\",\n \" list_cost DECIMAL(38,6),\\n\",\n \" currency STRING,\\n\",\n \" price_start_time TIMESTAMP,\\n\",\n \" price_end_time TIMESTAMP\\n\",\n \")\\n\",\n \"USING DELTA;\\n\"\n ]\n },\n {\n \"cell_type\": \"code\",\n \"execution_count\": 0,\n \"metadata\": {\n \"application/vnd.databricks.v1+cell\": {\n \"cellMetadata\": {},\n \"inputWidgets\": {},\n \"nuid\": \"6ooo649o-58o5-4705-o089-o761o0oo65o9\",\n \"showTitle\": false,\n \"title\": \"\"\n }\n },\n \"outputs\": [],\n \"source\": [\n \"%sql\\n\",\n \"select * from billing_data.billing_data_schema.billing_materialized_view limit 1\"\n ]\n },\n {\n \"cell_type\": \"code\",\n \"execution_count\": 0,\n \"metadata\": {\n \"application/vnd.databricks.v1+cell\": {\n \"cellMetadata\": {},\n \"inputWidgets\": {},\n \"nuid\": \"3oo83180-83o0-40o2-ooo2-o5oo3o8o07o8\",\n \"showTitle\": false,\n \"title\": \"\"\n }\n },\n \"outputs\": [],\n \"source\": [\n \"%sql\\n\",\n \"TRUNCATE TABLE billing_data.billing_data_schema.billing_materialized_view\"\n ]\n },\n {\n \"cell_type\": \"code\",\n \"execution_count\": 0,\n \"metadata\": {\n \"application/vnd.databricks.v1+cell\": {\n \"cellMetadata\": {},\n \"inputWidgets\": {},\n \"nuid\": \"24o4o239-oo29-4o15-9ooo-57o9o4o6o966\",\n \"showTitle\": false,\n \"title\": \"\"\n }\n },\n \"outputs\": [],\n \"source\": [\n \"%sql\\n\",\n \"INSERT OVERWRITE TABLE billing_data.billing_data_schema.billing_materialized_view\\n\",\n \"SELECT \\n\",\n \" t1.account_id,\\n\",\n \" t1.workspace_id,\\n\",\n \" t1.record_id,\\n\",\n \" t1.sku_name,\\n\",\n \" t1.cloud,\\n\",\n \" t1.usage_start_time,\\n\",\n \" t1.usage_end_time,\\n\",\n \" t1.usage_date,\\n\",\n \" t1.custom_tags,\\n\",\n \" t1.usage_unit,\\n\",\n \" t1.usage_quantity,\\n\",\n \" t1.usage_metadata,\\n\",\n \" t1.identity_metadata,\\n\",\n \" t1.record_type,\\n\",\n \" t1.ingestion_date,\\n\",\n \" t1.billing_origin_product,\\n\",\n \" t1.product_features,\\n\",\n \" t1.usage_type,\\n\",\n \" DATE_FORMAT(t1.usage_start_time, 'yyyy-MM') AS report_period,\\n\",\n \" list_prices.pricing.default AS unit_cost,\\n\",\n \" (t1.usage_quantity * list_prices.pricing.default) AS list_cost,\\n\",\n \" list_prices.currency_code AS currency,\\n\",\n \" list_prices.price_start_time,\\n\",\n \" list_prices.price_end_time\\n\",\n \"FROM \\n\",\n \" system.billing.usage t1\\n\",\n \"INNER JOIN \\n\",\n \" system.billing.list_prices list_prices \\n\",\n \"ON\\n\",\n \" t1.cloud = list_prices.cloud AND\\n\",\n \" t1.sku_name = list_prices.sku_name AND\\n\",\n \" t1.usage_start_time \u003e= list_prices.price_start_time AND\\n\",\n \" (t1.usage_end_time \u003c= list_prices.price_end_time OR list_prices.price_end_time IS NULL);\\n\"\n ]\n }\n ],\n \"metadata\": {\n \"application/vnd.databricks.v1+notebook\": {\n \"dashboards\": [],\n \"environmentMetadata\": null,\n \"language\": \"python\",\n \"notebookMetadata\": {\n \"mostRecentlyExecutedCommandWithImplicitDF\": {\n \"commandId\": 2555185811237458,\n \"dataframes\": [\n \"_sqldf\"\n ]\n },\n \"pythonIndentUnit\": 4\n },\n \"notebookName\": \"databricks_billing_details\",\n \"widgets\": {}\n }\n },\n \"nbformat\": 4,\n \"nbformat_minor\": 0\n}" 
} 
} 
```
