---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Anomaly Detection End Point"
breadcrumb:
  - "Cloudability API"
  - "Anomaly Detection End Point"
source_path: "SSVCLNQ/api-v3/anomaly-detection-end-point.html"
images:
  - "03-media/apptio-cloudability-standard/sout.gif"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Anomaly Detection End Point

## Summary

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

## The Anomalies Object

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

## How to generate an Apptio API key

Getting started with Cloudability API V3

## GET Anomalies Endpoint

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

## Query Parameters for id lookup

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

## More information on filters:

The get anomalies request does handle filter requests, but it will only work if provided valid Dimension, Operator and Value parameters. It is recommended to use the filters on the frontend because the Dimension, Operator and Value parameters will auto-populate based on the environment.

Example request with filters

```
curl --location 'https://api.cloudability.com/v3/anomalies?viewId=<viewId>&startDate=<year-month-day>&endDate=<year-month-day>&filter=<dimension><operator><value>' \
-u '<apptio api key>:'
```

## The Subscriptions Object

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

## POST Subscriptions Endpoint

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

## GET Subscriptions Endpoint

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

## PUT Subscription Endpoint:

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

## DELETE endpoint:

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
