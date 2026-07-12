---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Getting started with Cloudability API V3"
breadcrumb:
  - "Cloudability API"
  - "Getting started with Cloudability API V3"
source_path: "SSVCLNQ/api-v3/getting_started_with_the_cloudability.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Getting started with Cloudability API V3

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
