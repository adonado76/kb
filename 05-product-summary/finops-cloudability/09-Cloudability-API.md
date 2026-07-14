---
source_system: "apptio-cloudability-standard"
practice: "finops"
language: "en"
doc_type: "cloudability-standard"
consolidated_file: "09-Cloudability-API"
source_files_count: 62
last_updated: "2026-07-13"
---

# 09-Cloudability-API

## About the Cloudability API

<!-- sub-header -->
- **breadcrumb:** Cloudability API > About the Cloudability API
- **source_path:** SSVCLNQ/api-v3/aboutcloudabilityapiv3.html
- **original_file:** api-about-cloudability.md
- **images:** []

## About the Cloudability API

About the Cloudability API

The Cloudability API implementation is based on REST principles. You should find the interface to be predictable with use of resource-oriented URLs and reliance on standard HTTP features that are generally understood by off-the-shelf HTTP clients. For example the API relies on HTTP basic auth for authentication, HTTP verbs (methods such as GET,PUT...) for actions and standard HTTP response codes to indicate API errors or otherwise. By default all API responses are returned as JSON, but other formats such as CSV are available by setting the relevant HTTP media type.

Views and the API

Cloudability employs a Views System to give our customers a tailored experience as they make use of all aspects of our tool. This system is also in place within our API and has the following characteristics

- When making API requests we will automatically respect the default view attached to your user
- If you wish to switch to a different view with your API request you can use the viewId query parameter to declare your desired view. Example ?view_id=2970
- If you wish to apply no view at all, i.e. run the query across all data, then apply viewId with a value of zero. Example: ?view_id=0
- Note: Restricted users will only be able to apply views they have access to.

Special Notes

Note that sort and filtering functionality as documented below is not available for all end points. If you visit the individual end point documentation it will be noted whether this is supported or not.

For each V3 endpoint, an organization can make up to 300 requests per minute. When this rate limit is reached, V3 endpoints will throttle and return status code 429.

Enable Access to the Cloudability API

1. From the Cloudability Dashboard, select Manage Profile .
1. Navigate to the Preferences tab
1. In the Cloudability API section, select Enable Access . Cloudability generates the API key and shows it in the API KEY field. If access has been previously enabled, select Regenerate Key to revoke the previous key and create a new one.

---

## Account Group Entries

<!-- sub-header -->
- **breadcrumb:** Cloudability API > Account Group Entries
- **source_path:** SSVCLNQ/api-v3/account_group_entries.html
- **original_file:** api-account-group-entries.md
- **images:** []

## Account Group Entries

Manage Account Group Entries

Account Group Entries are the associations between a specific account and an account group. They link the two and only admins can create, update, and delete account groups entries. All users with API access can get their information.

Account Group Entries Object

- id (number) - Unique identifier for the Account Group Entries object
- account_group_id (number) - Unique identifier for the account group the value applies to
- account_identifier (string) - the unique identifier for the AWS account, Azure subscription or GCP project
- organization_service_account_id (number) - The internal Cloudability system ID of the account/subscription/project associated with this Account Group Entry
- value (string) – the value assigned to the account group for the account

Get a list of Account Group Entries

Example Query

```
curl https://api.cloudability.com/v3/account_group_entries -u ‘[auth_token]:’

```

Example Response

```
[
	{
		"id": 1,
		"account_group_id": 4672,
		"account_identifier": "1111-1111-1111",
		"organization_service_account_id": 123,
		"value": "red1"
	},
	{
		"id": 2,
		"account_group_id": 9582,
		"account_identifier": "2222-2222-2222",
		"organization_service_account_id": 123,
		"value": "red2"
	},
	{
		"id": 3,
		"account_group_id": 4672,
		"account_identifier": "1111-1111-1111",
		"organization_service_account_id": 123,
		"value": "orange1"
	}
]
```

Get a specific Account Group Entry

Example Query

```
curl https://api.cloudability.com/v3/account_group_entries/1

```

(Replace the value “1” above with the unique id of your account group entry)

Example response

```
[
	{
		"id": 1,
		"account_group_id": 4672,
		"account_identifier": "1111-1111-1111",
		"organization_service_account_id": 123,
		"value": "red1"
	}
]
```

Create an Account Group Entry

Example Query

```
curl -X POST https://api.cloudability.com/v3/account_group_entries \\
      -H 'Content-Type: application/json' \\
      -u ‘[auth_token]:’ \\
      -d @- << EOF
 {
 "account_group_id": 5686,
 "account_identifier": "1111-1111-1111",
 "value": "marketing team"
 }
 EOF
```

Upon successful creation the API will return the account group entries object

Update an Account Group Entry

Account Group Entries can have their values adjusted to any valid string, but cannot be repointed at difference Accounts or Account Groups (no error will be returned if attempted, however the update won’t be made). To do that, create a new Account Group Entry for the Account Group or Account in question.

Example Query

```
curl -X PUT https://api.cloudability.com/v3/account_group_entries/1 \\
      -H 'Content-Type: application/json' \\
      -u ‘[auth_token]:’ \\
      -d @- << EOF
 {
  "value": "legal team"
 }
EOF
```

Upon successful update the API will return the account group entries object

(Replace the value “1” above with the unique id of your account group entry)

Delete an Account Group Entry

Example Query

```
curl -X DELETE https://api.cloudability.com/v3/account_group_entries/1
-u ‘[auth_token]:’
```

(Replace the value “1” above with the unique id of your account group entry)

This will return a HTTP 204 status with no content on successful delete.

---

## Account Groups End Point

<!-- sub-header -->
- **breadcrumb:** Cloudability API > Account Groups End Point
- **source_path:** SSVCLNQ/api-v3/account_groups_end_point.html
- **original_file:** api-account-groups-end-point.md
- **images:** []

## Account Groups End Point

Manage Account Groups

Account Groups function like tags for AWS accounts, Azure Subscriptions and GCP projects. They allow you to assign a key/value pair where Account Group is the key and Account Group Entry maps the value. For example, you might create an Account Group of Environment and use Account Group Entries to assign a value of "Production", "Staging" or "Development" to individual cloud accounts in Cloudability.

In the Cloudability UI you can define Account Groups and Account Group Entries on the Accounts page. The API lets you perform programmatic CRUD-ing of the Account Groups and account group entries. Only admins can create, update, and delete Account Groups and Entries through the UI and API, while all other users can access the generated dimensions in dashboards and reports.

An Account Group can have many Account Group Entries, each entry mapping an account/project/subscription’s value for the group. Users are then able to report and filter against these defined account group keys with each one available as a reporting dimension throughout Cloudability.

End Point Particulars

/account_groups for all RESTful CRUD interactions

The Account Groups Object

id (number) - Unique identifier for the Account Group object

position (number) – The position of the account group in relation to all other account groups

name (string) – the name of the account group as it will appear throughout Cloudability

account_group_entry_values (array) – An informative list of current values for the account group. These values are updated via the Account Group Entries endpoint

Example Account Groups Object

```
{
	"id": 1,
	"position": 1,
	"name": "Project",
	"account_group_entry_values": [
		"Project timelapse",
		"Sunset",
		"Corporate"
	]
}
```

List Account Groups

List all current account groups

Example Request

curl https://api.cloudability.com/v3/account_groups -u ‘[auth_token]:’

Example Response

```
[
	{
		"id": 5784,
		"position": 1,
		"name": "Project",
		"account_group_entry_values": [
			"Project timelapse",
			"Sunset",
			"Corporate"
		]
	},
	{
		"id": 5785,
		"position": 2,
		"name": "Environment",
		"account_group_entry_values": [
			"Production",
			"Test",
			"Staging"
		]
	}
]
```

Get a specific Account Group

Example Request

curl https://api.cloudability.com/v3/account_groups/1 -u ‘[auth_token]:’ Copy

NOTE: This is the Account Group unique id assigned when it was created, not the Account Group position shown in app. The Account Group unique id can be found by using the API to make a GET request to list all the Account Groups.

Example Response

```
{
	"id": 1,
	"position": 2,
	"name": "Environment",
	"account_group_entry_values": [
		"Production",
		"Test",
		"Staging",
	]
 }
```

Create an Account Group

Example Request

```
curl -X POST https://api.cloudability.com/v3/account_groups \\
	 -H 'Content-Type: application/json' \\
     -u '[auth_token]:' \\
	 -d @- 
{
"position": 1,
"name": "Environment"
} 
EOF 
```

Upon successful creation the API will return the account group object

Note: The values associated with an Account Group are the values of the related Account Group Entries. As such, they cannot be modified via Account Group creation/modification, but rather via the Account Group Entries end point. You must also know the next available free slot (eg: position 1) and denote it for this to work.

Update an Account Group

You can use the API to update the name of any account group. You may have to do a GET request first to get the individual Account Group ID and then do a PUT request with that Account Group ID.

Example Requests

```
curl -X PUT https://api.cloudability.com/v3/account_groups/1 \\
	 -H 'Content-Type: application/json' \\
	 -u '[auth_token]:' \\
	 -d @- 
{
	"name": "Env"
}		
EOF		
```

Upon successful creation the API will return the account group object

Delete an Account Group

Note : You can only delete an Account Group when all Account Group Entries have been removed. You may have to do a GET request first to get the individual Account Group ID and then do a DELETE request with that Account Group ID.

Example Request

Curl -X DELETE https://api.cloudability.com/v3/account_groups/:id -u '[auth_token]:'

A successful deletion returns a 200OK status code with the deleted object in the body payload

---

## Anomaly Detection End Point

<!-- sub-header -->
- **breadcrumb:** Cloudability API > Anomaly Detection End Point
- **source_path:** SSVCLNQ/api-v3/anomaly-detection-end-point.html
- **original_file:** api-anomaly-detection-end-point.md
- **images:**
  - 03-media/apptio-cloudability-standard/sout.gif

## Anomaly Detection End Point

### Summary

The Anomaly Detection API end point can be used to retrieve spending anomalies and create anomaly subscriptions as outlined in Anomaly Detection .

| API type | Public Endpoint (US) | Description |
| --- | --- | --- |
| API type | Public Endpoint (US) | Description |
| GET | https://api.cloudability.com/v3/anomalies | used to get anomalies or a single anomaly using id param |
| POST | https://api.cloudability.com/v3/anomaly-subscriptions | used to create a subscription |
| GET | https://api.cloudability.com/v3/anomaly-subscriptions | used to get subscriptions |
| GET | https://api.cloudability.com/v3/anomaly-subscriptions/:subscriptionId | used to get a single subscription using subscriptionId |
| GET | https://api.cloudability.com/v3/anomaly-subscriptions/all | used to get all subscriptions AnomalyDetectionFeatureFullAccessAdmin permission is required for this endpoint |
| PUT | https://api.cloudability.com/v3/anomaly-subscriptions/:subscriptionId | used to update a subscription using subscriptionId |
| DELETE | https://api.cloudability.com/v3/anomaly-subscriptions/:subscriptionId | used to delete a subscription from our records |

### The Anomalies Object

| key | value type | description |
| --- | --- | --- |
| key | value type | description |
| date | string | Date of the anomaly, e.g., "2018-02-14". |
| enhancedServiceName | string | e.g., AWS EC2. |
| usageFamily | string | e.g., Data Transfer. |
| unblendedCost | string | Total cost for the day. |
| unusualSpend | string | The unusual portion of the spend for the day. |
| vendorAccountName | string | Name associated with the account where the anomaly occurred. |
| currencyCode | string | The currencyCode associated with this customer’s configuration. |
| tags | array | list of tag objects associated with the anomaly. Each object contains tag, tagName and vendorTagValue |
| businessDimensions | array | list of businessDimension objects associated with the anomaly. Each object contains category, categoryKey and categoryValue |
| id | string | the unique identifier used to look up a specific anomaly |
| unusualSpendPercentage | string | The unusual percentage of the spend for the day. |
| issueFields | array | list of of Jira or ServiceNow issue objects associated with the anomaly. |
| vendor | string | the vendor where the anomaly originates from |

### How to generate an Apptio API key

Getting started with Cloudability API V3

### GET Anomalies Endpoint

public api example: https://api.cloudability.com/v3/anomalies

Query Parameters for date range lookup

| Parameter | Required | Description |
| --- | --- | --- |
| Parameter | Required | Description |
| startDate | Yes | the start date of the query |
| endDate | Yes | the end date of the query |
| viewId | Yes | the view being used for the request |

```
curl --request GET --url 'https://api.cloudability.com/v3/anomalies?viewId=<viewId>&startDate=<year-month-day>&endDate=<year-month-day>' \ 
-u '<apptio api key>:'

```

Example Response

```
{"result":[
{"date":"<date>","type":"<type>","enhancedServiceName":"<serviceName>","usageFamily":"<usageFamily>","unblendedCost":"<cost>","unusualSpend":"<unusualSpend>","vendorAccountName":"<account name>","currencyCode":"<currency code>","tags":["tag":"<tagId>", "tagName":"<tagName>"],"businessDimensions":["category":"<categoryID>", "categoryKey":"<categoryKey>"],"id":<id>,"unusualSpendPercentage":"<percentage>","issueFields":[]},
{"date":"<date>","type":"<type>","enhancedServiceName":"<serviceName>","usageFamily":"<usageFamily>","unblendedCost":"<cost>","unusualSpend":"<unusualSpend>","vendorAccountName":"<account name>","currencyCode":"<currency code>","tags":["tag":"<tagId>", "tagName":"<tagName>"],"businessDimensions":["category":"<categoryID>", "categoryKey":"<categoryKey>"],"id":<id>,"unusualSpendPercentage":"<percentage>","issueFields":[]},
{"date":"<date>","type":"<type>","enhancedServiceName":"<serviceName>","usageFamily":"<usageFamily>","unblendedCost":"<cost>","unusualSpend":"<unusualSpend>","vendorAccountName":"<account name>","currencyCode":"<currency code>","tags":["tag":"<tagId>", "tagName":"<tagName>"],"businessDimensions":["category":"<categoryID>", "categoryKey":"<categoryKey>"],"id":<id>,"unusualSpendPercentage":"<percentage>","issueFields":[]}
]}
```

### Query Parameters for id lookup

| Parameter | Required | Description |
| --- | --- | --- |
| Parameter | Required | Description |
| id | Yes | the anomaly’s ID |
| viewId | Yes | the view being used in the request |

Example request to retrieve a single anomaly

```
curl --location 'https://api.cloudability.com/v3/anomalies?viewId=<viewId>&id=<anomalyId>' \
-u '<apptio api key>:' 

```

Example Response

```

{"result":[{"date":"<date>","type":"<type>","enhancedServiceName":"<serviceName>","usageFamily":"<usageFamily>","unblendedCost":"<cost>","unusualSpend":"<unusualSpend>","vendorAccountName":"<account name>","currencyCode":"<currency code>","tags":["tag":"<tagId>", "tagName":"<tagName>"],"businessDimensions":["category":"<categoryID>", "categoryKey":"<categoryKey>"],"id":<id>,"unusualSpendPercentage":"<percentage>","issueFields":[]}]}

```

### More information on filters:

The get anomalies request does handle filter requests, but it will only work if provided valid Dimension, Operator and Value parameters. It is recommended to use the filters on the frontend because the Dimension, Operator and Value parameters will auto-populate based on the environment.

Example request with filters

```
curl --location 'https://api.cloudability.com/v3/anomalies?viewId=<viewId>&startDate=<year-month-day>&endDate=<year-month-day>&filter=<dimension><operator><value>' \
-u '<apptio api key>:'
```

### The Subscriptions Object

| key | value type | description |
| --- | --- | --- |
| key | value type | description |
| subscriptionID | string | UUID for the subscription |
| viewId | string | The view configured on the subscription |
| unusualSpendThreshold | int | The unusual spend threshold configured for the subscription |
| unusualPercentageThreshold | int | The unusual percentage threshold configured for the subscription |
| delivery | object | The object contains the method of alerting |
| sharedUserIds | string | (optional) The users that have been shared this subscription |
| description | string | (optional) The set description for the subscription |
| anomalyIgnoreRecord | object | (optional) The current ignore configuration set for this subscription |

### POST Subscriptions Endpoint

public api example: https://api.cloudability.com/v3/anomaly-subscriptions

Query parameters

| Parameter | Required | Description |
| --- | --- | --- |
| viewId | Yes | the view being used for the request |

Example request to create a new subscription

```
 curl -X POST 'https://api.cloudability.com/v3/anomaly-subscriptions?viewId=<viewId>' \
  -u ‘<apptio api key>:’ \
  --header 'Content-Type: application/json' \
  --data '{"unusualSpendThreshold":<amount>, "unusualPercentageThreshold":<amount>, "delivery": {"method":"<email or pagerduty>"}}'
```

Shared users and Description Example Request

```
 curl -X POST --location 'https://api.cloudability.com/v3/anomaly-subscriptions?viewId=<viewId>' \
  -u '<apptio api key>:' \
  --header 'Content-Type: application/json' \
  --data '{"unusualSpendThreshold":<amount>,"description":"<description>","sharedUserIds":["<userId>", "<userId>"],"unusualPercentageThreshold":<amount>,"delivery":{"method":"<email or pagerduty>"}}' 
```

Example Response:

```
{"result":{"subscriptionId":"<subId>","orgId":"<orgId>","viewId":"<viewId>","userId":"<userId>","unusualSpendThreshold":<spend amount>,"unusualPercentageThreshold":<percentage amount>,"defaultCurrency":"<currency Code>","creatorId":"<userId>","createdAt":"<timeStamp>","updatedAt":"<timeStamp>","delivery":{"method":"<pagerduty or email>","recipient":"<userId>"}}}
```

Clarification on creating a subscription for only unusualSpendThreshold or unusualPercentageThreshold:

If the creator of the subscription wants only unusalSpendThreshold or unusualPercentageThreshold then only include which one is required in the request.

- unusualSpendThreshold only request body example:

- --data '{"unusualSpendThreshold":<amount>,"description":"<description>","sharedUserIds":["<userId>"],"delivery":{"method":"<pagerduty or email>"}}'
- setting unsualSpendThreshold or unusalPercentageThreshold to = 0 will set that threshold to 0 because there are some customers that do use that.

### GET Subscriptions Endpoint

public api example: https://api.cloudability.com/v3/anomaly-subscriptions

Query parameters

| Parameter | Required | Description |
| --- | --- | --- |
| viewId | Yes | the view being used for the request |

Example Request

```
curl --location 'https://api.cloudability.com/v3/anomaly-subscriptions?viewId=<viewId>' \
-u '<apptio api key>:'
```

Example Response (1 example with a sharedUserIds populated and 1 without sharedUserIds populated)

```
{"result":[
      {"subscriptionId":"<subscriptionId>","orgId":"<orgId>","viewId":"<viewId>","userId":"<userId>","unusualSpendThreshold":<unusualSpendThreshold>,"unusualPercentageThreshold":<unusualPercentageThreshold>,"defaultCurrency":"<currency Code>","creatorId":"<userId>","createdAt":"<timeStamp>","updatedAt":"<timeStamp>","delivery":{"method":"<pagerduty or email>","recipient":"<userId>"},"sharedUserIds":"<userId>,<userId>"},
      {"subscriptionId":"<subscriptionId>","orgId":"<orgId>","viewId":"<viewId>","userId":"<userId>","unusualSpendThreshold":<unusualSpendThreshold>,"unusualPercentageThreshold":<unusualPercentageThreshold>,"defaultCurrency":"<currency Code>","creatorId":"<userId>","createdAt":"<timeStamp>","updatedAt":"<timeStamp>","delivery":{"method":"<pagerduty or email>","recipient":"<userId>"}}
      ]}
```

GET Single Subscription Endpoint:

public api example: https://api.cloudability.com/v3/anomaly-subscriptions /<subscriptionId>

Example Request

```
curl --location 'https://api.cloudability.com/v3/anomaly-subscriptions/<subscriptionId>' \
-u '<apptio api key>:'
```

Example Response

```
{"result":
  {"subscriptionId":"<subscriptionId>","orgId":"<orgId>","viewId":"<viewId>","userId":"<userId>","unusualSpendThreshold":<unusualSpendThreshold>,"unusualPercentageThreshold":<unusualPercentageThreshold>,"defaultCurrency":"<currency Code>","creatorId":"<userId>","createdAt":"<timeStamp>","updatedAt":"<timeStamp>","delivery":{"method":"<pagerduty or email>","recipient":"<userId>"},"sharedUserIds":"<userId>,<userId>"}
}
```

### PUT Subscription Endpoint:

public api example: https://api.cloudability.com/v3/anomaly-subscriptions/<subscriptionId>?viewId= <viewId>

| Parameter | Required | Description |
| --- | --- | --- |
| viewId | Yes | the view being used for the request |

Example Request

```
curl -X PUT --location 'https://api.cloudability.com/v3/anomaly-subscriptions/<subscriptionId>?viewId=<viewId>' \
-u '<apptio api key>:' \
--header 'Content-Type: application/json' \
--data '{"subscriptionId":"<subscriptionId>","orgId":"<orgId>","userId":"<userId>","unusualSpendThreshold":<unusualSpendThreshold>,"unusualPercentageThreshold":<unusualPercentageThreshold>,"defaultCurrency":"<currency Code>","creatorId":"<userId>","createdAt":"<timeStamp>","updatedAt":"<timeStamp>","delivery":{"method":"<pagerduty or email>","recipient":"<userId>"},"sharedUserIds":["<userId>,<userId>"],"source":"<source method>","description":""}'

```

Shared users clarification:

subscription owner can add users to the array [] of sharedUserIDs in the request. userIds must be comma seperated.

Example Response

```
200, only will response with an error if there was one
```

### DELETE endpoint:

Example: https://api.cloudability.com/v3/anomaly-subscriptions/<subscriptionId>

Example Request

```
curl -X DELETE --location 'https://api.cloudability.com/v3/anomaly-subscriptions/<subscriptionId>' \
-u '<apptio api key>:' \
```

Example Response

```
200, only will response with an error if there was one.
```

---

## Budgets & Forecasting End Points

<!-- sub-header -->
- **breadcrumb:** Cloudability API > Budgets & Forecasting End Points
- **source_path:** SSVCLNQ/api-v3/budgets_and_forecasting_endpoints.html
- **original_file:** api-budgets-forecasting-end-points.md
- **images:** []

## Budgets & Forecasting End Points

Summary

The Budgets and Forecasting API can be used to retrieve forecasts of future spending as well as interact with budgets.

- This end point does not support filtering and sorting.

End Point Particulars

end point : /estimate

end point : /forecast

end point : /budgets for all RESTful CRUD interactions related to budgets.

end point : /budget-subscriptions/ for all RESTful CRUD interactions related to budget subscriptions.

---

## Budgets and Budget Subscriptions

<!-- sub-header -->
- **breadcrumb:** Cloudability API > Budgets & Forecasting End Points > Budgets and Budget Subscriptions
- **source_path:** SSVCLNQ/api-v3/budgets_and_budget_subscriptions.html
- **original_file:** points-budgets-budget-subscriptions.md
- **images:** []

## Budgets and Budget Subscriptions

The Budget Object

id (string) - UUID for the budget

viewId (string) - The viewId the budget is applied against

name (string) - The name of the budget

basis (string) - Cost basis. One of "cash," "amortized," "adjusted", "adjustedAmortized" and "list"

ownerId (string) - The unique id of the person who created the budget

months (array) - list of month objects for those having defined budgets.

month (string) - month of spend YYYY-MM

threshold (integer) - budget limit for that month

Example Budget Object

```
{
  "result": {
      "id": "8a028d91-1234-abcd-54fc-0a131052b72f",
      "viewId": "0",
      "name": "Q4 Amortized",
      "basis": "amortized",
      "ownerId": "11235",
      "months": [
        {
          "month": "2017-10",
          "threshold": 19500
        },
        {
          "month": "2017-11",
          "threshold": 20500
        },
        {
          "month": "2017-12",
          "threshold": 21500
        }
      ]
    }
}
```

Example Budget Requests

Create a Budget

```
curl -X POST "https://api.cloudability.com/v3/budgets" \\
     -H 'Content-Type: application/json' \\
     -u ‘[auth_token]:’ \\
     -d @- << EOF
{
  "name": "TesterTon",
  "basis": "cash",
  "viewId": "0",
  "months": [
    {
      "month": "2018-01",
      "threshold": 19500
    },
    {
      "month": "2018-02",
      "threshold": 20500
    },
    {
      "month": "2018-03",
      "threshold": 21500
    }
  ]
}
EOF
```

A successful operation will result in the object being created and returned to the client.

Retrieve a Budget

```
curl "https://api.cloudability.com/v3/budgets/0643ce32-ca2b-4776-6492-2397a0e96c7f" \\
     -u ‘[auth_token]:’
```

Update a Budget

```
 curl -X PUT https://api.cloudability.com/v3/budgets/0643ce32-ca2b-4776-6492-2397a0e96c7f \\
     -H 'Content-Type: application/json' \\
     -u ‘[auth_token]:’ \\
     -d @- << EOF
{
  "name": "TesterTon",
  "basis": "amortized",
  "viewId": "0",
  "months": [
    {
      "month": "2018-01",
      "threshold": 29500
    }
  ]
}
EOF

```

Delete a Budget

curl -X DELETE https://api.cloudability.com/v3/budgets/0643ce32-ca2b-4776-6492-2397a0e96c7f \\ -u ‘[auth_token]:’

List All Budgets

```
curl https://api.cloudability.com/v3/budgets \\
     -u ‘[auth_token]:’
```

The Budget Subscription Object

As well as creating budgets for your cloud spend you can create subscriptions to receive an email notification if you exceed and/or are projected to exceed your budget.

id (string) - id for the subscription

budgetId (string) - budgetId that the subscription applies to

notifyExceeded (boolean) - notify when actual spend exceeds budget, true of false

notifyExpected (boolean) - notify when expected spend exceeds budget, true of false

Example Budget Subscription Object

```
{
  "result": {
      "id": "3f38dd43-f953-43d8-91bc-0184818f7598",
      "budgetId": "d090e29e-2a26-4ca5-7f9a-67be3134081e",
      "notifyExceeded": false,
      "notifyExpected": true
  }
}
```

Example Budget Subscription Requests

Create a Budget Subscription

```
 curl -X POST "https://api.cloudability.com/v3/budget-subscriptions" \\
     -H 'Content-Type: application/json' \\
     -u ‘[auth_token]:’ \\
     -d @- << EOF
{
  "budgetId": "d090e29e-2a26-4ca5-7f9a-67be3134081e",
  "notifyExpected": true,
  "notifyExceeded": true
}\t
EOF
```

Retrieve a Budget Subscription

```
curl https://api.cloudability.com/v3/budget-subscriptions/3f38dd43-f953-43d8-91bc-0184818f7598 \\
     -u ‘[auth_token]:’
```

Update a Budget Subscription

```
curl -X PUT https://api.cloudability.com/v3/budget-subscriptions/3f38dd43-f953-43d8-91bc-0184818f7598 \\
     -H 'Content-Type: application/json' \\
     -u ‘[auth_token]:’ \\
     -d @- << EOF
{
  "budgetId": "d090e29e-2a26-4ca5-7f9a-67be3134081e",
  "notifyExpected": true,
  "notifyExceeded": false
}\t
EOF
```

Delete a Budget Subscription

```
curl -X DELETE https://api.cloudability.com/v3/budget-subscriptions/3f38dd43-f953-43d8-91bc-0184818f7598 \\
     -u ‘[auth_token]:’
```

List All Budget Subscriptions

```
curl https://api.cloudability.com/v3/budget-subscriptions \\
     -u ‘[auth_token]:’
```

---

## Estimates

<!-- sub-header -->
- **breadcrumb:** Cloudability API > Budgets & Forecasting End Points > Estimates
- **source_path:** SSVCLNQ/api-v3/estimates.html
- **original_file:** points-estimates.md
- **images:** []

## Estimates

Generating an Estimate

Arguments

| Argument | Required | Description |
| --- | --- | --- |
| viewId | Yes | The id of the view you are generating the estimate for. viewId=0 will apply estimate to all cost data. |
| basis | Yes | The cost basis for the estimate. examples: basis=cash basis=amortized basis=adjusted basis=adjustedAmortized basis=list |

The Estimate Object

Summary Block - Here are the headline figures for your estimate

estimatedSpend (number) - estimated spending for the current month

previousMonthSpend (number) - total spending in the previous month

cumulativeMtdSpend (array) - list of spending objects. Each object includes date and value.

previousMonthFinalized (boolean) - whether the invoice for the prior month is finalized

currentDate (string) - effective date for the estimate

details Block - a list of Spending Driver objects defined by serviceName/usageFamily combinations. Each object contains:

serviceName (string) - Vendor service name such as AWS EC2, AWS RDS...

usageFamily (string) - Type of cost activity such as Instance Usage, Storage...

previousMonthSpend (number) - How much was spent on this item last month

mtdSpend (number) - current month spending to date for this item

estimatedSpend (number) - Estimated spend for this item at end of month

Cumulative Month-To-Date Spend(cumulativeMtdSpend) Block - a list of date-spend objects

date (string) - Date of spend YYYY-MM-DD

spend (number) - Spend for that date in USD.

Example Estimate Object

In this sample response, we're only showing the first three entries of "cumulativeMtdSpend" and "details" for readability purposes.

```
{
  "result": {
    "estimatedSpend": 138429.32,
    "previousMonthSpend": 142252.16238499997,
    "previousMonthFinalized": true,
    "currentDate": "2018-06-11",
    "cumulativeMtdSpend": [
      {
        "date": "2018-06-01",
        "spend": 10418.500360999999
      },
      {
        "date": "2018-06-02",
        "spend": 14226.970056999999
      },
      {
        "date": "2018-06-03",
        "spend": 18270.250674
      }
    ]
  },
  "details": [
    {
      "serviceName": "AWS EC2",
      "estimatedSpend": 54638.37,
      "mtdSpend": 23101.275903,
      "previousMonthSpend": 56600.280253,
      "usageFamily": "Instance Usage"
    },
    {
      "serviceName": "AWS Support",
      "estimatedSpend": 15000,
      "mtdSpend": 0,
      "previousMonthSpend": 15000,
      "usageFamily": "Support"
    },
    {
      "serviceName": "AWS RDS",
      "estimatedSpend": 13761.53,
      "mtdSpend": 5101.559999999999,
      "previousMonthSpend": 13690.639,
      "usageFamily": "Instance Usage"
    }
  ]
}
```

Example Estimate Request

Retrieve Current Month Estimate

Quite simply perform a GET request at the /estimate end point, specifying a cost basis.

You must supply a viewId for your request. Set viewId=0 to see the estimate for all of your spending.

```
curl "https://api.cloudability.com/v3/estimate?basis=cash&viewId=11235"\\
     -u ‘[auth_token]:
```

The estimate endpoint is limited to 10 requests per user per minute and 20 requests per org per minute.

---

## Forecasts

<!-- sub-header -->
- **breadcrumb:** Cloudability API > Budgets & Forecasting End Points > Forecasts
- **source_path:** SSVCLNQ/api-v3/forecasts.html
- **original_file:** points-forecasts.md
- **images:** []

## Forecasts

Generating a Forecast

Arguments

| Argument | Required | Description | Type |
| --- | --- | --- | --- |
| viewId | Yes | The id of the view you are generating the forecast for. viewId=0 will apply forecast to all cost data. | string |
| basis | Yes | The cost basis for the estimate. Must be one of [cash, amortized, adjusted, adjustedAmortized, list] | string |
| monthsBack | Yes | How many months of history to use when predicting future costs. Must be between 3 and 24 | int |
| monthsForward | Yes | How many months of spending to forecast. Must be between 1 and 24 | int |
| useCurrentEstimate | No | Whether to include the current month estimate in spending model. Defaults to false. | bool |
| removeCredits | No | Whether to remove credits from the spending model. Defaults to false. | bool |
| removeOneTimeCharges | No | Whether to remove one time charges from the spending model. Defaults to false. | bool |

The Forecast Object

currentMonth (string) - the current month, format YYYY-MM

currentEstimate (number) - estimated spending for the current month

forecastTotal (number) - Total spending over the duration of your forecast

actualTotal (number) - Total spending over the comparison historical period

parameters (object) - The list of parameters used for your forecast

viewId (string)

monthsForward (integer)

monthsBack (integer)

basis (string)

useCurrentEstimate (boolean)

removeOneTimeCharges (boolean)

removeCredits (boolean)

actual - A list of month-spend objects for comparative historical cloud costs

month (string) - the month YYYY-MM

spend (number) - the recorded spend

actualDetail - A list of detailed month-spend objects for comparative historical cloud costs

month (string) - the month YYYY-MM

spend (number) - the recorded spend

serviceName (string) - The normalised service name. Example 'AWS EC2'

usageFamily (string) - The usage family. Example 'Instance Usage'

forecast - A list of month-spend objects for projected spend

month (string) - the month YYYY-MM

spend (number) - the projected spend

lowerBound (number) - projected lower bound of spend

upperBound (number) - projected upper bound of spend

forecastDetail - A list of detailed month-spend objects for projected spend

month (string) - the month YYYY-MM

spend (number) - the projected spend

serviceName (string) - The normalised service name. Example 'AWS EC2'

usageFamily (string) - The usage family. Example 'Instance Usage'

Example Forecast Object

In this sample response, we're only showing the first three entries of "actual," "actualDetail," "forecast" and "forecastDetail" for readability purposes.

```
{
  "result": {
    "parameters": {
      "viewId": "0",
      "monthsForward": 8,
      "monthsBack": 6,
      "basis": "cash",
      "useCurrentEstimate": false,
      "removeOneTimeCharges": false,
      "removeCredits": false
    },
    "currentMonth": "2018-09",
    "currentEstimate": 169444.38000000006,
    "forecastTotal": 1972164.1539731494,
    "actualTotal": 1518.7159940000001,
    "actual": [
      {
        "month": "2017-09",
        "spend": 187078.84031799991
      },
      {
        "month": "2017-10",
        "spend": 192950.680001
      },
      {
        "month": "2017-11",
        "spend": 170649.45000099996
      }
    ],
    "actualDetail": [
      {
        "month": "2017-09",
        "spend": 0.012558,
        "serviceName": "AWS API Gateway",
        "usageFamily": "API Request"
      },
      {
        "month": "2017-09",
        "spend": 2.6000000000000002e-05,
        "serviceName": "AWS API Gateway",
        "usageFamily": "Data Transfer"
      },
      {
        "month": "2017-09",
        "spend": 0.014471999999999999,
        "serviceName": "AWS Administrative",
        "usageFamily": "Other"
      }
    ],
    "forecast": [
      {
        "month": "2018-10",
        "lowerBound": 152748.68445406112,
        "spend": 204665.66745104585,
        "upperBound": 256582.65044803056
      },
      {
        "month": "2018-11",
        "lowerBound": 164779.69238992754,
        "spend": 217735.0150468521,
        "upperBound": 270690.3377037764
      },
      {
        "month": "2018-12",
        "lowerBound": 176197.59003756387,
        "spend": 230212.01914762674,
        "upperBound": 284226.4482576897
      }
    ],
    "forecastDetail": [
      {
        "month": "2018-10",
        "spend": 1.244314631343604,
        "serviceName": "AWS API Gateway",
        "usageFamily": "API Request"
      },
      {
        "month": "2018-11",
        "spend": 1.3898872510930294,
        "serviceName": "AWS API Gateway",
        "usageFamily": "API Request"
      },
      {
        "month": "2018-12",
        "spend": 1.528232288256353,
        "serviceName": "AWS API Gateway",
        "usageFamily": "API Request"
      }
    ]
  }
}
```

Example Forecast Request

Retrieve Current Forecast

Quite simply perform a GET request at the /forecast end point, specifying all required parameters.

```
curl "https://api.cloudability.com/v3/forecast?basis=cash&monthsForward=12&monthsBack=6&viewId=11235"\\
     -u ‘[auth_token]:’
```

---

## Business Mappings End Point

<!-- sub-header -->
- **breadcrumb:** Cloudability API > Business Mappings End Point
- **source_path:** SSVCLNQ/api-v3/business_mappings_endpoint.html
- **original_file:** api-business-mappings-end-point.md
- **images:** []

## Business Mappings End Point

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

---

## Business Mapping Expression Language

<!-- sub-header -->
- **breadcrumb:** Cloudability API > Business Mappings End Point > Business Mapping Expression Language
- **source_path:** SSVCLNQ/api-v3/business_mapping_expression.html
- **original_file:** point-business-mapping-expression-language.md
- **images:** []

## Business Mapping Expression Language

Summary

We have created a DSL especially so that you can to define the matchExpression and valueExpression fields in your mapping rules elegantly, and the syntax is pretty simple. If you’ve ever written code in Java, JavaScript, Ruby, Python, or any other popular programming language, the concepts of our expression language should be pretty familiar. Even if you haven't it's very straightforward to create these expressions and Cloudability will provide plenty of examples.

Literals: Text, Date-times Objects, and Numbers

The expression language has three different types of literal data: text, date-time objects, and numbers. Although you can use either single-quotes or double quotes to express literal text objects (with backslashes to escape literal quotes or apostrophes embedded within the string) it's advisable to use single quotes since it will be awkward to use double-quoted expression strings within double-quoted JSON strings.

```
'This is also text.'
'This text has \\'embedded apostrophes\\'.'
'This text has "embedded quotes", but is wrapped in apostrophes.'
```

To create date-time objects, just create a string literal whose contents conform with a well-known date format, either YYYY-MM-DD , to specify the date only (with the time set to midnight UTC), or YYYY-MM-DDTHH:MM:SS.000Z , to specify the complete date-time.

You can omit the final “Z” character -- as well as the millisecond fractions and the decimal point, from the complete date-time object -- but the timestamp will always be interpreted with UTC timezone.

```
'2018-01-01'
'2017-04-10T10:10:10'
'2017-04-10T10:10:10.123Z'
```

For numbers, you can use numerals, minus signs, decimal points, and exponential notation

```
1
3.14159
-2.5
6.02e+23
0.05e-23
```

Field Lookups

Field lookups let you define an expression based on any attribute within the line item data-point: including all dimensions, metrics, account groups, tags, and business dimensions. Field lookups are written by declaring the slot kind in all caps, and then using square-brackets enclosing a string with the name of the appropriate key. It will feel similar to retrieving a value from a hash in many programming languages. Go to the bottom of this page for a full list of available dimensions and metrics.

Note key names are not case-sensitive, so you can write them in uppercase or lowercase, like this:

```
DIMENSION['account_identifier']
METRIC['adjusted_cost']
ACCOUNT_GROUP['Environment']
TAG['NAME']
BUSINESS_DIMENSION['Business Unit']
BUSINESS_METRIC['Cost (Storage Backup 10% Surcharge)']
```

When you lookup METRIC or BUSINESS_METRIC values, the result will always be numeric, but most other kinds of field-lookup (dimensions, account groups, tags, and business dimensions) will generally produce text results.

The only exception is the DIMENSION['date'] expression which will always produce a date-time result.

Operators

Existence Operator

When writing an expression that uses these field lookups, the most basic logical test we can perform is the test of existence. The EXISTS operator checks that a text-field with a particular key exists, and has a non-empty value. For example, consider an expression like this:

```
EXISTS TAG['business unit']
```

We can use this expression to test whether a tag named “business unit” exists on this data point. If so, then the expression successfully matches. Likewise, we can use the negated EXISTS operator to match on data-points with no such value:

```
!EXISTS TAG['business unit']
```

Text Operators

These operators allow you to match the text in dimensions, account groups, tags, and business dimensions. You can compare these field-lookup text values with one another, or with literal string values in the expression. Text comparisons are always done in a case-insensitive manner (where the two strings “ABC” vs “abc” are considered equal to one another)

You can check any text for equality using the equality operator (==), or conversely, you can use the inequality operator (!=), to match text that’s not equal, like this:

```
DIMENSION['vendor_account_identifier'] == '123456789012'
DIMENSION['vendor_account_identifier'] != '123456789012'
```

While it’s obvious that you can compare the text in a dimension value to the text in a literal string, you can actually also compare two dimension values to each other, like this:

```
DIMENSION['vendor_account_identifier'] == DIMENSION['account_identifier']
```

You can perform partial text matching, using the three self-explanatory operators STARTS_WITH , ENDS_WITH , and CONTAINS , like this:

```
DIMENSION['item_description'] CONTAINS '-maps-'
DIMENSION['region'] STARTS_WITH 'us-'
DIMENSION['compute_usage_type'] ENDS_WITH 'xlarge'
```

You can also take the logical opposite of any of these operators by including the NOT operator (!) immediately before the operator name, like this:

```
DIMENSION['item_description'] !CONTAINS '-maps-'
DIMENSION['region'] !STARTS_WITH 'us-'
DIMENSION['compute_usage_type'] !ENDS_WITH 'xlarge'
```

You can perform letter case conversion using the operators LOWER and UPPER .

To convert letters to lower case:

```
{

  "matchExpression" : "EXISTS TAG['cost category']",

  "valueExpression" : "LOWER(TAG['cost category'])"

}
```

To convert letters to upper case:

```
{

  "matchExpression" : "EXISTS TAG['cost category']",

  "valueExpression" : "UPPER(TAG['cost category'])"
}
```

You can use the IN operator to match a text value against a comma-delimited list of candidate values, like this:

```
DIMENSION['region'] IN ('us-east-1', 'us-west-1', 'eu-west-1')
'abc-123' IN (TAG['product-code'], BUSINESS_DIMENSION['service-code'])
```

Regular Expression Operators

We provide the FIND operator for use with matchExpressions to match a given text value against a Regular Expression pattern, like this:

```
TAG['created_by'] FIND /[a-z]+@example.com/
```

Regular Expression patterns are always contained within a pair of forward-slash characters (/) and the syntax of the expression conforms with the Pattern syntax, as implemented in the Java Standard Library.

It’s important to note that, since these Regular Expression patterns are always contained within JSON strings, any backslash-escape sequences need to use double-backslashes, like this:

```
TAG['two_words separated_by_whitespace'] FIND /\\w+\\s+\\w+/
```

The FIND operator searches for any instances of the designated Regular Expression within the target string, even if it doesn’t match the entire string. To match the entire string, be sure to include the boundary markers for start of text (^) and end-of-text ($), like this:

```
'abc-xyz' FIND /^[a-z]{3}-[a-z]{3}$/
```

It’s worth reiterating here that all text-comparisons in the expression language are case-insensitive, so we compile all regular expressions in a case-insensitive manner as well.

The FIND operator above purely tests for truth in matchExpressions. We also provide a special operator for valueExpressions to capture string elements described below.

We provide the REPLACE operator for use with valueExpressions such that text elements can be captured using regular expressions and surfaced for your business dimension. The format is very similar to that used with the FIND operator with the notable addition of an extra forward slash character (/). We use standard notation for regex captures such as using closed parenthesis to capture the groups and $1, $2... to reference them. The REPLACE operator is particularly handy where you have multiple concepts delimited within a dimension - often tags - and you want a clean way to extract individual concepts. Let's say we have a tag for ownership which looks something like "TeamAlpha:DepartmentBeta:BusinessCharlie" we could extract and surface the team with the following expression:

```
TAG['ownership'] REPLACE /^(\\w+):.*/$1/
```

The above expression would yield "teamalpha".

REPLACE can support more sophisticated requirements. For example we can handle surfacing multiple captures and join them with regular text. The following expression:

```
TAG['ownership'] REPLACE /^(.+):.+:(.+)/team-$1-business-$2/
```

would yield the value "team-teamalpha-business-businesscharlie"

Join Operator

You can join any two strings of text using the text-combining operator (~), like this:

```
TAG['primary_code'] ~ '-' ~ TAG['secondary_code']
```

In the example above we are joining the strings with '-' placed between them, but you can combine however you like. The text-combining operator is most useful in a valueExpression expression (rather than in the matchExpression), as a way of extracting values from dimensions and tags, to build composite text values assembled from those other bits and pieces.

Numeric and Date-time Operators

Since this expression language allows you to write rules based on METRIC values, which are numeric rather than textual, you’ll need a set of operators for comparing and manipulating numbers.

The set of comparison operators includes: equality (==), inequality (!=), greater-than (>), greater-than-or-equal (>=), less-than (<), and less-than-or-equal (<=). The set of arithmetic operators includes: addition (+), subtraction (-), multiplication (*), division (/), and exponentiation (^).

These examples show how you can create expressions that compare metric values using numeric operators:

```
METRIC['cost_adjusted'] == 0.0
METRIC['on_demand_hours'] != 0.0
METRIC['adjusted_cost'] <= METRIC['Cost']
METRIC['usage_quantity'] >= 100
METRIC['reserved_hours'] >= METRIC['on_demand_hours']
```

These same operators can also be applied to date-time objects, including date-time DIMENSION values, like this:

```
DIMENSION['date'] < '2018-01-01'
DIMENSION['date'] >= '2017-04-10T10:10:10'
DIMENSION['date'] == '2017-10-31T00:00:00.000Z'
```

Logical Operators and Parentheses

Finally, within any matchExpression, you can use logical operators like AND (&&), OR (||), and NOT (!) to apply Boolean logic to your sub-expressions, like this:

```
DIMENSION['region'] == 'us-east-1' && TAG['Environment'] != 'staging'
```

By default, these Boolean expressions follow the same order-of-operations as standard programming languages (like Java or Python), and also like those languages, you can wrap sub-expressions in parentheses to clarify or override the default logical ordering:

```
!(

  DIMENSION['compute_usage_type'] !STARTS_WITH 'm'

  &&
  (

	TAG['Environment'] == 'production'

	||

	TAG['Environment'] == 'staging'

  )
)
&&
EXISTS BUSINESS_DIMENSION['Business Unit']
```

---

## Business Mapping Templates

<!-- sub-header -->
- **breadcrumb:** Cloudability API > Business Mappings End Point > Business Mapping Templates
- **source_path:** SSVCLNQ/api-v3/business_mapping_templates.html
- **original_file:** point-business-mapping-templates.md
- **images:** []

## Business Mapping Templates

Business Mapping Dimensions

Sample Mapping of a Business Dimension for Compliance

There are a number of attributes of a cloud spend item that you could use to describe it as a compliant or not. For example is it of a compliant instance type, have the right tags applied or exit in a compliant region? Here is an example for region compliance.

```
  {
    "name": "Region Compliance",
    "defaultValue": "Non Compliant",
    "statements": [
      {
        "matchExpression": "!EXISTS DIMENSION['region']",
        "valueExpression": "'Not Applicable'"
      },
      {
        "matchExpression": "DIMENSION['region'] == 'ap-southeast-2'",
        "valueExpression": "'Compliant'"
      },
      {
        "matchExpression": "DIMENSION['region'] == 'us-west-2'",
        "valueExpression": "'Compliant'"
      },
      {
        "matchExpression": "DIMENSION['region'] == 'eu-west-1'",
        "valueExpression": "'Compliant'"
      }
    ]
 }
```

Sample Mapping of a Business Dimension for Chargeback - Canonical List of Tag Values

Many organizations will use an ITSM tool such as Service Now to keep a catalog of official chargeback/application codes. We can utilize these within mappings to create logical groupings. Note below that we explicitly categorize costs which are tagged but aren't a member of the canonical list.

```
{
  "name": "Business Application",
  "defaultValue": "Untagged",
  "statements": [
    {
      "matchExpression": "TAG['Movie'] == 'Coco' || TAG['Movie'] == 'Brave' || TAG['Movie'] == 'A Bugs Life'",
      "valueExpression": "'Pixar Original'"
    },
    {
      "matchExpression": "TAG['Movie'] CONTAINS 'Toy Story' || TAG['Movie'] CONTAINS 'The Incredibles'",
      "valueExpression": "'Pixar Series'"
    },
    {
      "matchExpression": "TAG['Movie'] == 'Shrek' || TAG['Movie'] == 'Kung Fu Panda'",
      "valueExpression": "'Dreamworks'"
    },
    {
      "matchExpression": "EXISTS TAG['Movie']",
      "valueExpression": "'Non Canonical Value'"
    }
  ]
}
```

Sample Mapping of a Business Dimension for Chargeback - Use Tag Value if Exists, Fall Back to Account

We see a number of our customers take this approach. The goal, as always, is to have every dollar spent allocated. Tagging will be the primary mechanism for allocation, but 'account owners' will be responsible for items that fall between the cracks. Note below how we explicitly default to 'Unallocated' for items that aren't picked up by the statements. These items could then be addressed with further statements focused on account ownership, a different tag or a completely different billing attribute.

```
{
  "name": "Business Unit",
  "defaultValue": "Unallocated",
  "statements": [
    {
      "matchExpression": "EXISTS TAG['Business']",
      "valueExpression": "TAG['Business']"
    },
    {
      "matchExpression": "DIMENSION['vendor_account_identifier'] == '123456789012'",
      "valueExpression": "'Business Unit A'"
    },
    {
      "matchExpression": "DIMENSION['vendor_account_identifier'] == '888844442222'",
      "valueExpression": "'Business Unit B'"
    },
    {
      "matchExpression": "DIMENSION['vendor_account_identifier'] == '666633331111'",
      "valueExpression": "'Business Unit C'"
    }
  ]
}
```

Business Mapping Metrics

Sample Mapping of a Business Metric to Contextualize Spend in Unit Economic Terms

Users have reporting questions that are specific to their business when understanding Cloud costs. Being able to contextualize Cloud spending against business specific KPIs (like "cost per X") to visualize trends will enable stakeholders to make decisions based on data that is meaningful to the business. For example, understanding your Cloud spend as a cost per million daily active users.

```
{
    "name": "Cost (Per Million DAU)",
    "numberFormat": "currency",
    "preMatchExpression": "",
    "defaultValueExpression": "",
    "statements": [
        {
            "matchExpression": "DIMENSION['date'] == '2019-01-01'",
            "valueExpression": "METRIC['unblended_cost'] / 68989980 * 1000000"
        },
        {
            "matchExpression": "DIMENSION['date'] == '2019-01-02'",
            "valueExpression": "METRIC['unblended_cost'] / 70901268 * 1000000"
        },
        {
            "matchExpression": "DIMENSION['date'] == '2019-01-03'",
            "valueExpression": "METRIC['unblended_cost'] / 68336154 * 1000000"
        }
    ]
}
```

Sample Mapping of a Business Metric to Build in a Surcharge

Build in and surface costs inclusive of management fees, provided services, licensing fees or any other costs incurred - captured in a single in-app metric.

For example: create a surcharge (markup / upcharge) for all storage backups managed on behalf of external and/or internal customers.

```
{
 "name": "Cost (Storage Backup 10% Surcharge)",
 "kind": "BUSINESS_METRIC",
 "numberFormat": "currency",
 "preMatchExpression": "(DIMENSION['vendor'] == 'amazon' && DIMENSION['usage_family'] == 'storage'",
 "defaultValueExpression": "METRIC['unblended_cost']",
 "statements": [{
   "matchExpression": "DIMENSION['invoice_date'] == '2019-09-01' && DIMENSION['transaction_type'] == 'usage' && DIMENSION['usage_type'] CONTAINS 'snapshot'",
   "valueExpression": "METRIC['unblended_cost'] * 1.10"
  },
  {
   "matchExpression": "DIMENSION['invoice_date'] == '2019-10-01' && DIMENSION['transaction_type'] == 'usage' && DIMENSION['usage_type'] CONTAINS 'snapshot'",
   "valueExpression": "METRIC['unblended_cost'] * 1.10"
  },
  {
   "matchExpression": "DIMENSION['invoice_date'] == '2019-11-01'  && DIMENSION['transaction_type'] == 'usage' && DIMENSION['usage_type'] CONTAINS 'snapshot'",
   "valueExpression": "METRIC['unblended_cost'] * 1.10"
  }]
}
```

---

## Common Dimension Keys

<!-- sub-header -->
- **breadcrumb:** Cloudability API > Business Mappings End Point > Common Dimension Keys
- **source_path:** SSVCLNQ/api-v3/appendix.html
- **original_file:** point-common-dimension-keys.md
- **images:** []

## Common Dimension Keys

This is a list of the most popular DIMENSION keys currently available to use in the expression language. The attribute names are the standard names you use when interacting with these dimensions through all of Cloudability 's API end points. It's worth drawing special attention to how account IDs and account names are handled. For the account/subscription where the expense occurred make sure you include the 'vendor_' prefix. If you don't it will be referring to the associated master payer.

To manage rule changes between dates use the date API attribute. Note that even though we will accept date strings which include a time component we will always resolve these back to the day itself. i.e statements are evaluated at the day level and no-intra day logic applies.

| API Attribute | Description | UI Path* | Example Values | Comments |
| --- | --- | --- | --- | --- |
| container_namespace | Container Namespace cost was associated with | Containers/Namespace | "Team A" |  |
| container_cluster_name | Container Cluster resource cost belongs to | Containers/Cluster Name | "Production Cluster" |  |
| date | The date the expense was incurred | Time/Date | "2018-02-09","2018-02-09T09:00:00Z" | You can provide a date or date-time string. We resolve back to date. |
| day_of_week | what day of the week the cost was incurred | Time/Day of Week | "Thursday" |  |
| enhanced_service_name | The Cloudability name for the vendor service | Vendor/Service Name | "AWS EC2", "Azure Compute", "AWS EBS" | A synthetic and predictable dimension provided by Cloudability |
| engine | Database, data warehouse or cache engine | Usage/Engine | "MySQL", "PostgreSQL", "Memcached", "SQL SERVER" |  |
| instance_category | The category for the instance's family is within | Usage/Instance Category | Compute Optimized, General Purpose, Memory Optimized |  |
| instance_family | The family the instance falls within | Usage/Instance Family | "c5", "r5", "t2", "m3" |  |
| instance_size | The size of the instance | Usage/Instance Size | "large", "nano", "10xlarge" |  |
| instance_type | The full instance type string for the instance. A user friendly representation across vendors and services | Usage/Instance Type | "c5.large", "Standard_E4_v3", "t2.nano" | For RDS we remove the 'db.' prefix to achieve consistency |
| item_description | The detailed description provided by the vendor for the line item | Vendor/Item Description | $0.80 per On Demand Linux m4.4xlarge Instance Hour |  |
| lease_type | Lease type for the instance | Usage/Lease Type | "On Demand", "Reserved", "Spot" |  |
| offering_class | The offering class of the RI applied | Reservation Class | "Standard", "Convertible" | Only applicable to instance hours covered by RIs |
| operating_system | The Operating System for Instance | Usage/Operating System | "Linux", "Windows" |  |
| operation | Descriptive dimension provided by AWS | Usage/Operation | "RunInstances", "GetMetricData" |  |
| reservation_identifier | The unique ID for the reservation | Usage/Reservation ID | "93d06157-7eaa-419a-8a54-0a85bb0864f3" | Applies to Sign Up charges, recurring items and instance hours that consume RIs. |
| region | The official vendor region | Vendor/Region | "ap-southeast-2", "us-eas-2", "australiasoutheast" | Region names are specific to vendor |
| region_zone | The AZ provided by the vendor | Vendor/Availability Zone | "ap-southeast-2a", "us-east-1b" |  |
| resource_identifier | The unique ID for the resource provided by the vendor | Usage/Resource ID | "i-a37ef5dcf51cd8c1a", "vol-0o873bca0f2d0c898" |  |
| seller | Who sold the service | Vendor/Seller | "AWS Marketplace", "Amazon", "Azure" | A synthetic dimension to describe who actually sold the service, special focus on marketplace |
| service_name | The name of the service as provided by the vendor. For a easier and normalised version use enhanced_service_name instead | Vendor/Product Name | "Amazon Elastic Compute Cloud", "Microsoft.Compute", "Microsoft.Storage" |  |
| tenancy | The tenancy for EC2 instances | Tenancy | "shared", "host", "dedicated" | see AWS docs |
| transaction_type | The high level type of transaction | Usage/Transaction Type | "usage", "recurring", "one-time" |  |
| usage_family | The family of usage | Usage/Usage Family | "Instance Usage", "Data Transfer", "Storage", "Load Balancer Usage", "Support" | A synthetic dimension that describes the type of usage across cloud services |
| usage_type | Detailed descriptive dimension as provided by vendor | Usage/Usage Type | "APS2-EBS:VolumeUsage.gp2", "APS2-BoxUsage:m4.2xlarge" |  |
| vendor | The cloud vendor name | Vendor/Vendor | "Amazon", "Azure" |  |
| vendor_account_identifier | The unique identifier the vendor provides for the account or subscription where the cost occurred. | Vendor/Account ID | "111122223333" for AWS "0d3d81f1-41f9-4f1a-8b3c-856b6822ff4f" for Azure | No dashes '-' between digits for AWS, however they are required for Azure. |
| vendor_account_name | The name of the account or subscription that you have set in the cloud vendor. | Vendor/Account Name | Production Account, Cyril Rioli's Account, Client Services | A simple string as you entered with the vendor |

---

## Multiple Rules Working Together

<!-- sub-header -->
- **breadcrumb:** Cloudability API > Business Mappings End Point > Multiple Rules Working Together
- **source_path:** SSVCLNQ/api-v3/multiple_rules_working_together.html
- **original_file:** point-multiple-rules-working-together.md
- **images:** []

## Multiple Rules Working Together

Most organization will have multiple Business Mappings, working together as a set. You can even have some Business Mappings that depend upon the output (the resultant Business Dimension or Business Metric) of other Business Mappings.

The Mapping Rule engine knows how to solve the hierarchy of dependencies between those rules, validating that the entire set of rules for any given organization actually make sense together, without stepping on one another’s toes, and rejecting any new Tag Rules that violate those constraints.

Unique Names

For example, it doesn’t make sense to have two different rules with the same name and the API will return a 400 error if you attempt this.

Preventing Cyclic Dependencies

The Mapping Rule engine allows some rules to depend on the output of other rules, and it automatically figures out how to evaluate rules in the correct order, so that you don’t need to worry about it.

Examples

In the Business Dimension example below, the rule for mapping ABC depends on the value of BUSINESS_DIMENSION['XYZ'] , which depends on TAG['AppServiceId'] .

```
[
  {
    "name": "ABC",
    "index": 1,
    "defaultValue": "Unallocated",
    "statements": [
      {
        "matchExpression": "EXISTS BUSINESS_DIMENSION['XYZ']",
        "valueExpression": "BUSINESS_DIMENSION['XYZ']"
      }
    ]
  },
  {
    "name": "XYZ",
    "index": 2,
    "defaultValue": "Unallocated",
    "statements": [
      {
        "matchExpression": "EXISTS TAG['AppServiceId']",
        "valueExpression": "TAG['AppServiceId']"
      }
    ]
  }
]
```

The Mapping Rule engine is smart enough to know that it needs to lookup the TAG['AppServiceId'] value first, and then use that value to calculate BUSINESS_DIMENSION['XYZ'] , and finally to use that value to calculate BUSINESS_DIMENSION['ABC'] . You don’t have to do anything special to force the correct ordering. The Mapping Rule engine does it for you.

But if you define rules whose dependency chain creates an infinite loop, then the engine will reject those rules when you attempt to create them. The next example illustrates this point:

```
[
  {
    "name": "ABC",
    "index": 1,
    "defaultValue": "Unallocated",
    "statements": [
      {
        "match": "EXISTS BUSINESS_DIMENSION['XYZ']",
        "name": "BUSINESS_DIMENSION['XYZ']"
      }
    ]
  },
  {
    "name": "XYZ",
    "index": 2,
    "defaultValue": "Unallocated",
    "statements": [
      {
        "matchExpression": "EXISTS BUSINESS_DIMENSION['ABC']",
        "valueExpression": "BUSINESS_DIMENSION[ABC]"
      }
    ]
  }
]
```

In this example, we’ve created a rule that calculates BUSINESS_DIMENSION['ABC'] based upon the value of BUSINESS_DIMENSION['XYZ'] . But the other rule, which calculates BUSINESS_DIMENSION['XYZ'] depends upon the value of BUSINESS_DIMENSION['ABC'] .

On their own, each of these rules looks valid, but when we try to combine them into a cohesive rule-set, they create an infinite dependency loop upon one another, and the Mapping Rule engine will reject them.

Similar to the above example, in the context of Business Metrics, the example below highlights how you can use the output value from one Business Metric as input to a new custom metric.

```
{
	"name": "Cost (Per XYZ)",
	"numberFormat": "currency",
	"preMatchExpression": "",
	"defaultValueExpression": "METRIC['unblended_cost']",
	"statements": [{
			"matchExpression": "DIMENSION['date'] == '2019-01-01'",
			"valueExpression": "METRIC['unblended_cost'] / 34989890"
		},
		{
			"matchExpression": "DIMENSION['date'] == '2019-01-02'",
			"valueExpression": "METRIC['unblended_cost'] / 35901234"
		},
		{
			"matchExpression": "DIMENSION['date'] == '2019-01-03'",
			"valueExpression": "METRIC['unblended_cost'] / 34336077"
		}
	]
}
```

In this unit economics use case example, we are starting out by calculating the "cost per XYZ" where this could be cost per number of active users, or cost per ride share, cost per subscription, etc ...

We can then take those results and further contextualize our Cloud spend by surfacing the "cost per XYZ" in terms of FTEs (full time engineers). For example:

```
{
	"name": "Cost in FTEs (Per XYZ)",
	"numberFormat": "number",
	"preMatchExpression": "",
	"defaultValueExpression": "METRIC['unblended_cost']",
	"statements": [{
			"matchExpression": "DIMENSION['date'] == '2019-01-01'",
			"valueExpression": "BUSINESS_METRIC['Cost (Per XYZ)'] / 120000"
		},
		{
			"matchExpression": "DIMENSION['date'] == '2019-01-02'",
			"valueExpression": "BUSINESS_METRIC['Cost (Per XYZ)'] / 120000"
		},
		{
			"matchExpression": "DIMENSION['date'] == '2019-01-03'",
			"valueExpression": "BUSINESS_METRIC['Cost (Per XYZ)'] / 120000"
		}
	]
}
```

---

## Structure of a Business Mapping

<!-- sub-header -->
- **breadcrumb:** Cloudability API > Business Mappings End Point > Structure of a Business Mapping
- **source_path:** SSVCLNQ/api-v3/structure_of_a_business_mapping.html
- **original_file:** point-structure-business-mapping.md
- **images:** []

## Structure of a Business Mapping

The Structure of a Business Mapping

The JSON payload that is used to define a Business Mapping is called a Mapping Rule. A basic Mapping Rule looks like this

```
{
  "name": "Continent",
  "defaultValue": "Unallocated",
  "statements": [
    {
      "matchExpression": "DIMENSION['region'] STARTS_WITH 'us-'",
      "valueExpression": "'United States'"
    },
    {
      "matchExpression": "DIMENSION['region'] STARTS_WITH 'eu-'",
      "valueExpression": "'Europe'"
    }
  ]
}
```

Every Mapping Rule is defined with a meaningful name (as this is the label the resultant Business Dimension or Business Metric will take throughout Cloudability reports), a sequence of statements for testing different match conditions, and a defaultValue which only applied when none of the statements could be successfully matched.

The Expression Language

We have created a DSL especially so that you can to define the matchExpression and valueExpression fields in your Mapping Rules elegantly, and the syntax is pretty simple. If you’ve ever written code in Java, JavaScript, Ruby, Python, or any other popular programming language, the concepts of our expression language should be pretty familiar. Even if you haven't it's very straightforward to create these expressions and Cloudability will provide plenty of examples. For detailed information on the expression language checkout Business Mapping Expression Language .

The Business Dimension

```
{
  "name": "ATUM - Towers",,
  "kind": "BUSINESS_DIMENSION",
  "defaultValue": "Unmapped",
  "statements": [{
      "matchExpression": "(DIMENSION['service_name'] CONTAINS 'Network' || DIMENSION['enhanced_service_name'] CONTAINS 'Network')",
      "valueExpression": "'Network'"
    },
    {
      "matchExpression": "DIMENSION['enhanced_service_name'] == 'AWS EBS' || DIMENSION['enhanced_service_name'] == 'Azure Storage' || DIMENSION['enhanced_service_name'] == 'GCP Cloud Storage' || DIMENSION['enhanced_service_name'] == 'AWS S3'",
      "valueExpression": "'Storage'"
    },
    {
      "matchExpression": "(DIMENSION['enhanced_service_name'] == 'AWS EC2' || DIMENSION['enhanced_service_name'] == 'Azure Compute' || DIMENSION['enhanced_service_name'] == 'AWS ECS' || DIMENSION['enhanced_service_name'] == 'AWS Lambda')",
      "valueExpression": "'Compute'"
    }
  ]
}
```

Name

The name field indicates the unique identifier for all the Business Dimension values generated by this rule. Just like Vendor Tags are key/value pairs with unique names for each key, Business Dimensions are also key/value pairs, and this field defines the keys in those key/value pairs.

Statements

Every Mapping Rule also defines an ordered sequence of statements .

Each statement in a Mapping Rule contains two different expressions, written using our custom expression language (described later in this document): the matchExpression is like a test, which will be evaluated as either true or false for every data-point, and the valueExpression evaluates to a string of text representing the value for the resultant Business Dimension.

At runtime, we evaluate each of these statements, sequentially (i.e. from top to bottom), and when we find a matchExpression that actually matches, we evaluate the corresponding valueExpression expression to generate a text value for the resultant Business Dimension.

Comparing our expression language to other programming languages you might have used before, it’s helpful to think of the matchExpression as being like an if statement and the valueExpression as being like a then statement .

In particular, we only calculate the result value of the valueExpression for statements with a matching matchExpression .

Default Values

If we step through the complete list of statements for a line item and don't find a matching matchExpression , then we use the defaultValue defined at the top-level of the rule as the text-value of this item. Some good examples of default values could be 'Unallocated', 'Non Compliant', 'Not Applicable' etc. i.e chose something that is specific to the Business Dimension you are creating.

Type of Business Mapping

The kind attribute represents the declaration that we are defining a Business Dimension versus a Business Metric for our Business Mapping construct

The Business Metric

```
{
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
    }
  ]
}
```

Name

The name field indicates the unique identifier for the Business Metric values generated by the Business Mapping statement rules you have defined. Every Business Metric created requires a name; ideally it should reflect the business context that you are trying to share and be descriptive such that users will quickly make sense of it. The name provided for the custom metric will appear in Cloudability reports and dashboards.

Statements

Every Business Metric also defines an ordered sequence of Business Mapping statements .

The statements defined for a Business Metric contain two different expressions, written using our custom expression language. the matchExpression is like a test, which will be evaluated as either " True " or " False " for every data-point. and the valueExpression is arithemetically evaluated to a decimal value. At runtime, we evaluate each of these statements sequentially (i.e. from top to bottom), and when we have a matchExpression that results in "match", the corresponding valueExpression expression is then evaluated to generate a decimal value for the custom metric. You can think of the matchExpression as being like an " if statement " and the valueExpression as being like a " then statement ".

Number Format

In addition to a name, the custom metric you create will be evaluated to a number and surfaced as currency or a regular decimal number. The use case driving this custom metric will help you decide on the appropriate number format. For example: if your usecase is to provide a surcharge for management fees, then the custom metric format will be currency.

Default Values

The defaultValueExpression is defined at the top-level and represents the value for this Business Metric if, after stepping through the complete list of Business Mapping statements for a Business Metric, we don't find any data points that match the defined matchExpression (s). The defaultValueExpression should be consistent with the type of Business Metric being created.

Pre-Match Expression

The expression declared in the preMatchExpression section is evaluated first; then expressions are evaludated in the statements section. If no matches are found for the expression defined within the preMatchExpression , then we immediately jump to the defaultValueExpression , skipping the statements section. The preMatchExpression represents a centralized/global expression which is evaluated before all other defined expressions contained within statements section; It can be left empty (without a defined expression).

Type of Business Mapping

The kind attribute represents the declaration that we are defining a Business Metric versus a Business Dimension for our Business Mapping construct

---

## Calculated Metrics End Point

<!-- sub-header -->
- **breadcrumb:** Cloudability API > Calculated Metrics End Point
- **source_path:** SSVCLNQ/api-v3/calculated_metrics_end_point.html
- **original_file:** api-calculated-metrics-end-point.md
- **images:** []

## Calculated Metrics End Point

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

---

## Cloud Sustainability End Points

<!-- sub-header -->
- **breadcrumb:** Cloudability API > Cloud Sustainability End Points
- **source_path:** SSVCLNQ/api-v3/cloud-sustainability-api.html
- **original_file:** api-cloud-sustainability-end-points.md
- **images:** []

## Cloud Sustainability End Points

The Cloud sustainability API endpoint can be used to retrieve sustainability metrics.

End Point Detail

Sustainability metrics follow all the API functionality supported by the Cost Reporting Endpoint . For sustainability metrics information, we are adding two new metrics: carbon_emissions and kwh_consumption

Example Sustainability Report Object

Retrieve a list of sustainability metrics by performing a GET request at the reporting endpoint.

Example Request

```
curl 'https://api.cloudability.com/v3/reporting/cost/run?start_date=2024-08-01&end_date=2024-08-28&dimensions=region&metrics=total_amortized_cost,carbon_emissions,kwh_consumption,embodied_emissions,operational_emissions&filters=region[]=us-east-1,us-west-2’ -u ‘[auth_token]
```

Example Response

```
 {
  "results": [],
  "meta": {
    "dates": {
      "start": "2024-08-01T00:00:00Z",
      "end": "2024-08-28T00:00:00Z"
    },
    "filters": [
      {
        "comparator": "[]=",
        "value": "us-east-1,us-west-2’",
        "measure": {
          "name": "region",
          "label": "Region",
          "description": "The region in which a resource exists or a usage charge occurred, for example: us-east-1 for AWS, US East for Azure, us-east1 for GCP and us-ashburn-1 for OCI.",
          "data_type": "string",
          "type": "dimension",
          "group": {
            "ID": 2,
            "Key": "billing",
            "Name": "Billing"
          },
          "sub_group": {
            "ID": 7,
            "Key": "vendor",
            "Name": "Vendor"
          }
        }
      }
    ],
    "metrics": [
      {
        "name": "total_amortized_cost",
        "label": "Cost (Amortized)",
        "description": "This is an “accrual” cost metric, representing the consumed cost during any period. This metric is handy for ensuring commitments are allocated to the time and place they are consumed.",
        "data_type": "currency",
        "type": "metric",
        "group": {
          "ID": 2,
          "Key": "billing",
          "Name": "Billing"
        },
        "sub_group": {
          "ID": 3,
          "Key": "costs",
          "Name": "Costs"
        }
      },
      {
        "name": "carbon_emissions",
        "label": "Estimated Carbon Emissions (MTCO2e)",
        "description": "Estimated Carbon emissions by a resource in metric tons of carbon dioxide equivalent - MTCO2e",
        "data_type": "float",
        "type": "metric",
        "group": {
          "ID": 2,
          "Key": "billing",
          "Name": "Billing"
        },
        "sub_group": {
          "ID": 14,
          "Key": "sustainability",
          "Name": "Sustainability"
        }
      },
      {
        "name": "kwh_consumption",
        "label": "Power Consumed (kWh)",
        "description": "Power consumed by a resource in Kilo Watt Hours - kWh",
        "data_type": "float",
        "type": "metric",
        "group": {
          "ID": 2,
          "Key": "billing",
          "Name": "Billing"
        },
        "sub_group": {
          "ID": 14,
          "Key": "sustainability",
          "Name": "Sustainability"
        }
      }
    ],
    "dimensions": [
      {
        "name": "region",
        "label": "Region",
        "description": "The region in which a resource exists or a usage charge occurred, for example: us-east-1 for AWS, US East for Azure, us-east1 for GCP and us-ashburn-1 for OCI.",
        "data_type": "string",
        "type": "dimension",
        "group": {
          "ID": 2,
          "Key": "billing",
          "Name": "Billing"
        },
        "sub_group": {
          "ID": 7,
          "Key": "vendor",
          "Name": "Vendor"
        }
      }
    ],
    "aggregates": [
      {
        "name": "total_amortized_cost",
        "label": "Cost (Amortized)",
        "description": "This is an “accrual” cost metric, representing the consumed cost during any period. This metric is handy for ensuring commitments are allocated to the time and place they are consumed.",
        "data_type": "currency",
        "type": "metric",
        "value": "0"
      },
      {
        "name": "carbon_emissions",
        "label": "Estimated Carbon Emissions (MTCO2e)",
        "description": "Estimated Carbon emissions by a resource in metric tons of carbon dioxide equivalent - MTCO2e",
        "data_type": "float",
        "type": "metric",
        "value": "0"
      },
      {
        "name": "kwh_consumption",
        "label": "Power Consumed (kWh)",
        "description": "Power consumed by a resource in Kilo Watt Hours - kWh",
        "data_type": "float",
        "type": "metric",
        "value": "0"
      }
    ]
  },
  "offset": 0,
  "pagination": {},
  "limit": 0,
  "total_results": 0
}
```

---

## Cloudability Workload Planning  API End Points

<!-- sub-header -->
- **breadcrumb:** Cloudability API > Cloudability Workload Planning  API End Points
- **source_path:** SSVCLNQ/api-v3/workload-planning-api-endpoints.html
- **original_file:** api-cloudability-workload-planning-end-points.md
- **images:** []

## Cloudability Workload Planning API End Points

Workload Planning API end points can be used to create, manage your workloads, add resources and update Workload Planning Preferences.

If you wish to see the allowed values when importing multiple resources via JSON file, refer to Uploading multiple resources for a given workload.

Use Cases

1. Creating a workload
1. Uploading multiple resources for a given workload
1. Generating a recommendation and saving a recommendation
1. Exporting workload to csv
1. Duplicating workload
1. Deleting workload

Creating a workload and getting a workload ID

You will need to define your workload preferences and common information as a start.

Once validated, you will get the workload ID that will be required as a parameter for the next APIs.

```
curl -X 'POST' \ 'https://api.cloudability.com/v3/workload' \
-u '<Token Generated>' \
-H 'Content-Type: application/json' \
-d @- << EOF
		
```

```
{
  "name": "test workload",
  "description": "test desc",
  "group": "test_group",
  "csp": [
    {
      "vendor": "OCI",
      "region": "ap-melbourne-1,ap-sydney-1,ca-montreal-1,sa-saopaulo-1,sa-vinhedo-1",
      "leaseType": "ONDEMAND",
      "discountEnabled": false,
      "upliftEnabled": false,
      "discountDesc": "",
      "discountPercent": 0
    },
    {
      "vendor": "GCP",
      "region": "asia-east1,asia-east2,asia-northeast1,asia-northeast2,asia-northeast3",
      "leaseType": "SPOT",
      "commitmentTerm": "3 YEAR",
      "paymentOptions": "NO UPFRONT",
      "discountEnabled": false,
      "upliftEnabled": false,
      "discountDesc": "",
      "discountPercent": 0,
      "sudEnabled": true
    },
    {
      "vendor": "AZURE",
      "region": "asia-pacific-east,asia-pacific-southeast,australia-central,australia-central-2",
      "leaseType": "COMMITTED",
      "computeOffering": "RESERVED_INSTANCES",
      "commitmentTerm": "1 YEAR",
      "paymentOptions": "FULL UPFRONT",
      "discountEnabled": false,
      "upliftEnabled": false,
      "discountDesc": "",
      "discountPercent": 0
    },
    {
      "vendor": "AWS",
      "region": "ap-northeast-1,eu-west-1,us-east-1,us-west-2",
      "leaseType": "ONDEMAND",
      "computeOffering": "EC2",
      "commitmentTerm": "1 YEAR",
      "paymentOptions": "PARTIAL UPFRONT",
      "discountEnabled": false,
      "upliftEnabled": false,
      "discountDesc": "",
      "discountPercent": 0
    }
  ],
  "status": "IN_PROGRESS"
}
```

Response Object

| Key | Required | Description |
| --- | --- | --- |
| "name" | Yes | string |
| "description" | No | string |
| "group" | No | ( not used currently ) |
| "vendor" | Yes | string allowed values: "AWS", "Azure", "GCP", "OCI" |
| "region" | Yes | string Please note that you can use the API below to get the list of the available regions: curl-X'GET'\ 'https://api.cloudability.com/v3/workload/static-data' \ -u '<Token Generated>' |
| "leaseType" | Yes | string allowed values for AWS, GCP, AZURE: "COMMITTED", "ONDEMAND", "SPOT" Allowed values for OCI: "ONDEMAND", "CAPACITY_RESERVATION", "SPOT" |
| "computeOffering" | Yes | string allowed values for AWS: "COMPUTE", "EC2", "STANDARD_RI", CONVERTIBLE _RI" allowed values for Azure: "RESERVED_INSTANCES", "COMPUTE" Please note that for Azure, "COMPUTE" is currently used for Savings Plan. This value will be updated soon. |
| "CommitmentTerm" | Yes | string allowed values: "1 YEAR", "3 YEAR" |
| paymentOptions | Yes | String allowed values for AWS: "NO UPFRONT", "ALL UPFRONT", "PARTIAL UPFRONT" allowed values for AZURE: "NO UPFRONT", "ALL UPFRONT" allowed value for GCP: "NO UPFRONT" |
| "subEnabled" | Yes | boolean This field corresponds to Sustained Use Discount for GCP - the true value means that GCP costs will get SUD applied. It is not used for AWS and Azure. |
| "status" | Yes | string allowed values: "IN_PROGRESS,IN_REVIEW,APPROVED,READY_FOR_REVIEW" |
| "preferredCsp" | Yes | string allowed values: Any CSP from the vendor selected This field determines which could provider is your preferred one in case of multi-cloud comparison and it can be updated later. |

Uploading multiple resources for a given workload

We currently support both JSON and XLSX format to upload multiple resources / requirements for your workload.

A. Download an example of file (template) or the list of existing resources

Example Request

```
curl -X 'GET' \
'https://api.cloudability.com/v3/workload/{download-type}/{format}/export/{workload-id}' \
-H 'accept: application/hal+json' \
-u '<Token Generated>'
```

| Key | Required | Description |
| --- | --- | --- |
| Workload-ID | Yes | string - should be in uuid format |
| Download-type | Yes | string allowed values: “template” (if you want a JSON or XLSX file example) or “resources” (if you want to get the list of existing resources in your workload) |
| format | Yes | string allowed values: "json" or "xlsx" |

B. Description of required keys for each service type while adding resources in the JSON or XLSX file

Virtual Machine

| Key | Required | Description |
| --- | --- | --- |
| "name" | Yes | string |
| "cpu" | Yes | integer |
| "ram" | Yes | integer - amount of memory (GB) |
| "gpuCount" | No | integer |
| "os":"string", | Yes | string allowed values: "Windows", "Linux", |
| "cspOverride":{ "vendor":"string", "region":"string", "regionType":"string" | No | If don't want to use it, you can have an empty or null value. If you find the list of VM resources using the GET API below. For url param: use the vendor name and the region. curl -X POST 'https://api.cloudability.com/v3/internal/virtual-machine/instance' \ --header 'Authorization: <Token Generated>'' \ --header 'Content-Type: application/json' \ --data '{"vendor":"<vendor>","region":"<region>"}' |
| "localStorage" | No | integer |
| "tenancy" | Yes | string allowed values: "SHARED", "DEDICATED" |
| "networkGb" | Yes | integer |
| "upTime" | Yes | integer |
| "quantity" | Yes | Integer - number of VMs |
| "byol" | Yes | boolean allowed values: "true", "false" |
| "deplyomentOption" | Yes | string allowed values: "SINGLE-AZ", "MULTI-AZ" It is only used for AWS, but the value needs to be provided for |
| " blockStorage " { "name": "string", "storageType": " integer", "storageGb": " integer", "iops": " integer", "throughput": " integer", "snapshotGb": " integer", "quantity": " integer" } } | No | Allowed values for storage type: “SSD” or “HDD” Note: Block storage needs to have a name provided The quantity should be the same as the number of VMs (VM quantity) |
| "cspOverride": { "vendor": "string", "region": "string", "resourceType": "string" | No | If don't want to use it, you can have an empty or null value. You can find the list of instances using the GET API below. For url param: use "block" and the vendor name curl -X 'GET' \ 'https://api.cloudability.com/v3/workload/storage/instance/{vendor}?serviceType=block' \ -u '<Token Generated>' |

Managed Database

| Key | Required | Description |
| --- | --- | --- |
| "name" | Yes | string |
| "cpu" | Yes | integer |
| "ram" | Yes | integer |
| "license" | Yes | string allowed values: "MySQL", "PostgreSQL", "SqlServer" |
| "cspOverride": { "vendor": "string", "region": "string", "resourceType": "string | No | If don't want to use it, you can have an empty or null value. You can find the list of database resources using the GET API below. For url param: use the vendor name and the region. curl -X POST 'https://api.cloudability.com/v3/internal/managed-database/instance' \ --header 'Authorization: <Token Generated>'' \ --header 'Content-Type: application/json' \ --data '{"vendor":"<vendor>","region":"<region>"}' |
| "localStorage" | No | integer |
| "tenancy" | Yes | string This field is not used. |
| "networkGb" | No | integer |
| "upTime" | Yes | integer |
| "quantity" | Yes | Integer |
| "byol" | Yes | boolean Default value is "false" |
| "deploymentOption" | Yes | string allowed values: "SINGLE-AZ", "MULTI-AZ" It is only used for AWS, but the value needs to be provided for every vendor. |
| "storageType": " integer", "storageGb": " integer", "iops": " integer", "throughput": " integer", "snapshotGb": " integer", "quantity": " integer", "cspOverride": { "vendor": "", "region": "", "resourceType": "" } } | No | Block storage is optional and the attributes below are only mandatory if you wish to attach block storage to your Database. Allowed values for storage type: “SSD” or “HDD” Note: Block storage needs to have a name provided The quantity should be the same as the number of Managed Database (Managed Database Quantity) “SnapshotGb” corresponds to “Backup Storage” and will be updated soon |

Additional Storage

| Key | Required | Description |
| --- | --- | --- |
| "name" | Yes | string |
| "storageType" | Yes | string allowed values: "SSD" or "HDD" |
| "storageGb" | Yes | integer |
| "quantity" | Yes | integer |
| "iops" | No | integer |
| "throughput" | No | integer |
| "snapshotGb" | No | integer |
| "cspOverride": { "vendor": "string", "region": "string" "resourceType": "string" | No | You can find the list of instances using the GET API below. For url param: use "block" and the vendor name. curl -X 'GET' \ 'https://api.cloudability.com/v3/workload/storage/instance/{vendor}?serviceType=block' \ -u '<Token Generated>' |

Object Storage

| Key | Required | Description |
| --- | --- | --- |
| "name" | Yes | string |
| "storageGb" | Yes | integer |
| "quantity" | Yes | integer |
| "retrievalGb" | Yes | integer |

Load Balancer

| Key | Required | Description |
| --- | --- | --- |
| "name" | Yes | string |
| "bandwidth" | No | integer |
| "processedGb" | Yes | integer |
| "quantity" | Yes | integer |

Other

| Key | Required | Description |
| --- | --- | --- |
| "name" | Yes | string |
| "csp" | Yes | string allowed values: "AWS", "AZURE", "GCP", "OCI" |
| "serviceName" | Yes | string |
| "description" | No | string |
| "cost" | Yes | integer |
| "currency" | Yes | string allowed values: "USD", "GBP", etc |

When importing a JSON or XLSX file, the names of all services need to be present in the file. If no resources/ requirement need to be added for a given service type, it should be present with empty brackets. For example: For load balancer: “loadbalancer”: [].

C. Importing the file to add resources

Example Request

```
curl -X 'POST' \
'https://api.cloudability.com/v3/workload/bulk-upload/{upload-type}{workload-id}' \
-H 'accept: application/json' \
-H 'Content-Type: multipart/form-data' \
-F 'Resource file=@template.json;type=application/json' \
-u '<Token Generated>'
```

| Key | Required | Description |
| --- | --- | --- |
| Workload-ID | Yes | string - should be in uuid format |
| upload-type | Yes | string allowed value "JSON, XLSX" |

D. Getting the resources in error post upload

Example Request

```
curl -X 'GET' \
'https://api.cloudability.com/v3/workload/errors/export/{workload-id}' \
-H 'accept: application/json' \
-u '<Token Generated>'
```

Getting information about the added resources

The GET API below will provide the list of all resources that were recently added, resource ID and additional configuration details.

```
curl -X 'GET' \ 
' https://api.cloudability.com/v3/workload/{workload-id}/resource' \ 
-H 'accept: application/json' \
```

Generating Recommendations

You will need to run a job to generate the recommendation for your resources. The job needs to be executed once per workload, and it would need to be re-run if any requirement is updated later.

Example Request:

```
curl -X 'POST' \ 
'https://api.cloudability.com/v3/workload/job/{workload-ID}' \ 
-u '<Token Generated>' \ 
-d ''
```

Then, you can call the GET API below to check the job status and see if it was successful.

Example Request:

```
curl -X 'GET' \ 
'https://api.cloudability.com/v3/workload/job/status/{workload-ID}' \ 
-u '<Token Generated>' \ 
Request URL
```

Visualizing Recommendations

To get the recommendation for your resources, you will need to enter your workload ID and the vendor as parameters.

You will get the resource ID as well as a recommendation ID that will be used for the next step. The GET API below fives you details about all recommendations across all service types for a given CSP.

Example Request (for AWS):

```
curl -X 'GET' \ 
'https://api.cloudability.com/v3/workload/{workload-ID}/recommendations/aws' \
-u '<Token Generated>'
```

Saving Recommendations

To save each recommendation, you need to provide the resource ID, the recommendation ID, the CSP name and additional fields in the body using the PUT API call below.

For each requirement and each CSP, one recommendation should be saved. There can be a single PUT API call to save all recommendations at once.

The recommendations need to be part of array body for the PUT API call.

Whenever there is a new recommendation available, this PUT API call below needs to be updated accordingly.

Example Request:

```
curl -X 'PUT' \ 
'https://api.cloudability.com/v3/workload/{workload-ID}/cloud-cost' \
-u '<Token Generated>'
-H 'Content-Type: application/json' \
-d '
```

```
[
  {
    "resourceId": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
    "recommendationId": "3fa85f64-5717-4562-b3fc-2c963f66afa7",
    "serviceType": "compute",
    "csp": "AWS"
    "priceType": "ONDEMAND",
    "price": 200,
    "quantity": 100000,
    "additionalInfo": "string",
    "region": "us-west-2"
}
]
```

|  | Required | Description |
| --- | --- | --- |
| resourceID | Yes | string |
| recommendationID | Yes | string |
| serviceType | Yes | string allowed values: "compute", "database", "block_storage", "blob_storage", "network", "other" |
| csp | Yes | string allowed values: "AWS", "AZURE", "GCP" |
| priceType | Yes | string allowed values: "Committed", "ONDEMAND", "SPOT" |
| quantity | Yes | integer |
| additionalinfo | No | This field is not used. |

Viewing Workload

Example Request (Workload "Summary" Tab):

```
curl -X 'GET' \ 
'https://api.cloudability.com/v3/workload/report/summary/{workload-id}?vendor={vendor}' \ 
-u '<Token Generated>'
```

Example Request (Workload "Analysis" Tab):

```
curl -X 'GET' \ 
'https://api.cloudability.com/v3/workload/report/analysis/{workload-id}?vendor={vendor}' \ 
-u '<Token Generated>'
```

Exporting Workload Summary to Excel

Example Request

```
curl -X 'GET' \ 
'https://api.cloudability.com/v3/workload/report/export/{workload-id}' \
-u '<Token Generated>
```

| Key | Required | Description |
| --- | --- | --- |
| WorkloadID | Yes | string - ID provided in the workload endpoint object response |

Example Request

```
curl -X 'GET' \ 
'https://api.cloudability.com/v3/workload/report/export/{workload-id}' \
-u '<Token Generated>'
```

Duplicating workload

Example Request

Perform a GET request at the scorecards end point, specifying a view Id and dimension.

```
curl -X 'POST' \ 'https://api.cloudability.com/v3/workload/duplicate' \
-u '<Token Generated>' \
-H 'Content-Type: application/json' \
-d '{
"id": "string",
"name": "string"
}'
```

| Key | Required | Description |
| --- | --- | --- |
| ID | Yes | string - ID provided in the workload endpoint object response |
| name | Yes | string - name for the workload duplicate |

Deleting Workload

Example Request:

```
curl -X 'DELETE' \ 
'https://api.cloudability.com/v3/workload/{workload-id}' \ 
-u '<Token Generated>'
```

| Key | Required | Description |
| --- | --- | --- |
| WorkloadID | Yes | string - ID provided in the workload endpoint object response |

Getting the List of Workloads

Example Request:

```
curl -X 'GET' \ 
'https://api.cloudability.com/v3/internal/workload?offset={}&limit={}&search={}&user-type={}' \ 
-u '<Token Generated>'
```

| Key | Required | Description |
| --- | --- | --- |
| offset | Yes | int |
| limit | Yes | int |
| search | Yes | string |
| user-type | Yes | string allowed values - all, admin, mine, shared |

Updating Workload Planning Preferences

Workload Planning Preferences can only be updated by Cloudability Admin.

A. Current Workload Planning Preferences

Example Request:

```
curl -X 'GET' \ 
'https://api.cloudability.com/v3/workload/admin-preferences' \ 
-u '<Token Generated>'
```

Preference view feature is available to Admin users and the users who have view preferences permissions.

B. Updating Workload Planning Preferences

Example Request

```
curl -X 'PUT' \ 
'https://api.cloudability.com/v3/workload/admin-preferences' \ 
-u '<Token Generated>' \ 
-H 'Content-Type: application/json' \ 
-d '
```

```
'{
    "preferences": [
  { 
    "vendor": "string",
    "allowed": true,
    "onDemandEnabled": true,
    "committedEnabled": true,
    "spotEnabled": true,
    "capacityReservationEnabled": true,
    "commitmentDefaultOptionsDisabled": true,
    "computeOffering": "string",
    "commitmentTerm": "string",
    "paymentOptions": "string",
    "sudEnabled": true,
    "discountUpliftDesc": "string",
    "discountUpliftPercent": 100,
    "unusedCapacity": 100
  }
 ]
 }'
Send feed
```

---

## Containers End Points

<!-- sub-header -->
- **breadcrumb:** Cloudability API > Containers End Points
- **source_path:** SSVCLNQ/api-v3/containers_endpoints.html
- **original_file:** api-containers-end-points.md
- **images:** []

## Containers End Points

With the Container Cost Allocation tool in Cloudability , you can get visibility into shared resource usage and cost by Kubernetes Clusters, Namespaces, Services, and Labels.

With the public API, you can:

1. Provision a new cluster for data collection.
1. Return the YAML deployment for a provisioned cluster.
1. Get a list of provisioned clusters for your organization, the date each cluster was provisioned, and a timestamp for the first and last date Cloudability received data for each cluster.
1. Perform queries to allocate cost across one or more clusters, grouping by namespace, services, labels or other dimensions.
1. Get usage of CPU, Memory, Network, and Filesystem by day for a filtered set of data.
1. Get a list of Label Keys observed in a given timeframe for a filtered set of data.
1. Return counts of distinct values for dimension keys for a given time-frame.

Learn more about Kubernetes Cost Allocation .

Containers End Points

- Provisioning
- Clusters
- Allocations
- Usage
- Labels
- Counts

---

## Clusters

<!-- sub-header -->
- **breadcrumb:** Cloudability API > Containers End Points > Clusters
- **source_path:** SSVCLNQ/api-v3/clusters.html
- **original_file:** points-clusters.md
- **images:** []

## Clusters

Starting November 14th, this endpoint will require the parameter concise=true

Summary

Get a list of provisioned clusters for your organization, the date each cluster was provisioned, and a timestamp for the first and last date Cloudability received data for each cluster.

End point

```
 /containers/v2/clusters 
```

Query Arguments

| Parameter | Description | Default | Allowed |
| --- | --- | --- | --- |
| start/end | Start/End date for the window of cluster results. Affects what nodes are returned (only nodes that were seen in this window will be in the results). | Required | Format YYYY-MM-DD |
| pretty | Pretty-print the JSON response | None | true |
| viewId | The ID number of the view with which to process the request. A value of 0 indicates no view. | Required |  |

Example Requests

```
curl "https://api.cloudability.com/v3/containers/v2/clusters?pretty=true&start=2018-11-01&end=2018-11-05&viewId=0" -u "${API_KEY}:"
```

```
{
  "result": {
    "clusters": [
      {
        "id": "f603489e-5bc0-4749-a61b-c5be59208355",
        "name": "cluster-aws",
        "firstSeen": "2018-07-26T00:00:00Z",
        "lastSeen": "2018-11-02T00:00:00Z",
        "provisionedAt": "2018-07-26T00:00:00Z",
        "nodes": [
          {
            "vendor": "Amazon",
            "resourceIdentifier": "i-05c3b8dcc15a2ecdb"
          },
          {
            "vendor": "Amazon",
            "resourceIdentifier": "i-0f58a6f23f21fddb9"
          },
          {
            "vendor": "Amazon",
            "resourceIdentifier": "i-056744c5a41b70336"
          },
          {
            "vendor": "Amazon",
            "resourceIdentifier": "i-0b6c49803ffcc4e21"
          },
          {
            "vendor": "Amazon",
            "resourceIdentifier": "i-02b379cab2292a66e"
          },
          {
            "vendor": "Amazon",
            "resourceIdentifier": "i-04d2edb03deb725a8"
          }
        ]
      },
      {
        "id": "dfd2581f-480f-11e8-b253-42010a80003a",
        "name": "cluster-gke",
        "firstSeen": "2018-04-24T00:00:00Z",
        "lastSeen": "2018-11-02T00:00:00Z",
        "provisionedAt": "2018-04-24T00:00:00Z",
        "nodes": [
          {
            "vendor": "GCP",
            "resourceIdentifier": "my-cluster-386473/us-central1-a/gke-staging-gke-default-pool-38d4xy10-dm97"
          },
          {
            "vendor": "GCP",
            "resourceIdentifier": "my-cluster-386473/us-central1-a/gke-staging-gke-default-pool-38d4xy10-t9h8"
          },
          {
            "vendor": "GCP",
            "resourceIdentifier": "my-cluster-386473/us-central1-a/gke-staging-gke-default-pool-38d4xy10-xtm9"
          }
        ]
      },
      {
        "id": "81dbeaa8-489f-11e8-a546-0a58ac1f024c",
        "name": "provisioned-cluster",
        "firstSeen": "2018-04-25T00:00:00Z",
        "lastSeen": "2018-11-05T00:00:00Z",
        "provisionedAt": "2018-04-25T00:00:00Z",
        "nodes": []
      },
    ],
    "meta": {
      "orgHasProvisioned": true,
      "orgHasData": true,
      "firstSeenDate": "2018-04-13T00:00:00Z"
    }
  }
}
```

---

## Counts

<!-- sub-header -->
- **breadcrumb:** Cloudability API > Containers End Points > Counts
- **source_path:** SSVCLNQ/api-v3/counts.html
- **original_file:** points-counts.md
- **images:** []

## Counts

This endpoint will be deprecated on November 14th, 2025, with most of its functionality now available through the Report API. We recommend migrating to the new API to avoid any disruption.

Summary

Return counts of distinct values for dimension keys for a given timeframe.

End Point

/containers/counts

Query Arguments

| Parameter | Description | Default | Allowed |
| --- | --- | --- | --- |
| start/end | Start/End date for the window of usage results. | Required | Format YYYY-MM-DD |
| dimensions | The dimensions to get counts for. The result will have a count for each dimension key specified. Comma-separated value | Required | cluster daemonset deployment job namespace pod replicaset replication_controller service cldy:labels:* (i.e. labels) |
| group | Group the reported data by the given dimensions. Comma-separated value | None | cluster daemonset deployment job namespace pod replicaset replication_controller service cldy:labels:* (i.e. labels) |
| filters | Filter the reported data to the given dimension values. | N/A |  |
| pretty | Pretty-print the JSON response | None | true |

Example Request

```
curl "https://api.cloudability.com/v3/containers/counts?pretty=true&start=2018-11-01&end=2018-11-05&dimensions=namespace,service&group=cluster" -u "${API_KEY}:"
```

```
{
  "result": {
    "groups": [
      {
        "group": [
          {
            "key": "cluster",
            "value": "e5ad2c07-2bd4-4e8f-afdf-6dbbcddc8cea"
          }
        ],
        "counts": [
          {
            "key": "namespace",
            "value": 9
          },
          {
            "key": "service",
            "value": 18
          }
        ]
      },
      {
        "group": [
          {
            "key": "cluster",
            "value": "0be6790f-e810-4f2e-a056-aa3f64c14504"
          }
        ],
        "counts": [
          {
            "key": "namespace",
            "value": 7
          },
          {
            "key": "service",
            "value": 12
          }
        ]
      },
      {
        "group": [
          {
            "key": "cluster",
            "value": "0be6790f-e810-4f2e-a056-aa3f64c14504"
          }
        ],
        "counts": [
          {
            "key": "namespace",
            "value": 11
          },
          {
            "key": "service",
            "value": 23
          }
        ]
      },
      {
        "group": [
          {
            "key": "cluster",
            "value": "642622c9-9dce-4789-bbdb-f0e002f0763b"
          }
        ],
        "counts": [
          {
            "key": "namespace",
            "value": 9
          },
          {
            "key": "service",
            "value": 11
          }
        ]
      },
      {
        "group": [
          {
            "key": "cluster",
            "value": "dfd2581f-480f-11e8-b253-42010a80003a"
          }
        ],
        "counts": [
          {
            "key": "namespace",
            "value": 7
          },
          {
            "key": "service",
            "value": 3
          }
        ]
      },
      {
        "group": [
          {
            "key": "cluster",
            "value": "8970c8f4-e7cd-46c2-b9e2-efa8e922fdeb "
          }
        ],
        "counts": [
          {
            "key": "namespace",
            "value": 6
          },
          {
            "key": "service",
            "value": 12
          }
        ]
      }
    ]
  }
}
```

---

## Labels

<!-- sub-header -->
- **breadcrumb:** Cloudability API > Containers End Points > Labels
- **source_path:** SSVCLNQ/api-v3/labels.html
- **original_file:** points-labels.md
- **images:** []

## Labels

Summary:

Get a list of Label Keys observed in a given timeframe for a filtered set of data.

End point:

/containers/labels

Query Arguments:

| Parameter | Description | Default | Allowed |
| --- | --- | --- | --- |
| start/end | Start/End date for the window of usage results. | Required | Format YYYY-MM-DD |
| filters | Filter the reported data to the given dimension values. | N/A |  |
| pretty | Pretty-print the JSON response | None | true |

Example Request

```
curl "https://api.cloudability.com/v3/containers/labels?pretty=true&start=2018-11-01&end=2018-11-05&filters=namespace==my-namespace&filters=cluster==${cluster_id}" -u "${API_KEY}:"
```

```
{
  "result": {
    "labels": [
      {
        "key": "cldy:labels:app",
        "keyDisplay": "app"
      },
      {
        "key": "cldy:labels:cluster",
        "keyDisplay": "cluster"
      },
      {
        "key": "cldy:labels:environment",
        "keyDisplay": "environment"
      },
      {
        "key": "cldy:labels:job-name",
        "keyDisplay": "job-name"
      },
      {
        "key": "cldy:labels:name",
        "keyDisplay": "name"
      },
      {
        "key": "cldy:labels:role",
        "keyDisplay": "role"
      },
      {
        "key": "cldy:labels:run",
        "keyDisplay": "run"
      },
      {
        "key": "cldy:labels:team",
        "keyDisplay": "team"
      }
    ]
  }
}
```

---

## Provisioning

<!-- sub-header -->
- **breadcrumb:** Cloudability API > Containers End Points > Provisioning
- **source_path:** SSVCLNQ/api-v3/provisioning.html
- **original_file:** points-provisioning.md
- **images:** []

## Provisioning

Summary

Any cluster that you would like Cloudability 's Container Cost Allocation tool to report on must first be provisioned. The provisioning process generates credentials as well as a Kubernetes deployment config that should then be installed in the cluster. The deployment will launch the Cloudability Metrics Agent in the cluster, into its own namespace. The Metrics Agent will then gather information about the cluster periodically, and send it back to Cloudability.

The provisioning end points provide API access to the provisioning process.

Learn more about provisioning a Kubernetes cluster.

End Point

/containers/provisioning

Query Arguments

| Parameter | Required | Type | Description |
| --- | --- | --- | --- |
| clusterName | Yes | string | Name of the cluster to be provisioned (must be unique, and cannot be modified) |
| kubernetesVersion | This OR clusterVersion is required but not both | string | The version of Kubernetes that is running on the cluster to be provisioned. |
| clusterVersion | This OR kubernetesVersion is required but not both | String | The version the cluster is running on being provisioned. |

Valid clusterVersion strings include OpenShift and Kubernetes. In the format: "openshift_x.xx" and "kubernetes_x.xx"

Provisioning a Cluster

When you have a new cluster that you'd like to see in the Cloudability Container Allocation tool, you will need to deploy the IBM FinOps Agent into the cluster. The provisioning API allows you to let Cloudability know about the cluster by "provisioning" it via this API. Once provisioned, the API can then produce the deployment helm for you to deploy the IBM FinOps Agent to the new cluster.

Below is the sample curl

```
curl --request POST \
  --url https://api.cloudability.com/v3/containers/provisioning/v2/helm \
  --header 'Content-Type: application/json' \
  --header 'apptio-environmentid: XXX' \
  --header 'apptio-opentoken: XXX' \
  --data '{
	"clusterName": "Test-Cluster-Name",
	"clusterVersion": "1.31"
}'
```

```
{"result":
"helm install ibm-finops-agent ibm-finops/finops-agent 
--set agent.kubecost.enabled=false
 --set agent.cloudability.uploadRegion=<region> 
--set agent.cloudability.parseMetricsData=false 
--set agent.cloudability.secret.create=true 
--set agent.cloudability.secret.cloudabilityAccessKey='<key>' 
--set agent.cloudability.secret.cloudabilitySecretKey='<key>' 
--set agent.cloudability.secret.cloudabilityEnvId='id'
--set clusterId='<clusterName>' 
--create-namespace -n ibm-finops-agent "
}
```

Below is the curl to get yaml to provision a cluster for old metrics agent

```
curl -X POST "https://api.cloudability.com/v3/containers/provisioning?pretty" \\
-u "${API_KEY}:" \\
-H "Content-type: application/json" \\
--data-binary '{
 "clusterName":"myTestCluster",
 "kubernetesVersion":"1.11"
}'
```

```
{
  "result": {
    "id": 1,
    "clusterName": "myTestCluster",
    "createdAt": "2018-05-18T15:40:23.29551Z",
    "kubernetesVersion": "1.11",
   }
}
```

Now, the cluster has been added to our database and a kubernetes deployment configuration has been generated. Note the "id" in the response. Use that in the following examples where "$" is in the uri.

To retrieve the deployment configuration yaml:

```
curl "https://api.cloudability.com/v3/containers/provisioning/${ID}/config" \\
-u "${API_KEY}:"
```

The output is a kubernetes deployment yaml file that will deploy the Cloudability Metrics Agent to your new cluster (follow whatever process is typical for your company to deploy new services to the cluster).

List All Provisioned Clusters

```
curl "https://api.cloudability.com/v3/containers/provisioning?pretty" \\
-u "${API_KEY}:"
```

Update Provisioned Cluster

You can also update the provisioning details for a cluster. For example, request to update the kubernetes version to 1.12 for a cluster:

```
curl "https://api.cloudability.com/v3/containers/provisioning/${ID}?pretty" \\
-XPUT \\
-u "${API_KEY}:" \\
-H "Content-type: application/json" \\
--data-binary '{"kubernetesVersion":"1.12"}'
```

Once updated, you can fetch the updated deployment configuration through the same method as above, and then re-deploy the configuration to your cluster to update the Cloudability Metrics Agent.

Note: clusterName is read-only once created and cannot be modified. Further, you currently must provide ALL the other fields (even those not changing), otherwise they will be updated to whatever the default for the type is. Support for PATCH is coming, which will allow for only specifying the fields that are changing.

---

## Report API Documentation

<!-- sub-header -->
- **breadcrumb:** Cloudability API > Containers End Points > Report API Documentation
- **source_path:** SSVCLNQ/product/report-api-documentation.html
- **original_file:** points-report-api-documentation.md
- **images:** []

## Report API Documentation

Summary

The report endpoint is intended to replace many functions that were previously split across a variety of containers APIs and is intended to provide a more singular view of the data powering the containers insights feature.

This endpoint allows for analysis of data by specification of specific metrics to be aggregated which can be combined with groups and filters to gather cost.

Endpoint

/v3/containers/report

Query Parameters:

| Parameter | Required | Description | Default | Allowed |
| --- | --- | --- | --- | --- |
| viewId | No | Cloudability view identifier that can be passed to enable filtering by account identifiers | Organization default view identifier | 0 (all if permitted), any configured numeric value |

Request Body

The report request body is a json object comprised of a the following key attributes:

| Parameter | Required | Type | Example | Supported Values |
| --- | --- | --- | --- | --- |
| start | Yes | date | 2024-06-01 | Any date after 2022-01-01 |
| end | Yes | date | 2024-06-02 | Any date after 2022-01-01, must be greater than or equal to start date |
| costType | Yes | string | adjusted | See: Supported Cost Types |
| metrics | Yes | list of strings | ["total_cost", "total_cost_efficiency"] | See: Supported Metric Values |
| limit | Yes | integer | 10 | 1-1000 |
| widgetType | Type | string | top | See: Supported Widget Types |
| count | No | list of strings | ["cluster"] | See: Supported Group, Count and Filter Values |
| group | No | list of strings | ["cluster"] | See: Supported Group, Count and Filter Values |
| filters | No | list of strings | ["cluster=={cluster_uuid}"] | See: Supported Group, Count and Filter Values |
| sort | No | list of configurations | [{"sortMetric":"total_cost","sortOrder":" desc"}] | See: Supported Sort Configurations |
| paginationToken | No | string | � | See: Pagination |

Supported Cost Types

| Sort Type | Relation to Containers UI |
| --- | --- |
| adjusted | Cash |
| total_adjusted_amortized | Adjusted Amortized |

Supported Metric Values

| Metric | Standard Cost Metric | Standard Usage Metric | Notes |
| --- | --- | --- | --- |
| cpu/reserved | Yes | Yes | Evaluated based upon the maximum of requested and utilized resources |
| memory/reserved | Yes | Yes | Evaluated based upon the maximum of requested and utilized resources |
| network/rx | Yes | Yes | Fairshare values will always equal Allocated values |
| network/tx | Yes | Yes | Fairshare values will always equal Allocated values |
| filesystem/usage | Yes | Yes | � |
| persistent_volume/usage | Yes | Yes | Usage is determined based off of the requested size of the PV, and is 1:1 with a PVC |
| gpu/reserved | Yes | Yes | Fairshare values will always equal Allocated values |
| miscellaneous | Yes | No | This is a cost-only metric |

Request-able fields

| Field Name | Field Type | Supported Metrics | Meaning |
| --- | --- | --- | --- |
| total_cost_fairshare | Aggregated | N/A | Total fairshare cost across all metric types, this represents the aggregated underlying costs of all resources contributing to the query |
| total_cost_allocated | Aggregated | N/A | Total allocated cost across all metric types, this represents the utilized cost of all resources contributed to the query |
| total_cost_idle | Aggregated | N/A | Total idle cost across all metric types, calculated via total_cost_fairshare - total_cost_allocated |
| total_cost_efficiency | Aggregated | N/A | Total cost efficiency across all metric types, calculated via total_cost_allocated / total_cost_fairshare |
| usage_cost_efficiency | Aggregated | N/A | Usage cost efficiency across all metric types, calculated via a ratio of usage cost / total_cost_allocated |
| {metric} /usage_cost_allocated | Per Metric | cpu, memory | Usage cost per metric |
| {metric} /usage_cost_efficiency | Per Metric | cpu, memory | Usage cost efficiency per metric, calculated via a ratio of usage cost / total_cost_allocated |
| {metric}/request | Per Metric | cpu, memory, gpu | Amount of resources requested |
| {metric}/usage | Per Metric | cpu, memory, gpu | Amount of resources utilized |
| {metric}/limit | Per Metric | cpu, memory, gpu | Limit on resources, 0 in this case indicates no limit has been set |
| {metric}_cost_fairshare | Per Metric | Standard cost metrics | Fairshare cost representation of the metric usage |
| {metric}_cost_allocated | Per Metric | Standard cost metrics | Allocated cost representation of the metric usage |
| {metric}_cost_idle | Per Metric | Standard cost metrics | Fairshare - Allocated cost representation of the metric |
| {metric}_cost_efficiency | Per Metric | Standard cost metrics | Allocated/Fairshare cost value |
| {metric} _utilization_fairshare | Per Metric | Standard cost metrics | Fairshare utilization value |
| {metric} _utilization_allocated | Per Metric | Standard cost metrics | Allocated utilization value |
| {metric}_utilization_idle | Per Metric | Standard cost metrics | Fairshare - Allocated utilization |
| {metric} _utilization_efficiency | Per Metric | Standard cost metrics | Allocated/Fairshare utilization value |

Supported Widget Types

| Widget Type | Relation to Containers UI | Meaning | Requirements | Restrictions |
| --- | --- | --- | --- | --- |
| top | Table Data | This is the most common representation of containers data which returns aggregated data over the specified time period | � | Group must not contain a time period |
| kpi | KPI Widgets | This provides a singular value back | � | Single result only Group is not available Pagination is not available |
| bar | Bar Charts | This provides a set of top/bottom values without respect for generating continuous series of data across the time period | A time group must be set (ex: day) | Pagination is not available |
| line | Line Charts | This returns the top/bottom continuous series of data across the time period | A time group must be set (ex: day) | Pagination is not available |

Supported Group, Count and Filter Values

Groups, Counts, and Filters share a overlapping set of accessible data, which can be utilized in the following ways:

Groups

Groups return results aggregated by unique values in that field.

For example, grouping by cluster would return a result set that is isolated by cluster.

Counts

Counts return a result section that identifies the number of unique entries for that aspect.

For example, a count of namespaces would return the total number of namespaces within the selection.

Filters

Filters allow a user to constrain the result set to only a subset of results.

For example, supplying a filter of workload_type==deployment would only return results for workloads identified as being owned by a deployment.

| Value | Meaning | Example Returned Values | Supports Filter | Supports Group | Supports Count |
| --- | --- | --- | --- | --- | --- |
| cluster | Cluster unique identifier, a full set of these with name mappings can be retrieved from the clusters endpoint | XXXXXXX-XXXX-XXXX-XXXXXXXXXXXXXXXX | Yes | Yes | Yes |
| day | Allows for grouping data by day, must be used with a supported widgetType (bar/line) | 2024-06-01 | No | No | No |
| workload_type | Highest level owner type of the workload | deployment, cronjob, statefulset, etc | Yes | Yes | Yes |
| workload_name | Highest level owner name of the workload | my-service-name | Yes | Yes | Yes |
| namespace | Namespace where workloads are present | my-namespace-name | Yes | Yes | Yes |
| container | Container name that is running on the cluster | my-container-name | Yes | Yes | Yes |
| pod | Pod name that is running on the cluster | my-pod-name | Yes | Yes | Yes |
| node | Node name that is assigned | ip-1.2.3.4.region.compute.internal | Yes | Yes | Yes |
| node_id | Provider node identifier | aws:///region/i-1234 | Yes | Yes | Yes |
| instance_family | Instance family of the underlying node | t2 | Yes | Yes | Yes |
| instance_category | Instance category of the underlying node | General Purpose | Yes | Yes | Yes |
| instance_type | Instance type of the underlying node | t2.micro | Yes | Yes | Yes |
| savings_plan | Savings plan type applied to the underlying node | ComputeSavingsPlan | Yes | Yes | Yes |
| lease_type | Lease method of the underlying node | On-Demand | Yes | Yes | Yes |
| reserved_instance | If the underlying node is running as part of a reserved instance commitment | Y, N | Yes | Yes | Yes |
| cpu_allocatable | CPU units (in microcore), available on the underlying node | 48000000 | Yes | Yes | Yes |
| memory_allocatable | Memory (in bytes) available on the underlying node | 1000000000 | Yes | Yes | Yes |
| gpu_allocatable | GPU units (in microgpu), available on the underlying node | 1000000 | Yes | Yes | Yes |
| region | Region in which the underlying node is running | us-west-2 | Yes | Yes | Yes |
| zone | Availability zone in which the underlying node is running | us-west-2a | Yes | Yes | Yes |
| node_group | Node group (if detectable), that the underlying node is part of | my-node-group | Yes | Yes | Yes |
| vendor | Cloud provider that the cluster is running on | aws, azure, etc | Yes | No | No |
| cluster_type | Cluster type that is running | eks, gke, openshift, etc | Yes | No | No |

Using Filters

Filters can be configured by supplying the:

- Filtered Attribute Any value denoted as filterable in the above list

- Operator == Equals (case sensitive) []= One of (case sensitive)

- Filtered Value Any value that the user wants to filter upon

Examples:

- namespace==kube-system Will filter down results to only show data for kube-system

- workload_type[]=cronjob,job Will filter down results to only show data for cronjobs or jobs

Supported Sort Configurations

If not set, the sort feature defaults to sorting by the first specified metric column in descending order. This is setup to ensure pagination is always possible.

Sort values should be passed in the order that the caller wishes them to take place, and can be specified for any requested metric value.

The example below would sort rows by efficiency in descending order, then by total_cost in descending order.

```
[
  {
    "sortMetric": "total_cost_efficiency",
    "sortOrder": "desc"
   },
   {
     "sortMetric": "total_cost",
     "sortOrder": "desc"
   }
 ]
```

Pagination

| Field | Type | Description |
| --- | --- | --- |
| result.pagination.hasNext | boolean | Indicates whether there is a following page |
| result.pagination.nextToken | string | Provides a string value that may be passed back to the API to get the next set of results |

If the above data for pagination indicates that another page is available for consumption, then the value in "nextToken" can be passed back into the api via the "paginationToken" parameter.

The request must not be changed in any other regard, and doing so may cause errors or inconsistent results to be returned.

US Example (API endpoint): https://api.cloudability.com/v3/containers/report

Example Requests

```
curl --location 'https://api.cloudability.com/v3/containers/report' \
--header 'apptio-opentoken: {token}' \
--header 'apptio-environmentid: {env_id}' \
--header 'Content-Type: application/json' \
--data '{
    "start": "2024-06-10",
    "end": "2024-06-10",
    "costType": "adjusted",
    "metrics": [
	"total_cost"
    ],
    "group": [
	"namespace"
    ],
    "count": [
	"workload_name"
    ],
	"filters": [
		"cluster==XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX"
	],
    "sort": [
	{
	     "sortMetric": "total_cost",
	     "sortOrder": "desc"
	}
    ],
    "widgetType": "top",
    "limit": 1
}'
```

Example response, including the pagination token that can be passed back into the api.

```
{
    "result": {
	"data": [
	   {
		"count": [
		    {
			"key": "workload_name",
			"value": "20"
		    }
		],
		"dimensions": {
		    "namespace": "my-namespace"
		},
		"metrics": {
		    "total_cost": {
			"unit": "currency",
			"values": [
				100.00
			]
		    }
		}
	    }
	 ],
	"pagination": {
	    "hasNext": true,
	    "nextToken": "veryLongPaginationToken"
	}
   }
}

```

This response body is broken into the following section:

| Field | Type | Meaning |
| --- | --- | --- |
| result.data | []object | This is the primary response body that contains a series of elements identified by the requested group values |
| result.data[N].count | []map [string] string | This represents a set of objects containing the requested unique count of values |
| result.data[N].dimensions | map[string] string | This represents the uniquely grouped attributes determined by the grouped attributes |
| result.data[N].metrics | map[string] object | This represents the aggregated metric values. When grouping by time, each time unit will be represented by an index in the "values" array |
| result.data[N].metrics. {metric}.unit | string | The specific unit for that metric type, possible values are: currency, bytes, microcpu, microgpu, efficiency |
| result.data[N].metrics. {metric}.values | []float64 | A set of values representing the utilized resources over the time period. When grouping by day for example, each entry in the array represents a single day |

---

## Usage

<!-- sub-header -->
- **breadcrumb:** Cloudability API > Containers End Points > Usage
- **source_path:** SSVCLNQ/api-v3/usage.html
- **original_file:** points-usage.md
- **images:** []

## Usage

This endpoint will be deprecated on November 14th, 2025, with most of its functionality now available through the Report API. We recommend migrating to the new API to avoid any disruption.

Summary

Provides usage by day for a filtered set of data. Specify the time range, then metrics to aggregate, and the filters, and the results will show the resource allocation percentages and average values, by day over the time range.

End Point

/containers/usage

Query Arguments

| Parameter | Description | Default | Allowed |
| --- | --- | --- | --- |
| start/end | Start/End date for the window of usage results. | Required | Format YYYY-MM-DD |
| metrics | Metrics to calculate allocations for. Comma-separated value. | cpu/reserved memory/reserved_rss network/tx network/rx filesystem/usage | cpu/reserved cpu/usage memory/reserved memory/reserved_rss memory/usage network/tx network/rx filesystem/usage |
| filters | Filter the reported data to the given dimension values. NOTE if filtering on cluster , the cost basis is also filtered, affecting the allocation percentages | N/A |  |
| pretty | Pretty-print the JSON response | None | true |

Example Request

```
curl "https://api.cloudability.com/v3/containers/usage?pretty=true&start=2018-11-01&end=2018-11-05&metrics=cpu/reserved,filesystem/usage" \\
-u "${API_KEY}:"
```

```
{
  "result": {
    "allocations": [
      {
        "metrics": [
          {
            "key": "cpu/reserved",
            "allocation": [
              0.7987696152936873,
              0.8033224699512777,
              0.7962087739444434,
              0.7849621407764081,
              0.7979094432363594,
              0.7968074452235664
            ],
            "resource": {
              "mean": [
                24871023,
                23591075,
                24485813,
                24441104,
                24844240,
                24809927
              ],
              "unit": "microcpu"
            },
            "available": {
              "mean": [
                31136666,
                29366881,
                30753006,
                31136666,
                31136666,
                31136666
              ],
              "unit": "microcpu"
            }
          },
          {
            "key": "filesystem/usage",
            "allocation": [
              0.018209299442523686,
              0.018631274665818067,
              0.018326117929819974,
              0.018119344944692844,
              0.01838696498388433,
              0.0185451797742567
            ],
            "resource": {
              "mean": [
                4792551765,
                4500930636,
                4743095999,
                4763378979,
                4842758913,
                4858709445
              ],
              "unit": "bytes"
            },
            "available": {
              "mean": [
                263192539639,
                241579318488,
                258816188859,
                262889138326,
                263380004131,
                261993116531
              ],
              "unit": "bytes"
            }
          }
        ]
      }
    ]
  }
}
```

---

## Cost Reporting End Point

<!-- sub-header -->
- **breadcrumb:** Cloudability API > Cost Reporting End Point
- **source_path:** SSVCLNQ/api-v3/cost_reporting_endpoints.html
- **original_file:** api-cost-reporting-end-point.md
- **images:** []

## Cost Reporting End Point

The cost reporting endpoints are used to dynamically run cost reports and return detailed information about your organization’s cloud spend. These reports have the following features:

- Can be generated in JSON (default) or CSV format
- Help you to manage the saved cost reports
- Have flexible filtering and sorting
- Can select dimensions and metrics to customize as per the reporting needs
- Can add up to 15 dimensions and 8 metrics to an API call
- Pagination when the results exceed 10,000 rows

Cost Reporting End Points

- /reporting/reports/cost for listing current cost reports
- /reporting/cost/run for executing cost reports
- /reporting/cost/measures for listing available cost reporting measures
- /reporting/cost/filters for listing available comparison operators used in filters
- /reporting/cost/enqueue for enqueuing cost reports
- /reporting/reports/:id/state for checking the state of enqueued reports
- /reporting/reports/:id/results for retrieving finished enqueued reports

The Cost Report Object

- results (array) - list of cost row objects, each row comprised of reported dimensions and metrics
- meta (object) - object containing meta information about the report that was run dates (object) - start and end date strings marking the date range of the report filters (array) - list of filters applied to report with detailed information metrics (array) - list of metrics returned in report with detailed information dimensions (array) - list of dimensions returned in report with detailed information aggregates (array) - list of aggregated metrics with detailed information for report
- offset (number) - Position where to start for the results. Default is 0
- limit (number) - Maximum number of cost rows that can be returned
- total_results (number) - Total cost rows returned for executed report

Example Cost Report Object

```
{
  "results": [
   {
     "total_adjusted_amortized_cost": "586411.47",
      "vendor": "Amazon"
    },
    {
     "total_adjusted_amortized_cost": "5334044.71",
      "vendor": "Azure"
    }
     ],
      "meta": {
       "dates": {
       "start": "2022-02-01T00:00:00Z",
       "end": "2022-02-28T00:00:00Z"
      },
       "filters": [
  {
   "comparator": "==",
   "value": "usage",
   "measure": {
   "name": "transaction_type",
   "label": "Transaction Type",
   "description": "Break costs into Usage, One-Time Charges...",
   "data_type": "string",
   "type": "dimension",
    "group": {
     "ID": 2,
     "Key": "billing",
     "Name": "Billing"
     },
     "sub_group": {
     "ID": 6,
     "Key": "usage",
     "Name": "Usage"
      }
     }
    }
    ],
     "metrics": [
                    {
 "name": "total_adjusted_amortized_cost",
 "label": "Cost (Adjusted Amortized)",
 "description": "This cost is calculated using the unblended rate,...",
   "data_type": "currency",
   "type": "metric",
   "group": {
   "ID": 2,
    "Key": "billing",
    "Name": "Billing"
    },
    "sub_group": {
    "ID": 3,
    "Key": "costs",
    "Name": "Costs"
    }
   }
   ],
   "dimensions": [
   {
   "name": "vendor",
   "label": "Vendor",
   "description": "Vendor that provided the product",
   "data_type": "string",
   "type": "dimension",
   "group": {
    "ID": 2,
    "Key": "billing",
    "Name": "Billing"
    },
    "sub_group": {
    "ID": 7,
    "Key": "vendor",
    "Name": "Vendor"
    }
    }
   ],
   "aggregates": [
   {
   "name": "total_adjusted_amortized_cost",
   "label": "Cost (Adjusted Amortized)",
   "description": "This cost is calculated using the unblended rate...",
    "data_type": "currency",
    "type": "metric",
    "value": "5920456.18"
     }
    ]
   },
   "offset": 0,
   "limit": 0,
   "total_results": 2
 }
```

List current cost reports

Retrieve a list of cost reports either owned by or shared with the user or org.

```
curl 'https://api.cloudability.com/v3/reporting/reports/cost' -u '[auth_token]:'
```

Example Response

```
[ 
 { 
   "id": 1, 
      "category": "Cost Summary", 
      "custom": false, 
      "description": "A breakdown of last month's costs by vendor.", 
      "dimensions": [ 
	{ 
   "name": "vendor", 
   "label": "Vendor", 
   "description": "The cloud vendor associated with the cost item. Valid values are Amazon, Azure and GCP.", 
   "data_type": "string", 
   "type": "dimension", 
   "group": { 
   "id": 2, 
   "key": "billing", 
   "name": "Billing" 
   }, 
    "sub_group": { 
    "id": 7, 
    "key": "vendor", 
    "name": "Vendor" 
	} 
	} 
      ], 
	"end_date": "end of last month", 
	"filters": [], 
    "metrics": [ 
    { 
     "name": "unblended_cost", 
     "label": "Cost (Total)", 
	 "description": "This is the default cost metric throughout Cloudability. It is a “cash” metric and simply represents the invoiced amount associated with any cost item as reported by the cloud vendor.", 
     "data_type": "currency", 
     "type": "metric", 
     "group": { 
     "id": 2, 
     "key": "billing", 
     "name": "Billing" 
  }, 
  "sub_group": { 
  "id": 3, 
  "key": "costs", 
  "name": "Costs" 
  } 
   }, 
     ], 
 "order": "desc", 
 "owned_by_user": false, 
 "shared_with_organization": true, 
 "permission": { 
 "actions": [ 
 "read" 
 ] 
  }, 
  "report_dimension_links": [], 
  "secondary_end_date": null, 
  "secondary_start_date": null, 
  "shared": false, 
  "shares": [], 
  "sort_by": "unblended_cost", 
  "star": false, 
  "start_date": "0 of last month", 
  "subscriptions": [], 
  "title": "Costs by Vendor Last Month" 
  } 
   ]
```

Getting list of available measures

To retrieve a list of measures recognized by the server, perform a GET at the measures endpoint. The measures include both dimensions and metrics that can be used in reports.

```
curl ‘https://api.cloudability.com/v3/reporting/cost/measures’ -u ‘[auth_token]:’
```

| Argument | Description |
| --- | --- |
| apply_allocations(Optional) | If apply_allocations is true, only the measures supported by cost sharing are listed. Conversely, if it is false, all measures are included in the list. Allowed: true/false |

Example Response

```
[
 {
   "data_type" : "currency",
    "description" : "Total cost including taxes and credits",
     "group" : {
     "key" : "billing",
    "name" : "Billing"
     },
    "label" : "Total Invoiced Costs",
    "name" : "invoiced_cost",
     "sub_group" : {
     "key" : "costs",
     "name" : "Costs"
     },
     "type" : "metric"
    },
     {
 "data_type" : "string",
 "description" : "The account name for a linked account in consolidated billing",
 "group" : {
 "key" : "billing",
 "name" : "Billing"
   },
 "label" : "Linked Account Name",
 "name" : "linked_account_name",
  "sub_group" : {
  "key" : "vendor",
  "name" : "Vendor"
   },
   "type" : "dimension"
  }
]
```

Getting list of available filter operators

Retrieve a list of recognized filter operators for requesting data

```
curl ‘https://api.cloudability.com/v3/reporting/cost/filters’ -u ‘[auth_token]:’
```

Example Response

```
  [
        "!=@",  # does not contain
        "!=",   # not equals
        "!==",  # strictly not equals*
        "<=",   # less than or equals
        ">",    # greater than
        "[]!=", # not in*
        "===",  # strictly equals*
        "<",    # less than
        "=@",   # contains
        "!^=",  # does not start with
        "!$=",  # does not end with
        "==",   # equals
        ">="    # greater than or equals
        "$=",   # ends with
        "[]=",  #    in*
        "^=",   # starts with
        ]
```

* Note that these operators are available via the API only

Run a cost report

Request Parameters

| Argument | Description |
| --- | --- |
| start_date (required) | The start date for the cost report. Format: YYYY-MM-DD |
| end_date (required) | The end date for the cost report. Format: YYYY-MM-DD |
| dimensions (required) | Comma delimited list of dimensions to include in report. Example: dimensions=vendor,region |
| metrics (required) | Comma delimited list of metrics to include in report. Example: metrics = total_amortized_cost,usage_hours |
| filters | Filter to apply to report. Filters can be based on dimensions or metrics. Note : the filters query parameter is for a single filter only. Use multiple query parameters for multiple filters Example : filters = transaction_type%3D%3Dusage Important: the comparison operator should generally be URL encoded (as above) to avoid problems with special characters |
| sort | Comma delimited list of measures, each appended with ASC or DESC to indicate order (order is required). Example: sort = total_amortized_costASC,regionDESC |
| limit | The maximum number of rows to return. Example: limit = 50 |
| offset | Position to start for the results. Example: offset = 100 |
| chart | Format the row data for chart purposes (based around dates). Example: chart = 1 |
| view_id | If omitted, the user's default view will be applied. Unrestricted users can set view_id = 0 to remove view. |
| applyAllocations | If the optional parameter is set to true, the report will include information on post allocated costs. Conversely, if it is absent or set to false, the report will contain details on per allocated costs. |

Note: Relative/dynamic date strings supported by the v3 cost reporting endpoint:

| Relative/ Dynamic date strings |
| --- |
| “7 days ago at 00:00:00” |
| “8 days ago at 00:00:00" |
| “10 days ago at 00:00:00” |
| “14 days ago at 00:00:00" |
| “30 days ago at 00:00:00” |
| “31 days ago at 00:00:00" |
| “60 days ago at 00:00:00” |
| “90 days ago at 00:00:00" |
| “beginning of last day” |
| “beginning of last week” |
| “beginning of last month”, “0 of last month” |
| “beginning of last quarter” |
| “beginning of last half” |
| “beginning of last year” |
| “beginning of day”, “beginning of this day” |
| “beginning of week”, “beginning of this week” |
| “beginning of month”, “beginning of this month”, “1st” |
| “beginning of period”, “beginning of this period” |
| “beginning of quarter”, “beginning of this quarter” |
| “beginning of half”, “beginning of this half” |
| “beginning of year”, “beginning of this year” |
| “today at 00:00:00” |
| “00:00:00" |
| “23:59:59” |
| “yesterday at 00:00:00" |
| “yesterday at 23:59:59” |
| “end of last day” |
| “end of last week” |
| “end of last month” |
| “end of last quarter” |
| “end of last half” |
| “end of last year” |
| “end of last week to date” |
| “end of last month to date” |
| “end of last quarter to date” |
| “end of last year to date” |
| “end of day”, “end of this day” |
| “end of week”, “end of this week” |
| “end of month”, “end of this month” |
| “end of quarter”, “end of this quarter” |
| “end of half”, “end of this half” |
| “end of year”, “end of this year” |
| “end of next day” |
| “end of next week” |
| “end of next month” |
| “end of next quarter” |
| “end of next half” |
| “end of next year” |

Handling Pagination

Pagination is implemented if the number of rows in a returned report exceeds 10,000. This typically occurs when users add several dimensions to a report that have high cardinality, such as resource_identifier. The total_results having a value of 10,000 and presence of a pagination object indicates pagination has occurred.

Example pagination object:

```
"pagination": {
        "next": "38bc18d0",
        "previous": "1d93c71e"
```

To navigate between the pages of a report, add a token query parameter to the end of the report URL with the applicable token ID value (e.g., token = 38bc18d0).

Note : You can increase the auto-pagination to 64,000 rows by setting limit = 0 in the request parameters

Run a typical cost report by - grouped by cloud vendor with cost amortized

```
curl ‘https://api.cloudability.com/v3/reporting/cost/run?start_date=2022-02-01&end_date=2022-02-28&dimensions=vendor&metrics=total_amortized_cost&sort=total_amortized_costASC&filters=transaction_type%3D%3Dusage’ -u ‘[auth_token]:’
```

Example Response

```
{
   "results": [
   {
   "total_amortized_cost": "5334044.71",
   "vendor": "Azure"
   },
         {
   "total_amortized_cost": "593944.59",
   "vendor": "Amazon"
    }
      ],
    "meta": {
    "dates": {
    "start": "2022-02-01T00:00:00Z",
    "end": "2022-02-28T00:00:00Z"
       },
     "filters": [
      {
    "comparator": "==",
    "value": "usage",
    "measure": {
    "name": "transaction_type",
    "label": "Transaction Type",
    "description": "A new dimension ...",
    "data_type": "string",
    "type": "dimension",
      "group": {
       "ID": 2,
       "Key": "billing",
      "Name": "Billing"
          },
      "sub_group": {
      "ID": 6,
      "Key": "usage",
      "Name": "Usage"
      }
       }
        }
     ],
        "metrics": [
        {
       "name": "total_amortized_cost",
       "label": "Cost (Amortized)",
       "description": "This cost is ...",
       "data_type": "currency",
       "type": "metric",
       "group": {
       "ID": 2,
         "Key": "billing",
         "Name": "Billing"
           },
          "sub_group": {
          "ID": 3,
          "Key": "costs",
          "Name": "Costs"
          }
           }
            ],
         "dimensions": [
                 {
     "name": "vendor",
     "label": "Vendor",
     "description": "Vendor that provided the product",
      "data_type": "string",
       "type": "dimension",
       "group": {
      "ID": 2,
       "Key": "billing",
          "Name": "Billing"
            },
         "sub_group": {
         "ID": 7,
         "Key": "vendor",
         "Name": "Vendor"
          }
           }
            ],
          "aggregates": [
            {
      "name": "total_amortized_cost",
      "label": "Cost (Amortized)",
      "description": "This cost is ...",
      "data_type": "currency",
      "type": "metric",
      "value": "5927989.3"
        }
         ]
           },
    "offset": 0,
    "pagination": {},
     "limit": 10000,
     "total_results": 2
}
```

Generate a Report of Cost Data and Retrieve the Results Later

This option is applicable when reports take a long time to return, by triggering the report generation but retrieving the results later. The end point to the asynchronous cost reporting takes the same parameters as the synchronous cost reporting, but instead of waiting and returning the contents of the report, it will instead return a request token.

The current state of processing is retrieved by requesting the state resource for the given token. When the state is given as "finished", the contents of the report can be retrieved by requesting the results resource for the token. An example is given below:

```
curl ‘https://api.cloudability.com/v3/reporting/cost/enqueue?start_date=2022-02-01&end_date=2022-02-28&dimensions=vendor&metrics=total_adjusted_amortized_cost-u ‘[auth_token]:’
```

Example Response

```
{"id":31272850}
```

```
curl ‘https://api.cloudability.com/v3/reporting/cost/enqueue?start_date=2022-02-01&end_date=2022-02-28&dimensions=vendor&metrics=total_adjusted_amortized_cost&useDimensionNames=true -u ‘[auth_token]:’
```

Query the State of an Asynchronous Report

Valid state of an asynchronous report are enqueued, running, errored and finished . This can be queried with the following API call (replace :id with your report ID, as returned from the enqueue call)

```
curl https://api.cloudability.com/v3/reporting/reports/:id/state -u ‘[auth_token]:’

```

Example Response

```
{"status":"running"}
```

Retrieve a Report Previously Generated by Enqueue

Reports that have a state of finished can be retrieved. This returns a standard cost report object.

```
curl ‘https://api.cloudability.com/v3/reporting/reports/:id/results’ -u ‘[auth_token]:’
```

List of sample reports

Below are a few sample reports that can help you with usage of the cost reports API.

Cost report with relative dates

```
curl ‘https://api.cloudability.com/v3/reporting/cost/run?start_date=beginning+of+last+quarter&end_date=end+of+last+quarter&dimensions=vendor&metrics=total_adjusted_amortized_cost’ -u ‘[auth_token]:’
```

Cost report with apply allocations

```
curl ‘https://api.cloudability.com/v3/reporting/cost/run?applyAllocations=true&dimensions=vendor&metrics=total_adjusted_amortized_cost’ -u ‘[auth_token]:’

```

Cost by cloud vendor and region, filtered to usage only and returned via CSV

```
curl -H ‘Accept: text/csv’ ‘https://api.cloudability.com/v3/reporting/cost/run?start_date=2022-02-01&end_date=2022-02-28&dimensions=vendor,region&metrics=total_amortized_cost&filters=transaction_type%3D%3Dusage’ -u ‘[auth_token]:’

```

Cost report with multiple dimensions and filters (amortized cost > 100, region contains ‘us-east-‘)

```
curl ‘https://api.cloudability.com/v3/reporting/cost/run?start_date=2022-02-01&end_date=2022-02-28&dimensions=vendor,region,enhanced_service_name&metrics=total_amortized_cost&filters=total_amortized_cost%3E100&filters=region%3D%40us-east-’ -u ‘[auth_token]:’
```

Going to next cost report page via token

```
curl ‘https://api.cloudability.com/v3/reporting/cost/run?start_date=2022-02-01&end_date=2022-02-28&dimensions=vendor,region,resource_identifier&metrics=total_amortized_cost,usage_hours=&tokenId=e641deae’ -u ‘[auth_token]:’ 
```

Using the “IN” operator to get cost information for two regions

```
curl ‘https://api.cloudability.com/v3/reporting/cost/run?start_date=2022-02-01&end_date=2022-02-28&dimensions=region,enhanced_service_name&metrics=total_amortized_cost&filters=region[]%3Dus-east-1,us-west-2’ -u ‘[auth_token]:’
```

---

## Cost Sharing End Points

<!-- sub-header -->
- **breadcrumb:** Cloudability API > Cost Sharing End Points
- **source_path:** SSVCLNQ/api-v3/cost_sharing_endpoints.html
- **original_file:** api-cost-sharing-end-points.md
- **images:** []

## Cost Sharing End Points

Summary

Every organization has a bucket of cloud costs that needs to be shared across departments. Cloudability ’s Business Mapping can help you minimize the size of the shared costs bucket, the need to fully allocate shared costs remains. Cost Sharing allows you to create a bucket of shared costs, define allocation rules, allocate the shared costs based on the defined rules and then generate an exportable report. The Cost Sharing API end points can be used to set cost sharing (allocation or distribution) rules and retrieve the result. Learn more about Cost Sharing here.

Cost Sharing End Points

Cost Sharing Rule Setting End Points: /cost-sharing/rules

Cost Sharing Result Report End Points: /reporting/cost-sharing

---

## Cost Sharing Allocations

<!-- sub-header -->
- **breadcrumb:** Cloudability API > Cost Sharing End Points > Cost Sharing Allocations
- **source_path:** SSVCLNQ/api-v3/allocations-cost-sharing.html
- **original_file:** points-cost-sharing-allocations.md
- **images:** []

## Cost Sharing Allocations

Summary

The Allocations API serves as the foundation for cost sharing, managing the core allocation entities and their relationships with business dimensions. This API lets you create, manage, and remove cost allocation frameworks.

Key features

The key features for Allocations API include the following:

- Create new allocation structures for business dimensions
- Update existing allocations with new business dimension mappings
- Retrieve single or multiple allocation configurations
- Delete allocation structures with cascading rule cleanup
- Support for up to 25 business dimensions

Cost sharing Allocations API perform the following:

- Maintain creation and updates timestamps
- Support owner attribution for tracking
- Include ordering capabilities for organization
- Maintain referential integrity with associated rules

End Points

POST /v3/cost-sharing/allocation

This API is used for creating a new allocations.

Query Arguments for the Request Body

| Parameter | Description | Default | Allowed |
| --- | --- | --- | --- |
| businessDimensionIndex | The Allocation will be created for this Business Dimension Index | REQUIRED | Numeric values between 1 - 25 that’s not already used in any Allocation |

Example Request

```
curl --request POST \
	 --url 'https://api.cloudability.com/v3/cost-sharing/allocation' \
	 --header 'authorization: ${JWT_TOKEN}' \
	 --header 'content-type: application/json' \
	 --header 'x-cldy-user-id: ${USER_ID}' \
	 --header 'x-fd-env-id: ${ENVIRONMENT_ID}' \
	 --data '{
			  "businessDimensionIndex": 20
		     }'
```

Example Response

```
{
 "result": {
	     "allocationId": "bf219659-2a20-4814-bda3-11c04b76d711",
	     "businessDimensionIndex": 20,
	     "createdAt": "2025-01-27T08:12:27.231Z",
            "updatedAt": "2025-01-27T08:12:27.231Z",
	     "order": 25
	    }
}
```

PUT /v3/cost-sharing/allocation

This API is used for updating an existing allocation.

Query Arguments for the Request Body

| Parameter | Description | Default | Allowed |
| --- | --- | --- | --- |
| allocationId | ID of the existing allocation that needs to be updated | REQUIRED | An existing, valid Allocation ID |
| businessDimensionIndex | The Allocation will be created for this Business Dimension Index | REQUIRED | Numeric values between 1 - 25 that’s not already used in any Allocation |

Example Request

```
curl --request PUT \
	 --url https://api.cloudability.com/v3/cost-sharing/allocation \
	 --header 'authorization: ${JWT_TOKEN}' \
	 --header 'content-type: application/json' \
	 --header 'x-cldy-user-id: ${USER_ID}' \
	 --header 'x-fd-env-id: ${ENVIRONMENT_ID}' \
	 --data '{
			  "allocationId": "bf219659-2a20-4814-bda3-11c04b76d711",
			   "businessDimensionIndex": 14
				}'
```

Example Response

```
{
 "result": {
 "allocationId": "bf219659-2a20-4814-bda3-11c04b76d711",
 "businessDimensionIndex": 14,
 "createdAt": "2025-01-27T08:12:27.000Z",
 "updatedAt": "2025-01-27T08:17:25.292Z",
 "order": 0
}
}
```

GET /v3/cost-sharing/allocation

This API is used for retrieving all existing allocation.

Example Request

```
curl --request GET \
      --url https://api.cloudability.com/v3/cost-sharing/allocation \
      --header 'authorization: ${JWT_TOKEN}' \
      --header 'x-fd-env-id: ${ENVIRONMENT_ID}''
```

Example Response

```
{
 "result": [
	    {
	     "allocationId": "18b0cab7-46f8-4526-b328-1cab27ec2c28",
	     "businessDimensionIndex": 1,
	     "createdAt": "2024-08-27T06:52:40.000Z",
	     "owner": "Sai Krishna",
	     "updatedAt": "2025-01-13T20:31:39.000Z",
	     "order": 1
	    },
	    {
	     "allocationId": "da1c9f96-4e20-4d40-a17c-43149e304ee0",
	     "businessDimensionIndex": 4,
	     "createdAt": "2024-12-06T17:52:52.000Z",
	     "owner": "Shivesh Singh",
	     "updatedAt": "2024-12-06T17:52:52.000Z",
	     "order": 2
	     },
	     {
	      "allocationId": "bf2b6626-6b98-4e6a-a8e2-0e5b231a5b4c",
	      "businessDimensionIndex": 14,
	      "createdAt": "2024-12-06T19:43:31.000Z",
	      "owner": "Komal Dhuri",
	      "updatedAt": "2024-12-06T19:43:31.000Z",
	      "order": 3
	      }
	     ]
}
```

GET /v3/cost-sharing/allocation/${allocationId}

This API is used for retrieving a specific allocation by its Allocation ID.

Query Arguments

| Parameter | Description | Default | Allowed |
| --- | --- | --- | --- |
| allocationId | ID of the existing allocation that needs to be retrieved | REQUIRED | An existing, valid Allocation ID |

Example Request

```
curl --request GET \
	 --url https://api.cloudability.com/v3/cost-sharing/allocation/18b0cab7-46f8-4526-b328-1cab27ec2c28 \
	 --header 'authorization: ${JWT_TOKEN}' \
	 --header 'x-fd-env-id: ${ENVIRONMENT_ID}'
```

Example Response

```
{
 "result": {
	     "allocationId": "0e5d398b-07e2-4969-854a-f01abe9e35ca",
	     "businessDimensionIndex": 14,
	     "createdAt": "2024-08-27T06:52:40.000Z",
	     "updatedAt": "2025-01-13T20:31:39.000Z",
	     "rules": []
           }
}
```

Another example of allocation having some rules is as follows:

Example Request

```
curl --request GET \
     --url https://api.cloudability.com/v3/cost-sharing/allocation/d806a527-1554-49f3-9c8f-a5deae0e37b6 \
     --header 'authorization: ${JWT_TOKEN}' \
     --header 'x-fd-env-id: ${ENVIRONMENT_ID}'
```

Example Response

```
{
 "result": {
 "allocationId": "d806a527-1554-49f3-9c8f-a5deae0e37b6",
 "businessDimensionIndex": 17,
 "createdAt": "2024-07-29T09:38:56.000Z",
 "owner": "Shilpesh Solanki",
 "updatedAt": "2024-10-15T02:08:09.000Z",
 "rules": [
         {
	   "ruleId": "db674ad7-9935-4971-9412-8e9eca60a54d",
	   "source": [
	      {
		"name": "datalink",
		"weight": 0
	      }
	      ],
	    "destination": [
	       {
		 "name": "databricks",
		 "weight": 0.25
		},
		{
		 "name": "datalake",
		 "weight": 0.75
		}
		],
		 "allocationMethod": "proportional_fixed_weighting",
		 "telemetryMetricIndex": 0
		},
		{
		 "ruleId": "4ba8fa54-b1eb-49ff-a5d5-37be5502de66",
		 "source": [
			   {
			    "name": "aql",
			    "weight": 0
			   }
		           ],
			   "destination": [
			  {
			  "name": "cdc",
			  "weight": 0.5
			  },
			  {
			   "name": "ccm",
			   "weight": 0.5
			   }
			   ],
			   "allocationMethod": "even_split",
			   "telemetryMetricIndex": 0
			   },
		           {
			     "ruleId": "5fdda893-f3b7-449a-b389-d8ad3218ec85",
			     "source": [
			     {
			      "name": "benchmarking",
			      "weight": 0
			     }
			     ],
			     "destination": [
			      {
				"name": "vedas",
				"weight": 0
			       },
			       {
				"name": "cdc",
				"weight": 0
				}
				],
				"allocationMethod": "telemetry_consumption",
				"telemetryIdentifier": "custom",
				"telemetryMetricIndex": 2
				},
				{
				"ruleId": "fa9cffcf-40c0-4979-9061-4cac7b048401",
				"source": [
				{
				"name": "akp",
				"weight": 0
				},
				{
				"name": "aviatrix",
				"weight": 0
				}
				],
				"destination": [
				{
				"name": "targetprocess",
				"weight": 0
				},
				{
				"name": "counterstrike",
				"weight": 0
				},
				{
				"name": "datadog",
				"weight": 0
				}
				],
				"allocationMethod": "proportional_metric",
				"telemetryMetricIndex": 0
				}
				]
				}
}
```

DELETE /v3/cost-sharing/allocation

This API is used for deleting one or more allocations by specifying their IDs.

Query Arguments

| Parameter | Description | Default | Allowed |
| --- | --- | --- | --- |
| allocationIds | List of one or more Allocation IDs of the existing allocation(s) that need to be deleted | REQUIRED | One or more existing, valid Allocation IDs |

Example Request

```
curl --request DELETE \
	 --url https://api.cloudability.com/v3/cost-sharing/allocation \
	 --header 'authorization: ${JWT_TOKEN}' \
	 --header 'content-type: application/json' \
	 --header 'x-cldy-user-id: ${USER_ID}' \
	 --header 'x-fd-env-id: ${ENVIRONMENT_ID}' \
	 --data '{
		   "allocationIds": [
		   "0e5d398b-07e2-4969-854a-f01abe9e35ca",
		   "0b40db49-d796-46e2-b69f-b3778fe419b4"
				]
	         }'
```

Example Response

```
{
 "result": {
	     "message": "Deletion successful. 2 allocation records deleted. 0 rules deleted"
	    }
}
```

---

## Cost Sharing Result Report End Points

<!-- sub-header -->
- **breadcrumb:** Cloudability API > Cost Sharing End Points > Cost Sharing Result Report End Points
- **source_path:** SSVCLNQ/api-v3/cost_sharing_result_report.html
- **original_file:** points-cost-sharing-result-report-end.md
- **images:** []

## Cost Sharing Result Report End Points

Summary

Retrieve the Cost Sharing's result report.

Attributes of a result report are:

startDate - the start date of the cost data

endDate - the end date of the cost data

metric - the cost metric to use for this allocation

Example Request - Retrieving Result Report

Note: metric is required for any report using a non-Proportional type cost-sharing rule.

```
### Request (17)
curl "https://api.cloudability.com/v3/internal/reporting/cost-sharing?endDate=2019-03-12&startDate=2019-03-02&metric=unblended_cost" \\
     -u ‘[auth_token]:’
```

```
{
  "columnHeaders": {
    "dimensions": [
      "category1"
    ],
    "metrics": [
      {
        "name": "total_cost",
        "dataType": "currency"
      },
      {
        "name": "non_shared_amount",
        "dataType": "currency"
      },
      {
        "name": "shared_amount",
        "dataType": "currency"
      },
      {
        "name": "allocated_share_amount",
        "dataType": "currency"
      },
      {
        "name": "allocated_share_percent",
        "dataType": ""
      },
      {
        "name": "post_shared_amount",
        "dataType": "currency"
      }
    ]
  },
  "aggregates": [
    {
      "values": [
        "2107194.4920047736"
      ]
    }
  ],
  "filters": [],
  "count": 2,
  "pagination": {},
  "dates": {
    "start": "2019-03-02",
    "end": "2019-03-12"
  },
  "rows": [
    {
      "dimensions": [
        "little services"
      ],
      "metrics": [
        {
          "count": "0",
          "max": "0",
          "min": "0",
          "sum": "763436.0316036056"
        },
        {
          "count": "0",
          "max": "0",
          "min": "0",
          "sum": "0"
        },
        {
          "count": "0",
          "max": "0",
          "min": "0",
          "sum": "763436.0316036056"
        },
        {
          "count": "0",
          "max": "0",
          "min": "0",
          "sum": "0"
        },
        {
          "count": "0",
          "max": "0",
          "min": "0",
          "sum": "0"
        },
        {
          "count": "0",
          "max": "0",
          "min": "0",
          "sum": "0"
        }
      ]
    },
    {
      "dimensions": [
        "big services"
      ],
      "metrics": [
        {
          "count": "0",
          "max": "0",
          "min": "0",
          "sum": "135622.52503421396"
        },
        {
          "count": "0",
          "max": "0",
          "min": "0",
          "sum": "135622.52503421396"
        },
        {
          "count": "0",
          "max": "0",
          "min": "0",
          "sum": "0"
        },
        {
          "count": "0",
          "max": "0",
          "min": "0",
          "sum": "84070.49655704634"
        },
        {
          "count": "0",
          "max": "0",
          "min": "0",
          "sum": "0.10054724124811285"
        },
        {
          "count": "0",
          "max": "0",
          "min": "0",
          "sum": "219693.02159126033"
        }
      ]
    }
  ]
}
```

---

## Cost Sharing Rule Setting End Points

<!-- sub-header -->
- **breadcrumb:** Cloudability API > Cost Sharing End Points > Cost Sharing Rule Setting End Points
- **source_path:** SSVCLNQ/api-v3/cost_sharing_rule_setting.html
- **original_file:** points-cost-sharing-rule-setting-end.md
- **images:** []

## Cost Sharing Rule Setting End Points

Summary

Define a set of rules around how to allocate or distribute the shared costs.

The Rule Object

updatedAt (timestamp): when it was last updated

businessDimension (string): the business dimension whose values will drive cost-sharing

sourceIncludeBuckets : values from the Business Dimension to include

scopeDimension : scopes the cost-sharing to master payer or linked accounts

mapping : the mapping details

type : proportional, fixed, or even split mapping

targetExcludeBuckets : what business dimension values to exclude

metricName : the cost metric to use for this allocation

Example Rule Object

```
{
\t"updatedAt":"2019-03-13T18:31:36.129Z",
\t"businessDimension":"category4",
\t"sourceIncludeBuckets":[
\t\t"Cloudy Production",
\t\t"Cloudy Consolidated Master"
\t],
\t"scopeDimension":"account_identifier",
\t"mapping":{
\t\t"type":"ProportionalMapping",
\t\t"targetExcludeBuckets":[
\t\t\t"Cloudy IAM Account",
\t\t\t"Cloudy Staging"
    ],
\t\t"metricName":"unblended_cost"
  }
}
```

Example Cost Sharing Rule Requests

Example Request - Setting Proportional Allocation Rule

Allocate the shared costs to chosen targets proportionally based on the target's direct costs.

Note: metricName is required for the Proportional type (mode) only

```
curl -X "POST" "https://api.cloudability.com/v3/internal/cost-sharing/rules" \\
     -H 'Content-Type: application/json; charset=utf-8' \\
     -u ‘[auth_token]:’ \\
     -d $'{
  "scopeDimension": "account_identifier",
  "businessDimension": "category1",
  "sourceIncludeBuckets": [
    "CloudX Production",
    "CloudX Consolidated Master"
  ],
  "mapping": {
    "type": "ProportionalMapping",
    "targetExcludeBuckets": [
      "CloudX IAM Account",
      "Other Excluded Bucket"
    ],
    "metricName": "unblended_cost"
  }
}'
```

```
{
\t"updatedAt":"2019-03-13T18:31:36.129Z",
\t"businessDimension":"category4",
\t"sourceIncludeBuckets":[
\t\t"CloudX Production",
\t\t"CloudX Consolidated Master"
\t],
\t"scopeDimension":"account_identifier",
\t"mapping":{
\t\t"type":"ProportionalMapping",
\t\t"targetExcludeBuckets":[
\t\t\t"CloudX IAM Account",
\t\t\t"Cloudability Customer Trustee"
    ],
\t\t"metricName":"unblended_cost"
  }
}
```

---

## Cost Sharing Rules

<!-- sub-header -->
- **breadcrumb:** Cloudability API > Cost Sharing End Points > Cost Sharing Rules
- **source_path:** SSVCLNQ/api-v3/rules-cost-sharing.html
- **original_file:** points-cost-sharing-rules.md
- **images:** []

## Cost Sharing Rules

Summary

The Rules API handles the specific cost distribution logic within allocations, defining how costs flow from sources to destinations. This API supports all four allocation methods and their specific requirements.

Supported Allocation Methods

The supported allocation methods are as below with their respective features:

1. Even Split Distribution Equally distributes costs across destinations No weighting requirements Simplest implementation model
1. Proportional (Direct Charges) Distributes based on existing direct charges Dynamically adjusts with usage Supports multiple sources and destinations
1. Fixed Weighting Uses predefined weights for distribution Requires weights to total 100% Supports precise cost control
1. Telemetry/ Consumption Based Uses actual usage metrics Requires telemetry metric index Supports dynamic usage-based allocation

Key Features

The key features of Cost Sharing Rules allocation method are:

- Full CRUD operations for rules
- Batch operations support
- Validation of allocation methods
- Weight verification for fixed weighting
- Source and destination management
- Integration with telemetry systems

End Points

POST /v3/cost-sharing/allocation/${allocationId}/rule

This API is used for deleting one or more allocations by specifying their IDs.

Query Arguments

| Parameter | Description | Default | Allowed |
| --- | --- | --- | --- |
| allocationId | The ID of the existing allocation for which the Rule needs to be created | REQUIRED | An existing, valid Allocation ID |
| allocationMethod | The Allocation method using which the cost will be allocated/ distributed from “source(s)” to “target(s)” | REQUIRED | Allocation ids can be one of the following: Even_Split : Display label on the UI - Even Split Proportional_Metric : Display label on the UI - Proportional (Direct Charges) Proportional_Fixed_Weighting : Display label on the UI: Fixed Weighting Telemetry_Consumption : Display label on the UI - Telemetry / Consumption |
| source | List of one or more “source” nodes whose cost needs to be Reallocated/ Distributed | REQUIRED | NA |
| name (in source node | Name of the source | REQUIRED | Text |
| Weight (in source node) | Weight (Percentage/ Ratio) of the cost allocation |  | Floating point number |
| destination | List of one or more “destination” nodes to which the cost needs to be reallocated/distributed based on the “allocationMethod” specified in the Rule | REQUIRED | NA |
| name (in destination node) | Name of the destination | REQUIRED for the destination node, if present | Floating point number |
| weight (in destination node) | Weight (Percentage/ Ratio) of the cost allocation | REQUIRED for the “destination” node, if present. In case of Allocation Method Proportional_Fixed_Weighting . For this allocation method, the weights must add to 100% |  |

Even Split: Example Request

```
curl --request POST \
	 --url https://api.cloudability.com/v3/cost-sharing/allocation/d806a527-1554-49f3-9c8f-a5deae0e37b6/rule \
	 --header 'authorization: ${JWT_TOKEN}' \
	 --header 'content-type: application/json' \
	 --header 'x-fd-env-id: ${ENVIRONMENT_ID}' \
	 --data '{
		   "allocationMethod": "even_split",
		   "source": [
		   {
		     "name": "aql",
		     "weight": 0
		   }
		   ],
		    "destination": [
		     {
		      "name": "ccm",
		      "weight": 0
		      },
		      {
		      "name": "cdc",
		      "weight": 0
		      }
		      ]
		      }'
```

Even Split: Example Response

```
{
  "result": {
  "ruleId": "4ba8fa54-b1eb-49ff-a5d5-37be5502de66",
  "source": [
{
  "name": "aql",
  "weight": 0
}
],
 "destination": [
{
 "name": "cdc",
 "weight": 
},
{
 "name": "ccm",
 "weight": 0.5
}
],
 "allocationMethod": "even_split",
 "telemetryMetricIndex": 0
}
}
```

Proportional (Direct Charges): Example Request

```
curl --request POST \
	 --url https://api.cloudability.com/v3/cost-sharing/allocation/d806a527-1554-49f3-9c8f-a5deae0e37b6/rule \
	 --header 'authorization: ${JWT_TOKEN}' \
	 --header 'content-type: application/json' \
	 --header 'x-fd-env-id: ${ENVIRONMENT_ID}' \
	 --data '{
	          "allocationMethod": "proportional_metric",
	          "source": [
			{
			 "name": "akp",
			 "weight": 0
			},
			{
			 "name": "aviatrix",
			 "weight": 0
			}
			],
			"destination": [
			 {
			  "name": "counterstrike",
			  "weight": 0
			 },
			 {
		          "name": "datadog",
			  "weight": 0
			 },
			 {
			  "name": "targetprocess",
			  "weight": 0
			 }
			 ]
             }'
```

Proportional (Direct Charges): Example Response

```
{
{
  "result": {
  "ruleId": "fa9cffcf-40c0-4979-9061-4cac7b048401",
  "source": [
	{
	 "name": "akp",
	 "weight": 0
	 },
	{
	 "name": "aviatrix",
	 "weight": 0
       }
	],
	 "destination": [
	{
	 "name": "targetprocess",
	 "weight": 0
	},
       {
	 "name": "counterstrike",
	 "weight": 0
	},
       {
	 "name": "datadog",
	 "weight": 0
	}
	],
	 "allocationMethod": "proportional_metric",
	  telemetryMetricIndex": 0
       }
       }
```

Fixed Weighting: Example Request

```
curl --request POST \
	 --url https://api.cloudability.com/v3/cost-sharing/allocation/d806a527-1554-49f3-9c8f-a5deae0e37b6/rule \
	 --header 'authorization: ${JWT_TOKEN}' \
	 --header 'content-type: application/json' \
	 --header 'x-fd-env-id: ${ENVIRONMENT_ID}' \
	 --data '{
		   "allocationMethod": "proportional_fixed_weighting",
		   "source": [
	         {
		   "name": "datalink",
		   "weight": 0
	         }
		 ],
		   "destination": [
		 {
		   "name": "databricks",
		   "weight": 0.25
		 },
		 {
		   "name": "datalake",
		   "weight": 0.75
		  }
		  ]
		  }'
```

Fixed Weighting: Example Response

```
{
 "result": {
 "ruleId": "db674ad7-9935-4971-9412-8e9eca60a54d",
 "source": [
 {
  "name": "datalink",
  "weight": 0
 }
 ],
 "destination": [
 {
  "name": "databricks",
  "weight": 0.25
 },
 {
  "name": "datalake",
  "weight": 0.75
 }
 ],
  "allocationMethod": "proportional_fixed_weighting",
  "telemetryMetricIndex": 0
 }
 }
```

Telemetry/ Consumption: Example Request

```
curl --request POST \
     --url https://api.cloudability.com/v3/cost-sharing/allocation/d806a527-1554-49f3-9c8f-a5deae0e37b6/rule \
     --header 'authorization: ${JWT_TOKEN}' \
     --header 'content-type: application/json' \
     --header 'x-fd-env-id: ${ENVIRONMENT_ID}' \
     --data '{
		"allocationMethod": "telemetry_consumption",
		"source": [
	{
		"name": "benchmarking",
		"weight": 0
	}
			],
		"destination": [
	{
		"name": "cdc",
		"weight": 0
	},
	{
		"name": "vedas",
		"weight": 0
	}
	                       ],
	        "telemetryMetricIndex": 2,
	        "telemetryIdentifier": "custom"
       }'
			
```

Telemetry/ Consumption: Example Response

```
{
 "result": {
 "ruleId": "5fdda893-f3b7-449a-b389-d8ad3218ec85",
 "source": [
  {
   "name": "benchmarking",
   "weight": 0
  }
  ],
   "destination": [
  {
   "name": "vedas",
   "weight": 0
  },
  {
  "name": "cdc",
  "weight": 0
  }
  ],
  "allocationMethod": "telemetry_consumption",
  "telemetryIdentifier": "custom",
  "telemetryMetricIndex": 2
  }
  }
```

GET /cost-sharing/allocation/${allocationId}/rule/${ruleId}

This API is used to retrieve the details of an existing Rule.

Query Arguments

| Parameter | Description | Default | Allowed |
| --- | --- | --- | --- |
| allocationId | The ID of the existing allocation | REQUIRED | An existing, valid Allocation ID |
| ruleId | ID of the Rule whose details need to be retrieved | REQUIRED | An existing, valid Rule ID |

Example Request

```
curl --request GET \
      --url https://api.cloudability.com/v3/cost-sharing/allocation/d806a527-1554-49f3-9c8f-a5deae0e37b6/rule/4ba8fa54-b1eb-49ff-a5d5-37be5502de66 \
      --header 'authorization: ${JWT_TOKEN}' \
      --header 'x-fd-env-id: ${ENVIRONMENT_ID}'
```

Example Response

```
{
 "result": {
 "ruleId": "4ba8fa54-b1eb-49ff-a5d5-37be5502de66",
 "source": [
 {
 "name": "aql",
 "weight": 0
 }
 ],
 "destination": [
 {
 "name": "cdc",
 "weight": 0.5
 },
 {
 "name": "ccm",
 "weight": 0.5
 }
 ],
 "allocationMethod": "even_split",
 "telemetryMetricIndex": -1
 }
 }
	
```

PUT /cost-sharing/allocation/${allocationId}/rule

This API is used to or updating one or more Rules of an allocation.

Query Arguments

| Parameter | Description | Default | Allowed |
| --- | --- | --- | --- |
| allocationId | The ID of the existing allocation | REQUIRED | An existing, valid Allocation ID |
| rules | List of one or more nodes for updating Rules by ID | REQUIRED | List of nodes |
| ruleId | Id of the rule to be updated | REQUIRED | An existing, valid Rule ID |
| allocationMethod | The Allocation method using which the cost will be allocated/ distributed from “source(s)” to “target(s)” | REQUIRED | Allocation ids can be one of the following: Even_Split : Display label on the UI - Even Split Proportional_Metric : Display label on the UI - Proportional (Direct Charges) Proportional_Fixed_Weighting : Display label on the UI: Fixed Weighting Telemetry_Consumption : Display label on the UI - Telemetry / Consumption |
| source | List of one or more “source” nodes whose cost needs to be reallocated/ distributed | REQUIRED | NA |
| name (in source node) | Name of the source | REQUIRED | Text |
| weight (in source node) | Weight (Percentage/ Ratio) of the cost allocation | REQUIRED | Floating point number |
| destination | List of one or more destination nodes to which the cost needs to be reallocated/ distributed based on the allocationMethod specified in the rule | REQUIRED | NA |
| name (in destination node) | Name of the destination | REQUIRED for the destination node, if present | Text |
| weight (in destination node) | Weight (Percentage/ Ratio) of the cost allocation | REQUIRED for the destination node, if present In case of allocation method Proportional_Fixed_Weighting . For this allocation method, the weights must add up to 100% | Floating point number |

Example Request

```
curl --request PUT \
      --url https://api.cloudability.com/v3/cost-sharing/allocation/d806a527-1554-49f3-9c8f-a5deae0e37b6/rule \
      --header 'authorization: ${JWT_TOKEN}' \
      --header 'content-type: application/json' \
      --header 'x-cldy-user-id: ${USER_ID}' \
      --header 'x-fd-env-id: ${ENVIRONMENT_ID}' \
      --data '{
		"rules": [
		{
		 "allocationMethod": "proportional_fixed_weighting",
		 "source": [
		{
		 "name": "datalink",
	         "weight": 0
		}
		],
		"destination": [
	        {
		"name": "databricks",
		"weight": 0.25
		},
		{
		 "name": "docstore",
		 "weight": 0.75
		}
		],
		 "ruleId": "db674ad7-9935-4971-9412-8e9eca60a54d"
		}
		]
		}'
```

Example Response

```
{
 "result": {
 "allocationId": "d806a527-1554-49f3-9c8f-a5deae0e37b6",
 "businessDimensionIndex": 17,
 "createdAt": "2024-07-29T09:38:56.000Z",
 "owner": "Shilpesh Solanki",
 "updatedAt": "2024-10-15T02:08:09.000Z",
 "rules": [
  {
   "ruleId": "db674ad7-9935-4971-9412-8e9eca60a54d",
   "source": [
  {
   "name": "datalink",
   "weight": 0
  }
  ],
  "destination": [
  {
   "name": "docstore",
   "weight": 0.75
   },
   {
    "name": "databricks",
    "weight": 0.25
   }
   ],
   "allocationMethod": "proportional_fixed_weighting",
   "telemetryMetricIndex": 0
   },
  {
   "ruleId": "4ba8fa54-b1eb-49ff-a5d5-37be5502de66",
   "source": [
  {
   "name": "aql",
   "weight": 0
  }
  ],
  "destination": [
  {
   "name": "cdc",
   "weight": 0.5
  },
  {
   "name": "ccm",
   "weight": 0.5
  }
  ],
  "allocationMethod": "even_split",
  "telemetryMetricIndex": 0
  },
  {
  "ruleId": "5fdda893-f3b7-449a-b389-d8ad3218ec85",
  "source": [
  {
  "name": "benchmarking",
  "weight": 0
  }
  ],
  "destination": [
  {
  "name": "vedas",
  "weight": 0
  },
  {
   "name": "cdc",
   "weight": 0
  }
  ],
  "allocationMethod": "telemetry_consumption",
  "telemetryIdentifier": "custom",
  "telemetryMetricIndex": 2
  },
  {
  "ruleId": "fa9cffcf-40c0-4979-9061-4cac7b048401",
  "source": [
  {
   "name": "akp",
   "weight": 0
  },
  {
   "name": "aviatrix",
   "weight": 0
  }  
  ],
   "destination": [
  {
   "name": "targetprocess",
   "weight": 0
  },
  {
   "name": "counterstrike",
   "weight": 0
   },
   {
    "name": "datadog",
    "weight": 0
   }
   ]
    "allocationMethod": "proportional_metric",
    "telemetryMetricIndex": 0
   }
   ]
   }
   }
```

DELETE /cost-sharing/allocation/${allocationId}/rule

This API is used to delete one or more rules of an allocation.

Query Arguments

| Parameter | Description | Default | Allowed |
| --- | --- | --- | --- |
| allocationId | The ID of the existing allocation | REQUIRED | An existing, valid Allocation ID |
| ruleIds | Id of the rule which need to be deleted | REQUIRED | One or more existing, valid Rule Id(s) |

Example Request

```
curl --request DELETE \
     --url https://api.cloudability.com/v3/cost-sharing/allocation/d806a527-1554-49f3-9c8f-a5deae0e37b6/rule \
     --header 'authorization: ${JWT_TOKEN}' \
     --header 'content-type: application/json' \
     --header 'x-cldy-user-id: ${USER_ID}' \
     --header 'x-fd-env-id: ${ENVIRONMENT_ID}' \
     --data '{
"ruleIds": [
	     "4ba8fa54-b1eb-49ff-a5d5-37be5502de66",
	     "5fdda893-f3b7-449a-b389-d8ad3218ec85"
	    ]
              }'
```

Example Response

```
{
 "result": {
 "message": "Deletion successful. 2 rule records deleted."
}
}
```

---

## Cost Sharing Telemetry

<!-- sub-header -->
- **breadcrumb:** Cloudability API > Cost Sharing End Points > Cost Sharing Telemetry
- **source_path:** SSVCLNQ/api-v3/telemetry-cost-sharing.html
- **original_file:** points-cost-sharing-telemetry.md
- **images:** []

## Cost Sharing Telemetry

Summary

The Telemetry API manages usage-based metrics for cost allocation, enabling data-driven distribution based on actual resource consumption patterns.

Core Functions

The core functions for Telemetry include:

- Upload telemetry data via CSV
- Retrieve uploaded telemetry data
- Download telemetry files
- Delete telemetry records
- Access metric meta data
- Query available destinations

Data Requirements

Following data requirements need to be met for Telemetry API.

- Date: Time stamp for measurements
- Category: Business dimension mapping
- Value: Actual metric measurement
- CSV format validation
- Business dimension index mapping

Integration Points

The integration points for telemetry API include the following:

- Links with allocation rules
- Maps to business dimensions
- Supports custom metrics
- Enables dynamic cost distribution
- Maintains historical data

End Points

POST /cost-sharing/telemetry-data?businessDimensionIndex={{businessDimensionIndex}}

This API is used for uploading Telemetry data in a CSV format for a specific Business Dimension.

Query Arguments

| Parameter | Description | Default | Allowed |
| --- | --- | --- | --- |
| businessDimensionIndex | The allocation will be created for this Business Dimension Index | REQUIRED | Numeric values between 1 - 25 not already used in any allocation |
| files | CSV file containing the Telemetry Data | REQUIRED | A CSV file in a valid format. |

Telemetry File Specifications

| Collumn | Collumn Index | Nullable | Description |
| --- | --- | --- | --- |
| Date | 1 | No | A yyyy-MM-dd string. The value can be specified within and also without double-quotes. So “2025-01-25” AND 2025-01-25, both are valid values. When an uploaded Telemetry File is downloaded, the downloaded copy with have the date within double-quotes (eg. “2025-01-25”. |
| Business Dimension | 2 | No | The name of the column must be the name of a business dimension. The contents of the column must be values of that business dimension. |
| Metrics | 3 | No | Custom metric. Could be cost or usage metric, or other metric that may be relevant to the user or data source. Used for allocation. Column name should be descriptive of the metric. Must not be null or empty : The field should contain a value and cannot be left blank. Negative values are not supported: The field must contain a numeric value that is non-negative (i.e., zero or positive numbers are allowed) |

Example Request

```
curl --request POST \
      --url 'https://api.cloudability.com/v3/cost-sharing/telemetry-data?businessDimensionIndex=20' \
      --header 'accept: application/json, text/plain, */*' \
      --header 'authorization: ${JWT_TOKEN}' \
      --header 'content-type: multipart/form-data' \
      --header 'x-fd-env-id: ${ENVIRONMENT_ID}' \
      --form files=@/Downloads/telemetry_data.csv
```

Example Response

```
{
 "result": {
 "message": "telemetry data files uploaded successfully"
}
}
```

GET /cost-sharing/telemetry-data?businessDimensionIndex={{businessDimensionIndex}}

This API is used for retrieving the Telemetry data from the database for a specific Business Dimension previously uploaded through a CSV file.

Query Arguments

| Parameter | Description | Default | Allowed |
| --- | --- | --- | --- |
| businessDimensionIndex | The allocations will be created for this Business Dimension Index | REQUIRED | Numeric values between 1 - 25 not already used in any allocation |

Example Request

```
curl --request GET \
      --url 'https://api.cloudability.com/v3/cost-sharing/telemetry-data?businessDimensionIndex=20' \
      --header 'accept: application/json, text/plain, */*' \
      --header 'authorization: ${JWT_TOKEN}' \
      --header 'content-type: multipart/form-data; \
      --header 'x-fd-env-id: ${ENVIRONMENT_ID}'
			  
```

Example Response

```
{
 "result": [
{
 "fileName": "telemetry_data.csv",
 "createdAt": "2025-01-27T12:27:06.000Z",
 "updatedAt": "2025-01-27T12:27:06.000Z"
}
				]
				}
			  
```

GET /cost-sharing/telemetry-data/download?fileName=${fileName}&businessDimensionIndex=${businessDimensionIndex}

This API is used to download the Telemetry data file previously uploaded for the given Business Dimension.

Query Arguments

| Parameter | Description | Default | Allowed |
| --- | --- | --- | --- |
| businessDimensionIndex | The allocation will be created for this Business Dimension Index | REQUIRED | Numeric values between 1 - 25 not already used in any allocation |
| fileName | The name of the CSV file to be downloaded | REQUIRED | Text with a .csv extension |

Example Request

```
curl --request GET \
      --url 'https://api.cloudability.com/v3/cost-sharing/telemetry-data/download?fileName=telemetry_data.csv&businessDimensionIndex=20' \
      --header 'authorization: ${JWT_TOKEN}' \
      --header 'x-fd-env-id: ${ENVIRONMENT_ID}'
```

Example Response

```
Date,Category,Number of API Requests
 """2024-07-01""",prod_test,50
 """2024-07-01""",modeling,25
 """2024-07-01""",operative,25
 """2024-07-02""",apptio,50
 """2024-07-02""",ibm,25
 """2024-07-02""",TBM,25
			  
```

DELETE /cost-sharing/telemetry-data

This API is used for deleting one or more Telemetry data file(s) from the database for a specific Business Dimension previously uploaded through a CSV file.

Query Arguments

| Parameter | Description | Default | Allowed |
| --- | --- | --- | --- |
| businessDimensionIndex | The allocation will be created for this Business Dimension Index | REQUIRED | Numeric values between 1 - 25 not already used in any allocation |
| fileNames | List of one or more names of the files to be deleted | REQUIRED | List of file names |

Example Request

```
curl --request DELETE \
     --url https://api.cloudability.com/v3/cost-sharing/telemetry-data \
     --header 'accept: application/json, text/plain, */*' \
     --header 'authorization: ${JWT_TOKEN}' \
     --header 'content-type: application/json' \
     --header 'x-fd-env-id: ${ENVIRONMENT_ID}' \
     --data '{
 "fileNames": [
 "telemetry_data.csv"
 ],
 "businessDimensionIndex": 20
 }'
		s
```

Example Response

```
{
 "result": []
}
```

GET /cost-sharing/allocation/${businessDimensionIndex}/metrics-metadata

This API is used for retrieving the metadata of the metrics for which the data was uploaded through Telemetry files.

Query Arguments

| Parameter | Description | Default | Allowed |
| --- | --- | --- | --- |
| businessDimensionIndex | The allocation will be created for this Business Dimension Index | REQUIRED | Numeric values between 1 - 25 not already used in any allocation |

Example Request

```
curl --request GET \
      --url https://api.cloudability.com/v3/cost-sharing/allocation/14/metrics-metadata \
      --header 'authorization: ${JWT_TOKEN}' \
      --header 'x-fd-env-id: ${ENVIRONMENT_ID}'
```

Example Response

```
{
 "telemetryOptions": [
{
 "telemetryDataSource": "custom",
 "telemetryMetrics": [
{
 "metricName": "Number of API Requests",
 "metricIndex": 1
},
{
 "metricName": "Share",
 "metricIndex": 2
}
]
}
]
}
	
```

GET /cost-sharing/telemetry-destinations?businessDimensionIndex=${businessDimensionIndex}&metricIndex=${metricIndex}

This API is used for retrieving the Telemetry destinations for the given Business Dimension and Metric Index.

Query Arguments

| Parameter | Description | Default | Allowed |
| --- | --- | --- | --- |
| businessDimensionIndex | The allocation will be created for this Business Dimension Index | REQUIRED | Numeric values between 1 - 25 not already used in any allocation |
| metricIndex | Index of the metric | REQUIRED | Numeric value |

Example Request

```
curl --request GET \
      --url 'https://api.cloudability.com/v3/cost-sharing/telemetry-destinations?businessDimensionIndex=20&metricIndex=1'\
      --header 'authorization: ${JWT_TOKEN}' \
      --header 'x-fd-env-id: ${ENVIRONMENT_ID}'
```

Example Response

```
{
  "result": [
  "test",
  "modeling",
  "operative",
  "apptio",
  "ibm",
  "TBM"
 ]
 }
```

---

## Databricks End Points

<!-- sub-header -->
- **breadcrumb:** Cloudability API > Databricks End Points
- **source_path:** SSVCLNQ/api-v3/databricks_public_api.html
- **original_file:** api-databricks-end-points.md
- **images:** []

## Databricks End Points

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

---

## Datadog End Points

<!-- sub-header -->
- **breadcrumb:** Cloudability API > Datadog End Points
- **source_path:** SSVCLNQ/api-v3/datadog_public_api.html
- **original_file:** api-datadog-end-points.md
- **images:** []

## Datadog End Points

Summary

These end points are used to manage Datadog integration within Cloudability that support the creation, updation and deletion of Datadog credentials within Cloudability. .

With Cloudability being available in multiple regions, all references to api.cloudability.com in this API documentation should be referred to as mentioned in Getting started with Cloudability API V3 .

The Credential Object

- orgLabel (string) - organization label endpoint
- apiKey (string) - the api key
- applicationKey (string) - the application key
- rateLimit (string) - the api key limit
- endpoint (object) - account region endpoint
- datadogPublicId (string) - the publicId created after the datadog account is credentialized, it is used to prevent duplicates. Generated by Cloudability.
- apiKeyLast4 (string) - the last 4 digit of the apiKey
- applicationKeyLast4 (string) - the last 4 digit of the application Key
- state (string) - examples "unverified", "verified", "error"
- applicationKeyDetails (string) - contains the below details: owner (string) - details of application key owner name (string) - name of application key
- apiKeyDetails (string) - contains the below details: name (string) - details of api key creator created (string) - date timestamp corresponding to api key creation created_by (string) - email id of creator
- hostTotals (string) - contains the below details: total_up (string) - total host up total_active (string) - total host active
- reporting(list of string) : "Cost", "Utilization"
- isParentAccount(boolean) : flag to determine if an account is parent

End Points

end point : /v3/datadog/credentials for RESTful CRUD interactions

end point : /v3/datadog/credentials

end point : /v3/datadog/credentials/<publicKeyID>

end point : /v3/vendors/ datadog /accounts/<publicKeyID>/verify

List Accounts This API is used for listing Datadog accounts

Example Request

```
curl 'https://api.cloudability.com/v3/datadog/credentials' \\ 
 -u ‘[auth_token]:’                
```

Example Response

```
{ 
"result": [ 
{ 
"datadogPublicId": "a111aa11-11a1-1a1a-a1aa-1aa111aaa11a", 
"orgLabel": "Cloudability", 
"apiKeyLast4": "1111", 
"applicationKeyLast4": "3333", 
"rateLimit": 300, 
"state": "VERIFIED", 
"endpoint": "datadoghq.com", 
"applicationKeyDetails": { 
"owner": "emailid@email.com", 
"name": "new key" 
}, 
"apiKeyDetails": { 
"created_by": "emailid@email.com", 
"name": "default-auto-generated", 
"created": "2020-03-20 19:56:38" 
}, 
"hostTotals": { 
"total_up": 0, 
"total_active": 0 
}, 
"reporting": [ 
"Utilization" 
], 
"isParentAccount": false 
} 
] 
}  
```

Create Account - This API is used for creating a new Datadog credential

POST /v3/datadog/credentials

Example Request

```
curl -X POST --location 'https://api.cloudability.com/v3/datadog/credentials' \ 
         --header 'Content-Type: application/json' \   
         --data '{ 
    "orgLabel": "org-label", 
    "apiKey": "apikeya111aa11-11a1-1a1a-a1aa-1aa111aaa11a", 
    "applicationKey": "applicationkeyaa111aa11-11a1-1a1a-a1aa-1aa111aaa11a", 
    "rateLimit": 600, 
    "endpoint": "datadoghq.com", 
    "reporting": [ 
        "Cost", 
        "Utilization" 
    ], 
    "subscriptionModel": "Marketplace", 
    "dependentCSP": "AZURE" 
}'  
```

Example Response

```
{ 
    "result": { 
        "datadogPublicId": "aa111aa11-11a1-1a1a-a1aa-1aa111aaa11a", 
        "orgLabel": "org-label", 
        "apiKeyLast4": "a11a", 
        "applicationKeyLast4": "a11a", 
        "rateLimit": 600, 
        "state": "ERROR", 
        "endpoint": "datadoghq.com", 
        "applicationKeyDetails": {}, 
        "apiKeyDetails": { 
            "name": "Not Set" 
        }, 
        "hostTotals": { 
            "total_up": 0, 
            "total_active": 0 
        }, 
        "reporting": [ 
            "Cost", 
            "Utilization" 
        ], 
        "subscriptionModel": "Marketplace", 
        "dependentCSP": "AZURE", 
        "isParentAccount": false 
    } 
} 
```

Update Account - This API is used for updating the credential with the given ID

PUT v3/datadog/credentials/:publicKeyId

Example Request

```
curl --location --request PUT 'https://api.cloudability.com/v3/datadog/credentials/:publicKeyId' \ 
         --header 'Content-Type: application/json' \ 
         --data '{ 
    "orgLabel": "org-label", 
    "apiKey": "apikeyaa111aa11-11a1-1a1a-a1aa-1aa111aaa11a", 
    "applicationKey": "applicationkeyaa111aa11-11a1-1a1a-a1aa-1aa111aaa11a", 
    "rateLimit": 600, 
    "endpoint": "datadoghq.com", 
    "reporting": [ 
        "Cost", 
        "Utilization" 
    ], 
    "subscriptionModel": "Marketplace", 
    "dependentCSP": "AZURE" 
}’ 
```

Example Response

```
{ 
    "result": { 
        "datadogPublicId": "a111aa11-11a1-1a1a-a1aa-1aa111aaa11a", 
        "orgLabel": "org-label", 
        "apiKeyLast4": "a11a", 
        "applicationKeyLast4": "a11a", 
        "rateLimit": 600, 
        "state": "ERROR", 
        "endpoint": "datadoghq.com", 
        "applicationKeyDetails": {}, 
        "apiKeyDetails": { 
            "name": "Not Set" 
        }, 
        "hostTotals": { 
            "total_up": 0, 
            "total_active": 0 
        }, 
        "reporting": [ 
            "Cost", 
            "Utilization" 
        ], 
        "subscriptionModel": "Marketplace", 
        "dependentCSP": "AZURE", 
        "isParentAccount": false 
    } 
} 
```

Retrieve Account - This API is used for retrieving the Datadog credential information.

GET v3/datadog/:publicKeyId

Example Request

```
curl --location 'https://api.cloudability.com/v3/datadog/:publicKeyId' 
```

Example Response

```
{ 
    "result": { 
        "datadogPublicId": "a111aa11-11a1-1a1a-a1aa-1aa111aaa11a", 
        "orgLabel": "org-label", 
        "apiKeyLast4": "a11a", 
        "applicationKeyLast4": "a11a", 
        "rateLimit": 600, 
        "state": "ERROR", 
        "endpoint": "datadoghq.com", 
        "applicationKeyDetails": {}, 
        "apiKeyDetails": { 
            "name": "Not Set" 
        }, 
        "hostTotals": { 
            "total_up": 0, 
            "total_active": 0 
        }, 
        "reporting": [ 
            "Cost", 
            "Utilization" 
        ], 
        "subscriptionModel": "Marketplace", 
        "dependentCSP": "AZURE", 
        "isParentAccount": false 
    } 
} 
```

Delete Account - This API is used for deleting the credential with the given ID.

DELETE v3/internal/datadog/credentials/:publicKeyId

Example Request

```
curl -X DELETE 'https://api.cloudability.com/v3/datadog/credentials/:publicKeyId’ 

-u ‘[auth_token]:’   
```

Verify Account - This API is used for verifying the credential with the given ID.

POST v3/internal/datadog/credentials/:publicKeyId/verify

Example Request

```
curl --X POST 
'https://api.cloudability.com/v3/datadog/credentials/:publicKeyId/verify 
-u ‘[auth_token]:’ 
```

Example Response

```
{
         "result": {
         "datadogPublicId": "a111aa11-11a1-1a1a-a1aa-1aa111aaa11a",
         "orgLabel": "test",
         "apiKeyLast4": "a11a",
         "applicationKeyLast4": "a11a",
         "rateLimit": 600,
         "state": "ERROR",
         "endpoint": "datadoghq.com",
         "applicationKeyDetails": {},
         "apiKeyDetails": {
         "name": "Not Set"
         },
         "hostTotals": {
         "total_up": 0,
          "total_active": 0
         }
     }
}
```

---

## FOCUS Ingress End Points

<!-- sub-header -->
- **breadcrumb:** Cloudability API > FOCUS Ingress End Points
- **source_path:** SSVCLNQ/api-v3/focus_public_api.html
- **original_file:** api-focus-ingress-end-points.md
- **images:** []

## FOCUS Ingress End Points

Summary

Following are the list of public APIs provided specific to Custom Data.

With Cloudability being available in multiple regions, all references to api.cloudability.com in this API documentation should be referred to as mentioned in Getting started with Cloudability API V3 .

End Point Particulars

end point : /v3/vendors/byod/accounts for RESTful CRUD interactions

end point : /v3/vendors/byod/accounts?include=permissions&viewId=0

end point : /v3/vendors/byod/accounts/<account_id>?include=permissions&viewId=0

end point : /v3/vendors/byod/accounts/<account_id>?viewId=0

end point : /v3/vendors/byod/accounts/<account_id>/verification?include=permissions,associatedAccounts&viewId=0

end point : /v3/vendors/byod/accounts/<account_id>/archive?viewId=0

end point : /v3/vendors/byod/permissions/accounts/<account_id>

Parameters

- type (string) - "aws_byod_role” | “azure_byod” | “gcp_byod_role”,
- vendorKey (string) - “byod”
- byodVendor (string) - Name of FOCUS data vendor
- vendorAccountId (string) - account id,
- projectId (string) - GCP project ID
- tenantId (string) - UUID – Azure tenant ID,
- roleName (string) - “CloudabilityCustomDataRole “ - AWS role name
- externalId (string) - AWS external id
- subscriptionGuid (string) - UUID – Azure subscription ID,
- resourceGroupName (string) - Azure resource group name, storageAccountName(string): Azure storage account name,
- rootDir (string) - root directory path,
- subDirs (string) - sub directory path if any,
- manifestPrefix (string) - <this-value>-Manifest.json

End Points

POST v3/vendors/byod/accounts

This API is used for creating a new Databricks credential

Example Request for AWS

```
{
"vendorAccountId": "11111166421",
"type": "aws_byod_role",
"byodVendor": "GitHub",
"byodCostReportSpec": {
"rootDir": "byodbucket",
"subDirs": "subFolder",
"manifestPrefix": "cost-and-usage"
}
}
```

Example Response for AWS

```

"result": {
"id": "byod_11111166421_GitHub",
"vendorAccountName": "byod_11111166421_GitHub",
"vendorAccountId": "byod_11111166421_GitHub",
"vendorKey": "byod",
"verification": {
"state": "unverified"
},
"authorization": {
"type": "aws_byod_role",
"roleName": "CloudabilityBYODRole",
"externalId": "aa625912-a33b-4e64-85a4-81349d8d6ea1",
"rootDir": "byodbucket",
"subDirs": "subFolder",
"manifestPrefix": "cost-and-usage"
},
"createdAt": "2024-06-13T12:37:43+05:30",
"consumerOrgId": "",
"byodVendor": "GitHub"
}
}


```

Example Request for Azure

```
{
"vendorAccountId": "1111010",
"type": "azure_byod",
"byodVendor": "GitHub",
"tenantId": "aa2a724a-8aaa-4a66-813a-a6a9aa4a3021",
"byodAzureCostReportSpec": {
"subscriptionGuid": "a4a2aaa5-2384-4090-8a3a-7a01a6a417a1",
"resourceGroupName": "billingexportresourcegroup",
"storageAccountName": "billingexportstorageacct",
"rootDir": "focuspricesheetcontainer",
"subDirs": "focuspricesheetdir",
"manifestPrefix": "FocusTest"
}
```

Example Response for Azure

```
{
"result": {
"id": "byod_1111010_GitHub",
"vendorAccountName": "byod_1111010_GitHub",
"vendorAccountId": "byod_1111010_GitHub",
"vendorKey": "byod",
"verification": {
"state": "unverified"
},
"authorization": {
"type": "azure_byod",
"tenantId": "aa2a724a-8aaa-4a66-813a-a6a9aa4a3021",
"subscriptionGuid": "a4a2aaa5-2384-4090-8a3a-7a01a6a417a1",
"resourceGroupName": "billingexportresourcegroup",
"storageAccountName": "billingexportstorageacct",
"tenancyId": "aa2a724a-8baa-4a66-813a-a6a9aa4a3021",
"rootDir": "focuspricesheetcontainer",
"subDirs": "focuspricesheetdir",
"manifestPrefix": "FocusTest"
},
"createdAt": "2024-06-13T12:22:02+05:30",
"consumerOrgId": "",
"byodVendor": "GitHub"
}
}




```

Example Request for GCP

```
{
"vendorAccountId": "01A4AA-A4A7A3-AAAAAA",
"type": "gcp_byod_role",
"byodVendor": "GitHub",
"projectId": "project",
"byodCostReportSpec": {
"rootDir": "gcs_bucket",
"subDirs": "my/sub/dirs",
"manifestPrefix": "cost-and-usage"
}
}
```

Example Response for GCP

```

"result": {
"result": {
"id": "byod_01A4AA-A4A7A3-AAAAAA_GitHub",
"vendorAccountName": "byod_01A4AA-A4A7A3-AAAAAA_GitHub",
"vendorAccountId": "byod_01A4AA-A4A7A3-AAAAAA_GitHub",
"vendorKey": "byod",
"verification": {
"state": "unverified"
},
"authorization": {
"type": "gcp_byod_role",
"rootDir": "gcs_bucket",
"subDirs": "my/sub/dirs",
"manifestPrefix": "cost-and-usage"
},
"createdAt": "2024-06-13T12:29:45+05:30",
"consumerOrgId": "",
"byodVendor": "GitHub"
}
}
```

PUT v3/vendors/byod/accounts/<accountId>

This API is used for updating the credential with the given ID

Example Request for AWS

```
{
"vendorAccountId": "byod_111111111111_zoomnew",
"type": "aws_byod_role",
"byodVendor": "zoomnew",
"byodCostReportSpec": {
"rootDir": "byodbucket",
"subDirs": "subFolder1",
"manifestPrefix": "cost-and-usage"
}
}
```

Example Response for AWS

```
{
"result": {
"id": "byod_111111111111_zoomnew",
"vendorAccountName": "byod_111111111111_zoomnew",
"vendorAccountId": "byod_111111111111_zoomnew",
"vendorKey": "byod",
"verification": {
"state": "unverified"
},
"authorization": {
"type": "aws_byod_role",
"roleName": "CloudabilityBYODRole",
"externalId": "f1cf6025-a2e5-4252-b3bd-0580b384c1fa",
"rootDir": "byodbucket",
"subDirs": "subFolder1",
"manifestPrefix": "cost-and-usage"
},
"createdAt": "2024-06-17T14:54:27+05:30",
"consumerOrgId": "",
"byodVendor": "zoomnew"
}
}
```

GET /v3/vendors/byod/accounts/<accountID>

This API is used for returning byod credentials for the given account.

Example Response for AWS

```
{
"result": {
"id": "byod_111111111111_GitHub",
"vendorAccountName": "byod_111111111111_GitHub",
"vendorAccountId": "byod_111111111111_GitHub",
"vendorKey": "byod",
"verification": {
"state": "unverified"
},
"authorization": {
"type": "aws_byod_role",
"roleName": "CloudabilityBYODRole",
"externalId": "8e68ee11-8685-414b-982c-32871d62b322",
"rootDir": "s3byodbucket",
"subDirs": "subFolders",
"manifestPrefix": "cost-and-usage"
},
"createdAt": "2024-06-12T11:27:55+05:30",
"consumerOrgId": "",
"byodVendor": "GitHub"
}
}
```

Example Response for Azure

```
{
"result": {
"id": "byod_1111111_GitHub",
"vendorAccountName": "byod_1111111_GitHub",
"vendorAccountId": "byod_1111111_GitHub",
"vendorKey": "byod",
"verification": {
"state": "verified",
"lastVerificationAttemptedAt": "2024-06-17T09:19:53+05:30"
},
"authorization": {
"type": "azure_byod",
"tenantId": "cf2c724d-8bfd-4b66-813d-e6f9df4f3022",
"tenancyId": "cf2c724d-8bfd-4b66-813d-e6f9df4f3022"
},
"createdAt": "2024-06-13T12:01:46+05:30",
"consumerOrgId": "",
"byodVendor": "GitHub"
}
}
```

Example Response for GCP

```
{
"result": {
"id": "byod_01A091-A83A6A-1A55AA_GitHub",
"vendorAccountName": "byod_01A091-A83A6A-1A55AA_GitHub",
"vendorAccountId": "byod_01A091-A83A6A-1A55AA_GitHub",
"vendorKey": "byod",
"verification": {
"state": "verified",
"lastVerificationAttemptedAt": "2024-06-17T09:13:14+05:30"
},
"authorization": {
"type": "gcp_byod_role",
"rootDir": "staging-rightsizing-test",
"subDirs": "byod_data",
"manifestPrefix": "cost-and-usage"
},
"createdAt": "2024-06-13T12:52:44+05:30",
"consumerOrgId": "",
"byodVendor": "GitHub"
}
}
```

GET v3/vendors/byod/accounts

This API is used for returning all byod credentials for given org.

Example Response

```
{
"result": [
{
"id": "byod_111111111111_GitHub",
"vendorAccountName": "byod_111111111111_GitHub",
"vendorAccountId": "byod_111111111111_GitHub",
"vendorKey": "byod",
"verification": {
"state": "verified",
"lastVerificationAttemptedAt": "2024-06-11T17:44:01+05:30"
},
"authorization": {
"type": "aws_byod_role",
"roleName": "CloudabilityByodRole",
"externalId": "11111111-2222-3333-4444-555555555555",
"region": "us-west-2",
"rootDir": "s3byodbucket",
"subDirs": "subFolder",
"manifestPrefix": "cost-and-usage"
},
"createdAt": "2024-06-11T17:42:31+05:30",
"consumerOrgId": "",

"byodVendor": "GitHub"
},
{
"id": "byod_111111111111_GitHub",
"vendorAccountName": "byod_111111111111_GitHub",
"vendorAccountId": "byod_111111111111_GitHub",
"vendorKey": "byod",
"verification": {
"state": "unverified"
},
"authorization": {
"type": "aws_byod_role",
"roleName": "CloudabilityBYODRole",
"externalId": "8e68ee11-8685-414b-982c-32871d62b322",
"rootDir": "s3byodbucket",
"subDirs": "subFolder",
"manifestPrefix": "cost-and-usage"
},
"createdAt": "2024-06-12T11:27:55+05:30",
"consumerOrgId": "",

"byodVendor": "GitHub"
}
]
}
```

DELETE v3/vendors/byod/accounts/:accountId

This API is used for deleting the credential with the given ID.

Example Response

```
{
"result": {
"message": "Successfully deleted",
"vendorKey": "byod",
"vendorAccountId": "111111111111"
}
}
```

DELETE v3/vendors/byod/accounts/:accountId

This API is used for deleting the credential with the given ID.

Example Response

```
{
"result": {
"message": "Successfully deleted",
"vendorKey": "byod",
"vendorAccountId": "111111111111"
}
}
```

POST v3/vendors/byod/accounts/:accountId/verification

This API is used for verifying the credential with the given ID.

Example Response for AWS

```
{
"result": {
"id": "byod_111111111111_GitHub",
"vendorAccountName": "byod_111111111111_GitHub",
"vendorAccountId": "byod_111111111111_GitHub",
"vendorKey": "byod",
"verification": {
"state": "verified",
"lastVerificationAttemptedAt": "2024-06-17T09:08:58+05:30"
},
"authorization": {
"type": "aws_byod_role",
"roleName": "CloudabilityByodRole",
"externalId": "11111111-2222-3333-4444-555555555555",
"region": "us-west-2",
"rootDir": "s3byodbucket",
"subDirs": "subFolder",
"manifestPrefix": "cost-and-usage"
},
"createdAt": "2024-06-11T17:42:31+05:30",
"consumerOrgId": "",
"byodVendor": "GitHub"
}
}


```

Example Response for Azure

```
{
"result": {
"id": "byod_1111111_GitHub",
"vendorAccountName": "byod_1111111_GitHub",
"vendorAccountId": "byod_1111111_GitHub",
"vendorKey": "byod",
"verification": {
"state": "verified",
"lastVerificationAttemptedAt": "2024-06-17T09:19:53+05:30"
},
"authorization": {
"type": "azure_byod",
"tenantId": "aa2a724a-8aaa-4a66-813a-a6a9aa4a3022",
"tenancyId": "aa2a724a-8aaa-4a66-813a-a6a9aa4a3022"
},
"createdAt": "2024-06-13T12:01:46+05:30",
"consumerOrgId": "",
"byodVendor": "GitHub"
}
}


```

Example Response for GCP

```
{
"result": {
"id": "byod_01A091-A83A6A-1A55AA_GitHub",
"vendorAccountName": "byod_01A091-A83A6A-1A55AA_GitHub",
"vendorAccountId": "byod_01A091-A83A6A-1A55AA_GitHub",
"vendorKey": "byod",
"verification": {
"state": "verified",
"lastVerificationAttemptedAt": "2024-06-17T09:13:14+05:30"
},
"authorization": {
"type": "gcp_byod_role",
"rootDir": "staging-rightsizing-test",
"subDirs": "byod_data",
"manifestPrefix": "cost-and-usage"
},
"createdAt": "2024-06-13T12:52:44+05:30",
"consumerOrgId": "",
"byodVendor": "GitHub"
}
}
```

POST v3/vendors/databricks/accounts/:accountId/archive

This API is used for archiving the credential with the given ID.

Example Response for AWS

```
{
"result": {
"id": "byod_999999999933_GitHub",
"vendorAccountName": "byod_999999999933_GitHub",
"vendorAccountId": "byod_999999999933_GitHub",
"vendorKey": "byod",
"verification": {
"state": "archived"
},
"meta": {},
"consumerOrgId": ""
}
}
```

---

## Getting started with Cloudability API V3

<!-- sub-header -->
- **breadcrumb:** Cloudability API > Getting started with Cloudability API V3
- **source_path:** SSVCLNQ/api-v3/getting_started_with_the_cloudability.html
- **original_file:** api-getting-started-cloudability-v3.md
- **images:** []

## Getting started with Cloudability API V3

API Authentication

Author note: Authentication for Cloudability Commercial, Essential, Standard and Premium

You can use Cloudability API keys or Access Administration apptio-opentoken to authenticate Cloudability API requests.

Permissions for API interactions to create, update, read, and delete correspond with Cloudability user permissions. For example, only a Cloudability Admin can provision a new container cluster for data collection, while any Cloudability User with API access can get an existing container cluster's resource usage information.

| Region | Base URL |
| --- | --- |
| US | api.cloudability.com |
| US Gov Cloud (Federal) | api.usgov.cloudability.com |
| APAC | api-au.cloudability.com |
| Europe | api-eu.cloudability.com |
| Middle East | api-me.cloudability.com |
| Canada | api-ca.cloudability.com |
| India | api-in.cloudability.com |
| Japan | api-jp.cloudability.com |
| Singapore | api-sg.cloudability.com |

In GovCloud environments, you must use Access Administration apptio-opentoken to authenticate Cloudability API requests. Authentication using Cloudability API keys is not supported in GovCloud environments.

Cloudability API keys

To create a Cloudability API Key:

1. Open the following URL in your web browser: https://app.apptio.com/cloudability#/settings/preferences .
1. Under Cloudability API section, select Enable API . An API Key is generated and displayed in the text box.

Access Administration apptio-opentoken

For information on how to get an apptio-opentoken, refer to Access Administration API: Authentication via API keys .

Author note: Authentication for Cloudability Government

API interactions using Coudability API keys

Use the apptio-opentoken to enable access to our API. Visit Enhanced Access Administration API: Authentication via API keys to learn how to get an apptio-opentoken.

API interactions with Cloudability are secured over https. Your apptio-opentoken forms the username component of the basic auth header. So the authorization header would look something like:

Authorization: Basic

Example

The following API call returns a list of all current budgets.

```
curl https://api.cloudability.com/v3/budgets -u 'Your_API_Key:'
```

API Interactions

Author note: Authentication for Cloudability Commercial, Essential, Standard and Premium

API interactions using Coudability API keys

API interactions with Cloudability are secured over HTTPS. Your token forms the username component of the Basic Auth header. The authorization header for basic authentication will be in the following format:

Authorization: Basic

Example

The following API call returns a list of all current budgets.

```
curl https://api.cloudability.com/v3/budgets -u 'Your_API_Key:'
```

API interactions using Frontdoor apptio-opentoken

With this authentication method, pass the apptio-opentoken and apptio-environmentid in header.

Example

The following API returns a list of all current budgets.

```
curl https://api.cloudability.com/v3/budgets -H "apptio-opentoken: [apptio opentoken]" -H "apptio-environmentid: [apptio Access Administration environment id]"
```

Response Format

All successful responses will be in the following format:

```
{
    result: {} or [],
    meta: {},
}
```

- result will contain the results or payload for the call.
- Ancillary information (such as pagination breakdowns and others) will exist in the meta attribute, if relevant.
- Primitive values will be null if no value is present (that is, numbers, strings).
- Objects and arrays will return their empty states ( [] ) if no value is present.
- Dates are represented in ISO 8601 standard and use the YYYY-MM-DD format.

Headers

POST and PUT requests

Content-Type: application/json

GET requests (for all end points)

Accept: application/json

GET requests (supported by some end points)

Accept: text/csv

Authorization (if using Cloudability API keys)

Authorization: Basic <cldy_token>

Pagination

Not all end points support pagination. The end points that do not support pagination will always return all records. The end points that support pagination will return the first 50 matching records by default.

When attempting pagination, you must use the limit and offset parameters together. When you use these parameters, the result set will be restricted to the specified limit from the offset value.

The default value for limit is 50 (returns 50 records) and offset is 0 (start of the records).

Example

The following example shows how to use the limit and offset parameters with sort .

/views?limit=5&offset=20

Sorting

Use the sort query parameter sort your results. To specify the sort order, you can add - (descending) or + (ascending) before the attribute.

Examples

Sort the results for the portfolio end point by the end attribute in descending order.

/portfolio/ec2?sort=-end

Sort the results for the portfolio end point by the end attribute in ascending order.

/portfolio/ec2?sort=%2bend

(Make sure to correctly encode the + symbol.)

Filtering

When you use the filter query parameter, you supply a dimension you want to filter on, followed by the filter expression.

Filtered queries restrict the rows that are included in the result. Only the rows that meet the filter conditions are included in the result. Note that the client libraries automatically URL encode the filter operators. However, if you make requests directly to the protocol, you must explicitly URL encode the following filter operators. Also, filtering occurs before any dimensions are aggregated so that the returned metrics represent the total for only the relevant records.

Filter syntax: name operator expression

name: The name of the dimension on which to filter.

operator: Specifies the type of filter match to use. You can use the following operators:

== (equals)

!= (does not equal)

> (greater than)

< (less than)

>= (greater than or equal to)

<= (less than or equal to)

=@ (contains)

!=@ (does not contain)

expression: States the values included in the results.

To apply multiple filters to a request, delimit with commas in one filter parameter.

Examples

Check if the state is active:

/portfolio/ec2?filter=state==active

Check if the state is retired:

/portfolio/ec2?filter=state==retired

Check if the end is less than 1541803776000:

/portfolio/ec2?filter=end<1541803776000

Check if the end is greater than 1541803776000:

/portfolio/ec2?filter=end>1541803776000

Apply multiple filters:

/portfolio/ec2?filter=state==active,end>1541803776000

Cloudability end point examples

The documentation for each end point will include a number of examples which will show how to interact with the API. The examples will use cURL for HTTP interactions and jq for parsing JSON. Both of these CLI tools are widely used and can be easily employed to interact with a RESTful API.

---

## Governance End Points

<!-- sub-header -->
- **breadcrumb:** Cloudability API > Governance End Points
- **source_path:** SSVCLNQ/api-v3/governance_endpoints.html
- **original_file:** api-governance-end-points.md
- **images:** []

## Governance End Points

Summary

Cloud costs are easier to control before resources are deployed than after they're running in production. Cloudability's Governance API integrates directly into your development workflow, enabling teams to estimate costs, enforce policies, and catch budget issues during the pull request stage—before they impact your cloud bill.

Base URL and Versioning

All API endpoints use path-based versioning with the following base path: /v3/governance

API Categories

The Governance API is organized into the following categories:

1. Governance Set Up GitHub Integration: /github/installations, /github/check-runs, repositories/github HCP Terraform Integration: /hcp/runtask/credentials, /hcp/runtask/credentials/active, /hcp/runtask/{callback_path}
1. Deployment, Project & Preferences Management Manage deployments: /deployments, /deployments/{id}, deployments/{id}/policies, deployments/{id}/guardrails/cost Organize deployments into projects: deployments/move Create and manage projects: /projects, /projects/{id} Manage preferences: /preferences, /preferences/default-accounts
1. Policy Management & Evaluation Create and manage tagging and resource type policies: /policies, policies/{id}, /policies/options/{vendor_key} Create and manage cost guardrails: /guardrails/cost, /guardrails/cost/{id} Evaluate Terraform changes against resource type and tagging policies: /policy-evaluation/terraform
1. Cost Estimation & Resource Recommendation Calculate infrastructure cost differences from Terraform plans: /cost-estimate/terraform/diff Evaluate cost guardrails based on cost estimation Track cost impacts across deployments Generate resource recommendations: /recommendation/terraform
1. Pull Requests Tracking Get pull request details: /pull-requests, /pull-requests/{id} Approve pull requests
1. Metrics & Reporting Repository adoption metrics: /metrics/repo-adoption Policy compliance statistics: /metrics/policy-compliance Pull Request Statistics: /metrics/pr-stats Cost difference tracking by project: /total-cost-diff

---

## Cost Estimation & Resource Recommendation

<!-- sub-header -->
- **breadcrumb:** Cloudability API > Governance End Points > Cost Estimation & Resource Recommendation
- **source_path:** SSVCLNQ/api-v3/cost_estimation_resource_recommendation.html
- **original_file:** points-cost-estimation-resource-recommendation.md
- **images:** []

## Cost Estimation & Resource Recommendation

These endpoints help you understand the cost impact of infrastructure changes before deployment.

### Calculate Terraform Cost Difference – including cost guardrail evaluation

| Endpoint | POST /v3/governance/cost-estimate/terraform/diff |
| --- | --- |
| Endpoint | POST /v3/governance/cost-estimate/terraform/diff |
| Operation ID | calculateTerraformCostDiff |
| Description | Analyzes Terraform state changes to calculate cost differences and evaluate cost guardrails |

Request Body

| terraform_plan | object (required) - Terraform plan JSON |
| --- | --- |
| terraform_plan | object (required) - Terraform plan JSON |
| deployment_id | string (optional) - UUID of deployment for guardrail evaluation |
| resource_usage | object (optional) - Additional usage metrics |
| provider_accounts | object (optional) - Mapping of provider to account info |

Example Request

```
{
  "deployment_id": "123e4567-e89b-12d3-a456-426614174000",
  "terraform_plan": {},
  "resource_usage": {},
  "provider_accounts": {
    "aws": {
      "account_id": "123456789012",
      "vendor": "aws"
    }
  }
}
```

Response (200 OK)

Key Response Fields:

| meta.currency_used | Currency used for calculations |
| --- | --- |
| meta.currency_used | Currency used for calculations |
| meta.cost_guardrail_status | Pass/Fail/Warning status |
| meta.highest_failure_level | Highest severity level encountered |
| meta.unsupported_resources | Resources not supported for cost calculation |
| meta.errored_resources | Resources that encountered errors |
| result.total_cost_before | Totalcost before changes |
| result.total_cost_after | Total cost after changes |
| result.total_cost_diff | Net cost difference |
| result.cloud_resource_diffs | Per-resource cost breakdowns |
| result.cost_guardrails | Guardrail evaluation results |

Example Response

```
{
  "meta": {
    "currency_used": "USD",
    "exchange_rate_used": 1,
    "deployment_id": "123e4567-e89b-12d3-a456-426614174000",
    "deployment_name": "production",
    "highest_failure_level": "warning",
    "cost_guardrail_status": "passed",
    "unsupported_resources": {},
    "no_cost_resources": {},
    "errored_resources": {}
  },
  "result": {
    "total_cost_before": "120.00",
    "total_cost_after": "150.00",
    "total_cost_diff": "30.00",
    "cloud_resource_diffs": [
      {
        "vendor": "aws",
        "selector": "aws_instance.web",
        "resource_type": "instance",
        "cost_before": "50.00",
        "cost_after": "80.00",
        "cost_diff": "30.00",
        "custom_price": false,
        "csp_account": {
          "account_id": "123456789012",
          "vendor": "aws"
        }
      }
    ],
    "cost_guardrails": []
  }
}
```

### Generate Resource Recommendations

| Endpoint | POST /v3/governance/recommendation/terraform |
| --- | --- |
| Endpoint | POST /v3/governance/recommendation/terraform |
| Operation ID | generateTerraformRecommendations |
| Description | Analyzes Terraform state to suggest optimized resource configurations |

Request Body

| terraform_plan | object (required) - Terraform plan JSON |
| --- | --- |
| terraform_plan | object (required) - Terraform plan JSON |
| resource_usage | object (optional) - Usage metrics |
| provider_accounts | object (optional) - Provider to account mapping |

Example Request

```
{
  "terraform_plan": {},
  "resource_usage": {},
  "provider_accounts": {
    "aws": {
      "account_id": "123456789012",
      "vendor": "aws"
    }
  }
}
```

Response (200 OK)

| selector | Resource identifier in Terraform configuration |
| --- | --- |
| selector | Resource identifier in Terraform configuration |
| vendor | Cloud provider (aws, gcp, azure) |
| resource_type | Type of cloud resource |
| current_resource | Current resource configuration |
| recommended_resource | Recommended configuration |

Example Response

```
{
  "cloud_resource_recommendations": [
    {
      "selector": "aws_instance.web",
      "vendor": "aws",
      "resource_type": "instance",
      "current_resource": {
        "instance_type": "t3.large",
        "vcpu": 2,
        "memory_gb": 8
      },
      "recommended_resource": {
        "instance_type": "t3.medium",
        "vcpu": 2,
        "memory_gb": 4,
        "reason": "Current utilization suggests smaller instance"
      }
    }
  ]
}
```

---

## Deployment, Project, Preferences Management

<!-- sub-header -->
- **breadcrumb:** Cloudability API > Governance End Points > Deployment, Project, Preferences Management
- **source_path:** SSVCLNQ/api-v3/deployment_project_preferences_management.html
- **original_file:** points-deployment-project-preferences-management.md
- **images:** []

## Deployment, Project, Preferences Management

### Deployments

Deployments represent infrastructure configurations linked to repositories and cloud accounts.

List Deployments

| Endpoint | GET /v3/governance/deployments |
| --- | --- |
| Endpoint | GET /v3/governance/deployments |
| Access | Public |
| Description | Returns deployments with optional filtering. Includes accounts for each deployment |

Query Parameters

| project_id | string (optional) - Filter by project ID |
| --- | --- |
| project_id | string (optional) - Filter by project ID |
| name | string (optional) - Filter by deployment name |

Response (200 OK)

```

{
  "result": [
    {
      "id": "deploy-123",
      "name": "prod-deployment",
      "project_id": "proj-123",
      "org_id": 12345,
      "iac": "terragrunt",
      "vcs": "github",
      "repo_owner": "example-org",
      "repo_name": "infrastructure",
      "repo_id": "repo-456",
      "branch": "main",
      "accounts": [
        {
          "id": "acc-789",
          "deployment_id": "deploy-123",
          "account_id": "123456789012",
          "account_vendor": "aws"
        }
      ]
    }
  ]
}
```

Create Deployment

| Endpoint | POST /v3/governance/deployments |
| --- | --- |
| Endpoint | POST /v3/governance/deployments |
| Description | Creates a new deployment with associated accounts |

Request Body Fields

| name | string (required) - Deployment name |
| --- | --- |
| name | string (required) - Deployment name |
| project_id | string (optional) - Project ID |
| iac | string (required) - Infrastructure as code tool (e.g., terragrunt) |
| vcs | string (required) - Version control system (e.g., github) |
| repo_owner | string (required) - Repository owner |
| repo_name | string (required) - Repository name |
| repo_id | string (required) - Repository ID |
| branch | string (required) - Branch name |
| accounts | array (required) - Associated accounts |

Example Request

```
{
  "name": "prod-deployment",
  "project_id": "proj-123",
  "iac": "terragrunt",
  "vcs": "github",
  "repo_owner": "example-org",
  "repo_name": "infrastructure",
  "repo_id": "repo-456",
  "branch": "main",
  "accounts": [
    {
      "account_id": "123456789012",
      "account_vendor": "aws"
    }
  ]
}
```

### Deployment Operations

Get Deployment by ID

| Endpoint | GET /v3/governance/deployments/{id} |
| --- | --- |
| Endpoint | GET /v3/governance/deployments/{id} |
| Description | Retrieves deployment details including accounts |

Update Deployment

| Endpoint | PUT /v3/governance/deployments/{id} |
| --- | --- |
| Endpoint | PUT /v3/governance/deployments/{id} |
| Description | Replaces existing deployment data |

Delete Deployment

| Endpoint | DELETE /v3/governance/deployments/{id} |
| --- | --- |
| Endpoint | DELETE /v3/governance/deployments/{id} |
| Description | Removes deployment and associated accounts |
| Response | 204 No Content |

Get Deployment Policies

| Endpoint | GET /v3/governance/deployments/{id}/policies |
| --- | --- |
| Endpoint | GET /v3/governance/deployments/{id}/policies |
| Description | Get all policies applicable for a deployment |

Get Deployment Cost Guardrails

| Endpoint | GET /v3/governance/deployments/{id}/guardrails/cost |
| --- | --- |
| Endpoint | GET /v3/governance/deployments/{id}/guardrails/cost |
| Description | Get all cost guardrails for a deployment |

Move Deployments to Project

| Endpoint | PATCH /v3/governance/deployments/move |
| --- | --- |
| Endpoint | PATCH /v3/governance/deployments/move |
| Description | Move deployments to a project or unassigned group |
| Request Body | { "deployment_ids": [ "deploy-1", "deploy-2" ], "project_id": "proj-123" } |
| Response | 204 No Content |

### Projects

Projects are logical groupings for organizing deployments within an organization.

### List Projects

| Endpoint | GET /v3/governance/projects |
| --- | --- |
| Endpoint | GET /v3/governance/projects |
| Description | Returns a list of projects with optional filtering by name |

Query Parameters

| name | string (optional) - Filter by project name |
| --- | --- |
| name | string (optional) - Filter by project name |

Response (200 OK)

```
{
  "result": [
    {
      "id": "proj-123",
      "name": "Production",
      "org_id": 12345
    }
  ]
}
```

### Create Project

| Endpoint | POST /v3/governance/projects |
| --- | --- |
| Endpoint | POST /v3/governance/projects |
| Description | Creates a new project for an organization |

Request Body

```
{
  "name": "Production"
}
```

Response (201 Created)

```
{
  "result": {
    "id": "proj-123",
    "name": "Production",
    "org_id": 12345
  }
}
```

### Get, Update, and Delete Project

Get Project by ID

| Endpoint | GET /v3/governance/projects/{id} |
| --- | --- |
| Endpoint | GET /v3/governance/projects/{id} |
| Description | Retrieves details of a specific project |

Update Project

| Endpoint | PATCH /v3/governance/projects/{id} |
| --- | --- |
| Endpoint | PATCH /v3/governance/projects/{id} |
| Description | Updates project name |
| Request Body | { "name": "Updated Name" } |

Delete Project

| Endpoint | DELETE /v3/governance/projects/{id} |
| --- | --- |
| Endpoint | DELETE /v3/governance/projects/{id} |
| Description | Deletes project and moves deployments to unassigned |
| Response | 204 No Content |

### Organization Preferences

Manage organization-level preferences for governance configuration.

### Preferences Management

Get Preferences

| Endpoint | GET /v3/governance/preferences |
| --- | --- |
| Endpoint | GET /v3/governance/preferences |
| Description | Get organization preferences |

Response (200 OK)

```
{
  "result": {
    "org_id": 12345,
    "created_at": "2025-01-01T00:00:00Z",
    "updated_at": "2025-01-02T00:00:00Z",
    "default_aws_account": "123456789012"
  }
}
```

Create/Update Preferences

| Endpoint | PUT /v3/governance/preferences |
| --- | --- |
| Endpoint | PUT /v3/governance/preferences |
| Request Body | { "default_aws_account": "123456789012" } |

Get Default Accounts

| Endpoint | GET /v3/governance/preferences/default-accounts |
| --- | --- |
| Endpoint | GET /v3/governance/preferences/default-accounts |
| Description | Get default accounts for organization |

---

## Governance Set Up

<!-- sub-header -->
- **breadcrumb:** Cloudability API > Governance End Points > Governance Set Up
- **source_path:** SSVCLNQ/api-v3/governance_set_up.html
- **original_file:** points-governance-set-up.md
- **images:** []

## Governance Set Up

### GitHub Integration

Manage GitHub installations, repositories, and check runs for workflow integration.

GitHub Installations

Get Installation by ID

| Endpoint | GET /v3/governance/github/installations/{installation_id} |
| --- | --- |
| Endpoint | GET /v3/governance/github/installations/{installation_id} |

Delete Installation

| Endpoint | DELETE /v3/governance/github/installations/{installation_id} |
| --- | --- |
| Endpoint | DELETE /v3/governance/github/installations/{installation_id} |
| Description | Soft deletes installation |
| Response | 204 No Content |

### Repositories

| Endpoint | GET /v3/governance/repositories/github |
| --- | --- |
| Endpoint | GET /v3/governance/repositories/github |
| Description | Fetch all repositories registered for organization |

Response (200 OK)

```
{
  "total_count": 10,
  "result": [
    {
      "id": "repo-123",
      "repo_full_name": "org/infrastructure",
      "repo_name": "infrastructure",
      "repo_owner": "org"
    }
  ]
}
```

### HCP Terraform Integration

Integrate with HashiCorp Cloud Platform (HCP) Terraform run tasks.

HCP Runtask Credentials

Create Credentials

| Endpoint | POST /v3/governance/hcp/runtask/credentials |
| --- | --- |
| Endpoint | POST /v3/governance/hcp/runtask/credentials |
| Description | Create new credentials for HCP Runtasks |
| Request Body | { "description": "Production credentials" } (optional) |

Response (201 Created)

```
{
  "result": {
    "id": "cred-123",
    "hmac_key": "hmac_key_value",
    "callback_url_path": "/callback/123",
    "description": "Production credentials",
    "created_at": "2025-01-01T00:00:00Z",
    "created_by": 12345,
    "state": "active"
  }
}
```

Get Active Credentials

| Endpoint | GET /v3/governance/hcp/runtask/credentials/active |
| --- | --- |
| Endpoint | GET /v3/governance/hcp/runtask/credentials/active |
| Description | Retrieve currently active credentials |

Handle Callback

| Endpoint | POST /v3/governance/hcp/runtask/{callback_path} |
| --- | --- |
| Endpoint | POST /v3/governance/hcp/runtask/{callback_path} |
| Description | Handle HCP Runtask callback with HMAC authentication |
| Header | X-Tfc-Task-Signature (required) - HMAC signature |

---

## Metrics & Analytics

<!-- sub-header -->
- **breadcrumb:** Cloudability API > Governance End Points > Metrics & Analytics
- **source_path:** SSVCLNQ/api-v3/metrics_analytics.html
- **original_file:** points-metrics-analytics.md
- **images:** []

## Metrics & Analytics

Retrieve organizational metrics for adoption, compliance, and cost tracking.

### Repository Adoption Metrics

| Endpoint | GET /v3/governance/metrics/repo-adoption |
| --- | --- |
| Endpoint | GET /v3/governance/metrics/repo-adoption |
| Description | Repository adoption statistics with CostGuard |

Response (200 OK)

```
{
  "result": {
    "total": 100,
    "onboarded": 80,
    "percentage": "80%"
  }
}
```

### Policy Compliance Metrics

| Endpoint | GET /v3/governance/metrics/policy-compliance |
| --- | --- |
| Endpoint | GET /v3/governance/metrics/policy-compliance |
| Description | Tagging and vendor policy compliance statistics |

Response (200 OK)

```
{
  "result": {
    "tagging_compliance": {
      "complaint": 25,
      "percentage": "80%"
    },
    "total": 100,
    "vender_policy_compliance": {
      "complaint": 25,
      "percentage": "80%"
    }
  }
}
```

Pull Request Statistics

| Endpoint | GET /v3/governance/metrics/pr-stats |
| --- | --- |
| Endpoint | GET /v3/governance/metrics/pr-stats |
| Description | Detailed breakdown of PR statuses |

Response Fields

| total | Total PRs |
| --- | --- |
| total | Total PRs |
| cancelled | Cancelled PRs |
| open_error | Open PRs with errors |
| open_passed | Open PRs that passed |
| open_failed | Open PRs that failed |
| open_fixed | Open PRs that were fixed |
| open_approved | Open PRs that are approved |
| merged_error | Merged PRs with errors |
| merged_passed | Merged PRs that passed |
| merged_failed | Merged PRs that failed |
| merged_fixed | Merged PRs that were fixed |
| merged_approved | Merged PRs that were approved |

Total Cost Difference by Projects

| Endpoint | GET /v3/governance/metrics/total-cost-diff |
| --- | --- |
| Endpoint | GET /v3/governance/metrics/total-cost-diff |
| Description | Total cost difference by project from start of current month to today |

Response (200 OK)

```
{
  "result": {
    "total_cost_diff": 12345.67,
    "start_date": "2025-01-01",
    "end_date": "2025-01-11",
    "cost_diff_by_project": {
      "projectA": {
        "cost_diff": 123.45
      },
      "projectB": {
        "cost_diff": -123
      }
    }
  }
}
```

---

## Policy Management & Evaluation

<!-- sub-header -->
- **breadcrumb:** Cloudability API > Governance End Points > Policy Management & Evaluation
- **source_path:** SSVCLNQ/api-v3/policy_management_evaluation.html
- **original_file:** points-policy-management-evaluation.md
- **images:** []

## Policy Management & Evaluation

### Tagging & Resource Type policies

Policies define governance rules including tagging requirements and attribute constraints.

List Policies

| Endpoint | GET /v3/governance/policies |
| --- | --- |
| Endpoint | GET /v3/governance/policies |
| Description | Returns all policies with optional filtering and pagination |

Query Parameters

| category | string (optional) - Filter by category |
| --- | --- |
| category | string (optional) - Filter by category |
| vendor | string (optional) - Filter by vendor |
| org_level | boolean (optional) - Filter org-level policies |
| offset | integer (optional) - Pagination offset |
| limit | integer (optional) - Pagination limit |

Response (200 OK)

```
{
  "meta": {
    "total": 50,
    "limit": 20,
    "offset": 0
  },
  "result": [
    {
      "id": "pol-123",
      "name": "Required Tags Policy",
      "category": "tagging",
      "vendor": "aws",
      "org_id": 12345,
      "evaluate_existing_resources": true,
      "enforcement_level": "advisory",
      "is_org_level": true,
      "tag_rules": [
        {
          "tag_key": "Environment",
          "allowed_values": [
            "prod",
            "dev",
            "staging"
          ]
        }
      ],
      "attribute_rules": [],
      "attached_projects": []
    }
  ]
}
```

Get Resource Type Policy Options for a Specific Vendor

| Endpoint | GET /v3/governance/policies/options/{vendor_key} |
| --- | --- |
| Endpoint | GET /v3/governance/policies/options/{vendor_key} |
| Description | Retrieve available policy options for a vendor with optional filtering |

Parameters

| vendor_key | string (path, required) - Vendor identifier (aws, gcp, azure) |
| --- | --- |
| vendor_key | string (path, required) - Vendor identifier (aws, gcp, azure) |
| resource | string (query, optional) - Filter by resource name (EC2 - Compute Instance, EBS Volume) |
| attribute | string (query, optional) - Filter by attribute (Read Capacity, Write Capacity) |

### Create Policy

| Endpoint | POST /v3/governance/policies |
| --- | --- |
| Endpoint | POST /v3/governance/policies |
| Description | Creates a new policy. Either tag_rules or attribute_rules required |

Required Fields

| name | string - Policy name |
| --- | --- |
| name | string - Policy name |
| category | string - Policy category |
| vendor | string - Vendor (aws, gcp, azure) |
| evaluate_existing_resources | boolean - Evaluate existing resources |
| enforcement_level | string - Enforcement level (advisory, mandatory) |
| tag_rules OR attribute_rules | array - At least one required |

Optional Fields

| org_id | integer - Organization ID |
| --- | --- |
| org_id | integer - Organization ID |
| attached_projects | array[string] - Project IDs |
| is_org_level | boolean - Organization-level policy |

Example Request

```
{
  "name": "Required Tags Policy",
  "category": "tagging",
  "vendor": "aws",
  "evaluate_existing_resources": true,
  "enforcement_level": "advisory",
  "tag_rules": [
    {
      "tag_key": "Environment",
      "allowed_values": [
        "prod",
        "dev",
        "staging"
      ]
    }
  ],
  "is_org_level": true
}
```

### Policy Operations

Get Policy by ID

| Endpoint | GET /v3/governance/policies/{id} |
| --- | --- |
| Endpoint | GET /v3/governance/policies/{id} |
| Description | Retrieve specific policy details |

Update Policy

| Endpoint | PUT /v3/governance/policies/{id} |
| --- | --- |
| Endpoint | PUT /v3/governance/policies/{id} |
| Description | Updates policy. Same fields as create |
| Note | If attached_projects and is_org_level not set, all mappings removed |

Delete Policy

| Endpoint | DELETE /v3/governance/policies/{id} |
| --- | --- |
| Endpoint | DELETE /v3/governance/policies/{id} |
| Description | Deletes policy |
| Response | 200 OK |

### Resource Type & Tagging Policy Evaluation

Evaluate infrastructure changes against governance policies including tagging rules and resource attribute constraints.

### Evaluate Terraform Policies

| Endpoint | POST /v3/governance/policy-evaluation/terraform |
| --- | --- |
| Endpoint | POST /v3/governance/policy-evaluation/terraform |
| Operation ID | evaluateTerraformPolicies |
| Description | Analyzes Terraform state changes against defined policies to identify compliance issues |

Request Body

| terraform_plan | object (required) - Terraform plan JSON |
| --- | --- |
| terraform_plan | object (required) - Terraform plan JSON |
| deployment_id | string (optional) - UUID of deployment |
| resource_usage | object (optional) - Usage metrics |

Example Request

```
{
  "deployment_id": "123e4567-e89b-12d3-a456-426614174000",
  "terraform_plan": {},
  "resource_usage": {}
}
```

Response (200 OK)

Key Response Fields:

| meta.passed | Overall pass/fail status |
| --- | --- |
| meta.passed | Overall pass/fail status |
| meta.vendor_policy_passed | Vendor policy compliance |
| meta.tagging_policy_passed | Tagging policy compliance |
| meta.total_failed_policies | Count of failed policies |
| meta.highest_failure_level | Highest severity level |
| result.failed_policies | Array of policy failures with details |

Example Response

```
{
  "meta": {
    "deployment_id": "123e4567-e89b-12d3-a456-426614174000",
    "deployment_name": "production",
    "passed": false,
    "vendor_policy_passed": true,
    "tagging_policy_passed": false,
    "total_failed_policies": 1,
    "highest_failure_level": "mandatory"
  },
  "result": {
    "failed_policies": [
      {
        "policy_id": "pol-123",
        "policy_name": "Required Tags",
        "policy_category": "tagging",
        "enforcement_level": "mandatory",
        "failed_tag_rules": [
          {
            "tag_key": "Environment",
            "allowed_values": [
              "prod",
              "dev",
              "staging"
            ],
            "actual_key": "Environment",
            "actual_value": "test",
            "resource_name": "web_server",
            "resource_address": "aws_instance.web",
            "is_existing_resource": false,
            "resource_vendor": "aws"
          }
        ],
        "failed_attribute_rules": []
      }
    ]
  }
}
```

### Cost Guardrails

Cost guardrails enforce spending limits and thresholds for infrastructure changes.

List Cost Guardrails

| Endpoint | GET /v3/governance/guardrails/cost |
| --- | --- |
| Endpoint | GET /v3/governance/guardrails/cost |
| Description | Retrieve guardrails with optional filtering |

Query Parameters

| project_id | string (optional) - Filter by project |
| --- | --- |
| project_id | string (optional) - Filter by project |
| org_level | boolean (optional) - Org-level only |

Response (200 OK)

```
{
  "result": [
    {
      "id": "guard-123",
      "name": "Production Cost Limit",
      "category": "cost",
      "enforcement_level": "mandatory",
      "org_id": 12345,
      "cost_diff": {
        "max_allowed_diff": "1000.00"
      },
      "is_org_level": false,
      "attached_projects": [
        "proj-123"
      ]
    }
  ]
}
```

Create Cost Guardrail

| Endpoint | POST /v3/governance/guardrails/cost |
| --- | --- |
| Endpoint | POST /v3/governance/guardrails/cost |
| Description | Create a cost guardrail |

Required Fields

| name | string - Guardrail name |
| --- | --- |
| name | string - Guardrail name |
| category | string - Category |
| enforcement_level | string - Enforcement level |

Example Request

```
{
  "name": "Production Cost Limit",
  "category": "cost",
  "enforcement_level": "mandatory",
  "cost_diff": {
    "max_allowed_diff": "1000.00"
  },
  "is_org_level": false,
  "attached_projects": [
    "proj-123"
  ]
}
```

### Cost Guardrail Operations

Get Guardrail by ID

| Endpoint | GET /v3/governance/guardrails/cost/{id} |
| --- | --- |
| Endpoint | GET /v3/governance/guardrails/cost/{id} |

Update Guardrail

| Endpoint | PUT /v3/governance/guardrails/cost/{id} |
| --- | --- |
| Endpoint | PUT /v3/governance/guardrails/cost/{id} |

Delete Guardrail

| Endpoint | DELETE /v3/governance/guardrails/cost/{id} |
| --- | --- |
| Endpoint | DELETE /v3/governance/guardrails/cost/{id} |
| Response | 200 OK |

Note: The “Cost Guardrail” evaluation is done part of the Cost Estimation check – see endpoint “POST /v3/governance/cost-estimate/terraform/diff” for details.

---

## Pull Requests Tracking

<!-- sub-header -->
- **breadcrumb:** Cloudability API > Governance End Points > Pull Requests Tracking
- **source_path:** SSVCLNQ/api-v3/pull_requests_tracking.html
- **original_file:** points-pull-requests-tracking.md
- **images:** []

## Pull Requests Tracking

Track infrastructure changes through pull requests with policy evaluations and cost impacts.

List Pull Requests

| Endpoint | GET /v3/governance/pull-requests |
| --- | --- |
| Endpoint | GET /v3/governance/pull-requests |
| Description | Get all pull requests with filtering and pagination |

Query Parameters

| state | string (optional) - Filter by state |
| --- | --- |
| state | string (optional) - Filter by state |
| approved_by | array[integer] (optional) - Filter by approver user IDs |
| repository | string (optional) - Filter by repository |
| workflow_status | string (optional) - Filter by workflow status |
| order_by | array[string] (optional) - Order results |
| offset | integer (optional) - Pagination offset |
| limit | integer (optional) - Pagination limit |

Response (200 OK)

```
{
  "meta": {
    "total": 100,
    "limit": 20,
    "offset": 0
  },
  "result": [
    {
      "id": "pr-123",
      "title": "Update infrastructure config",
      "org_id": 12345,
      "state": "open",
      "vcs": "github",
      "url": "https://github.com/org/repo/pull/123",
      "repo_full_name": "org/repo",
      "base_branch": "main",
      "head_sha": "abc123",
      "created_at": "2025-01-01T00:00:00Z",
      "updated_at": "2025-01-02T00:00:00Z",
      "action_required": false,
      "is_approved": true,
      "status": "passed",
      "cost_diff": 50,
      "approvals": [],
      "affected_deployments": []
    }
  ]
}
```

### Pull Request Operations

Get Pull Request Detail

| Endpoint | GET /v3/governance/pull-requests/{id} |
| --- | --- |
| Endpoint | GET /v3/governance/pull-requests/{id} |
| Description | Get PR detail including latest workflow run |

Approve Pull Request

| Endpoint | POST /v3/governance/pull-requests/{id}/approve |
| --- | --- |
| Endpoint | POST /v3/governance/pull-requests/{id}/approve |
| Response | 204 No Content |

---

## MongoDB End Points

<!-- sub-header -->
- **breadcrumb:** Cloudability API > MongoDB End Points
- **source_path:** SSVCLNQ/api-v3/mongodb_public_api.html
- **original_file:** api-mongodb-end-points.md
- **images:** []

## MongoDB End Points

Summary

Following are the list of public APIs provided by Kissinger service specific to MongoDb.

With Cloudability being available in multiple regions, all references to api.cloudability.com in this API documentation should be referred to as mentioned in Getting started with Cloudability API V3 .

End Point Particulars

end point : /v3/vendors/mongodb/accounts for RESTful CRUD interactions

end point : /v3/vendors/mongodb/accounts?include=permissions&viewId=0

end point : /v3/vendors/mongodb/accounts/<account_id>?include=permissions&viewId=0

end point : /v3/vendors/mongodb/accounts/<account_id>?viewId=0

end point : /v3/vendors/mongodb/accounts/<account_id>/verification?include=permissions,associatedAccounts&viewId=0

end point : /v3/vendors/mongodb/accounts/<account_id>/archive?viewId=0

end point : /v3/vendors/mongodb/permissions/accounts/<account_id>

Parameters

- type(string) : "mongodb_user",
- vendorAccountId(string) : account id,
- publicKey(string) : public key,
- privateKey(string) : Private key,
- subscriptionModel(string) - “Direct” | “Marketplace”
- dependentCsp(string) - “AWS” | “AZURE” | “GCP”, should be passed only when subscriptionModel is set to “Marketplace”

End Points

```
curl 'https://api.cloudability.com/v3/vendors/mongodb/accounts?viewId=0' \\ 
   -u ‘[auth_token]:’ 
```

```
{ 
"result": [ 
{ 
"id": "111e11111e111111aa1111a1", 
"vendorAccountName": "111e11111e111111aa1111a1", 
"vendorAccountId": "111e11111e111111aa1111a1", 
"vendorKey": "mongodb", 
"verification": { 
"state": "verified", 
"lastVerificationAttemptedAt": "2026-02-07T06:14:10Z" 
}, 
"authorization": { 
"type": "mongodb_user", 
"permissions": [ 
"mongodb.list.organization", 
"mongodb.get.invoices" 
], 
"subscriptionModel": "Marketplace", 
"dependentCsp": "AWS" 
}, 
"createdAt": "2024-07-18T06:15:53Z", 
"consumerOrgId": "", 
"byodVendor": "ABSENT" 
}, 
{ 
"id": "222222f222b2ed2ccf2222aa", 
"vendorAccountName": "222222f222b2ed2ccf2222aa", 
"vendorAccountId": "222222f222b2ed2ccf2222aa", 
"vendorKey": "mongodb", 
"meta": {}, 
"parentAccountId": "111e11111e111111aa1111a1", 
"consumerOrgId": "" 
} 
] 
} 
```

Create Master Payer Account - This API is used for creating a new Master Payer account.

POST /v3/vendors/mongodb/accounts?viewId=0

Example Request

```
curl -X POST 'https://api.cloudability.com/v3/vendors/mongodb/accounts?viewId=0\\ 
-H 'Content-Type: application/json' \\ 
-u ‘[auth_token]:’ \\ 
-d @- << EOF 
{ 
 "type": "mongodb_user", 
 "vendorAccountId": "org-id", 
 "publicKey": "public-key", 
 "privateKey": "private-api-key", 
 "subscriptionModel": "Marketplace", 
 "dependentCsp": "AZURE" 
}              
```

Upon successful creation the API will return the credentials object.

Update Master Payer account

PUT /v3/vendors/mongodb/accounts/<account_id>?include=permissions&viewId=0

Example Request

```
curl -X PUT 'https://api.cloudability.com/v3/vendors/mongodb/accounts/<account_id>?viewId=0\\ 
-H 'Content-Type: application/json' \\ 
-u ‘[auth_token]:’ \\ 
-d @- << EOF 
{ 
"type": "mongodb_user", 
"vendorAccountId": "org-id", 
"publicKey": "new", 
"privateKey": "new", 
"subscriptionModel": "Marketplace", 
"dependentCsp": "AZURE" 
} 
```

Upon successful update the API will return the credentials object

Retrieve Account

GET /v3/vendors/mongodb/accounts/:<account_id>?viewId=0

Example Request

```
curl 
'https://api.cloudability.com/v3/vendors/mongodb/accounts/<account_id>’\\ 
-u ‘[auth_token]:’ 
```

Upon successful get, the API will return the credentials object

Delete Credential for Account

DELETE /v3/vendors/mongodb/accounts/<account_id>?viewId=0

```
Curl -X DELETE 
'https://api.cloudability.com/v3/vendors/mongodb/accounts/<account_id>?viewId=0\\ 
-u ‘[auth_token]:’ 
```

Verify Credential for Account

POST v3/vendors/mongodb/accounts/<account_id>/verification?include=permissions,associatedAccounts&viewId=0

Example Request

```
curl --X POST 
'https://api.cloudability.com/v3/vendors/mongodb/accounts/<account_id>/verification?include=permissions,associatedAccounts&viewId=0’\\ 
-u ‘[auth_token]:’ 
```

Upon successful verification the API will return the credentials object

Archive Account

POST /v3/vendors/mongodb/accounts/<account_id>/archive?viewId=0

```
curl --X POST 
'https://api.cloudability.com/v3/vendors/mongodb/accounts/<account_id>archive?viewId=0’\\ 
-u ‘[auth_token]:’ 
```

Get Permissions for Account

GET /v3/vendors/mongodb/permissions/accounts/<account_id>

Example Request

```
curl --X GET 
'https://api.cloudability.com/v3/vendors/mongodb/permissions/accounts/<account_id>’ 
\\ 
-u ‘[auth_token]:’
```

---

## PAGERDUTY End Points

<!-- sub-header -->
- **breadcrumb:** Cloudability API > PAGERDUTY End Points
- **source_path:** SSVCLNQ/api-v3/pagerduty_api.html
- **original_file:** api-pagerduty-end-points.md
- **images:** []

## PAGERDUTY End Points

Summary

Following are the list of public APIs specific to Pagerduty.

With Cloudability being available in multiple regions, all references to api.cloudability.com in this API documentation should be referred to as mentioned in Getting started with Cloudability API V3 .

End Point Particulars

end point : /v3/pagerduty/credentials for RESTful CRUD interactions

end point : /v3/pagerduty/credentials

end point : /v3/pagerduty/credentials/test

end point : v3/pagerduty/credentials/:incidentKeyId

Parameters

- incidentKeyId (string): generated uuid after adding the pagerduty integration
- incidentKeyName (string): Pagerduty incident key name
- incidentKey (string): Pagerduty incident key
- incidentKeyLast4 (string): Last 4 digit of incident key

List Pagerduty integrations

```
curl 'https://api.cloudability.com/v3/pagerduty/credentials' \\ 
 -u ‘[auth_token]:’ 
```

```
{ 
 "result": [ 
 { 
 "incidentKeyId": "a1a1a11a-1111-1111-1aa1-aa1a11aa111a", 
 "incidentKeyName": "Anomaly PagerDuty Testing", 
 "incidentKeyLast4": "1a11" 
 }, 
 { 
 "incidentKeyId": "b1b1b11b-1111-1111-1aa1-aa1a11aa111b", 
 "incidentKeyName": "ab-test-integration", 
 "incidentKeyLast4": "1b11" 
 } 
 ] 
}
```

Update pagerduty integration

end point

/v3/pagerduty/credentials/ :incidentKeyId

```
curl -X PUT 'https://api.cloudability.com/v3/pagerduty/credentials/:incidentKeyId  
-H 'Content-Type: application/json' \\ 
-u ‘[auth_token]:’ \\ 
-d @- << EOF 
{ 
 "incidentKey": "incident-key", 
 "incidentKeyName": "incident-key-name" 
}
```

Test pagerduty integration

end point

/v3/pagerduty/credentials/test

```
curl -X POST 'https://api.cloudability.com/v3/pagerduty/credentials/test 
-H 'Content-Type: application/json' \\ 
-u ‘[auth_token]:’ \\ 
-d @- << EOF 
{ 
 "incidentKey": "incident-key", 
 "incidentKeyId": "" 
}
```

Save pagerduty integration

end point

/v3/pagerduty/credentials

```
curl -X POST 'https://api.cloudability.com/v3/pagerduty/credentials 
-H 'Content-Type: application/json' \\ 
-u ‘[auth_token]:’ \\ 
-d @- << EOF 
{ 
 "incidentKey": "incident-key", 
 "incidentKeyName": "incident-key-name" 
}
```

Retrieve pagerduty integration

end point

/v3/pagerduty/credentials/ :incidentKeyId

```
curl 
'https://api.cloudability.com/v3/pagerduty/credentials/:incidentKeyId  
-u ‘[auth_token]:’
```

Delete pagerduty integration

end point

/v3/pagerduty/credentials/ :incidentKeyId

```
Curl -X DELETE 
'https://api.cloudability.com/v3/pagerduty/credentials/:incidentKeyId 
-u ‘[auth_token]:’
```

---

## Resource Inventory – Public API End Points

<!-- sub-header -->
- **breadcrumb:** Cloudability API > Resource Inventory – Public API End Points
- **source_path:** SSVCLNQ/api-v3/resource-inventory-public-api-endpoints.html
- **original_file:** api-resource-inventory-public-end-points.md
- **images:** []

## Resource Inventory – Public API End Points

Resource Inventory has the below public API endpoints:

Resource inventory report run API: The resource inventory run endpoint is used to dynamically run resource inventory reports and return detailed information about your organization’s resource details.

Resource Inventory API End Points

```
'curl 'https://api.cloudability.com/v3/reporting/resourceinventory/run - ‘[auth_token]:'

```

Request Parameters

| Argument | Description |
| --- | --- |
| service(required) | Services for the run report such as EC2,EBS,S3,Compute |
| vendor(required) | vendor for the run report such as AWS,AZURE,GCP |
| startDate (required) | The start date for the report. Format: YYYY-MM-DD |
| endDate (required) | The end date for the report. Format: YYYY-MM-DD |
| dimensions | Comma delimited list of dimensions to include in report. Example: dimensions=vendor,region |
| is_kpi | flag to identify whether to return either all the kpi or resources report. If omitted it is defaulted to 'false'. |
| metrics | Comma delimited list of metrics to include in report. Example: metrics = unblended_cost,adjusted_amortized_cost |
| limit | maximum number of records to return.If limit =0 or not provide it will show maximum 64000 records. |
| offset | Position to start for the results. Example: offset = 1 |
| filters | filter to apply on the measures for the report |
| viewId | If omitted, the user's default view will be applied |

Start date and end date difference should not be more than 31 days. Start date should not be more than three months before the current date.

Sample Request:

```
'curl 'https://api.cloudability.com/v3/reporting/resourceinventory/run?service=ec2&vendor=aws&startDate=2024-10-01&endDate=2024-10-05&limit=1&offset=0'"

```

Run API Sample Response

```
[ 
				{ 
				"KIP": null, 
				"columnHeaders":  {
				"keys":  [
				"vendor_account_name", 
				"region", 
				"resource_identifier",
			 	   "product_name",	
				"item_description",
				"state",
				"snapshot",
			"launch_date",
				"tagged_resource",
				"unblended_cost",
				"public_on_demand_cost",
				"adjusted_amortized_cost",
				"ec2_cpu_utilization_avg",
				"ec2_network_in_avg",
				"ec2_network_out_avg"
				]
				},
				"filters": [],
				"count": 1,
				"pagination": {},
				"dates": {
				"start": "2024-10-01",
				"end": "2024-10-05"
				},
				"month": "",
				"rows": [
				[
				"xyz Engineering",
				"xyz region",
				"sample resource id",
				"sample product name",
				"$1234 per Hour",
				"Not Available",
				"false",
				"Not Available",
				"true", 
				"1234.00",
				"1234.00", 
				"1234.00",
				"0.0",
				"0.0",
				"0.0"
				]
				]
				}
		
```

Resource inventory measures API: To retrieve the list of measures. Measures includes dimensions,metrics ,business dimensions, account groups, tags that can be used in reports.

Resource Inventory API End Points

```
'curl 'https://api.cloudability.com/v3/reporting/resourceinventory/measures - ‘[auth_token]:'
```

Request Parameters:

| Argument | Description |
| --- | --- |
| service(required) | Services for the run report such as EC2,EBS,S3,Compute |
| vendor(required) | vendor for the run report such as AWS,AZURE |

Sample Request:

```

				{ 
				"dimensions": [
				{
				"readable_name": "sampe dimension Name",
				"api_name": "xzy_abc"
				}
				],
				"metrics": [
				{
				"readable_name": "sample metric name",
				"api_name": "abc_xyz"
				}
				],
				"tags": [
				{
				"name": "sample tag name",
				"label": "sample tag label"
				}
				],
				"business_dimensions": [
				{
				"name": "sample business dimension name",
				"label": "sample business dimension label"
				}
				]
			}
```

List of Sample Reports

Below are a few sample reports that can help you with the usage of the resource inventory reports API:

Run report with relative dates in json:

```
'curl 'https://api.cloudability.com/v3/reporting/resourceinventory/run?service=ec2&vendor=aws&startDate=2024-10-01&endDate=2024-10-05&limit=5&offset=0'

```

Run and export report in csv:

```
'curl 'https://api.cloudability.com/v3/reporting/resourceinventory/run?service=ec2&vendor=aws&startDate=2024-10-01&endDate=2024-10-05&limit=5&offset=0' --header 'Accept: text/csv'
```

This output can be redirected to a csv file.

is_kpi should always be 'false' or omitted in case of report export in csv.

Run report with only kpi:

```
'curl 'https://api.cloudability.com/v3/reporting/resourceinventory/run?service=ec2&vendor=aws&startDate=2024-10-01&endDate=2024-10-05&limit=5&offset=0&is_kpi=true'

```

Measures API:

```
'curl 'https://api.cloudability.com/v3/reporting/resourceinventory/measures?service=ec2&vendor=aws'

```

---

## RI Planner End Point

<!-- sub-header -->
- **breadcrumb:** Cloudability API > RI Planner End Point
- **source_path:** SSVCLNQ/api-v3/ri_planner_endpoint.html
- **original_file:** api-ri-planner-end-point.md
- **images:**
  - 03-media/apptio-cloudability-standard/ri_top_of_planner.jpg

## RI Planner End Point

Summary

The RI Planner end point can be used to generate a list of recommendations for reserving instances (RIs) based on parameters that suit your business. Done well reserved instances are a very powerful way to save money on your AWS bill and Cloudability supports planning for EC2, RDS, Redshift and Elasticache.

Special Note: RI planning is a rather complex activity and this end point matches that reality. The documentation here will focus on the most useful and common interactions for end users. Accordingly you'll find the documentation format to be slightly different to that of other end points.

- This end point does not support filtering and sorting.

End Point Particulars

These end points are readonly and are used for generating an RI plan(lists of RI recommendations)

End point : /reservations/aws/recommendations/ec2

End point : /reservations/aws/recommendations/rds

End point : /reservations/aws/recommendations/redshift

End point : /reservations/aws/recommendations/elasticache

Creating your RI Plan - Query Arguments

Arguments

| Argument | Required? | Description |
| --- | --- | --- |
| startDate | Yes | Start date for the window of instance usage you'd like to analyse in generating a plan. Format YYYY-MM-DD |
| endDate | Yes | End date for the window of instance usage you'd like to analyse in generating a plan. Format YYYY-MM-DD |
| vendorAccountIds | Yes | The unique ID provided by the cloud vendor for the account you wish to create an RI plan for. Format 1234-4567-8901 |
| include | No | You will nearly always want to use this parameter. Use cases: include=associatedAccounts when running against a master payer account to pickup linked account usage. include=associatedAccounts,costs to also return a cost summary for the plan include=associatedAccounts,costs,summary to also return summary info for each RI classification. See details below |
| excludedPricingOptions | No | Exclude partial-upfront , no-upfront or all-upfront payment types from the plan. If argument not included RI plan will be forced to partial-upfront . To exclude multiple types separate with comma: excludedPricingOptions=no-upfront,partial-upfront |
| offeringClass | No | Create a plan for convertible or standard RIs. Defaults to standard. |
| term | No | one-year or three-year . Defaults to one-year |
| scope | No | region or availabilityZone . Defaults to region |
| optimizations | No | all , no-mods or mods-only . mods-only . all returns all recommendations. mods-only only returns RI modification recommendations. no-mods removes RI modification recommendations from what is returned. Defaults to all . |
| usageThreshold | No | Set the waterline usage level requirement for the RIs. For a 90% waterline use: usageThreshold=90 |
| savingsThreshold | No | Set a minimum savings rate for individual RI purchases savingsThreshold=20 would only recommend RIs that save at least 20% over running on demand. |

Cost Summary

The Cost Summary provides a summary of the impact available by following all RI purchase recommendations. It is powerful in conveying the surface area that can be impacted with smart RI decisions. It is the API equivalent of this summary in the UI version of the planner

To get the cost summary returned add 'costs' to the include parameter, for example 'include=associatedAccounts,costs'. Example curl:

```
curl "https://api.cloudability.com/v3/reservations/aws/recommendations/ec2?startDate=2018-04-05&endDate=2018-04-19&include=associatedAccounts,costs&vendorAccountIds=1234-4567-8901" \\
-H "apptio-opentoken: [apptio opentoken]" -H "apptio-environmentid: [environment id]"
```

The Cost Summary Attributes

onDemandMonthlyCost (number) - For the reservation count recommended, what would this cost to run fully on demand per month (i.e. what would it cost if we didn't reserve these)

totalOnDemandCost (number) - For the reservation count recommended, what would this cost to run fully on demand for the term of the reservation.

uncoveredOnDemandCost (number) - This represents the total amount of on-demand usage that the plan does NOT cover with RIs for the full term of your plan. The RI planner makes sure to not recommend RIs for usage which falls below the break even point (for example cyclical or spiky usage).

onDemandUpfront (integer) - This attribute is just here for convenience to tell us that running instances on demand has zero upfront cost, hence the value is always zero (0).

reservationUpfront (integer) - The upfront payment associated with the purchase count recommended. For no upfront RIs this will always return as 0.

reservationTotalCost (number) - The total cost of reserving the recommended amount for the full term, including upfront and recurring costs.

reservationAmortizedMonthlyCost (number) - the monthly cost of the RI purchase including upfront and recurring elements. i.e reservationTotalCost divided by the RI term in months.

totalEstimatedSavings (number) - The total savings you would make by following all recommendations. equivalent to ( totalOnDemandCost - reservationTotalCost )

savingsRate (number) - effectively a decimal value representing your savings percentage for the combined value of all recommendations. Determined by the ratio between totalOnDemandCost and reservationTotalCost .

breakEvenThreshold - The percentage of utilization an RI requires for it to be 'profitable'. The higher the savings rate the less utilisation any RI requires to be viable.

daysToBreakEven - How many days before the combined RI purchases recommended fully break even. See this blog post and the definition of 'Total RI Cost Break Even" for more details.

Example Cost Summary

```
"costs": {
      "onDemandUpfront": 0,
      "onDemandMonthlyCost": 126962.695,
      "totalOnDemandCost": 1523552.34,
      "uncoveredOnDemandCost": 255138.69629,
      "reservationUpfront": 549100,
      "reservationAmortizedMonthlyCost": 90948.10733,
      "reservationTotalCost": 1091377.288,
      "totalEstimatedSavings": 432175.052,
      "savingsRate": 0.28366,
      "daysToBreakEven": 261.46309
    }
```

RI Purchase Summary

The RI Purchase Summary provides a consumable list of recommended RI purchases. You can think of each item in the list as an individual recommendation similar to what you see in the main page of Cloudability 's RI planner. Individual recommendations are essentially a classification that can be reserved into, for example r4.large Linux instances in the ap-southeast-2 region and will take into account characteristics such as ISF/region scoping depending on your scenario.

Special Note: Classifications will be listed for cases where any related instance happens to run in the time window or if an RI is owned regardless of whether an action is recommended. For example no action may be present if RI utilization would be below the break even point or if the specific classification is covered by a ISF recommendation. Use your client side tool to manage this as shown below using jq.

To get the purchase summary returned add 'summary' to the include parameter, for example 'include=associatedAccounts,summary'. Example curl:

```
curl "https://api.cloudability.com/v3/reservations/aws/recommendations/ec2?startDate=2018-04-05&endDate=2018-04-19&include=associatedAccounts,summary&vendorAccountIds=1234-4567-8901" \\
-H "apptio-opentoken: [apptio opentoken]" -H "apptio-environmentid: [environment id]"
```

The Purchase Summary Attributes:

Each recommendation in the list will contain these attributes:

classification (object) - An object that describes the classification you can reserve into.

regionZone (string) - The region or zone to reserve into.

instanceType (string) - The instance type to reserve against

platform (string) - For EC2 this will be the OS and RDS this will be the engine .

tenancy (string) - Applicable for EC2, shared or dedicated tenancy.

ownedQuantity (integer) - How many of this classification of RIs do you already own

ownedReservations (object) - An object that describes relevant RIs you already own

light (integer) - Active RIs of this deprecated RI type

medium (integer) - Active RIs of this deprecated RI type

heavy (integer) - Active RIs of this deprecated RI type

noUpfront (integer) - Active RIs purchased through On Upfront payment option

partialUpfront (integer) - Active RIs purchased through Partial Upfront payment option

allUpfront (integer) - Active RIs purchased through All Upfront payment option

allocationCounts (object) - An object that describes the means to achieve desired RI level

modifiedToCover (integer) - Instance count that can be gained by modifying an existing underutilized RI.

coveredByRegionalScope (integer) - Current RIs that cover usage via being regionally scoped, but not ISF.

coveredByAzScope (integer) - Current RIs that cover usage via being AZ scoped.

coveredBySizeFlexibility (integer) - Current RIs that cover usage via being ISF scoped.

buyToCover (integer) - Recommend RI count to purchase to reach desired level.

exchangeToCover (integer) - Recommended convertible exchange actions will result in this amount of new RIs

recommendedQuantity (integer) - Quantity of RIs to own for maximum savings

recommendedQuantityUsage (number) - The percentage utilization of the last RI recommended, i.e. the least utilized RI that still happens to be above the break even point.

alreadyCovered (integer) - How many of the desired quantity are covered by RIs already owned. See 'covered' items in allocationCounts attribute for a breakdown of this number.

ownedPoints (integer) - ISF related. How many 'points' do you already own within the family due to active ISF RIs. Similar to the AWS normalization factor , but we base our values on nano being equal to 1 instead of 0.25 (thus allowing us to avoid decimals).

reallocatedPoints (integer) - ISF related. The points within a classification that are actually recommended to be modified out to a different classification.

unusedPoints (integer) - ISF related. The owned points within a classification that aren't currently used and can't be modified to salvage them.

totalHoursRunning (integer) - How many hours in your time window of analysis is there at least 1 instance running for the classification.

reservationCost (object) - A cost summary object as described above , but in this case being specific to just this classification.

Example Purchase Summary

```
"summary": {
      "coverage": [
        {
          "classification": {
            "regionZone": "ap-southeast-2",
            "instanceType": "r4.large",
            "platform": "linux",
            "tenancy": "shared"
          },
          "ownedQuantity": 37,
          "ownedReservations": {
            "light": 0,
            "medium": 0,
            "heavy": 0,
            "noUpfront": 0,
            "partialUpfront": 37,
            "allUpfront": 0
          },
          "allocationCounts": {
            "modifiedToCover": 0,
            "coveredByRegionalScope": 0,
            "coveredByAzScope": 0,
            "coveredBySizeFlexibility": 37,
            "buyToCover": 25,
            "exchangeToCover": 0
          },
          "recommendedQuantity": 62,
          "recommendedQuantityUsage": 0.90,
          "alreadyCovered": 37,
          "ownedPoints": 592,
          "reallocatedPoints": 0,
          "unusedPoints": 0,
          "totalHoursRunning": 360,
          "reservationCost": {
            "onDemandUpfront": 0,
            "onDemandMonthlyCost": 2912.7,
            "totalOnDemandCost": 34952.4,
            "uncoveredOnDemandCost": 0,
            "reservationUpfront": 10475,
            "reservationAmortizedMonthlyCost": 1748.91667,
            "reservationTotalCost": 20987,
            "totalEstimatedSavings": 13965.4,
            "savingsRate": 0.39955,
            "breakEvenThreshold": 0.60045,
            "daysToBreakEven": 219.16249
          }
        }
      ]
    }
```

Example Requests

A Three Year, All Upfront, Convertible RI Plan with 100% utilisation

```
curl "https://api.cloudability.com/v3/reservations/aws/recommendations/ec2?startDate=2018-04-05&endDate=2018-04-19&include=associatedAccounts,costs&vendorAccountIds=1234-4567-8901&usageThreshold=100&offeringClass=convertible&term=three-year&excludedPricingOptions=no-upfront,partial-upfront" \\
-u ‘[auth_token]:’
```

List Out All Buy Recommendations, Order by Highest Savings First

Important : This is effectively the list of recommendations you get when you go into the Cloudability RI planner and run a default plan.

```
curl "https://api.cloudability.com/v3/reservations/aws/recommendations/ec2?startDate=2018-04-05&endDate=2018-04-19&include=associatedAccounts,summary&vendorAccountIds=1234-4567-8901" \\
-u ‘[auth_token]:’ | jq '.result.summary.coverage | sort_by(.reservationCost.totalEstimatedSavings) | reverse'
```

Print Classification Details, Savings, and Buy Count for Highest Savings RIs

This is the same request as above. We are using jq to print out a very human friendly version of the list of recommendations.

```
curl "https://api.cloudability.com/v3/reservations/aws/recommendations/ec2?startDate=2018-04-05&endDate=2018-04-19&include=associatedAccounts,summary&vendorAccountIds=1234-4567-8901" \\
-u ‘[auth_token]:’ | jq '.result.summary.coverage | sort_by(.reservationCost.totalEstimatedSavings) | reverse | .[] | .classification + {savings: .reservationCost.totalEstimatedSavings} + {buy_count: .allocationCounts.buyToCover} '
```

List out Buy Recommendations with Savings over $10k

This is handy to remove no-action classifications and those with low savings figures.

```
curl "https://api.cloudability.com/v3/reservations/aws/recommendations/ec2?startDate=2018-04-05&endDate=2018-04-19&include=associatedAccounts,summary&vendorAccountIds=1234-4567-8901" \\-u ‘[auth_token]:’ | jq '.result.summary.coverage | .[] | select( .reservationCost.totalEstimatedSavings > 10000)'
```

---

## RI Portfolio End Points

<!-- sub-header -->
- **breadcrumb:** Cloudability API > RI Portfolio End Points
- **source_path:** SSVCLNQ/api-v3/ri_portfolio_endpoints.html
- **original_file:** api-ri-portfolio-end-points.md
- **images:** []

## RI Portfolio End Points

We have two RI Portfolio end points available. Our legacy offering gives a summary list of all existing reservations while our current end point gives a more detailed view including the overall utilization and savings associated with each individual RI.

Note that the current end point requires the CUR file.

---

## Reservation Portfolio End Point

<!-- sub-header -->
- **breadcrumb:** Cloudability API > RI Portfolio End Points > Reservation Portfolio End Point
- **source_path:** SSVCLNQ/api-v3/reservation_portfolio_endpoint.html
- **original_file:** points-reservation-portfolio-end-point.md
- **images:** []

## Reservation Portfolio End Point

Summary

The RI Portfolio end point can be used to retrieve a detailed list of all Reserved Instances (RIs) as well as understand how well utilized these reservations were over a particular period of time.

Learn more about the Reservation Portfolio.

Included examples in this document will focus on compute reservations an commitments but the patterns for other supported AWS services (i.e. RDS, Redshift and ElastiCache) are consistent with EC2 examples.

End Point Particulars

The end points are read-only for retrieving a list of Reservation Objects

- AWS EC2 RI end point : /reservations/aws/savings/ec2
- AWS Savings Plan end point : /reservations/aws/portfolio/savingsPlan
- **Azure compute RI end point **: /reservations/azure/portfolio/compute
- GCP compute CUD end point : /reservations/gcp/portfolio/ce
- AWS RDS RI end point : /reservations/aws/savings/rds
- AWS Redshift RI end point : /reservations/aws/savings/redshift
- AWS ElastiCache end point : /reservations/aws/savings/elasticache

AWS RI Arguments

| Argument | Required? | Description | Type |
| --- | --- | --- | --- |
| start | yes | Beginning of time window to look for RI usage, e.g. "2018-01-01" | string |
| end | yes | End of time window to look for RI usage e.g. "2018-01-01" | string |
| basis | no | Defaults to 'cash' though you may pass 'adjusted' to see savings net of any custom pricing rules | string |
| viewId | no | Defaults to 0. Only account-group based views are supported | integer |

The AWS Reservation Object

- availabilityZone (string): If applicable
- count (integer): Number of reserved instances in the RI
- duration (integer): duration of the RI in seconds
- end (string): The timestamp when the RI ends e.g., '2018-07-06T18:00:00Z'
- instanceType (string): e.g., 'r3.large'
- multiAz (string): Single-AZ or Multi-AZ (RDS only)
- netSavings (number): Total savings, reflecting the difference between what you paid for an RI and how much the hours you actually consumed would have cost if purchased On-Demand
- offeringClass (string): 'standard' or 'convertible
- offeringType (string): 'NoUpfront ', 'PartialUpfront' or 'AllUpfront'
- operatingSystem (string): Software and associated licensing info. e.g., "Linux" or "Windows with SQL Server Standard
- overallUtilization (number): The percent of purchased hours that were applied to a running instance
- region (string): e.g., 'us-east-1',
- reservationIdentifier (string): The vendor supplied unique id for your reservation
- scope (string): 'Region' or 'Availability Zone'
- start (string): The timestamp when the RI begins e.g., '2018-07-06T18:00:00Z'
- state (string): 'retired' or 'active'
- tenancy (string): 'default' or 'dedicated'
- term (integer): duration of the RI in years
- units (integer): number of ISF-Normalized hours in the RI
- unrealizedSavings (number): Any additional savings you could have achieved assuming complete RI utilization
- vendorAccountId (string): 12 digit string corresponding to your AWS account ID

Example AWS Reservation Object

```
{
  "result": [
    {
      "availabilityZone": "",
      "count": 1,
      "duration": 10368000,
      "end": "2018-11-03T16:17:39Z",
      "instanceType": "t2.large",
      "multiAz": "(not set)",
      "netSavings": 25.416000000000015,
      "offeringClass": "standard",
      "offeringType": "NoUpfront",
      "operatingSystem": "Linux",
      "overallUtilization": 1,
      "region": "us-east-1",
      "reservationIdentifier": "0202a336-1712-1712-1712-0202a336",
      "scope": "Region",
      "start": "2018-07-06T18:00:00Z",
      "state": "active",
      "tenancy": "default",
      "term": 1,
      "units": 4,
      "unrealizedSavings": 0,
      "vendorAccountId": "0123456789"
    }
  ]
}
```

Example AWS Reservation Portfolio Requests

List Subscriptions

The following will list any EC2 reservations that were active between March 1 and March 15, 2018 and with no view restrictions.

```
curl "https://api.cloudability.com/v3/reservations/aws/savings/ec2?basis=cash&start=2018-08-01&end=2018-08-15&viewId=0" \\
     -u ‘[auth_token]:’
```

AWS Savings Plan Arguments

| Argument | Required | Description | Type |
| --- | --- | --- | --- |
| filter | No | Attributes Measure(field) and value that savings plans in response must have. E.g. ‘InstanceFamily’ ‘r5’ | string |
| limit | No | Part of pagination range request for maximum count per page. | integer |
| offset | No | Part of pagination range request designating the first asset to be returned in the response. | integer |
| sortOrder | No | Measure(field) and direction (ascending/descending) order of assets in response. | string |
| viewId | No | Cloudability ViewID to be respected in response. | integer |

The AWS Savings Plan Object

- vendorAccountId (string): 12 digit string corresponding to your AWS account ID
- savingsPlanId (string): the vendor assigned identifier for the Savings Plan
- savingsPlanArn (string): The vendor assigned Savings Plan unique global identifier
- duration (integer): duration of the savings plan in seconds
- start (integer): The Epoch millisecond formatted time stamp of the Savings Plan becoming active
- end (integer): The Epoch millisecond formatted time stamp of when the Savings Plan will terminate
- term (integer): Savings Plan Term length in years
- type (string): Savings Plan type (EC2 or Compute)
- state (string): Current state of the Savings plan (e.g. Active)
- region (string): EC2 Savings Plan region designation (not applicable for Compute plans)
- ec2InstanceFamil (string): EC2 Savings Plan applicable instance family designation (not applicable for Compute plans)
- offeringType (string): Payment method/model designation (e.g. No Upfront)
- hourlyCommitment (integer): Hourly Savings Plan monetary commitment
- totalCommitment (integer): Total monetary commitment over the life of the savings plan
- currencyCode (string): Monetary units for Savings Plan hourly and total commitment
- upfront (integer): Initial payment made at inception of Savings Plan
- frequency (string): Applicable pricing interval units
- amount

(integer): Applicable pricing per frequency unit specified

Example AWS Savings Plan Object

```
{
  "result": [
    {
      "vendorAccountId": "############",
      "accountName": "AWS Consolidated Master",
      "savingsPlanId": "xx###x##x-xxxx-#xxx-xx##-x####x###xxx",
      "savingsPlanArn": "arn:aws:savingsplans::############:savingsplan/xx###x##x-xxxx-#xxx-xx##-x####x###xxx",
      "description": "1 year No Upfront r5 EC2 Instance Savings Plan in us-east-1",
      "start": 1573079358000,
      "end": 1604615357000,
      "duration": 31536000,
      "term": 1,
      "type": "EC2Instance",
      "state": "active",
      "region": "us-east-1",
      "ec2InstanceFamily": "r5",
      "offeringType": "No Upfront",
      "hourlyCommitment": 1,
      "totalCommitment": 8760,
      "pricing": {
        "offeringId": "c#####xx#-xxx#-##xx-x##x-#xx####xx#x#",
        "currencyCode": "USD",
        "upfront": 0,
        "recurring": {
          "frequency": "Hourly",
          "amount": 1
        }
      },
      "tags": []
    },
    {
      "vendorAccountId": "############",
      "accountName": "AWS Consolidated Master",
      "savingsPlanId": "xx###x##x-xxxx-#xxx-xx##-x####x###xxx",
      "savingsPlanArn": "arn:aws:savingsplans::############:savingsplan/xx###x##x-xxxx-#xxx-xx##-x####x###xxx",
      "description": "1 year No Upfront Compute Savings Plan",
      "start": 1573145364000,
      "end": 1604681363000,
      "duration": 31536000,
      "term": 1,
      "type": "Compute",
      "state": "active",
      "region": "(not set)",
      "ec2InstanceFamily": "(not set)",
      "offeringType": "No Upfront",
      "hourlyCommitment": 1,
      "totalCommitment": 8760,
      "pricing": {
        "offeringId": "c#####xx#-xxx#-##xx-x##x-#xx####xx#x#",
        "currencyCode": "USD",
        "upfront": 0,
        "recurring": {
          "frequency": "Hourly",
          "amount": 1
        }
      },
      "tags": []
    }
  ],
  "meta": {
    "aggregate": {
      "quantity": 2,
      "hourlyCommitment": 2
    },
    "pagination": {
      "totalCount": 2
    }
  }
}
```

Example Savings Plan Inventory Request

List Savings Plans

The following will list the first 50 active or expired r5 EC2 Savings Plans in us-east-1 sorted by expiration date from those expiring soonest to those expiring farthest in the future.

```
curl "https://api.cloudability.com/v3/reservations/aws/portfolio/savingsPlan?filter&limit=50&offset=0&product=savingsPlan&sortOrder=%2Bend&viewId=0" \\
     -H "apptio-opentoken: [apptio opentoken]" -H "apptio-environmentid: [environment id]"
```

The Google Cloud Platform(GCP) Commitment Endpoint

The following api endpoint will provide a list of commitments.

The following curl will work with GET/ POST requests: GET with query parameters and POST with request body.

```
curl 'https://api.cloudability.com/v3/reservations/gcp/portfolio/commitment' 
	 -H 'accept: application/json, text/plain, /' 
	 -H 'accept-language: en-US,en;q=0.9' 
	 -H 'authorization: Bearer [auth_token]' 
	 -H 'content-type: application/json' 
	 --data-raw '{"start":"2025-02-28","end":"2025-03-30","basis":"adjusted","filter":"commitment_category==spend","viewId":0,"limit":10,"offset":0,"sortOrder":"-billingAccountIdentifier","service":"scud-groups","services":"compute_engine"}'
		
```

The following table lists the valid payload options:

| Payload Options | Valid Format | Details |
| --- | --- | --- |
| start | Date in the format “YYYY-MM-DD" |  |
| end | Date in the format “YYYY-MM-DD" |  |
| basis | adjusted, cost |  |
| filter |  | Look how filters get formed in the developer toolbar. |
| sortOrder | A valid field e.g. billingAccountIdentifier for ALL, netsavings for other CUDs. |  |
| services | Comma separated string with values from compute_engine cloud_sql | Current supported services include “compute_engine” and “cloud_sql”. |

For SCUDs, RCUDs or ALL commitments to be returned via these endpoints, use the following in filters along with dates.

| Commitments | Filter Values | Details |
| --- | --- | --- |
| Flex CUDs Commitments | "commitment_category==spend" | When commitment category as spend is provided, the above endpoint should return Flex CUDs commitments only. |
| RCUDs Commitments | "commitment_category==resource" | When commitment category as resource is provided, the above endpoint should return Resource CUDs commitments only. |
| All Commitments | No filter added | When no commitment category is provided as filter, Flex CUDs and RCUDs are returned as response by merging the results of RCUD and SCUD commitments |
| Cloud SQL CUDs | "commitment_category==spend" | "commitment_category==spend" with services in payload should be “cloud_sql” |

The Google Cloud Platform(GCP) Commitment Endpoint Object

- commitmentGroupId (string): The commitment group id for the group commitment belongs to.
- billingAccountIdentifier (string): Billing Account Identifier in which commitment belong to.
- term (integer): CUD term length in years.
- region (string): Text description of the CUD's assigned region e.g. 'us-central'.
- status (string): Current CUD status.
- hourlyCommitmentAmount (string): Hourly commitment amount.
- hourlyCommitmentCost (string): Hourly commitment cost that is being paid.
- totalCommitmentAmount (string): Hourly commitment cost that is being paid.
- totalCommitmentCost (string): Total commitment cost to be paid.
- commitmentCostRemaining (string): Commitment remaining cost.
- remainingCost (string): Remaining cost of the CUD to be paid.
- commitmentDiscountRate (string): Commitment discount rate percentage / 100.
- creation (string): The creation date of the CUD was requested
- start (string): The start date of when the CUD began applying to usage
- end (string): The CUD expiration date
- expirationDate (string): The CUD expiration date
- offer (string): CUD offer details if available.
- description (string): Description of the CUD.
- name (string): User assigned CUD name
- accountIdentifier (string): User assigned account ID
- memory (integer): MB of memory allocated (at 1024MB/GB)
- vcpus (integer): vCPUs allocated to the CUD
- duration (integer): Duration of the RI in seconds
- statusMessage (string): Long form status description and explanation
- type (string): Flex-CUD or CUD type of the CUD
- commitmentGroupDetails (object): Commitment group details object {}
- service : Service name CUD belongs to
- reservationId/ commitmentId (string): Unique identifier of the CUD.
- commitmentCategory
- (string): Commitment category, Spend or Resource.

Example GCP Commitment Endpoint Object

This is example response for ALL Commitments with 1 Flex CUD (SCUD) and 1 RCUD.

```
"result": [
  {
    "commitmentGroupId": "01E091-D83A6B-1F55DD:spend:COMPUTE_ENGINE:all-regions",
    "billingAccountIdentifier": "01E091-D83A6B-1F55DD",
    "term": 1,
    "region": "n/a",
    "quantity": 0,
    "status": "Active",
    "hourlyCommitmentAmount": 0.12,
    "hourlyCommitmentCost": 0.086397,
    "totalCommitmentAmount": 89.28,
    "totalCommitmentCost": 64.279011,
    "commitmentCostRemaining": 275.78,
    "commitmentDiscountRate": 0.280029,
    "creation": "2024-01-04",
    "start": "2024-01-04",
    "end": "2025-01-04",
    "expirationDate": "2025-01-04",
    "offer": "services/compute.googleapis.com/standardOffers/ffe0f6a3-2f98-437e-8d49-fc443a05d3c2",
    "description": "billingAccounts/01E091-D83A6B-1F55DD/orders/2b455b7d-d3d2-4696-a9bd-6d046776edcf",
    "name": "James Smith requested Flex CUD",
    "accountIdentifier": "01E091-D83A6B-1F55DD",
    "memory": 0,
    "vcpus": 0,
    "duration": 0,
    "commitmentGroupDetails": {
    "reservationId": "01E091-D83A6B-1F55DD:spend:COMPUTE_ENGINE:all-regions",
    "commitmentCategory": "Spend",
    "region": "all-regions",
    "quantity": 3,
    "status": "Active",
    "nextExpirationDate": "2025-01-04",
    "netSavings": -13.279300,
    "realizedSavingsRate": -0.0991584521,
    "commitmentListDiscountRate": 0.290029,
    "hourlyCommitmentAmount": 0.180000,
    "totalCommitmentAmount": 133.920000,
    "hourlyCommitmentCost": 0.127795,
    "totalCommitmentCost": 95.079368,
    "scudGroupUtilization": 0.610836,
    "remainingCost": 503.310000,
    "accountIdentifier": "01E091-D83A6B-1F55DD",
    "unrealizedSavings": -13.279300,
    "nextExpiration": 0,
    "vcpus": 0,
    "memory": 0,
    "predefinedOnDemandPrice": 0.0,
    "customOnDemandPrice": 0.0,
    "commit1YrPrice": 0.0,
    "commit3YrPrice": 0.0,
    "orgId": 112844,
    "service": "COMPUTE_ENGINE",
    "billingAccountIdentifier": "01E091-D83A6B-1F55DD",
    "scuds": []
    },
     "orgId": 112844,
     "service": "COMPUTE_ENGINE",
     "reservationId": "2b455b7d-d3d2-4696-a9bd-6d046776edcf",
     "commitmentCategory": "Spend"
    },
	{
	 "commitmentGroupId": "staging-rightsizing:us-central1:GENERAL_PURPOSE_E2",
	 "billingAccountIdentifier": "staging-rightsizing",
	 "term": 1,
	 "region": "us-central1",
	 "quantity": 0,
	 "status": "ACTIVE",
	 "hourlyCommitmentAmount": 0.0,
	 "hourlyCommitmentCost": 0.0,
	 "totalCommitmentAmount": 0.0,
	 "totalCommitmentCost": 0.0,
	 "commitmentCostRemaining": 0.0,
	 "commitmentDiscountRate": 0.0,
	 "creation": "2024-06-18",
	 "start": "2024-06-19",
	 "end": "2025-06-19",
	 "expirationDate": "2025-06-19",
	 "offer": "0.0",
	 "description": "",
	 "name": "sean-e2-commitment",
	 "accountIdentifier": "staging-rightsizing",
	 "commitmentType": "GENERAL_PURPOSE_E2",
	 "memory": 2048,
	 "vcpus": 2,
	 "selfLink": "https://www.googleapis.com/compute/beta/projects/staging-rightsizing/regions/us-central1/commitments/sean-e2-commitment",
	 "statusMessage": "The commitment is active, and so will apply to current resource usage.",
	 "duration": 0,
	 "orgId": 112844,
	 "service": "COMPUTE_ENGINE",
	 "reservationId": "4034804980905703051",
	 "commitmentCategory": "Resource"
	},
	],
	"aggregate": {
	"quantity": 13,
	"unrealizedSavings": 0,
	"hourlyCommitment": 0.127795,
       "totalCommitment": 95.079368,
	"netSavings": 171.847206,
	"overallUtilization": 0.610836,
	"effectiveSavingsRate": 0.000000,
	"coverage": 0.007172,
	"remainingCommitmentCost": 503.310000,
	"rcudCoverageAmount": 964.089371,
	"scudCoverageAmount": 133.920001,
	"commitmentCoverageAmount": 1098.009372,
	"commitmentEligibleCoverageCost": 4456.955846,
	"relevantSpendCommitmentCoverageCost": 5554.965218,
	"rcudExclusiveEligibleCoverageCost": 6866.890625,
	"relevantAllCommitmentCoverageCost": 12421.855843,
	"costsUncoverableByCommitments": 4539.347407,
	"totalServiceODCost": 16961.203250,
	"sudCredit": -2038.881740
	},
	"pagination": {
	"totalCount": 2
	}


```

The commitment-groups endpoint has SCUDs or CUDs according to commitment category whereas commitment endpoint has commitmentGroupDetails against each commitment. But commitmentGroupDetails does not re-populate SCUDs or CUDs again for commitment endpoint.

The Google Cloud Platform(GCP) Commitment Groups Endpoint

The following api endpoint will provide a list of commitment groups and associated commitments in it.

The following curl will work with GET/ POST requests: GET with query parameters and POST with request body.

```
curl 'https://api.cloudability.com/v3/reservations/gcp/portfolio/commitment-groups' 
	 -H 'accept: application/json, text/plain, /' 
	 -H 'accept-language: en-US,en;q=0.9' 
	 -H 'authorization: Bearer [auth_token]' 
	 -H 'content-type: application/json' 
	 --data-raw '{"start":"2025-02-28","end":"2025-03-30","basis":"adjusted","filter":"commitment_category==spend","viewId":0,"limit":10,"offset":0,"sortOrder":"-netSavings","service":"scud-groups","services":"compute_engine"}'

```

The following table lists the valid payload options:

| Payload Options | Valid Format | Details |
| --- | --- | --- |
| start | Date in the format “YYYY-MM-DD" |  |
| end | Date in the format “YYYY-MM-DD" |  |
| basis | adjusted, cost |  |
| filter |  | Look how filters get formed in the developer toolbar. |
| sortOrder | A valid field e.g. billingAccountIdentifier for ALL, netsavings for other CUDs. |  |
| services | Comma separated string with values from compute_engine cloud_sql | Current supported services include “compute_engine” and “cloud_sql”. |

For SCUDs, RCUDs or ALL commitments to be returned via these endpoints, use the following in filters along with dates.

| Commitments | Filter Values | Details |
| --- | --- | --- |
| Flex CUDs Commitments | "commitment_category==spend" | When commitment category as spend is provided, the above endpoint should return Flex CUDs commitments only. |
| RCUDs Commitments | "commitment_category==resource" | When commitment category as resource is provided, the above endpoint should return Resource CUDs commitments only. |
| All Commitments | No filter added | When no commitment category is provided as filter, Flex CUDs and RCUDs are returned as response by merging the results of RCUD and SCUD commitments |
| Cloud SQL CUDs | "commitment_category==spend" | "commitment_category==spend" with services in payload should be “cloud_sql” |

The Google Cloud Platform(GCP) Commitment Groups Endpoint Object

- commitmentGroupId (string): The commitment group id for the group commitment belongs to.
- billingAccountIdentifier (string): Billing Account Identifier in which commitment belong to.
- term (integer): CUD term length in years.
- region (string): Text description of the CUD's assigned region e.g. 'us-central'.
- status (string): Current CUD status.
- hourlyCommitmentAmount (string): Hourly commitment amount.
- hourlyCommitmentCost (string): Hourly commitment cost that is being paid.
- totalCommitmentAmount (string): Hourly commitment cost that is being paid.
- totalCommitmentCost (string): Total commitment cost to be paid.
- commitmentCostRemaining (string): Commitment remaining cost.
- remainingCost (string): Remaining cost of the CUD to be paid.
- commitmentDiscountRate (string): Commitment discount rate percentage / 100.
- creation (string): The creation date of the CUD was requested
- start (string): The start date of when the CUD began applying to usage
- end (string): The CUD expiration date
- expirationDate (string): The CUD expiration date
- offer (string): CUD offer details if available.
- description (string): Description of the CUD.
- name (string): User assigned CUD name
- accountIdentifier (string): User assigned account ID
- memory (integer): MB of memory allocated (at 1024MB/GB)
- vcpus (integer): vCPUs allocated to the CUD
- duration (integer): Duration of the RI in seconds
- statusMessage (string): Long form status description and explanation
- type (string): Flex-CUD or CUD type of the CUD
- commitmentGroupDetails (object): Commitment group details object {}
- service : Service name CUD belongs to
- reservationId/ commitmentId (string): Unique identifier of the CUD.
- commitmentCategory (string): Commitment category, Spend or Resource.
- Example Google Cloud Platform(GCP) Commitment Groups Endpoint Object

This is an example response for Commitment Groups for Flex CUDs.

```
{
  {
   "result": [
	{
	 "reservationId": "01E091-D83A6B-1F55DD:spend:COMPUTE_ENGINE:all-regions",
	 "commitmentGroupId": "01E091-D83A6B-1F55DD:spend:COMPUTE_ENGINE:all-regions",
	 "commitmentCategory": "Spend",
	 "region": "all-regions",
	 "quantity": 3,
	 "status": "Active",
	 "nextExpirationDate": "2025-01-04",
	 "netSavings": 0.000000,
	 "commitmentListDiscountRate": 0.290000,
	 "hourlyCommitmentAmount": 0.180000,
	 "hourlyCommitmentCost": 0.127800,
	 "totalCommitmentAmount": 133.920000,
	 "totalCommitmentCost": 95.083200,
	 "totalLifeTimeCommitmentCost": 1214.136000,
	 "totalLifeTimeCommitmentAmount": 1752.000000,
	 "scudGroupUtilization": 0.000000,
	 "remainingCost": 261.010000,
	 "accountIdentifier": "n/a",
	 "unrealizedSavings": 0.000000,
	 "nextExpiration": 0,
	 "vcpus": 0,
	 "memory": 0,
	 "predefinedOnDemandPrice": 0.0,
	 "customOnDemandPrice": 0.0,
	 "commit1YrPrice": 0.0,
	 "commit3YrPrice": 0.0,
	 "scudsMinStartDate": "2024-01-04",
	 "orgId": 108194,
	 "service": "COMPUTE_ENGINE",
	 "billingAccountIdentifier": "01E091-D83A6B-1F55DD",
	 "scuds": [
	{
	 "commitmentGroupId": "01E091-D83A6B-1F55DD:spend:COMPUTE_ENGINE:all-regions",
	 "billingAccountIdentifier": "01E091-D83A6B-1F55DD",
	 "term": 1,
	 "region": "n/a",
	 "status": "Active",
	 "hourlyCommitmentAmount": 0.12,
	 "hourlyCommitmentCost": 0.0864,
	 "totalCommitmentAmount": 89.28,
	 "totalCommitmentCost": 64.2816,
	 "totalLifeTimeCommitmentCost": 756.864000,
	 "totalLifeTimeCommitmentAmount": 1051.200000,
	 "commitmentCostRemaining": 111.97,
	 "remainingCost": 111.97,
	 "commitmentDiscountRate": 0.28,
	 "creation": "2024-01-04",
	 "start": "2024-01-04",
	 "end": "2025-01-04",
	 "expirationDate": "2025-01-04",
	 "offer": "services/compute.googleapis.com/standardOffers/ffe0f6a3-2f98-437e-8d49-fc443a05d3c2",
	 "description": "billingAccounts/01E091-D83A6B-1F55DD/orders/2b455b7d-d3d2-4696-a9bd-6d046776edcf",
	 "name": "James Smith requested Flex CUD",
	 "accountIdentifier": "n/a",
	 "memory": 0,
	 "vcpus": 0,
	 "duration": 0,
	 "type": "Compute Flex-CUD",
	 "orgId": 108194,
	 "service": "COMPUTE_ENGINE",
	 "reservationId": "2b455b7d-d3d2-4696-a9bd-6d046776edcf",
	 "commitmentCategory": "Spend"
	},
	{
	 "commitmentGroupId": "01E091-D83A6B-1F55DD:spend:COMPUTE_ENGINE:all-regions",
	 "billingAccountIdentifier": "01E091-D83A6B-1F55DD",
	 "term": 1,
	 "region": "n/a",
	 "status": "Active",
	 "hourlyCommitmentAmount": 0.05,
	 "hourlyCommitmentCost": 0.036,
	 "totalCommitmentAmount": 37.2,
	 "totalCommitmentCost": 26.784,
	 "totalLifeTimeCommitmentCost": 315.360000,
	 "totalLifeTimeCommitmentAmount": 438.000000,
	 "commitmentCostRemaining": 46.66,
	 "remainingCost": 46.66,
	 "commitmentDiscountRate": 0.28,
	 "creation": "2024-01-04",
	 "start": "2024-01-04",
	 "end": "2025-01-04",
	 "expirationDate": "2025-01-04",
	 "offer": "services/compute.googleapis.com/standardOffers/ffe0f6a3-2f98-437e-8d49-fc443a05d3c2",
	 "description": "billingAccounts/01E091-D83A6B-1F55DD/orders/e3e36abf-36c6-4ebf-adb1-295e570f09da",
	 "name": "James Smith requested Flex CUD",
	 "accountIdentifier": "n/a",
	 "memory": 0,
	 "vcpus": 0,
	 "duration": 0,
	 "type": "Compute Flex-CUD",
	 "orgId": 108194,
	 "service": "COMPUTE_ENGINE",
	 "reservationId": "e3e36abf-36c6-4ebf-adb1-295e570f09da",
	 "commitmentCategory": "Spend"
	},
	{
	 "commitmentGroupId": "01E091-D83A6B-1F55DD:spend:COMPUTE_ENGINE:all-regions",
	 "billingAccountIdentifier": "01E091-D83A6B-1F55DD",
	 "term": 3,
	 "region": "n/a",
	 "status": "Active",
	 "hourlyCommitmentAmount": 0.01,
	 "hourlyCommitmentCost": 0.0054,
	 "totalCommitmentAmount": 7.44,
	 "totalCommitmentCost": 4.0176,
	 "totalLifeTimeCommitmentCost": 141.912000,
	 "totalLifeTimeCommitmentAmount": 262.800000,
	 "commitmentCostRemaining": 102.38,
	 "remainingCost": 102.38,
	 "commitmentDiscountRate": 0.46,
	 "creation": "2024-01-10",
	 "start": "2024-01-10",
	 "end": "2027-01-10",
	 "expirationDate": "2027-01-10",
	 "offer": "services/compute.googleapis.com/standardOffers/062a285d-8989-4ce7-8f9a-bed8d183236f",
	 "description": "billingAccounts/01E091-D83A6B-1F55DD/orders/fda5efd3-ca2e-4c79-9dfd-2d16f1746bbe",
	 "name": "Blake Corum 3 year commitment",
	 "accountIdentifier": "n/a",
	 "memory": 0,
	 "vcpus": 0,
	 "duration": 0,
	 "type": "Compute Flex-CUD",
	 "orgId": 108194,
	 "service": "COMPUTE_ENGINE",
	 "reservationId": "fda5efd3-ca2e-4c79-9dfd-2d16f1746bbe",
	 "commitmentCategory": "Spend"
      }
      ]
      }
      ],
	 "aggregate": {
        "quantity": 3,
	 "unrealizedSavings": 0.000000,
	 "netSavings": 0.000000,
	 "overallUtilization": 0.000000,
	 "effectiveSavingsRate": 0.000000,
	 "coverage": 0.000000,
	 "remainingCommitmentCost": 261.010000,
	 "totalRemainingCost": 261.010000,
	 "rcudCoverageAmount": 0.000000,
	 "scudCoverageAmount": 0.000000,
	 "spendCoveredResourceEligibleCost": 98.234687,
	 "resourceCoveredSpendEligibleCost": 166.385452,
	 "totalCoveredAmount": 0.000000,
	 "spendTotalCoveredAmount": 166.385452,
	 "resourceTotalCoveredAmount": 98.234687,
	 "spendCommitmentEligibleCoverageCost": 1199.875958,
	 "resourceCommitmentEligibleCoverageCost": 2769.947700,
	 "relevantResourceCommitmentCoverageCost": 2868.182387,
	 "relevantSpendCommitmentCoverageCost": 1366.261410,
	 "rcudExclusiveEligibleCoverageCost": 1573.353773,
	 "scudExclusiveEligibleCoverageCost": 3.282031,
	 "relevantAllCommitmentCoverageCost": 2773.229731,
	 "costsUncoverableByCommitments": 1185.002169,
	 "totalServiceODCost": 3958.231900,
	 "sudCredit": -634.953422,
	 "commitmentEligibleCoverageCost": 2773.229731,
	 "nonExclusiveEligibleCost": 1196.593927
	}
	 "pagination": {
	 "totalCount": 1
	}
       }


```

The commitment-groups endpoint has SCUDs or CUDs according to commitment category whereas commitment endpoint has commitmentGroupDetails against each commitment. But commitmentGroupDetails does not re-populate SCUDs or CUDs again for commitment endpoint.

The Azure Reserved Instance Object

- vendorAccountId (string): Vendor assigned unique alphanumeric subscription identifier
- reservationId (string): Vendor assigned unique alphanumeric reservation identifier
- AccountName (string): User assigned subscription name
- size (string): On demand instance family covered by the reservation(e.g.'DS1_v2')
- tier (string): On demand instance tier covered by the reservation (e.g.'Standard')
- term (integer): Reservation term length in years
- quantity (integer): Number of instances covered by the reservation
- region (string): Text description of the reservation's assigned region e.g. 'westus2'
- state (string): Current reservation status
- start (number): The Epoch millisecond formatted time stamp of when the CUD began applying to usage
- end (number): The Epoch millisecond formatted CUD expiration time stamp
- currencyCode (string): The currency reporting type for the reservation
- upfront (integer): The up front reservation purchase price in the applicable currency

Example Azure Reservation Object

```
{
  "result": [
    {
      "vendorAccountId": "2####252-2##4-4##e-9##7-b95#########",
      "reservationId": "45####04-3X#2-4##7-b##6-35c##XX###X#",
      "accountName": "AZU Staging US",
      "size": "DS1_v2",
      "tier": "Standard",
      "term": 1,
      "quantity": 3,
      "region": "westus2",
      "state": "Cancelled",
      "start": 1560211200000,
      "end": 1560729600000,
      "pricing": {
        "currencyCode": "USD",
        "upfront": 810
      }
    },
    {
      "vendorAccountId": "c####d37-eecc-##d6-###b-######da36a6",
      "reservationId": "XX6d##d7-b034-4XX8-a8a0-3bcc###a####",
      "accountName": "Azure Prod",
      "size": "B1s",
      "tier": "Standard",
      "term": 1,
      "quantity": 1,
      "region": "westus2",
      "state": "Succeeded",
      "start": 1557446400000,
      "end": 1588896000000,
      "pricing": {
        "currencyCode": "USD",
        "upfront": 53
      }
    },
    {
      "vendorAccountId": "26e#####-2##4-434e-####-b95f#####fd#",
      "reservationId": "3d####f7-0X##-40b0-b###-82bd######a#",
      "accountName": "AZU Staging US",
      "size": "DS1_v2",
      "tier": "Standard",
      "term": 1,
      "quantity": 2,
      "region": "westus2",
      "state": "Succeeded",
      "start": 1560729600000,
      "end": 1591747200000,
      "pricing": {
        "currencyCode": "USD",
        "upfront": 540
      }
    },
  "meta": {
    "aggregate": {
      "quantity": 6
    },
    "pagination": {
      "totalCount": 3
    }
  }
}
```

Example Azure Reservation Portfolio Request

The following will generate a list of Azure Reserved Instances

```
curl "https://api.cloudability.com/v3/reservations/azure/portfolio/compute" \\
     -u ‘[auth_token]:’
```

---

## RI Portfolio Legacy End Point

<!-- sub-header -->
- **breadcrumb:** Cloudability API > RI Portfolio End Points > RI Portfolio Legacy End Point
- **source_path:** SSVCLNQ/api-v3/ri_portfolio_legacy_endpoint.html
- **original_file:** points-ri-portfolio-legacy-end-point.md
- **images:** []

## RI Portfolio Legacy End Point

Summary

The RI Portfolio end point can be used to retrieve a list of all your current and historical Reserved Instances (RIs). This Cloudability feature is especially handy as it aggregates RIs across all of your linked and master payer accounts for EC2, RDS, Redshift and Elasticache.

Learn more about the RI portfolio features.

Examples in this document will focus on EC2, but you will find patterns consistent across other AWS products.

- This end point supports filtering and sorting.

End Point Particulars

These end points are read-only for retrieving a list of Reservation Objects

end point : /reservations/aws/portfolio/ec2

end point : /reservations/aws/portfolio/rds

end point : /reservations/aws/portfolio/redshift

end point : /reservations/aws/portfolio/elasticache

These end points return a meta attribute within the JSON payload that looks like the following. In the example below 399 represents the number of RI purchases , whereas 24615 is the total number of instances across those purchases.

```
 "meta": {
    "aggregate": {
      "quantity": 24615
    },
    "pagination": {
      "totalCount": 399
    }
  }
```

The Reservation Object

vendorAccountId (string) - 12 digit string corresponding to your AWS account ID

reservationId (string) - The vendor supplied unique id for your reservation

instanceType (string) - The exact instance type you reserved

availabilityZone (string) - The availability zone you reserved into. If region scoped this will return as an empty string.

region (string) - The Region you reserved into. If AZ scoped this will return as an empty string.

start (integer) - The timestamp for when the RI began it's active period, represented in Unix time with millisecond precision.

end (integer) - The timestamp for when the RI began ended it's active period, represented in Unix time with millisecond precision.

duration (integer) - The active time for the RI, measured in seconds

term (integer) - Term for the RI, one or two year

productDescription (string) - The Reserved Instance product platform description as defined by AWS. For example Linux/UNIX (Amazon VPC) for EC2, aurora-mysql for RDS

tenancy (string) - Whether the RI is for shared (default) or single-tenant (dedicated) hardware

quantity (integer) - The number of instances comprising the reservation

state (string) - The state of the RI, the main ones being active right now or retired since the term finished.

offeringType (string) - Generally these will be one of 'No Upfront', 'Partial Upfront' or 'All Upfront' but for older retired RIs could be Utilization based types.

offeringClass (string) - Standard or Convertible

scope (string) - Availability Zone or Region

pricing (hash) - object containing details of verification state:

currencyCode (string) - At this time, the only supported currency is USD

upfront (integer) - The Upfront cost for the RI

recurring (hash) - info regarding the recurring aspect of the purchased RI.

frequency (string) - The granularity for the recurring price fee. Current supported value is 'hourly'

amount (number) - The hourly recurring rate for the RI.

tags (array) - a list of the tags applied to the RI

Example Reservation Object

```
{
  "result": [
    {
      "vendorAccountId": "118273444843",
      "reservationId": "aa04e121-436e-4cd4-8e50-0f8ebd95c52b",
      "instanceType": "r3.2xlarge",
      "availabilityZone": "",
      "region": "us-east-1",
      "start": 1516386261000,
      "end": 1521570259000,
      "duration": 5184000,
      "term": 1,
      "productDescription": "Linux/UNIX (Amazon VPC)",
      "tenancy": "default",
      "quantity": 1,
      "state": "active",
      "offeringType": "No Upfront",
      "offeringClass": "standard",
      "scope": "Region",
      "pricing": {
        "currencyCode": "USD",
        "upfront": 0,
        "recurring": {
          "frequency": "Hourly",
          "amount": 0.418
        }
      },
      "tags": []
    }
  ]
}
```

Example Requests

List Subscriptions

The following will list all subscriptions, historic and current, for EC2

```
curl "https://api.cloudability.com/v3/reservations/aws/portfolio/ec2" \\
     -u ‘[auth_token]:’
```

List Currently Active Subscriptions

```
curl "https://api.cloudability.com/v3/reservations/aws/portfolio/ec2?filter=state==active" \\
-u ‘[auth_token]:’
```

List & Order By Soonest Expiry Date

```
curl "https://api.cloudability.com/v3/reservations/aws/portfolio/ec2?filter=state==active&sortOrder=%2Bend" \\-u ‘[auth_token]:’
```

---

## Rightsizing End Points

<!-- sub-header -->
- **breadcrumb:** Cloudability API > Rightsizing End Points
- **source_path:** SSVCLNQ/api-v3/rightsizing_end_points.html
- **original_file:** api-rightsizing-end-points.md
- **images:** []

## Rightsizing End Points

Summary

The Rightsizing API provides rightsizing recommendations for resources from supported services. For each of these resources, the API returns multiple optimization recommendations as well as descriptive information such as the current instance size, cost, idle percentage, and recommended actions. The maximum number of resources that can be returned at one time by an API call is 50,000.

End Points

These end points are read-only and are used for obtaining a list of rightsizing recommendations for your cloud resources, for these supported services:

Amazon Web Services

- EC2: /rightsizing/aws/recommendations/ec2
- EC2 ASG: /rightsizing/aws/recommendations/ec2-asg
- EBS: /rightsizing/aws/recommendations/ebs
- S3: /rightsizing/aws/recommendations/s3
- RDS: /rightsizing/aws/recommendations/rds
- Redshift: /rightsizing/aws/underutilized/redshift
- Lambda: /rightsizing/aws/recommendations/lambda
- Elastic IP: /rightsizing/aws/recommendations/elastic-ip

Microsoft Azure

- Compute (VMs) : /rightsizing/azure/recommendations/compute
- Managed Disk : /rightsizing/azure/recommendations/disk
- SQL Database : /rightsizing/azure/recommendations/sql
- Blob Storage : /rightsizing/azure/recommendations/blob-storage

Google Cloud Platform

- GCE: /rightsizing/gcp/recommendations/compute
- GCE MIG: /rightsizing/gcp/recommendations/compute-mig
- GDP: /rightsizing/gcp/recommendations/disk
- GCS: /rightsizing/gcp/recommendations/gcs

Containers

- Workloads: /rightsizing/containers/recommendations/workloads

```
"meta": {
    "totalCount": 4783,
    "aggregates": [
      {
        "basis": "On-Demand",
        "cost": 337029.28,
        "idleSavings": 930.84,
        "rightsizeSavings": 106857.60,
        "optimizedSavings": 229240.84
      }
    ]
  }
```

The following end points are used to snooze and un-snooze rightsizing recommendations for your cloud resources, where “{service}” should be substituted with the path of the service’s end point:

Snooze/Un-Snooze Recommendations

- Snooze: /rightsizing/{vendor}/recommendations/{service}/snooze
- Un-Snooze: /rightsizing/{vendor}/recommendations/{service}/unsnooze

For more information on using the API to snooze/un-snooze recommendations, please visit the “Snooze/Un-Snooze Recs” section on this page.

Request Parameters

| Argument | Description |
| --- | --- |
| basis (required) | The cost basis used. on-demand Values are or effective Default = on-demand Note: The effective cost basis is available for EC2 and RDS services |
| duration (required) | The look back period in days, used for calculating the recommendations. Valid values are : ten-day and thirty-day Default = ten-day Note: only thirty-day is available for S3 |
| filters | Filter the resources based on an attribute of your choice. Example: filters=recommendations.action==Rightsize . To base on attribute within recommendation itself prefix with 'recommendations.'. Multiple filters can be chained together with commas. Example: filters=recommendations.savings>20,recommendations.risk==0 Read more for more details on filtering. |
| limit (required) | Used together with offset to provide pagination . Example: limit=10 . default = 50 |
| maxRecsPerResource | Set a maximum number of recommendations to be delivered with each resource. Example: maxRecsPerResource=10 default = 1 |
| offset | Used together with limit to provide pagination . Example: offset=0 default = 0 |
| product | Product Name, Example ec2, ebs, s3 |
| sort | Sort the resources based on an attribute of your choice. Read more about sorting. Example: sort=-name (sort by name descending) Default: sort=-recommendations.savings ( sort resources with highest savings potential descending) |
| source | Source system for utilization data Examples: datadog , cloudwatch |
| vendorAccountIds | Filter to a list of vendor accounts. Separate accounts using commas. Example: vendorAccountIds=999988887777,111122223333 |
| viewId | The number of the View . If blank, the view will be your default view. |
| options | String value representing which recommendations to return based on if the resource is snoozed. Valid values are ONLY_SNOOZED which will return recommendations for only snoozed resources, or INCLUDE_SNOOZED which will return recommendations for both snoozed and un-snoozed resources. Omitting “option” will return only un-snoozed resources. (default) |

The Resource Object

Current Resource Summary

The result object contains a list of all matching resources. This is the summary data included with each:

service (string) - Name of Recommendation Service (ec2-recs, eb2,rec, etc)

name (string) - Name of the resource. Originates from the Name tag

resourceIdentifier (string) - The unique identifier provided by the vendor for the resource

vendorAccountId (string) - The unique identifier for the account the resource exists within

tagMappings (array) - list of tag key and value pairs of tag mappings

tag (string) - native/provider tag name

tagName (string) - name/key for tag mapping

vendorTagValue (string) - value for this tag

availabilityZone (string) - The availability zone the resource resides in

provider (string) - The source provider, for example, NATIVE

region (string) - The region the resource resides in

os (string) - The operating system of the resource

nodeType (string) - For EC2 this is the instance type of the resource

unitPrice (number) - The per unit rate

effectiveHourly (number) - The hourly rate charged for the resource based on effective rates. DEPRECATED. Instead will show as unitPrice when costBasis=effective .

totalSpend (number) - The entire cost for the resource over the last 10 or 30 days

iopsMax (number) - max IOPS count during period

throughputMax (number) - max throughput MB/S during period

idle (number) - represents the percentage of time the resource has been idle

localCapacity (number) - local EC2 instance storage in GB. Types without associated storage will have a value of -1

localDrives (number) - number of local drives attached to the instance. Types without associated storage will have a value of -1

cpuCapacity (number) - count of CPU cores for current instance

memoryCapacity (number) - memory capacity for current instance in GB

networkCapacity (number) - network capacity for current instance in GB

lastSeen (datetime) - date resource was last seen

tenancy (string) - deprecated

hoursRunning (number) - hours running within period

cpuMax (number) - max CPU percentage during period

memoryMax (number) - max Memory percentage during period

defaultSameFamily (boolean) - use same instance family

defaultCurrentGen (boolean) - use current generations

defaultMemoryFit (boolean) - use same memory specification

instanceTypeAsg (string) - list of the instance types contained in the auto scaling group

utilMemoryMax (number) - max memory percentage of the Lambda during period

utilDurationMax (number) - max running time of the Lambda during period

billedMilliseconds (number) – total running time of the Lambda during period

sourceConfiguredMemory (number) – the configured memory of the Lambda

sourceProcessorArchitectureFamily (number) – the processor architecture family for the Lambda

Recommendation List

For each resource listed there will be a recommendations attribute which is an associated list of recommendation objects. These are the attributes of each recommendation:

recommendations (array) - A list of recommendations for the resource. Described below

action (string) - what action to take: rightsize, terminate, autoscale

preferenceOrder (number) - deprecated

defaultsOrder (number) - deprecated

nodeType (string) - the target instance type

localCapacity (number) - local EC2 instance storage in GB for target resource

localDrives (number) - number of local drives attached to target instance

cpuCapacity (number) - count of CPU cores for target instance

memoryCapacity (number) - memory capacity for target instance in GB

networkCapacity (number) - network capacity of target instance

previousGenTarget (boolean) - Is target instance a previous generation type?

currentGen (boolean) - Is target instance a current generation type?

sameMemory (boolean) - use same memory size as source instance

sameFamily (boolean) - Is the target instance type within the same family

unitPrice (number) - The per unit rate

cpuRatio (number) - ratio of CPU cores (target/original)

memoryRatio (number) - ratio of memory capacity (target/original)

diskXPutCapacity (number) - ratio of memory capacity (target/original)

networkRatio (number) - ratio of network throughput capacity (target/original)

cpuRisk (number) - risk related to CPU - value between 0 and 5 TBC. 0 being zero risk

memoryRisk (number) - risk related to memory - value between 0 and 5 TBC

diskRisk (number) - local disk throughput risk - value between 0 and 5 TBC

networkRisk (number) - risk related to network throughput - value between 0 and 5 TBC

risk (number) - value of 0,1,2,3,4 or 5. 0 being no risk. 5 being highest risk

targetConfiguredMemory (number) – the target configured memory of the Lambda

savingsPct (number) - Savings as a percentage by moving to target type

savings (number) - Savings over the last 10 or 30 days if you had used the target type

inDefaults - deprecated

memoryFit deprecated

persistentStorageAdded TBC - we added EBS costs for say c3 to c4

snoozed (boolean) – is the recommendation snoozed?

Example Object

```
"result": [
    {
      "service": "ec2-recs",
      "name": "My EC2 Instance",
      "resourceIdentifier": "i-5b234a4fae415b77f",
      "vendorAccountId": "458273444843",
      "tagsMappings: [
        {
          "tagName": "tag_user_Environment",
          "vendorTagValue": "production"
        },
        {
          "tagName": "tag_user_Name",
          "vendorTagValue": "My EC2 Instance"
        }
      ],
      "availabilityZone": "ap-southeast-2b",
      "provider": "NATIVE"
      "region": "ap-southeast-2",
      "os": "Linux",
      "nodeType": "i3.8xlarge",
      "unitPrice": 1.81,
      "totalSpend": 434.11,
      "idle": 0,
      "localCapacity": 7600,
      "localDrives": 4,
      "cpuCapacity": 32,
      "memoryCapacity": 244,
      "networkCapacity": 10000,
      "lastSeen": "2019-10-31T23:00:00Z",
      "tenancy" : "default",
      "hoursRunning": 240,
      "cpuMax": 6,
      "memoryMax": 6,
      "recommendations": [
        {
          "action": "Rightsize",
          "preferenceOrder": 1,
          "defaultsOrder": 1,
          "nodeType": "x1e.xlarge",
          "localCapacity": 120,
          "localDrives": 1,
          "cpuCapacity": 4,
          "memoryCapacity": 122,
          "previousGenTarget": false,
          "currentGen": true,
          "sameMemory": false,
          "sameFamily": false,
          "unitPrice": 0.83,
          "cpuRatio": 0.13,
          "memoryRatio": 0.5,
          "diskXPutCapacity": 100,
          "networkRatio": 1,
          "cpuRisk": 0,
          "memoryRisk": 0,
          "diskRisk": 0,
          "networkRisk": 0,
          "risk": 0,
          "savingsPct": 54,
          "savings": 233.95,
          "inDefaults": true,
          "memoryFit": false,
          "persistentStorageAdded": false,
          "snoozed": false
        }
      ],
      "defaultSameFamily": false,
      "defaultCurrentGen": true,
      "defaultMemoryFit": false
    }
  ]
```

Some Important Attributes

There are a few attributes worth a special mention

- risk : This is the graded risk for an individual recommendation. risk can take a value of 0,1,2,3,4 or 5. 0 implies that we expect the recommendation to have sufficient headroom for your resource without any clipping. 1 through 5 indicate increasing risk that performance could be affected. Note that there is a total risk score as well as individual ones for CPU, Network, Memory and Disk.
- rank : rank is based on a grouping system of risk and savings. The highest ranking recommendation will come from the cohort with lowest risk. From that cohort it will pick the one with the highest savings. The next in line ranking wise will come from the cohort with second lowest risk, and again highest savings. Rank is established as such by cycling through these risk cohorts until all recommendations as ranked. See special notes at bottom of page for extra ranking options.

Examples

Full List of 10-day Dataset EC2 Recommendations

```


curl "https://api.cloudability.com/v3/rightsizing/aws/recommendations/ec2?limit=5&maxRecsPerResource=1&offset=0&duration=ten-day" -u api-token:

```

Full List of 30-day Dataset EBS Recommendations

```


curl "https://api.cloudability.com/v3/rightsizing/aws/recommendations/ebs?limit=5&maxRecsPerResource=1&offset=0&duration=thirty-day" -u apikey:


```

Give Me Just the Default Recommendation per Resource

```


curl "https://api.cloudability.com/v3/rightsizing/aws/recommendations/ec2?rank=default&maxRecsPerResource=1&sort=-recommendations.savings" -u apikey:


```

Give Me All the Recommendations for a Particular Resource/Instance Id

```



curl "https://api.cloudability.com/v3/rightsizing/aws/recommendations/ec2?filters=resourceIdentifier==i-ae3f332111" -u apikey:


```

Give Me Recommendations Just for Specific Accounts

```




curl "https://api.cloudability.com/v3/rightsizing/aws/recommendations/ec2?limit=5&offset=0&vendorAccountIds=999988887777&maxRecsPerResource=1&basis=on-demand&duration=ten-day" -u apikey:


```

Filter My Recommendations Based on Tags

```



curl "https://api.cloudability.com/v3/rightsizing/aws/recommendations/ec2?filters=<tag_key>==<tag_value>" -u apikey:


```

Special Notes

To add another layer to this ranking system you can add rank=default as a query parameter. This will prioritize 2 extra attributes, memoryFit and currentGen before going through the risk/savings routine. currentGen for example would make sure that m4s (a current generation) would get recommended ahead of m1s (previous generation). Recommendations can be memoryFit through two different means 1) Cloudability has received the memory data and identified a fit or 2) Cloudability hasn't received the memory data so memoryFit will only include instance types which have matching memory or higher.

Snooze/Un-Snooze Recs

The following end points are used to snooze and un-snooze rightsizing recommendations for your cloud resources, where “{vendor}” should be substituted with the path of the cloud vendor’s end point and “{service}” should be substituted with the path of the service’s end point.

- Snooze: /rightsizing/{vendor}/recommendations/{service}/snooze

This either adds or updates snooze entries with the supplied expiration, as well as flips the snooze value for the resource recommendation to true.

The following values are specific to snooze/un-snooze:

- expiresOn (date) – The snooze Expiration Date in yyyy-mm-dd format, or the value "never" to set an indefinite snooze.
- resources (array) - A map of Account IDs to a list of Resource IDs for which recommendations will be snoozed.

Example: Snooze individual EC2 resources

```
curl -X POST https://api.cloudability.com/v3/rightsizing/AWS/recommendations/EC2/snooze \\
	 -H 'Content-Type: application/json' \\
	 -u '[auth_token]:' \\
	 -d @- 
{
	"expiresOn": "2024-11-24",
       "resources": { 
       "123456789": ["resource_12345", "resource_123456"],
       "111112222": ["resource_6789"]
}
}		
EOF	
```

Example: Snooze resources matching a filter

```
curl -X POST https://api.cloudability.com/v3/rightsizing/AWS/recommendations/EC2/snooze \\
	 -H 'Content-Type: application/json' \\
	 -u '[auth_token]:' \\
	 -d @- 
{
	"expiresOn": "never",
       "vendorAccountIds": [123456789, 111112222],
       "filters": [
       "region=ap-southeast-2",
       "tag_user_Environment=staging"
]
}		
```

• Un-Snooze: /rightsizing/{vendor}/recommendations/{service}/unsnooze.

Essentially, the same format as the snooze endpoint, but without an expiration. Removes any expiration, as well as flips the snooze value for resource recommendation to false.

Example: Un-snooze individual resources

```
curl -X POST https://api.cloudability.com/v3/rightsizing/AWS/recommendations/EC2/unsnooze \\
	 -H 'Content-Type: application/json' \\
	 -u '[auth_token]:' \\
	 -d @- 
{
	"resources": {
          "123456789": ["resource_12345", "resource_123456"],
          "111112222": ["resource_6789"]
       }
}
```

Example: Un-snooze resources matching a filter

```
curl -X POST https://api.cloudability.com/v3/rightsizing/AWS/recommendations/EC2/snooze \\
	 -H 'Content-Type: application/json' \\
	 -u '[auth_token]:' \\
	 -d @- 
{
       "vendorAccountIds": [123456789, 111112222],
       "filters": [
       "region=ap-southeast-2",
       "tag_user_Environment=staging"
]
}		
```

---

## Rightsizing ROI End Points

<!-- sub-header -->
- **breadcrumb:** Cloudability API > Rightsizing ROI End Points
- **source_path:** SSVCLNQ/api-v3/rightsizing-roi-end-points.html
- **original_file:** api-rightsizing-roi-end-points.md
- **images:** []

## Rightsizing ROI End Points

Last Updated: 2025-08-08

Summary

The Rightsizing ROI API provides the rightsizing ROI recommendation data for resources from supported services. Read more about Rightsizing ROI .

End Points

Rightsizing ROI offers two actions at the following endpoint: /rightsizing-roi/actioned ( https://api.cloudability.com/v3/rightsizing-roi/actioned )

Supported Actions:

- GET - retrieve a list of the tracked recommendations in Rightsizing ROI
- DELETE – Delete a desired ticket

GET Request Parameters

| Argument | Description |
| --- | --- |
| filter | Filter the tracked recommendations based on an attribute of your choice. Example: {{filters=vendorService==AWS S3 }} (filter by S3 tracked recommendations only) Example: filters=assignee==John Doe (filter by tracked recommendations assigned to John Doe) |
| limit | Used together with offset. Example: limit=10 (default = 50) |
| offset | Used together with limit. Example: offset=0 (default = 0) |
| sort | Sort the tracked recommendations based on an attribute of your choice. Example: {{sort=+resourceName }} (sort by tracked recommendations name ascending) Default: sort=-potentialSavings (sort tracked recommendations with highest savings potential descending) |
| viewId | The number of the View . If blank, the view will be your default view. |

Response Object

| Key | Description |
| --- | --- |
| actionTaken | The action taken on the resource. This will be null if no action has been taken yet. |
| dateActioned | The date the action was taken on the resource. This will be null if no action has been taken yet. |
| policyId | UUID indicating the Rightsizing Policy from which the tracked recommendation was generated. |
| orgId | Unique integer representing the organization. |
| ymd | Integer representing the year-month-day when an tracked recommendation was generated via an automated Rightsizing Policy run. Example: 20230821. This will be 0 if the recommendation was generated via any other method (i.e. by manual ticket creation from a policy run or individually via Rightsizing page). |
| timeline | The look back period in days, used for calculating the recommendations, either ten-day or thirty-day. |
| provider | The source provider of utilization data from which the recommendations were calculated, for example, NATIVE or DATADOG or NEWRELIC. |
| vendorAccountId | The unique identifier for the account the resource exists within. |
| resourceIdentifier | The unique identifier provided by the vendor for the resource. |
| resourceName | Name of the resource. Originates from the Name tag. |
| vendorService | String designating the vendor and service of the resource type: Example, AWS EC2, Azure Compute. |
| resourceType | The current resource type if no action has been taken yet. The actioned new resource type if an action has been taken. |
| recommendedResourceType | The current top recommended resource type. |
| prevResourceType | The original resource type when the tracked recommendation was created. This will be null if no action has been taken yet. |
| prevRecommendedResourceType | The original top recommended resource type when the tracked recommendation was created. This will be null if no action has been taken yet. |
| integrationType | The type of integration used by the tracked recommendation. |
| action | The recommended action to take: rightsize, terminate, autoscale. |
| potentialSavings | The amount that can potentially be saved by taking this recommendation. Once tracked, this value will become zero, signifying that an action has been taken and there is no further potential savings. |
| realizedSavings | Only when a resource type change has been detected, this value represents the savings over 30-days when switching from the original resource type to the new type we detected. |
| percentSavings | Savings as a percentage by moving to target type. |
| costSavings | Savings over the last 10 or 30 days if you had used the target type. |
| basis | The cost basis used. Values are on-demand or effective Default = on-demand Note: the effective cost basis is available for EC2 and RDS services. |
| projectKey | Project key defined by the integration provider, example: "TEST". |
| issueId | Issue ID defined by non-Native integration provider. Example 1000 for Jira integration type. Field is unused (empty string) for Native integration type. |
| issueKey | Key for the issue: Example: "TEST-123". Used by all integration provider types. |
| assignee | Name of assignee of the tracked recommendation. |
| assigneeId | If the assignee is a User in our database with an email address, then this is the ID for lookup. |
| status | Status of the ticket. For Native integration type, currently allowed values are: To Do, In Progress or Done. For Jira integration type, these are defined by the connection Jira instance. |
| resolution | Resolution state of the ticket. example: "Unresolved", "Won't Do", "Resolved". |
| createdAt | Date created. |
| resolvedAt | Date resolved. |
| lastSeenAt | Timestamp of the last time this resource appeared in the Rightsizing pipeline (used to detect resource termination). |

The meta object indicates the total number of tracked recommendations returned by the given request, as well as the aggregate (sum) of the potentialSavings and realizedSavings across the returned results.

```
"result": [
    {
      "policyId": "",
      "orgId": 123456,
      "ymd": 0,
      "timeline": "thirty-day",
	  "provider": "NATIVE",
	  "vendorAccountId": "1234567890",
	  "resourceIdentifier": "i-1234567890",
	  "resourceName": "test-audit",
	  "vendorService": "AWS EC2",
	  "resourceType": "r5.16xlarge",
	  "recommendedResourceType": "r5.8xlarge",
	  "prevResourceType": "",
	  "prevRecommendedResourceType": "",
	  "integrationType": "NATIVE",
	  "action": "RIGHTSIZE",
	  "potentialSavings": 725.22,
	  "realizedSavings": null,
	  "percentSavings": 64,
	  "costSavings": 725.22,
	  "basis": "on-demand",
	  "projectKey": "TEST",
	  "issueId": "",
	  "issueKey": "TEST-12",
	  "assignee": "Jane Doe",
	  "assigneeId": "129617",
	  "createdAt": "2023-08-14T22:19:19.259+00:00",
	  "lastSeenAt": "2023-07-05T21:00:00.000+00:00"
	},
	{
	  "policyId": "",
	  "orgId": 123456,
	  "ymd": 0,
	  "timeline": "ten-day",
	  "provider": "NATIVE",
	  "vendorAccountId": "0987654321",
	  "resourceIdentifier": "arn:aws:rds:us-west-2:0987654321:db:resource-test-0",
	  "resourceName": "resource-test-0",
	  "vendorService": "AWS RDS",
	  "resourceType": "db.r5.4xlarge",
	  "recommendedResourceType": "db.r5.4xlarge",
	  "prevResourceType": "",
	  "prevRecommendedResourceType": "",
	  "integrationType": "NATIVE",
	  "action": "TERMINATE",
	  "potentialSavings": null,
	  "realizedSavings": 487.2,
	  "percentSavings": 100,
	  "costSavings": null,
	  "basis": "on-demand",
	  "projectKey": "TEST",
	  "issueId": "",
	  "issueKey": "TEST-10",
	  "assignee": "John Doe",
	  "assigneeId": "71880",
	  "status": "Done",
	  "resolution": "Done",
	  "createdAt": "2023-03-29T15:13:11.952+00:00",
	  "resolvedAt": "2023-07-14T19:32:55.074+00:00",
	  "lastSeenAt": "2023-07-05T23:00:00.000+00:00"		
      "tagsMappings: [
        {
          "tagName": "tag_user_Environment",
          "vendorTagValue": "production"
        },
        {
          "tagName": "tag_user_Name",
          "vendorTagValue": "My EC2 Instance"
        }
      ],
      "availabilityZone": "ap-southeast-2b",
      "provider": "NATIVE"
      "region": "ap-southeast-2",
      "os": "Linux",
      "nodeType": "i3.8xlarge",
      "unitPrice": 1.81,
      "totalSpend": 434.11,
      "idle": 0,
      "localCapacity": 7600,
      "localDrives": 4,
      "cpuCapacity": 32,
      "memoryCapacity": 244,
      "networkCapacity": 10000,
      "lastSeen": "2019-10-31T23:00:00Z",
      "tenancy" : "default",
      "hoursRunning": 240,
      "cpuMax": 6,
      "memoryMax": 6,
      "recommendations": [
        {
          "action": "Rightsize",
          "preferenceOrder": 1,
          "defaultsOrder": 1,
          "nodeType": "x1e.xlarge",
          "localCapacity": 120,
          "localDrives": 1,
          "cpuCapacity": 4,
          "memoryCapacity": 122,
          "previousGenTarget": false,
          "currentGen": true,
          "sameMemory": false,
          "sameFamily": false,
          "unitPrice": 0.83,
          "cpuRatio": 0.13,
          "memoryRatio": 0.5,
          "diskXPutCapacity": 100,
          "networkRatio": 1,
          "cpuRisk": 0,
          "memoryRisk": 0,
          "diskRisk": 0,
          "networkRisk": 0,
          "risk": 0,
          "savingsPct": 54,
          "savings": 233.95,
          "inDefaults": true,
          "memoryFit": false,
          "persistentStorageAdded": false
		}
	],
	"meta": {
		"totalCount": 2,
		"aggregates": [
		    {
				"potentialSavings": 725.22,
				"realizedSavings": 487.2
			}
		]
	}
}

```

DELETE Request parameters

| Argument | Description |
| --- | --- |
| orgId | Unique integer representing the organization. |
| ResourceId | The unique resource identifier that the ticket you want to delete is associated with |

Response Object

| Response | Description |
| --- | --- |
| 204 | Ticket successfully deleted, no content returned. |
| 400 | Bad Request |
| 404 | Item not found |
| 500 | Internal Server Error |

---

## Scorecards End Point

<!-- sub-header -->
- **breadcrumb:** Cloudability API > Scorecards End Point
- **source_path:** SSVCLNQ/api-v3/scorecards_end_point.html
- **original_file:** api-scorecards-end-point.md
- **images:** []

## Scorecards End Point

Summary

The Scorecards API end point can be used to retrieve your scorecard outlined in Scorecards KB .

- This end point does not support filtering and sorting.

End Point Particulars

end point : /scorecards for listing your organization's scorecard.

The Scorecards Object

The scorecards object has two blocks. In the main block, we show aggregate statistics for any spending within the scope of the supplied view as well as the grouping dimension. In the records block, we show scores for each individual business unit, as determined by the grouping dimension.

- Rightsizing Score - Measures how well you've matched the size of a resource to the workload
- Elasticity Score - Measures how well you are turning resources on and off in response to changing demand
- Pricing Score - Measures how well you're taking advantage of different purchasing options (including Spot and Reserved Instances) to pay the best possible price for a given resource
- The Overall Score combines these three components to give you a single metric measuring your overall cloud efficiency.

Example Scorecards Object

```
 {
  "result": {
    "dimensionKey": "group_name3",
    "elasticityScore": 0.7623178861,
    "overallScore": 0.63841755,
    "percentile": 0.5756578947,
    "pricingScore": 0.9395323124,
    "records": [
      {
        "dimensionValue": "cogs",
        "elasticityScore": 0.7187018801,
        "overallScore": 0.587071348,
        "pricingScore": 0.9614329474,
        "rightsizingScore": 0.2928227895,
        "totalSpend": 17472.9354800001
      },
      {
        "dimensionValue": "(not set)",
        "elasticityScore": 0.8770809734,
        "overallScore": 0.7298704459,
        "pricingScore": 0.8078440667,
        "rightsizingScore": 0.5487444058,
        "totalSpend": 4564.827239
      }
    ],
    "rightsizingScore": 0.3633010232,
    "totalSpend": 22037.7627189998
  }
}
```

Example Request - Retrieve a Scorecard

Perform a GET request at the /scorecards end point, specifying a viewId and dimension.

```
curl "https://api.cloudability.com/v3/scorecards?dimension=category4&duration=ten-day&viewId=0" \\
     -u ‘[auth_token]:’
```

---

## Snowflake End Points

<!-- sub-header -->
- **breadcrumb:** Cloudability API > Snowflake End Points
- **source_path:** SSVCLNQ/api-v3/snowflake_public_api.html
- **original_file:** api-snowflake-end-points.md
- **images:** []

## Snowflake End Points

Summary

These end points are used to manage credentials within Cloudability that support the integration and ingestion of Snowflake data.

With Cloudability being available in multiple regions, all references to api.cloudability.com in this API documentation should be referred to as mentioned in Getting started with Cloudability API V3 .

End Point Particulars

end point : /v3/vendors/snowflake/accounts for RESTful CRUD interactions

end point : /v3/vendors/snowflake/accounts?include=permissions&viewId=0

end point : /v3/vendors/snowflake/accounts/<account_id>?include=permissions&viewId=0

end point : /v3/vendors/snowflake/accounts/<account_id>?viewId=0

end point : /v3/vendors/snowflake/accounts/<account_id>/verification?include=permissions,associatedAccounts&viewId=0

end point : /v3/vendors/snowflake/accounts/<account_id>/terraform-template

end point : /v3/vendors/snowflake/accounts/<account_id>/archive?viewId=0

end point : /v3/vendors/snowflake/permissions/accounts/<account_id>

Parameters

- vendorAccountID (string) - account id of snowflake
- type (string) - “snowflake_user”
- accountName (string) - account name
- warehouseName (string) - snowflake warehouse name
- databaseName (string) - database name
- userName (string) - snowflake user name
- orgName (string) - org name
- subscriptionModel (string) - “Direct” | “Marketplace”
- dependentCsp (string) - “AWS” | “AZURE” | “GCP”, should be passed only when subscriptionModel is set to “Marketplace”

List Accounts

Example Request

```
curl 'https://api.cloudability.com/v3/vendors/snowflake/accounts?viewId=0' \\ 
   -u ‘[auth_token]:’ 
```

```
{ 
"result": [ 
{ 
"id": "account-id-1", 
"vendorAccountName": "account-name", 
"vendorAccountId": "account-id-1", 
"vendorKey": "snowflake", 
"verification": { 
"state": "verified", 
"lastVerificationAttemptedAt": "2026-02-07T05:14:13Z" 
}, 
"authorization": { 
"type": "snowflake_user", 
"permissions": [ 
"snowflake.get.costReports", 
"snowflake.get.warehouse.cost", 
"snowflake.list.accounts" 
], 
"subscriptionModel": "Marketplace", 
"dependentCsp": "AWS", 
"orgName": "Org_Name", 
"accountName": "AAA11111", 
"warehouseName": "CLDY_CANVAS_WNAME", 
"databaseName": "CLDY_CANVAS_DB_NAME", 
"userName": "CLDY_CANVAS_USER_NAME" 
}, 
"createdAt": "2025-12-10T09:39:08Z", 
"consumerOrgId": "", 
"byodVendor": "ABSENT" 
}, 
{ 
"id": "BA11111", 
"vendorAccountName": "CPROD_IN", 
"vendorAccountId": "BA11111", 
"vendorKey": "snowflake", 
"meta": {}, 
"parentAccountId": "account-id-1", 
"consumerOrgId": "" 
} 
] 
}  
```

Create Master Payer account

POST /v3/vendors/snowflake/accounts?viewId=0

This API is used for creating a new Snowflake credential

Example Request

```
curl -X POST 'https://api.cloudability.com/v3/vendors/snowflake/accounts?viewId=0\\ 
-H 'Content-Type: application/json' \\ 
-u ‘[auth_token]:’ \\ 
-d @- << EOF 
{ 
"type": "snowflake_user", 
"accountName": "Account_Name", 
"warehouseName": "Warehous_Name", 
"databaseName": "DB_Name", 
"userName": "User_Name", 
"orgName": "Org_Name", 
"subscriptionModel": "Marketplace", 
"dependentCsp": "AZURE" 
}        
```

Upon successful creation the API will return the credentials object.

Update Master Payer account

PUT /v3/vendors/snowflake/accounts/<account_id>?include=permissions&viewId=0

```
curl -X PUT 'https://api.cloudability.com/v3/vendors/snowflake/accounts/<account_id>?viewId=0\\ 
-H 'Content-Type: application/json' \\ 
-u ‘[auth_token]:’ \\ 
-d @- << EOF 
{ 
"type": "snowflake_user", 
"accountName": "AAA11111", 
"warehouseName": "CLDY_CANVAS_WNAME", 
"databaseName": "CLDY_CANVAS_DB_NAME", 
"userName": "CLDY_CANVAS_USER_NAME", 
"orgName": "ORG_NAME", 
"subscriptionModel": "Marketplace", 
"dependentCsp": "AWS" 
} 
```

Retrieve Account

GET /v3/vendors/snowflake/accounts/<account_id>?viewId=0

Example Request

```
curl 
'https://api.cloudability.com/v3/vendors/snowflake/accounts/<account_id>’\\ 
-u ‘[auth_token]:’
```

Delete Credential for Account

DELETE /v3/vendors/snowflake/accounts/<account_id>?viewId=0

Example Request

```
Curl -X DELETE 
'https://api.cloudability.com/v3/vendors/snowflake/accounts/<account_id>?viewId=0\\ 
-u ‘[auth_token]:’ 
```

Verify Credential for Account

POST v3/vendors/snowflake/accounts/<account_id>/verification?include=permissions,associatedAccounts&viewId=0

```
curl --X POST 
'https://api.cloudability.com/v3/vendors/snowflake/accounts/<account_id>/verification?include=permissions,associatedAccounts&viewId=0’\\ 
-u ‘[auth_token]:’ 
```

Get setup script for Account

GET /v3/vendors/snowflake/accounts/<account_id>/setup-scripts

Example Request

```
curl 
'https://api.cloudability.com/v3/vendors/snowflake/accounts/<account-id>/setup-scripts?viewId=0 
-u ‘[auth_token]:’ 
```

Archive Account

POST /v3/vendors/snowflake/accounts/<account_id>/archive?viewId=0

Example Request

```
curl --X POST 
'https://api.cloudability.com/v3/vendors/snowflake/accounts/<account_id>archive?viewId=0’\\ 
-u ‘[auth_token]:’ 
```

Get Permissions for Account

GET /v3/vendors/snowflake/permissions/accounts/<account_id>\

Example Request

```
curl --X GET 
'https://api.cloudability.com/v3/vendors/snowflake/permissions/accounts/<account_id>’ 
\\ 
-u ‘[auth_token]:’ 
```

---

## User Groups and Entra ID Groups End Point

<!-- sub-header -->
- **breadcrumb:** Cloudability API > User Groups and Entra ID Groups End Point
- **source_path:** SSVCLNQ/api-v3/user_entraid_groups_end_points.html
- **original_file:** api-user-groups-entra-id-groups-end-point.md
- **images:** []

## User Groups and Entra ID Groups End Point

### Summary

The User Groups and Entra ID Groups APIs can be used for all key tasks as it pertains to managing User Groups and Entra ID Groups , including retrieving group containers, listing groups, managing users, and syncing with Entra ID (aka Azure AD).

List of User Groups APIs

1. Get User Groups Container ID
1. Get User Groups by ID
1. Get User Count for a User Group
1. Get list of Users in a User Group
1. Get All Users Assigned to User Groups
1. Create a New User Group
1. Assign Users to a User Group
1. Delete a User Group

List of Entra ID Groups APIs

1. Get Entra ID Groups Container ID
1. Get Entra ID Groups by ID
1. Get User Count for an Entra ID Group.
1. Get list of Users in an Entra ID Group.
1. Get All Users assigned to Entra ID Group
1. Delete an Entra ID Group
1. Sync Entra ID Groups

### User Groups APIs

Endpoint :

```
GET https://api.cloudability.com/v3/api/groups?type=CLDY
```

Description :

Fetches the container ID for User Groups. This ID is required for all other User Group API operations.

Response Fields:

- id (UUID) – Unique identifier of the User Groups container.
- label (string) – Customer-defined label.
- type (string) – Always CLDY for User Groups.
- version (integer) – Version number of the container.

Sample Response:

```
[
  {
    "id": "8f6e56b0-4b55-4fa4-9a9a-11111abcd123",
    "label": "Apptio_usergroups",
    "type": "CLDY",
    "version": 1
  }
]
```

2. Get User Groups by ID

Endpoint:

```
GET https://api.cloudability.com/v3/api/groups/{groupsId}/units/list
```

Description:

This API returns a list of user groups. You need to provide the groupId obtained from the User Groups Container Id API as a parameter.

Response Fields:

- id (UUID) – User Group ID.
- orgHierarchyId (UUID) – User Group Container ID.
- type (string) – Always CUSTOMER_ORG for User Groups.
- label (string) – Name of the user group.
- level (integer) – Group hierarchy level.
- version (integer) – Version number.
- provisioningStatus (string) – Provisioning state ( NA if not applicable).
- cldyAccess (string) – Access type ( NA if not applicable).
- pricingType (string) – Pricing type ( NA if not applicable).
- properties (array) – Additional properties (if any).
- createdOn (float, epoch time) – Creation timestamp.
- updatedOn (float, epoch time) – Last updated timestamp.

Sample Response:

```

[
  {
    "id": "f2c41a02-9b3c-489f-b47d-00001abcd",
    "orgHierarchyId": "8f6e56b0-4b55-4fa4-9a9a-11111abcd123",
    "type": "CUSTOMER_ORG",
    "label": "VH-Grp-grpTest",
    "level": 1,
    "version": 2,
    "provisioningStatus": "NA",
    "cldyAccess": "NA",
    "pricingType": "NA",
    "properties": [],
    "createdOn": 1741064088.712111,
    "updatedOn": 1745992181.867502
  }
]
```

3. Get User Count for a User Group

Endpoint:

```
GET https://api.cloudability.com/v3/api/groups/{groupsId}/units/users/count
```

Description:

This API returns the total number of users assigned to a specific user group.

- groupsId passed in the request is the ID from the User Groups Container Id API.

Response Fields:

- orgHierarchyUnitId (UUID) – User Group ID.
- orgHierarchyLabel (string) – User Group name.
- userCount (integer) – Number of users in the group.

Sample Response:

```

[
  {
    "orgHierarchyUnitId": "f2c41a02-9b3c-489f-b47d-00001abcd",
    "orgHierarchyLabel": "Sq1 User Group",
    "userCount": 3
  }
]
```

4. Get list of Users in a User Group

Endpoint:

```
GET https://api.cloudability.com/v3/api/groups/{groupId}/units/{groupUnitId}/users?pageNumber=2&pageSize=10
```

Description:

This API fetches all users belonging to a specific user group.

- groupsID parameter provided in the request is the ID obtained from the User Groups Container Id API, and groupsUnitId is the ID of the user group.

- pageNumber and pageSize parameters are optional. Default value of pageNumber is 1, and the default value of pageSize is 10.

Response Fields:

- registeredUserId (string) – Frontdoor ID of a User.
- userId (string) – External User ID (AD Groups ID).
- email (string) – Email address.
- pagination (object) – Contains paging info.

Sample Response:

```

{
  "data": [
    {
      "registeredUserId": "b3a2-user-az123",
      "userId": "ext-user-001",
      "email": "user@example.com"
    }
  ],
  "pagination": {
    "pageNumber": 1,
    "pageSize": 10,
    "totalCount": 1,
    "totalPages": 1
  }
}
```

5. Get All Users Assigned to User Groups

Endpoint:

```
GET https://api.cloudability.com/v3/api/registered-users
```

Description:

This API retrieves the list of all users who are members of at least one user group, along with all the groups each user belongs to.

We need to map the users with individual user group for the response of this API.

Response Fields:

- registeredUserId (string) – Frontdoor ID of a User.
- userId (string) – External User ID (AD Groups ID) .
- email (string) – User email address.
- orgHierarchyUnitIds (array of UUIDs) – IDs of User Groups the user belongs to.

Sample Response:

```

{
  "registeredUserId": "fd-usr-8890",
  "userId": "b3a2-user-az123",
  "email": "user@example.com",
  "orgHierarchyUnitIds": [
    "f2c41a02-9b3c-489f-b47d-00001abcd",
    "c7d8bb22-35cd-4561-aaa9-99999xyz"
  ]
}
```

6. Create a New User Group

Endpoint:

```
POST https://api.cloudability.com/v3/api/groups/units/
```

Description:

This API is used to create a new user group by providing the required group details.

Request Body:

```

{
  "label": ["Test"]
}
```

Response Fields:

- alreadyRegisteredUnits (array) – Groups already existing.
- successfullyCreatedUnits (array) – Groups created successfully.

Sample Response:

```

{
  "alreadyRegisteredUnits": [],
  "successfullyCreatedUnits": ["Test"]
}
```

7. Assign Users to a User Group

Endpoint:

```
POST https://api.cloudability.com/v3/api/groups/{groupsId}/units/users
```

Description:

This API assigns users to a user group.

- groupId parameter provided in the request is the ID obtained from the User Groups Container Id API .

Request Body:

```

{
  "unitIds": ["f2c41a02-9b3c-489f-b47d-00001abcd"],
  "updatedUnitName": "",
  "addedUsers": [
    {
      "userId": "usr-12345",
      "email": "user@example.com"
    }
  ],
  "removedUsers": []
} 
```

Sample Response:

```

[
  {
    "registeredUserId": "usr-12345",
    "message": "User is successfully mapped to org hierarchy unit (f2c41a02-9b3c-489f-b47d-00001abcd)",
    "statusCode": 200
  }
]
```

8. Delete a User group

Endpoint:

```
DELETE https://api.cloudability.com/v3/api/groups/{groupsId}/units/{groupsUnitId}
```

Description:

This API deletes a user group.

- groupsID parameter provided in the request is the ID obtained from the User Groups Container Id API, and groupsUnitId is the ID of the user group.

### Entra ID Groups APIs

1. Get Entra ID Groups Container ID

Endpoint:

```
GET https://api.cloudability.com/v3/api/groups?type=USER_GROUPS
```

Description:

This API fetches the container ID for Entra ID Groups, which is required for all other Entra ID Group API operations. Since Entra IDs are tied to a container, fetching the container ID is a prerequisite to perform subsequent Entra ID operations.

Response Fields:

- id (UUID) – Unique identifier of the Entra ID container.
- label (string) – Customer-defined label.
- type (string) – Always USER_GROUPS for Entra IDs.
- version (integer) – Version of the container.

Sample Response:

```

[
  {
    "id": "7ca20dd3-d45e-4332-b87f-a9683b107e95",
    "label": "Apptio_entraIds",
    "type": "USER_GROUPS",
    "version": 1
  }
]
```

2. Get Entra ID Groups by ID

Endpoint:

```
GET https://api.cloudability.com/v3/api/groups/{groupsId}/units/list
```

Description:

This API returns a list of Entra ID groups. You need to provide the groupId obtained from the Entra ID Groups Container Id API as a parameter.

Response Fields:

- id (UUID) – Unique identifier of an Entra ID.
- orgHierarchyId (UUID) – Container ID returned by Get Entra IDs Container ID API.
- type (string) – Always AD_GROUP for Entra IDs.
- label (string) – Name of the Entra ID group.
- level (integer) – Hierarchy level of the group.
- version (integer) – Version of the group.
- provisioningStatus (string) – Status of provisioning ( NA if not applicable).
- cldyAccess (string) – Access type ( NA if not applicable).
- pricingType (string) – Pricing type ( NA if not applicable).
- properties (array) – Additional metadata.
- createdOn (float, epoch time) – Timestamp when the Entra ID was created.
- updatedOn (float, epoch time) – Timestamp of last update.

Sample Response:

```

{
  "id": "aee80182-1457-43ce-99c6-7ab80b982420",
  "orgHierarchyId": "7ca20dd3-d45e-4332-b87f-a9683b107e95",
  "type": "AD_GROUP",
  "label": "Cloudability_test",
  "level": 1,
  "version": 1,
  "provisioningStatus": "NA",
  "cldyAccess": "NA",
  "pricingType": "NA",
  "properties": [],
  "createdOn": 1751950837.279712,
  "updatedOn": 1751950837.279712
}
```

3. Get User Count for an Entra ID Group

Endpoint:

```
GET https://api.cloudability.com/v3/api/groups/{groupsId}/units/users/count
```

Description:

This API returns the total number of users assigned to an Entra ID group.

- groupsId passed in the request is the ID from the Get Entra ID Groups Container Id API.

Response Fields:

- orgHierarchyUnitId (UUID) – Unique ID of the Entra ID group.
- orgHierarchyLabel (string) – Name of the Entra ID group.
- userCount (integer) – Total number of users in the group.

Sample Response:

```

[
  {
    "orgHierarchyUnitId": "aee80182-1457-43ce-99c6-7ab80b982420",
    "orgHierarchyLabel": "cldy-test",
    "userCount": 3
  }
]
```

4. Get list of Users in an Entra ID Group

Endpoint:

```
GET https://api.cloudability.com/v3/api/groups/{groupId}/units/{groupUnitId}/users?pageNumber=2&pageSize=10
```

Description:

This API fetches all users belonging to a specific entra ID group.

- groupsID parameter provided in the request is the ID obtained from tthe Get Entra ID Groups Container Id API, and groupsUnitId is the ID of the entra ID group.
- pageNumber and pageSize parameters are optional. Default value of pageNumber is 1, and the default value of pageSize is 10.

Response Fields:

- registeredUserId (string) – Frontdoor ID of a User.
- userId (string) – External User ID (AD Groups ID).
- email (string) – Email address.
- pagination (object) – Contains paging info.

Sample Response:

```

{
  "data": [
    {
      "registeredUserId": "b3a2-user-az123",
      "userId": "ext-user-001",
      "email": "user@example.com"
    }
  ],
  "pagination": {
    "pageNumber": 1,
    "pageSize": 10,
    "totalCount": 1,
    "totalPages": 1
  }
}
```

5. Get All Users assigned to Entra ID Group

Endpoint:

```
GET https://api.cloudability.com/v3/api/registered-users
```

Description:

This API retrieves the list of all users who are members of at least one Entra ID group, along with all the Entra ID groups each user belongs to.

Response Fields:

- registeredUserId (string) – Frontdoor ID of a User.
- userId (string) – External User ID (AD Groups ID).
- email (string) – User’s email address.
- pagination (object) – Metadata for paginated results: pageNumber (integer) – Current page number. pageSize (integer) – Number of results per page. totalCount (integer) – Total number of users returned. totalPages (integer) – Number of pages available.

Sample Response:

```

{
  "data": [
    {
      "registeredUserId": "az-user-101",
      "userId": "fd-user-202",
      "email": "user@company.com"
    }
  ],
  "pagination": {
    "pageNumber": 1,
    "pageSize": 3,
    "totalCount": 3,
    "totalPages": 1
  }
}
```

6. Delete an Entra ID Group

Endpoint:

```
DELETE https://api.cloudability.com/v3/api/groups/{groupsId}/units/{groupsUnitId}
```

Description:

This API deletes a Entra ID group.

- groupsId parameter provided in the request is the ID obtained from the User Groups Container Id API, and groupsUnitId is the ID of the user group.

Parameters:

- groupsId (UUID) – Container ID from Get Entra IDs Container ID API.
- groupsUnitId (UUID) – Unique ID of the Entra ID to delete.

7. Sync Entra ID Groups

Endpoint:

```
POST https://api.cloudability.com/v3/api/groups/import?type=AD_GROUPS
```

Description:

This API syncs Entra IDs with Entra ID groups (aka Azure AD groups) based on the scope and filter criteria provided in the parameters.

Request Body:

Parameters:

- hierarchyType (string) - Always “USER_GROUPS“ for Entra ID Group sync.
- scope (string) - scope can be CONTAINS, PREFIX, SUFFIX
- filter (string) - any search string.

```

{
    "hierarchyType": "USER_GROUPS",
    "filterCriteria": {
        "scope":"CONTAINS",
        "filter": "cldy"
    }
}
```

---

## Users End Point

<!-- sub-header -->
- **breadcrumb:** Cloudability API > Users End Point
- **source_path:** SSVCLNQ/api-v3/users-end-point.html
- **original_file:** api-users-end-point.md
- **images:** []

## Users End Point

Summary

While user CRUD actions are now managed in Apptio's Frontdoor API , Cloudability administrators can still retrieve a list of their users and update users’ default views, and view shares through the Cloudability V3 Users API. To use this endpoint you must have the UserManagementFeatureFullAccess permission.

- This document defines the API for fetching/updating Users in Cloudability.
- The all user endpoint retrieves all users based on provided filters, pagination, and sorting parameters.
- All endpoints return data using a unified User Object Schema.
- All endpoints require a valid Bearer token for authentication.

End Point Particulars

Base URL:

```
https://api.cloudability.com/v3
```

All endpoints require a valid bearer token.

| Header | Required | Description |
| --- | --- | --- |
| Header | Required | Description |
| Authorization | ✅ | Bearer token for authentication |
| Content-Type | ✅ | application/json |

| Operation | Method | Endpoint |
| --- | --- | --- |
| Operation | Method | Endpoint |
| Get Details of a User | GET | /v3/users/{userId} |
| Get All Users | GET | /v3/users |
| Update a User | PUT | /v3/users/{userId} |

User Object Schema

This object is returned by multiple endpoints such as Get User , all Users , and Update User .

| Field | Type | Description |
| --- | --- | --- |
| Field | Type | Description |
| id | integer | The Unique Identifier of the User object. |
| frontdoor_user_id | string | The Frontdoor user UUID, a unique identifier for the user in a given Frontdoor environment. |
| frontdoor_login | string | The user’s Frontdoor login, a unique identifier for the user in a given Frontdoor environment. |
| email | string | The user’s Frontdoor email address. |
| full_name | string | The full name of the user as it will appear in user lists. |
| default_dimension_filter_set_id | integer | The default view ID linked to the user. It specifies which view is automatically loaded when the user launches the application. |
| shared_dimension_filter_set_ids | array[integer] | A list of view IDs accessible to the user, including views shared directly with the user or with the organization. |

Example User Object

```
{
   "id": 1,
   "frontdoor_user_id": "33ab2211-2b2b-4411-ee99-d90v98475n", 
   "frontdoor_login": "john@cloudability.com",
   "email": "john@cloudability.com",
   "full_name": "John Doe",
   "default_dimension_filter_set_id": null,
   "shared_dimension_filter_set_ids": [
        12,
        999,
        3646
    ]
}
```

### Get Details of a User

```
GET /v3/users/{userId}
```

Retrieves detailed information about a specific user.

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| Parameter | Type | Required | Description |
| userId | integer | ✅ | ID of requesting user |

Returns a single User Object

Example Request :

```
curl --location 'https://api.cloudability.com/v3/users/240772' \
--header 'accept: application/json, text/plain, */*' \
--header 'authorization;' \
```

Example Response:

```
{
   "id": 1,
   "frontdoor_user_id": "33ab2211-2b2b-4411-ee99-d90v98475n", 
   "frontdoor_login": "john@cloudability.com",
   "email": "john@cloudability.com",
   "full_name": "John Doe",
   "default_dimension_filter_set_id": null,
   "shared_dimension_filter_set_ids": [
        12,
        999,
        3646
    ]
}
```

### Getting List of Users

```
GET /v3/users
```

Retrieve List of all users in your Organization.

| Parameter | Type | Description |
| --- | --- | --- |
| Parameter | Type | Description |
| include_pagination_details | bool | Include pagination metadata (like total count, total pages) in response. |
| limit | int | Number of users to return per page if include_pagination_details is true |
| offset | int | Number of users to skip before starting to collect results. |
| sort_field | string | Field to sort users by. Allowed values: user_full_name, role_key, invitation_state. |
| sort_direction | string | Sorting order. Allowed values: asc, desc. |
| search | string | Search users by name or email. |

Returns an array of User Object

Example Request :

```
curl --location 'https://api.cloudability.com/v3/users' \
--header 'accept: application/json, text/plain, */*' \
--header 'authorization;' \
```

Example Response:

```
[
  {
   "id": 1,
   "frontdoor_user_id": "33ab2211-2b2b-4411-ee99-d90v98475n", 
   "frontdoor_login": "john@cloudability.com",
   "email": "john@cloudability.com",
   "full_name": "John Doe",
   "default_dimension_filter_set_id": 12,
   "shared_dimension_filter_set_ids": [
        12,
        999,
        3646
    ]
  }
  {
   "id": 123,
   "frontdoor_user_id": "22dd2222-2b2b-4444-ee99-d90v9847an", 
   "frontdoor_login": "lisa@cloudability.com",
   "email": "lisa@cloudability.com",
   "full_name": "Lisa Smith",
   "default_dimension_filter_set_id": 999,
   "shared_dimension_filter_set_ids": [
        12,
        999,
        4646
    ]
  }
]
```

### Update User

```
PUT /v3/users/{userId}
```

Updates the specific attributes of a user. This includes modifying role, restriction state, default dashboard and the list of shared view IDs accessible to the user.

All other user attributes must be managed via Access Administration . While a user’s name can be changed within Cloudability, be aware that any changes made to a name here will not be synchronize with Access Administration .

Path & Request Body

| Parameter | Type | Description |
| --- | --- | --- |
| Parameter | Type | Description |
| userId | integer | ID of the user to update. |
| user | object mentioned below | Wrapper object containing user update details. |

| Parameter | Type | Description |
| --- | --- | --- |
| Parameter | Type | Description |
| id | integer | Unique ID of the user to update (path parameter). |
| full_name | string | Full name of the user. |
| role | string | Role assigned to the user. Allowed values: Administrator, User. |
| unshare_existing_dimension_filter_sets | bool | If true, removes all previously shared filter sets before applying new ones. |
| restricted | bool | Restricts user access to specific resources. |
| new_shared_dimension_filter_set_ids | array[integer] | List of new view IDs to share with this user. |
| shared_dimension_filter_set_ids | array[integer] | Current list of shared dimension filter set IDs. |
| default_dimension_filter_set_id | integer | Default view/filter set ID associated with the user. |
| default_dashboard_id | integer | Default dashboard ID for the user. |

Returns the updated User Object reflecting all modified fields.

Example Request :

```
curl –X PUT https://api.cloudability.com/v3/users/1 \\
     -H ‘Content-Type: application/json’ \\
     -u ‘[auth_token]:’ \\
     -d @- << EOF
{
     "full_name": "Joan Doe",
     "default_dashboard_id": 345,
     "default_dimension_filter_set_id": 12,
     "new_shared_dimension_filter_set_ids": [12, 999]
}
EOF
```

(Replace the value 1 in the example with the unique ID of your user.)

Example Request - To remove All User View Shares

```
curl –X PUT https://api.cloudability.com/v3/users/1 \\
     -H ‘Content-Type: application/json’ \\
     -u ‘[auth_token]:’ \\
     -d @- << EOF
{
     "full_name": "Joan Doe",
     "default_dimension_filter_set_id": 1,
     "unshare_existing_dimension_filter_sets": true,
     "new_shared_dimension_filter_set_ids": []
}
EOF
```

(Replace the value 1 in the example with the unique ID of your user.)

---

## Utilization Reports End Point

<!-- sub-header -->
- **breadcrumb:** Cloudability API > Utilization Reports End Point
- **source_path:** SSVCLNQ/api-v3/utilization_reports_end_point.html
- **original_file:** api-utilization-reports-end-point.md
- **images:** []

## Utilization Reports End Point

The utilization reports endpoints are used to analyze utilization patterns for AWS EC2 instances. Utilization Analytics uses data from AWS Cloudwatch which presents instance-level details such as Average CPU utilization (percent), Bandwidth, and Disk I/O. Utilization analytics are great for visualizing overall elasticity and whether your instances require rightsizing or need to be turned off.

Cost metrics that are made available in Utilization Analytics are calculated in Cloudability using on-demand rates and cover only the compute portion of your bill (i.e., the billable instance hours but not bandwidth, storage, and etc.). As such, they should be used for trending only, not financial reporting. Note that the metric is referred to as Cost (Estimated).

Note that in order for Utilization Analytics to access utilization data, advanced credentialing needs to be in place on respective member accounts which will put in place proper IAM permissions.

Flexible filtering, sorting, and measure (dimensions and metrics) selection is available to craft results to meet specific reporting needs. As a recommended guideline, there is a max of 15 dimensions and 10 metrics that can be added to an API call. By default, results are returned in JSON. To get results in CSV format make sure to set the Accept header with a value of text/csv. Note that pagination is implemented when results exceed 10,000 rows, as described below. Example report calls are provided towards the bottom of this document.

Utilization Report End Point

- /reporting/reports/util for listing current utilization reports
- /reporting/util/run for executing utilization reports
- /reporting/util/measures for listing available utilization reporting measures
- /reporting/util/filters for listing available comparison operators used in filters
- /reporting/util/enqueue for enqueuing util reports
- /reporting/reports/:id/state for checking the state of enqueued reports
- /reporting/reports/:id/results for retrieving finished enqueued reports

The Utilization Report Object

- results (array) - list of utilization row objects, each row comprised of reported dimensions and metrics
- meta (object) - object containing meta information about the report that was run dates (object) - start and end date strings marking the date range of the report filters (array) - list of filters applied to report with detailed information metrics (array) - list of metrics returned in report with detailed information dimensions (array) - list of dimensions returned in report with detailed information aggregates (array) - list of aggregated metrics with detailed information for report offset (number) - Position where to start for the results. Default is 0 limit (number) - Maximum number of utilization rows that can be returned total_results (number) - Total utilization rows returned for executed report

Example Utilization Report Object (Review Example)

```
{
  "results": [
    {
      "instance_identifier": "i-1237aa0e1587577f5",
      "max_cpu_utilization": "0.91925"
    },
    {
      "instance_identifier": "i-0007aa0e1587572c7",
      "max_cpu_utilization": "0.179183"
    }
  ],
  "meta": {
    "dates": {
      "start": "2022-08-30T00:00:00Z",
      "end": "2022-08-30T00:00:00Z"
    },
    "filters": [],
    "metrics": [
      {
        "name": "max_cpu_utilization",
        "label": "CPU Utilization (Max)",
        "description": "The maximum percentage of CPU Utilization...
        "data_type": "percentage",
        "type": "metric",
        "group": {
          "ID": 9,
          "Key": "compute",
          "Name": "Compute"
        },
        "sub_group": {
          "ID": 12,
          "Key": "processing",
          "Name": "Processing"
        }
      }
    ],
    "dimensions": [
      {
        "name": "instance_identifier",
        "label": "Instance ID",
        "description": "The ID associated with a particular AWS instance.",
        "data_type": "string",
        "type": "dimension",
        "group": {
          "ID": 9,
          "Key": "compute",
          "Name": "Compute"
        },
        "sub_group": {
          "ID": 1,
          "Key": "common",
          "Name": "Common"
        }
      }
    ],
    "aggregates": [
      {
        "name": "max_cpu_utilization",
        "label": "CPU Utilization (Max)",
        "description": "The maximum percentage of CPU Utilization...",
        "data_type": "percentage",
        "type": "metric",
        "value": "0.91925"
      }
    ]
  },
  "offset": 0,
  "limit": 2,
  "total_results": 2
}
```

List Current Utilization Reports

Retrieve a list of utilization reports either owned by or shared with the user or org.

```
curl 'https://api.cloudability.com/v3/reporting/reports/util' -u '[auth_token]:'
```

Example Response

```
[
 {
  "id": 1,
  "author": {
  "id": 12345,
  "safe_name": "Test User"
  },
  "category": "Utilization",
  "custom": true,
  "description": "The number of instances running during each hour of the day over the last 7 days.",
  "dimensions": [
  {
  "name": "date",
  "label": "Date",
  "description": "The calendar date (e.g. YYYY-MM-DD).",
  "data_type": "date",
  "type": "dimension",
  "group": {
  "id": 9,
  "key": "compute",
  "name": "Compute"
  },
  "sub_group": {
  "id": 2,
  "key": "time",
  "name": "Time"
  }
   },
  {
  "name": "hour",
  "label": "Hour",
  "description": "The numeric hour of the day (e.g. 1pm => 13).",
  "data_type": "integer",
  "type": "dimension",
  "group": {
  "id": 9,
  "key": "compute",
  "name": "Compute"
  },
  "sub_group": {
  "id": 2,
  "key": "time",
  "name": "Time"
  }
   }
  ],
 "end_date": "23:59:59",
 "filters": [
 {
  "comparator": "==",
  "measure": {
  "name": "date",
  "label": "Date",
  "description": "The calendar date (e.g. YYYY-MM-DD).",
  "data_type": "date",
  "type": "dimension",
  "group": {
  "id": 9,
  "key": "compute",
  "name": "Compute"
  },
  "sub_group": {
  "id": 2,
  "key": "time",
  "name": "Time"
  }
   },
  "value": "2019-06-24"
  }
   ],
  "metrics": [
 {
  "name": "running_instances",
  "label": "Unique Instance Count",
  "description": "The total number of unique instances in a running state during a given time period.",
  "data_type": "integer",
  "type": "metric",
  "group": {
  "id": 9,
  "key": "compute",
  "name": "Compute"
  },
  "sub_group": {
  "id": 8,
  "key": "usage",
  "name": "Usage"
  }
   }
    ],
  "order": "asc",
  "owned_by_user": false,
  "shared_with_organization": false,
  "permission": {
  "actions": [
  "read"
  ]
   },
 "report_dimension_links": [],
 "secondary_end_date": null,
 "secondary_start_date": null,
 "shared": true,
 "shares": [],
 "sort_by": "date",
 "star": false,
 "start_date": "7 days ago at 00:00:00",
 "subscriptions": [],
 "title": "Elasticity - Running Instances per Hour"
  },
    ]
```

Getting list of available measures

Retrieve a list of measures recognized by the server. Measures includes both dimensions and metrics that can be used in reports. Simply perform a GET at the measures endpoint.

```
curl ‘https://api.cloudability.com/v3/reporting/util/measures’ -u ‘[auth_token]:’
```

Example Response

```
[
  {
    "name": "avg_cpu_utilization",
    "label": "CPU Utilization (Avg)",
    "description": "The average percentage of CPU Utilization...",
    "type": "metric",
    "group": {
      "id": 9,
      "key": "compute",
      "name": "Compute"
    },
    "sub_group": {
      "id": 12,
      "key": "processing",
      "name": "Processing"
    }
  },
  {
    "name": "utilization_hours",
    "label": "Utilization Hours",
    "description": "The total number of usage hours on an instance ...",
    "data_type": "integer",
    "type": "metric",
    "group": {
      "id": 9,
      "key": "compute",
      "name": "Compute"
    },
    "sub_group": {
      "id": 8,
      "key": "usage",
      "name": "Usage"
    }
  },
]
```

Getting list of available filter operators

Retrieve a list of recognized filter operators for requesting data

```
curl ‘https://api.cloudability.com/v3/reporting/util/filters’ -u ‘[auth_token]:’
```

Example Response

```
[
  "<=",   # less than or equals
  "[]=",  # in*
  ">="    # greater than or equals
  "<",    # less than
  "=@",   # contains
  "^=",   # matches
  "===",  # strictly equals*
  "==",   # equals
  "!=@",  # does not contain
  "!=",   # not equals
  "!==",  # strictly not equals*
  ">",    # greater than
  "!^=",  # does not match
  "!$=",  #does not end with
  "[]!=", # not in*
  "$=",   #end with
]	
```

* Note that these operators are available via the API only

Run a utilization report

Request Parameters

| Argument | Description |
| --- | --- |
| start_date (required) | The start date for the utilization report. Format: YYYY-MM-DD |
| end_date (required) | The end date for the utilization report. Format: YYYY-MM-DD |
| dimensions (required) | Comma delimited list of dimensions to include in report. Example: dimensions=date,instance_size |
| metrics (required) | Comma delimited list of metrics to include in report. Example: metrics=running_instances,utilization_hours |
| filters | Filter to apply to report. Filters can be based on dimensions or metrics. Note: the filters query parameter is for a single filter only. Use multiple query parameters for multiple filters. Example: filters=instance_size=@10xlarge Important: the comparison operator should generally be URL encoded (as above) to avoid problems with special characters |
| sort | Comma delimited list of measures, each appended with ASC or DESC to indicate order (order is required). Example: sort=avg_cpu_utilizationASC,regionDESC |
| limit | The maximum number of rows to return. Example: limit=50 |
| offset | Position to start for the results. Example: offset=100 |
| chart | Format the row data for chart purposes (based around dates). Example: chart=1 |
| view_id | If omitted, the user's default view will be applied. Unrestricted users can set view_id=0 to remove view. |

Note: Relative/dynamic date strings supported by the v3 cost reporting endpoint:

| Relative/ Dynamic date strings |
| --- |
| “7 days ago at 00:00:00” |
| “8 days ago at 00:00:00" |
| “10 days ago at 00:00:00” |
| “14 days ago at 00:00:00" |
| “30 days ago at 00:00:00” |
| “31 days ago at 00:00:00" |
| “60 days ago at 00:00:00” |
| “90 days ago at 00:00:00" |
| “beginning of last day” |
| “beginning of last week” |
| “beginning of last month”, “0 of last month” |
| “beginning of last quarter” |
| “beginning of last half” |
| “beginning of last year” |
| “beginning of day”, “beginning of this day” |
| “beginning of week”, “beginning of this week” |
| “beginning of month”, “beginning of this month”, “1st” |
| “beginning of period”, “beginning of this period” |
| “beginning of quarter”, “beginning of this quarter” |
| “beginning of half”, “beginning of this half” |
| “beginning of year”, “beginning of this year” |
| “beginning of next day” |
| “beginning of next week” |
| “beginning of next month” |
| “beginning of next quarter” |
| “beginning of next half” |
| “beginning of next year” |
| “today at 00:00:00” |
| “00:00:00" |
| “23:59:59” |
| “yesterday at 00:00:00" |
| “yesterday at 23:59:59” |
| “end of last day” |
| “end of last week” |
| “end of last month” |
| “end of last quarter” |
| “end of last half” |
| “end of last year” |
| “end of last week to date” |
| “end of last month to date” |
| “end of last quarter to date” |
| “end of last year to date” |
| “end of day”, “end of this day” |
| “end of week”, “end of this week” |
| “end of month”, “end of this month” |
| “end of quarter”, “end of this quarter” |
| “end of half”, “end of this half” |
| “end of year”, “end of this year” |
| “end of next day” |
| “end of next week” |
| “end of next month” |
| “end of next quarter” |
| “end of next half” |
| “end of next year” |

Handling Pagination

To support API performance pagination is implemented when the number of rows in a returned report exceeds 10,000. This typically occurs when users add several dimensions to a report that have high cardinality, such as resource_identifier. The total_results having a value of 10,000 and presence of a pagination object indicates pagination has occurred.

Example pagination object:

```
"pagination": {
  "next": "38bc18d0",
  "previous": "1d93c71e"
```

To navigate backwards and forwards between the pages of a report add a token query parameter to the end of the report URL with the applicable token value (e.g., token=38bc18d0).

Note : You can increase the auto-pagination to 64,000 rows by setting limit=0 in the request parameters

Run a typical utilization report – long-term utilization trends

```
curl ‘https://api.cloudability.com/v3/reporting/util/run?start_date=2022-01-01&end_date=2022-06-30&dimensions=date&metrics=total_bandwidth,avg_cpu_utilization&sort=dateASC&view_id=0’ -u ‘[auth_token]:’"
```

Example Response (subset of results shown)

```
{
  "results": [
    {
      "avg_cpu_utilization": "0.84463",
      "estimated_cost": "393.12",
      "instance_identifier": "i-0a70f28b01f652f14",
      "instance_name": "common-operations-ondemand-r5-large-green-Node",
      "instance_size": "r5.large",
      "total_bandwidth": "2019199735862",
      "utilization_hours": "24",
      "vendor_account_name": "My Account Name"
    },
    {
      "avg_cpu_utilization": "0.830585",
      "estimated_cost": "1071.2",
      "instance_identifier": "i-0278b62c3679c7286",
      "instance_name": "production-operations-spot-16cpu-64gb-green-Node",
      "instance_size": "m5ad.4xlarge",
      "total_bandwidth": "864959230667",
      "utilization_hours": "9",
      "vendor_account_name": "My Account Name"
    }
  ],
  "meta": {
    "dates": {
      "start": "2022-08-30T00:00:00Z",
      "end": "2022-08-30T00:00:00Z"
    },
    "filters": [],
    "metrics": [
      {
        "name": "avg_cpu_utilization",
        "label": "CPU Utilization (Avg)",
        "description": "The average percentage of CPU Utilization...",
        "data_type": "percentage",
        "type": "metric",
        "group": {
          "ID": 9,
          "Key": "compute",
          "Name": "Compute"
        },
        "sub_group": {
          "ID": 12,
          "Key": "processing",
          "Name": "Processing"
        }
      }
    ],
    "dimensions": [
      {
        "name": "instance_identifier",
        "label": "Instance ID",
        "description": "The ID associated with a particular AWS instance.",
        "data_type": "string",
        "type": "dimension",
        "group": {
          "ID": 9,
          "Key": "compute",
          "Name": "Compute"
        },
        "sub_group": {
          "ID": 1,
          "Key": "common",
          "Name": "Common"
        }
      }
    ],
    "aggregates": [
      {
        "name": "avg_cpu_utilization",
        "label": "CPU Utilization (Avg)",
        "description": "The average percentage of CPU Utilization. For EC2, this is the average percentage of allocated EC2 compute units in use for an instance.",
        "data_type": "percentage",
        "type": "metric",
        "value": "0.840516"
      }
    ]
  },
  "offset": 0,
  "pagination": {
    "next": "02f296f8"
  },
  "limit": 2,
  "total_results": 2
}
```

Generate a Report of Utilization Data and Retrieve the Results Later

This option is great for reports that take longer to return (because of high cardinality or timespan), triggering the report generation and then retrieving the results later. The end point to the asynchronous reporting flow takes the same parameters as the synchronous utilization reporting, but instead of waiting and returning the contents of the report, will instead return a request token. The current state of processing is retrieved by requesting the state resource for the given token. When the state is given as "finished", the contents of the report can be retrieved by requesting the results resource for the token. An example of the complete data flow follows the description of the results resource.

```
curl ‘https://api.cloudability.com/v3/reporting/util/enqueue?start_date=2022-01-01&end_date=2022-06-30&dimensions=date&metrics=total_bandwidth,avg_cpu_utilization&sort=dateASC&view_id=0’ -u ‘[auth_token]:’
```

```
curl ‘https://api.cloudability.com/v3/reporting/util/enqueue?start_date=2022-01-01&end_date=2022-06-30&dimensions=date&metrics=total_bandwidth,avg_cpu_utilization&sort=dateASC&view_id=0&useDimensionNames=true' -u ‘[auth_token]:’
```

Example Response

```
{"id":31272850}
```

Query the State of an Asynchronous Report

Valid states of an asynchronous report include: enqueued, running, errored and finished. The state can be queried with the following API call (replace :id with your report ID, as returned from the enqueue call)

```
curl https://api.cloudability.com/v3/reporting/reports/:id/state -u ‘[auth_token]:’
```

Example Response

```
{"status":"running"}
```

Retrieve a Report Previously Generated by Enqueue

Reports that have a state of finished can be retrieved. This returns a standard utilization report object

```
curl ‘https://api.cloudability.com/v3/reporting/reports/:id/results’-u ‘[auth_token]:’]"
```

Important note about pagination: Enqueued reports implement pagination in a similar manner to synchronous utilization reports. The only difference is that pages are sized at 30,000 rows instead of 10,000. This means enqueued reports won’t trigger pagination until the row count exceeds 30,000 rows.

List of sample reports

Below are a few sample reports that can help you with usage of the utilization reports API.

Utilization report with relative dates

```
curl ‘https://api.cloudability.com/v3/reporting/util/run?start_date=0+of+last+month&end_date=end+of+last+month&dimensions=date&metrics=total_bandwidth,avg_cpu_utilization&sort=dateASC&view_id=0’ -u ‘[auth_token]:’
```

Instance type usage trends, returned via CSV

```
 curl -H ‘Accept: text/csv’ ‘https://api.cloudability.com/v3/reporting/util/run?start_date=2022-02-01&end_date=2022-02-28&dimensions=instance_size&metrics=utilization_hours,running_instances&sort=utilization_hoursDESC’ -u ‘[auth_token]:’

```

Underutilized compute optimized instances (report with multiple dimensions and filters)

```
curl 'https://api.cloudability.com/v3/reporting/util/run?start_date=2022-02-01&end_date=2022-02-28&dimensions=instance_size&metrics=utilization_hours%2Crunning_instances&sort=utilization_hoursDESC' -u '[auth_token]:'
```

Typical utilization report (days since launch report)

```

curl ‘https://api.cloudability.com/v3/reporting/util/run?dimensions=launch_date&end_date=2022-08-30&filters=product_name%3D%3DAmazon%20Elastic%20Compute%20Cloud&limit=2&metrics=avg_cpu_utilization&relativePeriods=custom&sort=launch_dateDESC&start_date=2022-08-22&viewId=0’ -u ‘[auth_token]:’
```

---

## Vendor Credentials End Point (AWS)

<!-- sub-header -->
- **breadcrumb:** Cloudability API > Vendor Credentials End Point (AWS)
- **source_path:** SSVCLNQ/api-v3/vendor_credentials_end_point_1.html
- **original_file:** api-vendor-credentials-end-point-aws.md
- **images:** []

## Vendor Credentials End Point (AWS)

Summary

This end point is used to manage credentials within Cloudability that support the integration and ingestion of data from public cloud vendors. This includes tasks such as initial setup, listing out current credentials and deleting deprecated credentials.

This end point does not support filtering and sorting.

With Cloudability being available in multiple regions, all references to api.cloudability.com in this API documentation should be referred to as mentioned in Getting started with Cloudability API V3 .

End Point Particulars

end point : /vendors/AWS/accounts for RESTful CRUD interactions

end point : /vendors/AWS/accounts/[vendorAccountId]/verification

end point : /vendors/AWS/accounts/[vendorAccountId]/user-to-role-migration

end point : /vendors/AWS/accounts/[vendorAccountId]/cloudformation-template

end point : /vendors/AWS/accounts/[vendorAccountId]/external-id-rotation

end point : /vendors/aws/accounts/[account_id]/archive

The Credential Object

id (string) - 12 digit string corresponding to your AWS account ID

vendorAccountName (string) - The name give to your AWS account

vendorAccountId (string) - 12 digit string corresponding to your AWS account ID

vendorKey (string) - "aws"

verification (object) - object containing details of verification state:

state (string) - examples "unverified", "verified", "error"

lastVerificationAttemptedAt (string) - date timestamp, example: "1970-01-01T00:00:00.000Z"

message (string) - error message for credentials in error state

authorization (object) - object contain vendor specific authorization details

type (string) - "aws_role" or "aws_user"

region (string) - all supported regions on AWS such as "us-west-1" or "us-west-2"

roleName (string) - currently hardcoded to "CloudabilityRole"

bucketName (string) - the name of the bucket used

externalId (string) - the external ID used to prevent confused deputies . Generated by Cloudability

parentAccountId (string) - 12 digit string representing parent's account ID (if current cred is a linked account)

createdAt - (string) - date timestamp corresponding to Cloudability credential creation time

```
curl 'https://api.cloudability.com/v3/vendors/AWS/accounts?viewId=0' \\ 
 -u ‘[auth_token]:’
```

```
{ 
"result": [ 
{ 
"id": "111111111111", 
"vendorAccountName": "AccountName", 
"vendorAccountId": "111111111111", 
"vendorKey": "aws", 
"verification": { 
"state": "verified", 
"lastVerificationAttemptedAt": "2025-12-12T05:13:40Z" 
}, 
"authorization": { 
"type": "aws_role", 
"roleName": "CloudabilityRole", 
"bucketName": "test-321", 
"externalId": "1111111c-111e-1111-1111-e1111cfc1aee", 
"costAndUsageReport": { 
"name": "test-apptio", 
"prefix": "new" 
}, 
"region": "us-east-1", 
"isOrgLevelPolicyEnabled": true, 
"turboExecutionEnabled": false, 
"applicationType": "DUAL" 
}, 
"createdAt": "2025-07-02T12:01:40Z", 
"consumerOrgId": "", 
"byodVendor": "ABSENT" 
}, 
{ 
"id": "222222222222", 
"vendorAccountName": "testlinked", 
"vendorAccountId": "222222222222", 
"vendorKey": "aws", 
"verification": { 
"state": "verified", 
"lastVerificationAttemptedAt": "2025-12-12T05:12:54Z" 
}, 
"authorization": { 
"type": "aws_role", 
"permissions": [ 
"s3:ListAllMyBuckets", 
"ec2:DescribeSnapshots" 
], 
"roleName": "CloudabilityRole_OU", 
"externalId": "d111111c-111e-1111-1111-e1111cfc1aee", 
"region": "us-east-1", 
"turboExecutionEnabled": false, 
"applicationType": "DUAL" 
}, 
"createdAt": "2025-09-22T10:02:54Z", 
"parentAccountId": "111111111111", 
"consumerOrgId": "", 
"byodVendor": "ABSENT" 
} 
] 
}
```

```
curl -X POST 'https://api.cloudability.com/v3/vendors/aws/accounts' \\ 
 -H 'Content-Type: application/json' \\ 
 -u ‘[auth_token]:’ \\ 
 -d @- << EOF 
{ 
 "vendorAccountId": "999966667777", 
 "type": "aws_role", 
 "bucketName": "some bucket name", 
 "roleName": "CloudabilityRole", 
 "externalID": "some external ID", 
 "costAndUsageReport": { 
 "name": "costandusageboth", 
 "prefix": "some prefix" 
 }, 
 "region": "us-west-2", 
 "isOrgLevelPolicyEnabled": true 
}
```

Upon successful creation the API will return the credentials object.

Example 'Verified' Linked Account Credentials Object

```
{
  "result": {
    "id": "999988887777",
    "vendorAccountName": "Account Name",
    "vendorAccountId": "999988887777",
    "vendorKey": "aws",
    "verification": {
      "state": "verified",
      "lastVerificationAttemptedAt": "2017-11-03T08:35:55.049Z"
    },
    "authorization": {
      "type": "aws_role",
      "roleName": "CloudabilityRole",
      "externalId": "1265c251-1e14-49db-b933-af3364c8ac77"
    },
    "parentAccountId": "111122223333",
    "createdAt": "2017-11-03T07:35:55.049Z"
  }
}
```

Create Credential for Linked Account

Special Note : If your linked account is brand new to make sure Cloudability is aware of it run a verification on your master payer account . We do have a regular background job to register new accounts, but if your account is brand new do run the verification to guarantee the credential can be created as follows.

```
curl -X POST 'https://api.cloudability.com/v3/vendors/aws/accounts' \\
     -H 'Content-Type: application/json' \\
     -u ‘[auth_token]:’ \\
     -d @- << EOF
```

```
{
  "vendorAccountId": "999988887777",
  "type": "aws_role"
  "region": "us-west-2"				
}
EOF
```

Upon successful creation the API will return the credentials object.

To ensure the API returns all accounts with these credentials requests, add viewId=0 as a URL parameter. This will ensure any default view on your user account isn't applied.

Update Credential for an Account

```
curl -X PUT'https://api.cloudability.com/v3/vendors/aws/accounts/[account_id]' \\ 
 -H 'Content-Type: application/json' \\ 
 -u ‘[auth_token]:’ \\ 
 -d @- << EOF 
{ 
"type": "aws_role", 
"vendorAccountId": "111111111111", 
"bucketName": "test", 
"consumerOrgId": "", 
"costAndUsageReport": { 
"name": "test", 
"prefix": "test" 
}, 
"region": "us-west-2", 
"isOrgLevelPolicyEnabled": false, 
"externalId": "c1c1a1b1-b1c1-1111-ac11-e111a11f1ab1" 
} 
```

Upon successful update the API will return the credentials object.

Retrieve Account

```
curl 'https://api.cloudability.com/v3/vendors/AWS/accounts/[vendorAccountId]' \\
   -u ‘[auth_token]:’
```

Delete Credential for an Account

```
curl -X DELETE 'https://api.cloudability.com/v3/vendors/AWS/accounts/999988887777' \\
     -u ‘[auth_token]:’
```

Verify Credentials for an Account

```
curl -X POST 'https://api.cloudability.com/v3/vendors/AWS/accounts/999988887777/verification' \\
     -u ‘[auth_token]:’
```

```
{ 
  "result": { 
    "id": "999988887777", 
    "vendorAccountName": "Account Name", 
    "vendorAccountId": "999988887777", 
    "vendorKey": "aws", 
    "verification": { 
      "state": "verified", 
      "lastVerificationAttemptedAt": "2017-11-03T08:35:55.049Z" 
    }, 
    "authorization": { 
      "type": "aws_role", 
      "roleName": "CloudabilityRole", 
      "externalId": "1265c251-1e14-49db-b933-af3364c8ac77" 
    }, 
    "parentAccountId": "111122223333", 
    "createdAt": "2017-11-03T07:35:55.049Z" 
  } 
} 
```

Get CloudFormation Template for Account

```
curl 'https://api.cloudability.com/v3/vendors/AWS/accounts/999988887777/cloudformation-template' \\
     -u ‘[auth_token]:’
```

Rotate the External ID

```
 curl -X POST 'https://api.cloudability.com/v3/vendors/AWS/accounts/999988887777/external-id-rotation' \\
     -u ‘[auth_token]:’
```

```
{ 
"result": { 
"id": "string", 
"vendorAccountName": "string", 
"vendorAccountId": "string", 
"vendorKey": "string", 
"verification": { ... }, 
"authorization": { 
"type": "string", 
"permissions": ["string"], 
"roleName": "string", 
"externalId": "string", // This will contain the new rotated external ID 
"bucketName": "string", 
... 
}, 
"meta": { ... }, 
"additionalData": { ... }, 
"createdAt": "string", 
"parentAccountId": "string",
"associatedAccounts": [...], 
"customRole": boolean, 
"consumerOrgId": "string", 
"byodVendor": "string" 
} 
}  
```

Archive Account

```
curl -X POST https://api.cloudability.com/v3/vendors/aws/accounts/[account_id]/archive -u ‘[auth_token]:’
```

Recipe for Adding New Linked Account Credentials (AWS)

1. If your linked account is brand new to make sure Cloudability is aware of it run a verification on your master payer account . We do have a regular background job to register new accounts, but if your account is brand new do run the verification to guarantee the credential can be created in the next step. Note: The background job can take a few hours to bring in the new linked accounts
1. Create Credential For Linked Account
1. Get Cloudformation Template (CFT) For Account
1. Create CFT Stack in AWS via AWS console or AWS API/SDK/CLI (net result is the creation of the IAM role Cloudability assumes)
1. Verify Credentials for an account

Recipe for Migrating AWS User Creds to AWS Role Creds

1. Migrate a AWS User Credential to AWS Role Credential
1. Get Cloudformation Template (CFT) For Account
1. Create the CFT Stack in AWS via AWS console or AWS API/SDK/CLI
1. Verify Credentials for an account

Recipe for Rotating External ID

1. Rotate ExternalId
1. Update CFT Stack in AWS
1. Verify Credentials for an account

Recipe for Creating Credential, Retrieving External ID and Creating IAM Role with Your Own Scripting

The only unique thing about each CloudFormation template is the externalID itself. This is a AWS best practice from a security perspective, but instead of needing to generate a separate template each time you could just activate a credential, retrieve it's externalID and then script on your end to create the role. Here are the calls to do this:

1. Create the credential within Cloudability
1. The externalID is returned within the JSON response from a successful request above. It can also be obtained afterward by retrieving the account credential .
1. Use a script on your end to apply the externalID as a parameter with your own template.
1. Verify Credentials for an account

---

## Vendor Credentials End Point (OCI)

<!-- sub-header -->
- **breadcrumb:** Cloudability API > Vendor Credentials End Point (OCI)
- **source_path:** SSVCLNQ/api-v3/vendor_credentials_end_point_oci.html
- **original_file:** api-vendor-credentials-end-point-oci.md
- **images:** []

## Vendor Credentials End Point (OCI)

Summary

This end point is used to manage credentials within Cloudability that support the integration and ingestion of data from public cloud vendors. This includes tasks such as initial setup, listing out current credentials and deleting deprecated credentials.

This end point does not support filtering and sorting.

With Cloudability being available in multiple regions, all references to api.cloudability.com in this API documentation should be referred to as mentioned in Getting started with Cloudability API V3 .

End Point Particulars

end point : /v3/vendors/oci/accounts for RESTful CRUD interactions

end point : /v3/vendors/oci/accounts?include=permissions&viewId=0

end point : /v3/vendors/oci/accounts/<account_id>?include=permissions&viewId=0

end point : /v3/vendors/oci/accounts/<account_id>/terraform-template

end point : /v3/vendors/oci/accounts/<account_ id>/verification?include=permissions,associatedAccounts&viewId=0

end point : /v3/vendors/oci/accounts/<account_id>/archive?viewId=0

Parameters

- Id (string) - tenancy OCID
- vendorAccountName (string) - tenancy name
- vendorAccountId (string) - tenancy OCID
- vendorKey (string) - oci
- roleName (string) - currently hardcoded to "CloudabilityRole",
- verification (object) - object containing details of verification state: state (string) - examples "unverified", "verified", "error" lastVerificationAttemptedAt (string) - date timestamp, example: "1970-01-01T00:00:00.000Z" message (string) -error message for credentials in error state
- authorization (object) -object contain vendor specific authorization details type (string) - oci_user (this field will never change) tenancyId (string) - tenancy OCID userId (string) - user OCID region - home region name groupId - group OCID namespace - currently hardcoded to “bling” but can be updated
- createdAt - (string) - date timestamp corresponding to Cloudability credential creation time
- ociCostReportSpec namespace bucket compartment privateDetails fingerprint (string) -fingerprint passphrase (string) - optional field secret (string) - private key

List Accounts

Example Request

```
curl 'https://api.cloudability.com/v3/vendors/oci/accounts?viewId=0' \\ 
 -u ‘[auth_token]:’
```

Example Response

```
{ 
"result": [ 
{ 
"id": "ocid1.tenancy.oc1..aaaaaaaa1aaaaaaaaa1aaa1aa1aaaaa1aaaaaaaaaa1aaaaaaaaaa1aaaaaa", 
"vendorAccountName": "testaccount", 
"vendorAccountId": "ocid1.tenancy.oc1..aaaaaaaa1aaaaaaaaa1aaa1aa1aaaaa1aaaaaaaaaa1aaaaaaaaaa1aaaaaa", 
"vendorKey": "oci", 
"verification": { 
"state": "verified", 
"lastVerificationAttemptedAt": "2026-02-04T08:14:11Z" 
}, 
"authorization": { 
"type": "oci_user", 
"permissions": [ 
"oci.list.assignedSubscriptions", 
"oci.list.tenancies", 
"oci.get.instanceFamily", 
"oci.list.imageShape.Compatibility", 
"oci.list.computeShapes", 
"oci.get.costReports", 
"oci.get.metrics", 
"oci.list.computeImages" 
], 
"tenantId": "ocid1.tenancy.oc1..aaaaaaaa1aaaaaaaaa1aaa1aa1aaaaa1aaaaaaaaaa1aaaaaaaaaa1aaaaaa", 
"tenancyId": "ocid1.tenancy.oc1..aaaaaaaa1aaaaaaaaa1aaa1aa1aaaaa1aaaaaaaaaa1aaaaaaaaaa1aaaaaa", 
"userId": "ocid1.user.oc1..aaaaaaaamcxbi4ldug2wgmytoakyjjmhaeb33lb7fflbnfpwxzlbdmzrqyoa", 
"groupId": "ocid1.group.oc1..aaaaaaaafnl54eo33p6kqgxynrvqxcrkvm3hjwzichapgekxtrkjgi2qmn3a", 
"region": "us-chicago-1", 
"namespace": "bling" 
}, 
"createdAt": "2023-07-05T10:24:20Z", 
"consumerOrgId": "", 
"byodVendor": "ABSENT" 
}, 
{ 
"id": "ocid1.tenancy.oc1..aaaaaaaa2aaaaaaaaa2aaa2aa2aaaaa2aaaaaaaaaa2aaaaaaaaaa2aaaaaa", 
"vendorAccountName": "testaccountchild1", 
"vendorAccountId": "ocid1.tenancy.oc1..aaaaaaaa2aaaaaaaaa2aaa2aa2aaaaa2aaaaaaaaaa2aaaaaaaaaa2aaaaaa", 
"vendorKey": "oci", 
"verification": { 
"state": "error", 
"message": "No permissions present for this account", 
"lastVerificationAttemptedAt": "2026-02-04T04:52:11Z" 
}, 
"authorization": { 
"type": "oci_user", 
"tenantId": "ocid1.tenancy.oc1..aaaaaaaa2aaaaaaaaa2aaa2aa2aaaaa2aaaaaaaaaa2aaaaaaaaaa2aaaaaa", 
"tenancyId": "ocid1.tenancy.oc1..aaaaaaaa2aaaaaaaaa2aaa2aa2aaaaa2aaaaaaaaaa2aaaaaaaaaa2aaaaaa", 
"userId": "ocid1.user.oc1..aaaaaaaa3aaaaaaaaa2aaa2aa2aaaaa2aaaaaaaaaa3aaaaaaaaaa3aaaaaa", 
"groupId": "ocid1.group.oc1..aaaaaaaa4aaaaaaaaa4aaa4aa4aaaaa4aaaaaaaaaa3aaaaaaaaaa3aaaaaa", 
"region": "us-chicago-1" 
}, 
"createdAt": "2023-07-09T08:30:54Z", 
"parentAccountId": "ocid1.tenancy.oc1..aaaaaaaa1aaaaaaaaa1aaa1aa1aaaaa1aaaaaaaaaa1aaaaaaaaaa1aaaaaa", 
"consumerOrgId": "", 
"byodVendor": "ABSENT" 
} 
] 
}
```

Create Credential for Root Tenancy

Example Request

```
curl -X POST 'https://api.cloudability.com/v3/vendors/oci/accounts?viewId=0 
\\ 
-H 'Content-Type: application/json' \\ 
-u ‘[auth_token]:’ \\ 
-d @- << EOF 

{ 
   "vendorAccountId": "sample tenant OCID", 
   "tenancyId": "sample tenant OCID", 
   "ociCostReportSpec": { 
   "namespace": "bling", 
   "bucket": "sample tenant OCID", 
   "compartment": "sample tenant OCID" 
}, 
      "type": "oci_user" 
} 
```

Update Credential for newly created Tenancy after running the terraform template

Example Request

```
curl -X PUT 'https://api.cloudability.com/v3/vendors/oci/accounts/<tenancy-id>?include=permissions&viewId=0 
\\ 
-H 'Content-Type: application/json' \\ 
-u ‘[auth_token]:’ \\ 
-d @- << EOF 

{ 
"vendorAccountId": "sample tenant OCID", 
"tenancyId": "sample tenant OCID", 
"userId": "user-id", 
"region": "region", 
"groupId": "group-id", 
"ociCostReportSpec": { 
"bucket": "bling", 
"namespace": "bling", 
"compartment": "sample tenant OCID" 
}, 
"privateDetails": { 
"fingerprint": " fingerprint-details ", 
"passphrase": " passphrase-details", 
"secret": " secret " 
}, 
"type": "oci_user" 
} 
```

Retrieve a Tenancy

Example Request

```
curl   
'https://api.cloudability.com/v3/vendors/oci/accounts/[vendorAccountId]’\\ 
-u ‘[auth_token]:’ 
```

Delete Credential for a Tenancy

Example Request

```
curl --X DELETE  
'https://api.cloudability.com/v3/vendors/oci/accounts/<account_id>?viewId=0’ 
-u ‘[auth_token]:’ 
```

V erify Credential for a Tenancy

Example Request

```
curl --X POST  
'https://api.cloudability.com/v3/vendors/oci/<account_id>/verification?include=permissions,associatedAccounts&viewId=0’ \\ 
-u ‘[auth_token]:’ 
```

Get Terraform Template for a Tenancy

Example Request

```
curl   
'https://api.cloudability.com/v3/vendors/oci/<account_id>/terraform-template’ \\ 
-u ‘[auth_token]:’ 
```

Archive Tenancy

Example Request

```
curl --X POST  
'https://api.cloudability.com/v3/vendors/oci/<account_id>archive?viewId=0’ \\ 
-u ‘[auth_token]:’ 
```

---

## Vendor Credentials End Points (Azure)

<!-- sub-header -->
- **breadcrumb:** Cloudability API > Vendor Credentials End Points (Azure)
- **source_path:** SSVCLNQ/api-v3/azure-vendor-credential-end-points.html
- **original_file:** api-vendor-credentials-end-points-azure.md
- **images:** []

## Vendor Credentials End Points (Azure)

Summary

These end points are used to manage Azure integration within Cloudability which supports creation, updation, and deletion of Azure credentials.

This end point does not support filtering and sorting.

With Cloudability being available in multiple regions, all references to api.cloudability.com in this API documentation should be referred to as mentioned in Getting started with Cloudability API V3 .

End Point Particulars

Public Enrollment Account (EA)

end point : /v3/vendors/azure/accounts for RESTful CRUD interactions

end point : /v3/vendors/azure/accounts/[account_id]?viewId=0

end point : /v3/vendors/azure/accounts/[account_id]/setup-scripts

end point : /v3/vendors/azure/accounts/[account_id]/verification

end point : /v3/vendors/azure/accounts/[account_id] /archive

Public Microsoft Customer Agreement (MCA)

end point : /v3/vendors/azure/accounts for RESTful CRUD interactions

end point : /v3/vendors/azure/accounts/[account_id] ?viewId=0

end point : /v3/vendors/azure/accounts/[account_id]/setup-scripts

end point : /v3/vendors/azure/accounts/[account_id]/verification

end point : /v3/vendors/azure/accounts/[account_id] /archive

The Credential Object

vendorAccountName (string) - Azure vendor Account Name

vendorAccountId (string) - Azure vendor Account ID of customers

vendorKey (string) - states the vendor type (Azure).

verification : contains state of the account

state (string) - it specifies whether the account is in verified/unverified/error state

authorization : contains the below details:

type (string) - the provider type (azure_enrollment/azure_mca/azure_subscription)

enrollmentId (string) - the enrollement account Id(only present in Azure Enrollment Accounts)

tenantId (string) - unique identifier assigned to each Azure Active Directory (AAD) instance

subscriptionGuid (string) - is a unique identifier assigned to each Azure subscription

resourceGroupName (string) - is a unique name assigned to a logical container for Azure resources

storageAccountName (string) - is the unique name assigned to an Azure Storage account

containerName (string) - refers to the unique name assigned to a container within an Azure Storage account

directoryName (string) - refers to a folder or directory within a storage account

exportNameCost (string) - cost export file name

exportNameAmortized (string) - amortized export file name

tenancyId (string) - refers to the tenantId which is a globally unique identifier assigned to each Azure Active Directory (AAD)

turboExecutionEnabled (boolean) - default to false - only required for Cloudability premium

createdAt (string) - the timestamp at which the account is credentialized

additionalData( object) -

accountAlias(string) – Alias name for a billing account for MSP

AzureTenantId(string) –– tenant id of the uncredentialled account for MSP

consumerOrgId (string) - if the account belongs to msp_consumer, this is the orgId of MSP_CONSUMER (optional, needs to be provided only if it belongs to MSP).

Public EA/MCA API

List Accounts

```
curl 'https://api.cloudability.com/v3/vendors/azure/accounts?viewId=0' \\ 
 -u ‘[auth_token]:’ 
```

```
{ 
"result": [ 
{ 
"id": "11112222", 
"vendorAccountName": "11112222", 
"vendorAccountId": "11112222", 
"vendorKey": "azure", 
"verification": { 
"state": "verified", 
"lastVerificationAttemptedAt": "2025-12-16T12:32:32Z" 
}, 
"authorization": { 
"type": "azure_enrollment", 
"permissions": ["Cost Export Report", "Amortized Export Report"], 
"enrollmentId": "11112222", 
"tenantId": "11a1a111-1111-1111-1111-11aa11111aff", 
"subscriptionGuid": "ecf11fd1-dc11-11b1-1af1-db11a1a1becf", 
"resourceGroupName": "costexport", 
"storageAccountName": "cloudabilityactualcost", 
"containerName": "apptiocostmgmtcontainer", 
"directoryName": "apptiocostmgmtdirectory", 
"exportNameCost": "cloudabilityactualcost", 
"exportNameAmortized": "cloudabilityamortizedcost", 
"tenancyId": "11a1a111-1111-1111-1111-11aa11111aff" 
}, 
"meta": {}, 
"additionalData": {}, 
"createdAt": "2021-03-09T16:05:37Z", 
"consumerOrgId": "", 
"byodVendor": "ABSENT" 
}, 
```

Create Azure EA credential

```
curl –location --request POST 'https://api.cloudability.com/v3/vendors/azure/accounts' \ 
--header 'Content-Type: application/json' \ 
--data '{ 
"vendorAccountId": "11111111", 
"type": "azure_enrollment", 
"tenantId": "11f1a111-1111-1111-1111-11cf11111bff", 
"consumerOrgId": "", 
"costReportSpec": { 
"subscriptionGuid": "ecf11fd1-dc11-11b1-1af1-db11a1a1becf", 
"resourceGroupName": "test", 
"storageAccountName": "test-acc", 
"containerName": "test-cont", 
"directoryName": "test-dir", 
"exportNameCost": "test-cost", 
"exportNameAmortized": "test-amortized" 
}'
```

```
{
"result": { 
"id": "11111111", 
"vendorAccountName": "11111111", 
"vendorAccountId": "11111111", 
"vendorKey": "azure", 
"verification": { 
"state": "unverified" 
}, 
"authorization": { 
"type": "azure_enrollment", 
"enrollmentId": "11111111", 
"tenantId": "11f1a111-1111-1111-1111-11cf11111bff", 
"subscriptionGuid": "ecf11fd1-dc11-11b1-1af1-db11a1a1becf", 
"resourceGroupName": "test", 
"storageAccountName": "test-acc", 
"containerName": "test-cont", 
"directoryName": "test-dir", 
"exportNameCost": "test-cost", 
"exportNameAmortized": "test-amortized", 
"tenancyId": "11f1a111-1111-1111-1111-11cf11111bff" 
}, 
"meta": {}, 
"createdAt": "2023-12-28T11:02:42Z", 
"consumerOrgId": "" 
} 
} 
```

```
curl –location --request POST 'https://api.cloudability.com/v3/vendors/azure/accounts' \ 
--header 'Content-Type: application/json' \ 
--data ' { 
"vendorAccountId": "1111a1a1-1111-1a11-aa11-a111a111111a:1111aa11-a1aa-1aa1-1111-1111a11a1aa1_2024-05-08", 
"type": "azure_mca", 
"tenantId": "11111111-11a1-11aa-1111-111a111a1a11", 
"consumerOrgId": "", 
"costReportSpec": { 
"subscriptionGuid": "22111111-11a1-11aa-1111-111a111a1a22", 
"resourceGroupName": "test_resource", 
"storageAccountName": "test_account", 
"containerName": "test_container", 
"directoryName": "test_dir", 
"exportNameCost": "test_cost", 
"exportNameAmortized": "test_amort" 
} 
}' 
```

```
{ 
"result": { 
"id": "1111a1a1-1111-1a11-aa11-a111a111111a:1111aa11-a1aa-1aa1-1111-1111a11a1aa1_2024-05-08", 
"vendorAccountName": "1111a1a1-1111-1a11-aa11-a111a111111a:1111aa11-a1aa-1aa1-1111-1111a11a1aa1_2024-05-08", 
"vendorAccountId": "1111a1a1-1111-1a11-aa11-a111a111111a:1111aa11-a1aa-1aa1-1111-1111a11a1aa1_2024-05-08", 
"vendorKey": "azure", 
"verification": { 
"state": "unverified" 
}, 
"authorization": { 
"type": "azure_mca", 
"tenantId": "11111111-11a1-11aa-1111-111a111a1a11", 
"subscriptionGuid": "22111111-11a1-11aa-1111-111a111a1a22", 
"resourceGroupName": "test_resource", 
"storageAccountName": "test_account", 
"containerName": "test_container", 
"directoryName": "test_dir", 
"exportNameCost": "test_cost", 
"exportNameAmortized": "test_amort", 
"tenancyId": "11111111-11a1-11aa-1111-111a111a1a11" 
}, 
"additionalData": {}, 
"createdAt": "2025-12-17T08:25:45Z", 
"consumerOrgId": "", 
"byodVendor": "ABSENT" 
} 
}
```

```
curl –location --request POST 'https://api.cloudability.com/v3/vendors/azure/accounts' \ 
--header 'Content-Type: application/json' \ 
--data '{ 
"vendorAccountId": "a1a11111-111a-1111-11a1-a1111a1a1111:aa1111aa-aaa1-1aa1-111a-a1aa1a111a1a_2024-09-30", 
"type": "azure_mpa", 
"tenantId": "11111111-11a1-11aa-1111-111a111a1a11", 
"consumerOrgId": "111111", 
"costReportSpec": { 
"subscriptionGuid": "11111111-11a1-11aa-1111-111a111a1a22", 
"resourceGroupName": "tes_resource", 
"storageAccountName": "test_storage", 
"containerName": "test_container", 
"directoryName": "test_dir", 
"exportNameCost": "test_cost", 
"exportNameAmortized": "test_amortized" 
} 
}'
```

```
{ 
"result": { 
"id": "a1a11111-111a-1111-11a1-a1111a1a1111:aa1111aa-aaa1-1aa1-111a-a1aa1a111a1a_2024-09-30", 
"vendorAccountName": "a1a11111-111a-1111-11a1-a1111a1a1111:aa1111aa-aaa1-1aa1-111a-a1aa1a111a1a_2024-09-30", 
"vendorAccountId": "a1a11111-111a-1111-11a1-a1111a1a1111:aa1111aa-aaa1-1aa1-111a-a1aa1a111a1a_2024-09-30", 
"vendorKey": "azure", 
"verification": { 
"state": "unverified" 
}, 
"authorization": { 
"type": "azure_mpa", 
"tenantId": "11111111-11a1-11aa-1111-111a111a1a11", 
"subscriptionGuid": "11111111-11a1-11aa-1111-111a111a1a22", 
"resourceGroupName": "tes_resource", 
"storageAccountName": "test_storage", 
"containerName": "test_container", 
"directoryName": "test_dir", 
"exportNameCost": "test_cost", 
"exportNameAmortized": "test_amortized", 
"tenancyId": "11111111-11a1-11aa-1111-111a111a1a11" 
}, 
"additionalData": {}, 
"createdAt": "2025-12-17T08:32:10Z", 
"consumerOrgId": "113924", 
"byodVendor": "ABSENT" 
} 
}
```

```
curl --location --request PUT 'https://api.cloudability.com/v3/vendors/azure/accounts/<master-account-id>/auth-locations?viewId=0' \ 
--header 'Content-Type: application/json' \ 
--data ' { 
"vendorAccountIds": [ 
"11aaaa1a-11a1-1111-11a1-111a1a1aa111", 
"22aaaa2a-22a2-2222-22a2-222a2a2aa222", 
"33aaaa3a-33a3-3333-33a3-333a3a3aa333" 
], 
"turboExecutionEnabled": false 
}' 
```

```
{ 
"result": [ 
{ 
"vendorAccountId": "11aaaa1a-11a1-1111-11a1-111a1a1aa111", 
"tenantId": "11a1a111-1111-1111-1111-42aa11114aaa", 
"authUrl": "https://login.microsoftonline.com/11a1a111-1111-1111-1111-42aa11114aaa/oauth2/authorize?client_id=5bb55bbb-5555-55b5-55bb-55b5bb5bbb5b&response_type=code&response_mode=query&redirect_uri=https%3A%2F%2Fapi.cloudability.com%2Fcallback%2Factive-directory-auth%2Fconfig%2F&resource=https%3A%2F%2Fmanagement.azure.com%2F&state=8888888c-8cc8-88c8-cccc-ccc88ccc888a" 
}, 
{ 
"vendorAccountId": "22aaaa2a-22a2-2222-22a2-222a2a2aa222", 
"tenantId": "22a2a222-1111-1111-1111-42aa11114aaa", 
"authUrl": "https://login.microsoftonline.com/22a2a222-1111-1111-1111-42aa11114aaa/oauth2/authorize?client_id=6bb66bbb-6666-66b6-66bb-66b6bb6bbb6b&response_type=code&response_mode=query&redirect_uri=https%3A%2F%2Fapi.cloudability.com%2Fcallback%2Factive-directory-auth%2Fconfig%2F&resource=https%3A%2F%2Fmanagement.azure.com%2F&state=9999999c-9cc9-99c9-cccc-ccc99ccc999a" 
}, 
{ 
"vendorAccountId": "33aaaa3a-33a3-3333-33a3-333a3a3aa333", 
"tenantId": "33a3a333-3333-1111-1111-42aa11114aaa", 
"authUrl": "https://login.microsoftonline.com/33a3a333-3333-1111-1111-42aa11114aaa/oauth2/authorize?client_id=7bb77bbb-7777-77b7-77bb-77b7bb7bbb7b&response_type=code&response_mode=query&redirect_uri=https%3A%2F%2Fapi.cloudability.com%2Fcallback%2Factive-directory-auth%2Fconfig%2F&resource=https%3A%2F%2Fmanagement.azure.com%2F&state=4c-4cc4-4c4-cccc-ccc4ccc4a" 
} 
] 
}
```

```
curl --location --request PUT 'https://api.cloudability.com/v3/vendors/azure/accounts/11111111' \ 
--header 'Content-Type: application/json' \ 
--data '{ 
"vendorAccountId": "11111111", 
"type": "azure_enrollment", 
"tenantId": "11f1a111-1111-1111-1111-11cf11111bff", 
"consumerOrgId": "", 
"costReportSpec": { 
"subscriptionGuid": "ecf11fd1-dc11-11b1-1af1-db11a1a1becf", 
"resourceGroupName": "costexportName", 
"storageAccountName": "cloudabilityactualcost", 
"containerName": "apptiocostmgmtcontainer", 
"directoryName": "apptiocostmgmtdirectory", 
"exportNameCost": "NA", 
"exportNameAmortized": "NA" 
}'
```

```
{ 
"result": { 
"id": "11111111", 
"vendorAccountName": "11111111", 
"vendorAccountId": "11111111", 
"vendorKey": "azure", 
"verification": { 
"state": "unverified" 
}, 
"authorization": { 
"type": "azure_enrollment", 
"enrollmentId": "11111111", 
"tenantId": "11f1a111-1111-1111-1111-11cf11111bff", 
"subscriptionGuid": "ecf11fd1-dc11-11b1-1af1-db11a1a1becf", 
"resourceGroupName": "costexportName", 
"storageAccountName": "cloudabilityactualcost", 
"containerName": "apptiocostmgmtcontainer", 
"directoryName": "apptiocostmgmtdirectory", 
"exportNameCost": "NA", 
"exportNameAmortized": "NA", 
"tenancyId": "11f1a111-1111-1111-1111-11cf11111bff" 
}, 
"meta": {}, 
"createdAt": "2021-03-09T16:05:37Z", 
"consumerOrgId": "" 
} 
}
```

```
curl --location --request PUT 'https://api.cloudability.com/v3/vendors/azure/accounts/1111a1a1-1111-4d11-aa11-a111a111111a:1111aa11-b1aa-1aa1-2222-3333f44e2aa1_2019-05-01?viewId=0' \ 
--header 'Content-Type: application/json' \ 
--data '{ 
"vendorAccountId": "1111a1a1-1111-4d11-aa11-a111a111111a:1111aa11-b1aa-1aa1-2222-3333f44e2aa1_2019-05-01", 
"type": "azure_mca", 
"tenantId": "a2a22aaa-22aa-222a-aa22-2a2aa2aaa2a2", 
"consumerOrgId": "", 
"costReportSpec": { 
"subscriptionGuid": "a2a22aaa-22aa-222a-aa22-2a2aa2aaa2a2", 
"resourceGroupName": "test", 
"storageAccountName": "test", 
"containerName": "test", 
"directoryName": "test", 
"exportNameCost": "test", 
"exportNameAmortized": "test1" 
} 
}'
```

```
{ 
"result": { 
"id": "1111a1a1-1111-4d11-aa11-a111a111111a:1111aa11-b1aa-1aa1-2222-3333f44e2aa1_2019-05-01", 
"vendorAccountName": "1111a1a1-1111-4d11-aa11-a111a111111a:1111aa11-b1aa-1aa1-2222-3333f44e2aa1_2019-05-01", 
"vendorAccountId": "1111a1a1-1111-4d11-aa11-a111a111111a:1111aa11-b1aa-1aa1-2222-3333f44e2aa1_2019-05-01", 
"vendorKey": "azure", 
"verification": { 
"state": "unverified" 
}, 
"authorization": { 
"type": "azure_mca", 
"tenantId": "a2a22aaa-22aa-222a-aa22-2a2aa2aaa2a2", 
"subscriptionGuid": "a2a22aaa-22aa-222a-aa22-2a2aa2aaa2a2", 
"resourceGroupName": "test", 
"storageAccountName": "test", 
"containerName": "test", 
"directoryName": "test", 
"exportNameCost": "test", 
"exportNameAmortized": "test1", 
"tenancyId": "a2a22aaa-22aa-222a-aa22-2a2aa2aaa2a2" 
}, 
"additionalData": {}, 
"createdAt": "2025-02-27T10:51:38Z", 
"consumerOrgId": "", 
"byodVendor": "ABSENT" 
} 
}
```

```
curl --location --request PUT 'https://api.cloudability.com/v3/vendors/azure/accounts/a1a11111-111a-1111-11a1-a1111a1a1111:aa1111aa-aaa1-1aa1-111a-a1aa1a111a1a_2024-09-30?viewId=0' \ 
--header 'Content-Type: application/json' \ 
--data '{ 
"vendorAccountId": "a1a11111-111a-1111-11a1-a1111a1a1111:aa1111aa-aaa1-1aa1-111a-a1aa1a111a1a_2024-09-30", 
"type": "azure_mpa", 
"tenantId": "11111111-11a1-11aa-1111-111a111a1a11", 
"consumerOrgId": "111111", 
"costReportSpec": { 
"subscriptionGuid": "11111111-11a1-11aa-1111-111a111a1a22", 
"resourceGroupName": "tes_resource", 
"storageAccountName": "test_storage", 
"containerName": "test_container", 
"directoryName": "test_dir", 
"exportNameCost": "test_cost", 
"exportNameAmortized": "test_amortized" 
} 
}' 
```

```
{ 
"result": { 
"id": "a1a11111-111a-1111-11a1-a1111a1a1111:aa1111aa-aaa1-1aa1-111a-a1aa1a111a1a_2024-09-30", 
"vendorAccountName": "a1a11111-111a-1111-11a1-a1111a1a1111:aa1111aa-aaa1-1aa1-111a-a1aa1a111a1a_2024-09-30", 
"vendorAccountId": "a1a11111-111a-1111-11a1-a1111a1a1111:aa1111aa-aaa1-1aa1-111a-a1aa1a111a1a_2024-09-30", 
"vendorKey": "azure", 
"verification": { 
"state": "unverified" 
}, 
"authorization": { 
"type": "azure_mpa", 
"tenantId": "11111111-11a1-11aa-1111-111a111a1a11", 
"subscriptionGuid": "11111111-11a1-11aa-1111-111a111a1a22", 
"resourceGroupName": "tes_resource", 
"storageAccountName": "test_storage", 
"containerName": "test_container", 
"directoryName": "test_dir", 
"exportNameCost": "test_cost", 
"exportNameAmortized": "test_amortized", 
"tenancyId": "11111111-11a1-11aa-1111-111a111a1a11" 
}, 
"additionalData": {}, 
"createdAt": "2025-12-17T08:32:10Z", 
"consumerOrgId": "113924", 
"byodVendor": "ABSENT" 
} 
} 
```

```
curl 'https://api.cloudability.com/v3/vendors/azure/accounts/<account-id>/setup-scripts?viewId=0' \\ 
 -u ‘[auth_token]:’ 
```

```
{ 
"result": { 
"scripts": "script content........" 
} 
}
```

```
curl -X POST 'https://api.cloudability.com/v3/vendors/azure/accounts/<account-id>/verification?viewId=0' \\ 
 -u ‘[auth_token]:’
```

```
{ 
"result": { 
"id": "11111111", 
"vendorAccountName": "11111111", 
"vendorAccountId": "11111111", 
"vendorKey": "azure", 
"verification": { 
"state": "error", 
"message": "Azure EA account cannot be verified because of below reasons:\n1. AZURE_ENROLLMENT_READER(billing:EnrollmentReader) role has not been assigned to Cloudability's Service Principal\n2. Azure EA API access key is Absent/Invalid/Expired\n3. All the Blob Storage related parameters are not provided/Invalid\nOne of the above mentioned reasons should be addressed.", 
"lastVerificationAttemptedAt": "2025-12-17T09:48:07Z" 
}, 
"authorization": { 
"type": "azure_enrollment", 
"enrollmentId": "11111111", 
"tenantId": "11a1a111-1111-1111-1111-11aa11111a11", 
"subscriptionGuid": "aaa111aa1-aa11-11a1-1aa1-aa11a1a1aaaa", 
"resourceGroupName": "costexport", 
"storageAccountName": "test", 
"containerName": "test", 
"directoryName": "test", 
"exportNameCost": "test", 
"exportNameAmortized": "test", 
"tenancyId": "11a1a111-1111-1111-1111-11aa11111a11" 
}, 
"additionalData": {}, 
"createdAt": "2024-01-31T12:20:03Z", 
"consumerOrgId": "" 
} 
}
```

```
curl -X POST 'https://api-s.cloudability.com/v3/vendors/azure/accounts/<account-id>/archive?viewId=0' \\ 
 -u ‘[auth_token]:’
```

```
{ 
"result": { 
"id": "11111111", 
"vendorAccountName": "11111111", 
"vendorAccountId": "11111111", 
"vendorKey": "azure", 
"verification": { 
"state": "archived" 
}, 
"meta": {}, 
"consumerOrgId": "" 
} 
}
```

```
curl -X DELETE 'https://api.cloudability.com/v3/vendors/azure/accounts/[account-id]?viewId=0' \\ 
 -u ‘[auth_token]:’ 
```

```
{ 
"result": { 
"message": "Successfully deleted", 
"vendorKey": "azure", 
"vendorAccountId": "11111111" 
} 
}
```

---

## Vendor Credentials End Points (GCP)

<!-- sub-header -->
- **breadcrumb:** Cloudability API > Vendor Credentials End Points (GCP)
- **source_path:** SSVCLNQ/api-v3/gcp-vendor-credential-end-points.html
- **original_file:** api-vendor-credentials-end-points-gcp.md
- **images:** []

## Vendor Credentials End Points (GCP)

Summary

This end point is used to manage GCP within Cloudability that support the creation, updation and deletion of GCP credentials.

This end point does not support filtering and sorting.

With Cloudability being available in multiple regions, all references to api.cloudability.com in this API documentation should be referred to as mentioned in Getting started with Cloudability API V3 .

End Point Particulars

end point : /v3/vendors/gcp/accounts

end point : /v3/vendors/gcp/accounts/[account_id]?viewId=0

end point : /v3/vendors/gcp/accounts/[account_id]/setup-scripts

end point : /v3/vendors/gcp/permissions/accounts/[account_id]

end point : /v3/vendors/gcp/accounts/[account_id]/verification

end point : /v3/vendors/gcp/accounts/[account_id]/archive

The Credential Object

tableFqn (string) - combination of project-id:dataset_id.gcp_billing_export (project-id:dataset_id.gcp_billing_export_v1_11F1AC_1111A1_11CA11)

gcpOrgId (string) - the gcp organizationId (needs to be provided if gcp automation is used)

consumerOrgId (string) - if the account belongs to msp_consumer, this is the orgId of MSP_CONSUMER (optional, needs to be provided only if it belongs to MSP)

rlbdate (string) - resource label billing date (optional- required in case of GCP Detailed Billing)

isResourceLevelBillingRequired (boolean)) - it can have true/false (optional- required in case of GCP Detailed Billing)

vendorAccountName (string) - GCP vendor Account ID of customers

vendorKey (string) - states the vendor type (GCP)

verification (string) -contains state of the account

state (string) -it specifies whether the account is in verified/unverified/error state

authorization (string) - contains the below details:

type (string) - the provider type

tableName (string) - billing export table name

projectId (string) - billing export project Id

datasetId (string) - billing export dataset Id

bucketName (string) - the gcp bucket name (optional- required in case of GCP Detailed Billing/GCS)

permissions (string) - contains all permission present in a given GCP account after verification

createdAt ( string) - the timestamp at which the account is credentialized

script (string) - the script required to setup GCP role in customer's account

```
curl 'https://api.cloudability.com/v3/vendors/gcp/accounts?viewId=0' \\ 
 -u ‘[auth_token]:’ 
```

```
{ 
"result": [ 
{ 
"id": "111A11-11A1AA-1A1111", 
"vendorAccountName": "111A11-11A1AA-1A1111", 
"vendorAccountId": "111A11-11A1AA-1A1111", 
"vendorKey": "gcp", 
"verification": { 
"state": "verified", 
"lastVerificationAttemptedAt": "2025-12-16T05:22:18Z" 
}, 
"authorization": { 
"type": "gcp_role", 
"permissions": [ 
"bigquery.jobs.create", 
"compute.commitments.list", 
"compute.instances.list", 
"bigquery.tables.getData", 
"compute.disks.list", 
"monitoring.timeSeries.list" 
], 
"tableName": "gcp_billing_export_v1_111A11_11A1AA_1A1111", 
"projectId": "final-best-project", 
"datasetId": "Standard_billing", 
"turboExecutionEnabled": false 
}, 
"createdAt": "2023-09-20T16:50:44Z", 
"consumerOrgId": "" 
}, 
] 
}
```

Create GCP credential for Standard Billing account

```
curl --location 'https://api.cloudability.com/v3/vendors/gcp/accounts' \
     --header 'Content-Type: application/json' \
     --data '{
	       "type": "gcp_role",
	       "tableFqn": "samplestandard:sample.gcp_billing_export_v1_11A1DD-D1F1E1-K11111",
	       "gcpOrgId": "",
	       "consumerOrgId": "",
	       "rlbdate": "",
	       "bucketName": "test1",
	       "isResourceLevelBillingRequired": false
				}'
```

```
{
 "result": {
	     "id": "1A1DD-D1F1E1-K11111",
	     "vendorAccountName": "1A1DD-D1F1E1-K11111",
	     "vendorAccountId": "1A1DD-D1F1E1-K11111",
	     "vendorKey": "gcp",
	     "verification": {
	     "state": "unverified"
			     },
	     "authorization": {
				"type": "gcp_role",
				"bucketName": "test1",
				"tableName": "gcp_billing_export_v1_1A1DD-D1F1E1-K11111",
				"projectId": "samplestandard",
				"datasetId": "sample"
				},
				"createdAt": "2023-12-27T11:37:50Z",
				"consumerOrgId": ""
				}
				}
```

```
ccurl --location 'https://api.cloudability.com/v3/vendors/gcp/accounts' \ 
     --header 'Content-Type: application/json' \ 
     --data ' { 
    "type": "gcp_role", 
    "tableFqn": "test12:billing_gcp12.gcp_billing_export_resource_v1_11A111_A11A1A_1A11A1", 
    "gcpOrgId": "", 
    "consumerOrgId": "", 
    "rlbdate": "2024-12", 
    "bucketName": "testBucket", 
    "isResourceLevelBillingRequired": true, 
    "turboExecutionEnabled": false 
}' 
```

Upon successful creation the API will return the credentials object.

```
curl -X POST 'https://api.cloudability.com/v3/vendors/gcp/accounts' \\ 
 -H 'Content-Type: application/json' \\ 
 -u ‘[auth_token]:’ \\ 
 -d @- << EOF 
{ 
"type": "gcp_role", 
"projectId": "final-best-project" 
} 
```

Upon successful creation the API will return the credentials object.

Update the GCP credential with the given ID

```
curl --location 'https://api.cloudability.com/v3/vendors/gcp/accounts/01A4DD-D4F7E3-F19690?viewId=0' \
	 --header 'Content-Type: application/json' \
	 --data '{
		  "vendorAccountId": "01A1DD-D1F1E1-F11111",
		  "type": "gcp_role",
		  "tableFqn": "samplestandard:sample.gcp_billing_export_v1_01A1DD-D1F1E1-F11111",
		  "consumerOrgId": "",
		  "bucketName": "sampleData",
		  "isResourceLevelBillingRequired": false,
		  "rlbdate": "",
		  "gcpOrgId": ""
				}'
```

```
{
 "result": {
 "id": "01A1DD-D1F1E1-F11111",
 "vendorAccountName": "01A1DD-D1F1E1-F11111",
 "vendorAccountId": "01A1DD-D1F1E1-F11111",
 "vendorKey": "gcp",
 "verification": {
		   "state": "unverified"
		  },
 "authorization": {
		    "type": "gcp_role",
		    "bucketName": "sampleData",
		    "tableName": "gcp_billing_export_v1_01A1DD-D1F1E1-F11111",
		    "projectId": "samplestandard",
		    "datasetId": "sample"
		   },
		    "createdAt": "2023-12-20T01:15:23Z",
		    "consumerOrgId": ""
		   }
		   }
```

```
curl 'https://api.cloudability.com/v3/vendors/gcp/accounts/[account-id]/setup-scripts?viewId=0' \\ 
 -u ‘[auth_token]:’
```

```
{
 "result": {
	     "scripts": "gcloud iam roles create CloudabilityRole_Billing \\\n --project \\\n samplestandard \\\n --title \\\n \"Cloudability Billing Role\" \\\n --description \\\n \"Allows Cloudability access to billing account data\" \\\n --permissions \\\n bigquery.jobs.create,bigquery.tables.getData,bigquery.tables.export,storage.buckets.get,storage.buckets.getIamPolicy,storage.multipartUploads.abort,storage.multipartUploads.create,storage.multipartUploads.list,storage.multipartUploads.listParts,storage.objects.create,storage.objects.delete,storage.objects.get,storage.objects.list,storage.objects.update \\\n --stage=GA \ngsutil iam ch serviceAccount:billing-data-service-acct@cloudability-credentials.iam.gserviceaccount.com:projects/samplestandard/roles/CloudabilityRole_Billing gs://sampleData\ngcloud projects add-iam-policy-binding samplestandard \\\n --member serviceAccount:billing-data-service-acct@cloudability-credentials.iam.gserviceaccount.com \\\n --role 'projects/samplestandard/roles/CloudabilityRole_Billing'"
	    }
	    }
}
```

Verifies GCP Credential with a given ID

```
when verification fails

{
 "result": {
 "id": "11A1DD-D1F1E1-K11111",
 "vendorAccountName": "11A1DD-D1F1E1-K11111",
 "vendorAccountId": "11A1DD-D1F1E1-K11111",
 "vendorKey": "gcp",
 "verification": {
 "state": "error",
 "message": "The Cloudability role or service account key does not have IAM role(s) with sufficient permissions assigned to it. Please ensure that the role or service account has the following permissions: [bigquery.jobs.create, bigquery.tables.getData, bigquery.tables.export, storage.buckets.get, storage.buckets.getIamPolicy, storage.multipartUploads.abort, storage.multipartUploads.create, storage.multipartUploads.list, storage.multipartUploads.listParts, storage.objects.create, storage.objects.delete, storage.objects.get, storage.objects.list, storage.objects.update]",
 "lastVerificationAttemptedAt": "2023-12-27T11:42:25Z"
 },
  "authorization": {
  "type": "gcp_role",
  "bucketName": "test1",
  "tableName": "gcp_billing_export_v1_11A1DD-D1F1E1-K11111",
  "projectId": "samplestandard",
  "datasetId": "sample"
},
  "createdAt": "2023-12-27T11:37:50Z",
 "consumerOrgId": ""
}
}





when verification succeeds

{
  "result": {
  "id": "11F1AC-1111A1-11CA11",
  "vendorAccountName": "11F1AC-1111A1-11CA11",
  "vendorAccountId": "11F1AC-1111A1-11CA11",
  "vendorKey": "gcp",
  "verification": {
  "state": "verified",
  "lastVerificationAttemptedAt": "2023-12-27T11:53:25Z"
  },
  "authorization": {
  "type": "gcp_role",
  "permissions": [
  "bigquery.tables.getData",
  "consumerprocurement.orders.get",
  "consumerprocurement.orders.list",
  "bigquery.jobs.create"
                 ],
		   "tableName": "gcp_billing_export_v1_11F1AC-1111A1-11CA11",
		   "projectId": "cldy-billing-data",
		   "datasetId": "cloudability_billing_gcp"
		   },
		   "createdAt": "2020-04-23T16:42:42Z",
		   "consumerOrgId": ""
		   }
}
```

```
curl -X POST 'https://api.cloudability.com/v3/vendors/gcp/accounts/[account-id]/archive?viewId=0' \\ 
    -u ‘[auth_token]:’ 
```

```
{
 "result": {
	     "id": "11A1DD-D1F1E1-K11111",
	     "vendorAccountName": "11A1DD-D1F1E1-K11111",
	     "vendorAccountId": "11A1DD-D1F1E1-K11111",
	     "vendorKey": "gcp",
	     "verification": {
	     "state": "archived"
	    },
	     "meta": {},
	     "consumerOrgId": ""
	    }
}
```

```
curl -X DELETE 'https://api.cloudability.com/v3/vendors/gcp/accounts/[account-id]?viewId=0' \\ 
    -u ‘[auth_token]:’
```

```
{
 "result": {
	     "message": "Successfully deleted",
	     "vendorKey": "gcp",
	     "vendorAccountId": "11A1DD-D1F1E1-K11111"
	     }
}
```

---

## Vendor Credentials End Points (IBM)

<!-- sub-header -->
- **breadcrumb:** Cloudability API > Vendor Credentials End Points (IBM)
- **source_path:** SSVCLNQ/api-v3/vendor_credentials_end_points_ibm.html
- **original_file:** api-vendor-credentials-end-points.md
- **images:** []

## Vendor Credentials End Points (IBM)

Summary

This end point is used to manage credentials within Cloudability that support the integration and ingestion of data from public cloud vendors. This includes tasks such as initial setup, listing out current credentials and deleting deprecated credentials. This end point does not support filtering and sorting.

With Cloudability being available in multiple regions, all references to api.cloudability.com in this API documentation should be referred to as mentioned in Getting started with Cloudability API V3 .

End Point Particulars

end point : /v3/vendors/ibm/accounts for RESTful CRUD interactions

end point : /v3/vendors/ibm/accounts?viewId=0

end point : /v3/vendors/ibm/accounts/<account_id>?include=permissions&viewId=0

end point : /v3/vendors/ibm/accounts/<account_id>

end point : /v3/vendors/ibm/accounts/<account_id>?viewId=0

end point : / v3/vendors/ibm/accounts/<account_id>/verification? include=permissions,associatedAccounts&viewId=0

end point : /v3/vendors/ibm/accounts/<account_id>/terraform-template

end point : /v3/vendors/ibm/accounts/<account_id>/archive?viewId=0

end point : /v3/vendors/ibm/permissions/accounts/<account_id>

end point : /v3/vendors/ibm/accounts?include=permissions&viewId=0

Parameters

- vendorAccountID (string) - account id of IBM cloud
- region (string) - region of the account
- enterpriseID (string) - enterprise id of the IBM account
- IbmCostReportSpec:
- costReportName - manifest file name costPrefix - path of the manifest file bucketName (string) - name of the bucket present in the IBM account bucketRegion - region of bucket present in IBM account storageInstantName - instance name of storage

To ensure the API returns all accounts with these credential requests, add viewId=0 as a URL parameter. This will ensure any default view on your user account isn't applied.

List Accounts

Example Request

```
curl 'https://api.cloudability.com/v3/vendors/ibm/accounts?viewId=0' \\ 
   -u ‘[auth_token]:’ 
```

Example Request

```

{ 
"result": [ 
{ 
"id": "1111aaa11aaa1a1a111111111a11aa11", 
"vendorAccountName": "Master account", 
"vendorAccountId": "1111aaa11aaa1a1a111111111a11aa11", 
"vendorKey": "ibm", 
"verification": { 
"state": "verified", 
"lastVerificationAttemptedAt": "2026-02-04T11:14:11Z" 
}, 
"authorization": { 
"type": "ibm_role", 
"permissions": [ 
"ibm.list.accounts", 
"ibm.get.objects" 
], 
"bucketName": "apptio-cloud-integration-billing-data", 
"costAndUsageReport": { 
"name": "manifest", 
"prefix": "IBMCloud-Billing-Reports" 
}, 
"region": "us-east", 
"storageInstanceName": "Cloud Object Storage-apptio", 
"bucketRegion": "us-east", 
"enterpriseId": "3333aaa33aaa3a3a233333333a33aa22" 
}, 
"createdAt": "2025-12-13T09:09:48Z", 
"consumerOrgId": "", 
"byodVendor": "ABSENT" 
}, 
{ 
"id": "2222aaa22aaa2a2a222222222a22aa22", 
"vendorAccountName": "Child account", 
"vendorAccountId": "2222aaa22aaa2a2a222222222a22aa22", 
"vendorKey": "ibm", 
"meta": {}, 
"parentAccountId": "1111aaa11aaa1a1a111111111a11aa11", 
"consumerOrgId": "" 
} 
] 
} 
```

Create Master Payer

```
POST /v3/vendors/ibm/accounts?viewId=0
```

Example Request

```
curl -X POST 'https://api.cloudability.com/v3/vendors/ibm/accounts?viewId=0\\ 
-H 'Content-Type: application/json' \\ 
-u ‘[auth_token]:’ \\ 
-d @- << EOF 

{ 
   "vendorAccountId": "1234567", 
   "region": "us-east", 
   "enterpriseId": "6dd1xxxx109xxxx1be976xxxxd6d62df", 
   "ibmCostReportSpec": { 
   	"bucketName": "daily-cost-exports-enterprise", 
   	"bucketRegion": "us-east", 
       "storageInstanceName": "Cloud Object Storage-InEnterpriseAccount", 
       "costReportName": "manifest", 
       "costPrefix": "IBMCloud-Billing-Reports" 
}, 
      "type": "ibm_role" 
} 
```

Upon successful creation the API will return the credentials object.

Update Master Payer

PUT /v3/vendors/ibm/accounts/<account_id>?include=permissions&viewId=0

Example Request

```
curl -X PUT 'https://api.cloudability.com/v3/vendors/ibm/accounts/<account_id>?viewId=0\\ 
-H 'Content-Type: application/json' \\ 
-u ‘[auth_token]:’ \\ 
-d @- << EOF 

{ 
   "vendorAccountId": "1234567", 
   "region": "us-east", 
   "enterpriseId": "6dd1xxxx109xxxx1be976xxxxd6d62df", 
   "ibmCostReportSpec": { 
   	"bucketName": "daily-cost-exports-enterprise", 
   	"bucketRegion": "us-east", 
       "storageInstanceName": "Cloud Object Storage-InEnterpriseAccount", 
       "costReportName": "manifest", 
       "costPrefix": "IBMCloud-Billing-Reports" 
}, 
      "type": "ibm_role" 
}  
```

Retrieve Account

```
GET /v3/vendors/ibm/accounts/<account_id>?viewId=0
```

Example Request

```
curl 
'https://api.cloudability.com/v3/vendors/ibm/accounts/<account_id>’\\ 
-u ‘[auth_token]:’ 
```

Delete Credential for Account

```
DELETE /v3/vendors/ibm/accounts/<account_id>?viewId=0
```

Example Request

```
curl 
'https://api.cloudability.com/v3/vendors/ibm/accounts/<account_id>?viewId=0\\ 
-u ‘[auth_token]:’  
```

Verify Credential for Account

```
POST v3/vendors/ibm/accounts/<account_id>/verification?include=permissions,associatedAccounts&viewId=0
```

Example Request

```
curl --X POST
'https://api.cloudability.com/v3/vendors/ibm/accounts/<account_id>/verification?include=permissions,associatedAccounts&viewId=0’\\
-u ‘[auth_token]:’
```

Get Terraform Template for Account

```
GET /v3/vendors/ibm/accounts/<account_id>/terraform-template
```

Example Request

```
 curl
'https://api.cloudability.com/v3/vendors/ibm/<account_id>/terraform-template’\\
-u ‘[auth_token]:’ 
```

Archive Account

```
POST /v3/vendors/ibm/accounts/<account_id>/archive?viewId=0
```

Example Request

```
 curl --X POST
'https://api.cloudability.com/v3/vendors/ibm/accounts/<account_id>archive?viewId=0’\\
-u ‘[auth_token]:’
```

Get Permissions for Account

```
GET /v3/vendors/ibm/permissions/accounts/<account_id>
```

Example Request

```
 curl --X GET
'https://api.cloudability.com/v3/vendors/ibm/permissions/accounts/<account_id>’
\\
-u ‘[auth_token]:’ 	
```

---

## Views End Point

<!-- sub-header -->
- **breadcrumb:** Cloudability API > Views End Point
- **source_path:** SSVCLNQ/api-v3/views_end_point.html
- **original_file:** api-views-end-point.md
- **images:** []

## Views End Point

Summary

The Views API end point can be used for all key tasks as it pertains to managing Cloudability Views . Cloudability Views allow our customers to give each and every user a unique view or set of views of your cloud spend and usage. It also supports limiting the scope of what is visible to individual users.

- This document defines all CRUD APIs for Views in Cloudability.
- Each API endpoint enables creating, reading, updating, or deleting user views and retrieving all views for a given user.
- All endpoints return data using a unified View Object Schema.
- The end point does not support filtering and sorting.

```
https://api.cloudability.com/v3
```

All endpoints require a valid bearer token.

| Header | Required | Description |
| --- | --- | --- |
| Header | Required | Description |
| Authorization | ✅ | Bearer token for authentication |
| Content-Type | ✅ | application/json |

| Operation | Method | Endpoint |
| --- | --- | --- |
| Operation | Method | Endpoint |
| Create a View | POST | /views |
| Get Details of a View | GET | /views/{viewId} |
| Get All Views for a User | GET | /views |
| Update a View | PUT | /views/{viewId} |
| Delete a View | DELETE | /views/{viewId} |

View Object

This object is returned by multiple endpoints such as Create , Get Details , List , and Update View .

| Field | Type | Description |
| --- | --- | --- |
| Field | Type | Description |
| id | string | Unique identifier of the view |
| title | string | Title or name of the view |
| description | string | Description of the view |
| sharedWithOrganization | boolean | Whether the view is shared organization-wide |
| ownerId | string | ID of the user who created the view |
| parentViewId | string | ID of the parent view (if hierarchical) |
| sharedWithUsers | array[string] | User IDs the view is shared with |
| sharedOrgUnitIDs | array[string] | Organization unit IDs this view is shared with |
| filters | array[Filter Object] | Filters applied to the view |
| ownerEmail | string | Owner email id |
| derivedUserIds | (array[object]) | Users who have inherited access to this view through shared org units. Each object contains ViewID (string) and UserID (string) [Hierarchical View] |
| derivedOrgUnitIDs | (array[object]) | Org units that have inherited access through parent view sharing. Each object contains ViewID (string) and OrgUnitID (string)[Hierarchical View] |
| viewSource | string | Source of the view. Possible values: SYSTEM, BUSINESS_MAPPING |
| viewSourceId | string | ID referencing the source entity (e.g. business mapping ID) if applicable, empty string otherwise [Hierarchical View] |
| mappedViewIds | (array[string]) | IDs of child or related views mapped to this view (used in view hierarchies) |
| defaultUserIds | (array[integer]) | User IDs for whom this view is set as their default view |

| Field | Type | Description |
| --- | --- | --- |
| Field | Type | Description |
| field | string | Field name used for filtering |
| comparator | string | Comparison operator ( == , =@ , != , >= , etc.) |
| value | string | Value used in filter condition |

### Create a View

Endpoint

```
POST /views
```

Description

Creates a new view and returns the created View object.

Request Body

| Field | Type | Required | Description |
| --- | --- | --- | --- |
| Field | Type | Required | Description |
| title | string | ✅ | Title of the view |
| filters | array[Filter Object] | ✅ | Filters applied to the view |
| description | string | ❌ | Description of the view |
| sharedWithOrganization | boolean | ❌ | Whether shared organization-wide |
| sharedWithUsers | array[string] | ❌ | User IDs the view is shared with |
| sharedOrgUnitIDs | array[string] | ❌ | IDs of user groups or Entra ID groups |

Example Request (Create a view shared with Organization)

```
curl -X POST 'https://api.cloudability.com/v3/views' \
--header 'authorization: Bearer <Auth Token>' \
--header 'content-type: application/json' \
--data '{
    "title": "Test View Amazon23",
    "description": "vendor view",
    "filters": [
        {
            "field": "vendor",
            "comparator": "==",
            "value": "Amazon"
        }
    ],
    "sharedWithOrganization": true,
    "sharedWithUsers": [
    ],
    "sharedOrgUnitIDs": []
}'
```

Example Response

Returns a single view Object.

```
{
    "result": {
        "id": "123",
        "title": "Test View Amazon",
        "description": "vendor view",
        "ownerId": "1234",
        "sharedWithUsers": [
            "12345"
        ],
        "derivedUserIds": [],
        "derivedOrgUnitIDs": [],
        "sharedWithOrganization": true,
        "filters": [
            {
                "field": "vendor",
                "comparator": "==",
                "value": "Amazon"
            }
        ],
        "parentViewId": "-1",
        "viewSource": "SYSTEM",
        "ownerEmail": "xyz.xyz@ibm.com"
    }
} 
```

Example Request (Create a view shared with specific Users)

POST your JSON payload to the /views end point with your sharedWithUsers attribute containing a list of userIDs the view is to be shared with. The sharedWithOrganization attribute should be set to false .

```
curl -X POST 'https://api.cloudability.com/v3/views' \
--header 'authorization: Bearer <Auth Token>' \
--header 'content-type: application/json' \
--data '{
    "title": "Test View Amazon",
    "description": "vendor view",
    "filters": [
        {
            "field": "vendor",
            "comparator": "==",
            "value": "Amazon"
        }
    ],
    "sharedWithOrganization": false,
    "sharedWithUsers": [
        "1234"
    ],
    "sharedOrgUnitIDs": []
}'
```

### Get Details of a View

Endpoint

```
GET /views/{viewId}
```

Description

Retrieves detailed information for a specific view.

Example Request

```
curl https://api.cloudability.com/v3/views/{viewId} \
  -H "Authorization: Bearer <auth_token>"
```

Example Response

```
{
    "result": {
        "id": "1234",
        "title": "test_view",
        "description": "",
        "ownerId": "123",
        "sharedWithUsers": [
            "12345"
        ],
        "derivedUserIds": [],
        "derivedOrgUnitIDs": [],
        "sharedWithOrganization": false,
        "filters": [
            {
                "field": "vendor",
                "comparator": "==",
                "value": "Amazon"
            }
        ],
        "parentViewId": "-1",
        "viewSource": "SYSTEM",
        "ownerEmail": "xyz@xyz.com"
    }
}
```

### Getting List of Views for a User

Endpoint

```
GET /views
```

Description

Retrieves all views accessible to the specified user. If user is an admin of the org then all the views of the org will be returned by the API (except the private views).

```
curl https://api.cloudability.com/v3/views \
  -H "Authorization: Bearer <auth_token>"
```

```
{
    "result": [
        {
            "id": "1234",
            "title": "AWS Dashboard view test",
            "description": "Test view for AWS dashboard",
            "ownerId": "123",
            "sharedWithUsers": [],
            "derivedUserIds": [],
            "derivedOrgUnitIDs": [],
            "sharedWithOrganization": true,
            "filters": [
                {
                    "field": "vendor",
                    "comparator": "==",
                    "value": "Amazon"
                }
            ],
            "parentViewId": "-1",
            "viewSource": "SYSTEM",
            "ownerEmail": "xyz@xyz.com"
        },
        {
            "id": "12345",
            "title": "Test View",
            "description": "",
            "ownerId": "123",
            "sharedWithUsers": [],
            "derivedUserIds": [],
            "derivedOrgUnitIDs": [],
            "sharedWithOrganization": true,
            "filters": [
                {
                    "field": "category13",
                    "comparator": "==",
                    "value": "xyz"
                }
            ],
            "parentViewId": "-1",
            "viewSource": "SYSTEM",
            "ownerEmail": "xyz@xyz.com"
        }
    ]
}
```

### Update a View

Endpoint

```
PUT /views/{viewId}
```

Description

Updates details of an existing view..

Example Request

```
curl -X PUT https://api.cloudability.com/v3/views/{viewId} \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer <auth_token>" \
  --data '{
    "title": "test_view",
    "description": "",
    "filters": [
        {
            "field": "vendor",
            "comparator": "==",
            "value": "Amazon"
        }
    ],
    "sharedWithOrganization": false,
    "sharedWithUsers": [
        "1234"
    ],
    "sharedOrgUnitIDs": []
}
```

```
{
    "result": {
        "id": "123456",
        "title": "test_view",
        "description": "",
        "ownerId": "123",
        "sharedWithUsers": [
            "1234"
        ],
        "derivedUserIds": [],
        "derivedOrgUnitIDs": [],
        "sharedWithOrganization": false,
        "filters": [
            {
                "field": "vendor",
                "comparator": "==",
                "value": "Amazon"
            }
        ],
        "parentViewId": "-1",
        "viewSource": "SYSTEM",
        "ownerEmail": "abc.xyz@def.com"
    },
    "updatedViews": []
}
```

### Delete a View

Endpoint

```
DELETE /views/{viewId}
```

Description

Deletes a view permanently.

```
curl -X DELETE https://api.cloudability.com/v3/views/{viewId} \
  -H "Authorization: Bearer <auth_token>"
```

```
{
    "result": {
        "id": "12345",
        "title": "",
        "description": "",
        "ownerId": "",
        "sharedWithUsers": null,
        "derivedUserIds": null,
        "derivedOrgUnitIDs": null,
        "sharedWithOrganization": false,
        "filters": null
    },
    "deletedViewIds": [
        "12345"
    ]
}
```

### Error Responses for View APIs

| Status Code | Meaning | Example Message |
| --- | --- | --- |
| Status Code | Meaning | Example Message |
| 400 | Bad Request | Invalid or missing parameters |
| 401 | Unauthorized | Missing or invalid authentication token |
| 403 | Forbidden | SSO default view cannot be deleted / SSO default view cannot be unshared with the organization |
| 404 | Not Found | View not found |
| 422 | Unprocessable Entity | View is being used as a default by one or more users |
| 500 | Internal Server Error | Unexpected system error |

Special Note About Filters

Views are based on creating filters around Accounts , Account Groups or Tags . You can have multiple filters for any view.

The supported operators are:

!=@, =@, !=, ==, >=, <=, >, <

So for example to create a filter set for your first *account group * equals 'Production" AND tag number 5 contains 'farm' you'd have:

```
"filters": [
        {
          "label": "Env",
          "field": "group_name1",
          "comparator": "==",
          "value": "Production"
        },
        {
          "label": "Project Tag",
          "field": "tag5",
          "comparator": "=@",
          "value": "farm"
        }
      ]
```

Example Sequence - Add New View; Create New User Defaulted to View

Follow section above to create your view. This will return a view id which you can assign to any user as their default view. You can also get this id from your view list .

Now create a new user (or update a previous one) and include the view id in the default_dimension_filter_set_id attribute

```
curl -X POST https://app.cloudability.com/v3/users?auth_token=[auth_token] \\
     -H "Content-Type: application/json" \\
     -d @- << EOF
{
  "user": {
    "full_name": "John Doe",
    "role": "User",
    "restricted": false,
    "email": "john_doe@example.com",
    "default_dimension_filter_set_id": [view_id],
    "new_shared_dimension_filter_set_ids": []
  }
}
EOF
```

---
