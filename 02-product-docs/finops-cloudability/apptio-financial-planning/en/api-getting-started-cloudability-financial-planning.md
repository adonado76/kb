---
source_system: "apptio-financial-planning"
practice: "tbm"
language: "en"
doc_type: "financial-planning"
title: "Getting Started with Cloudability Financial Planning API"
breadcrumb:
  - "Cloudability Financial Planning API"
  - "Getting Started with Cloudability Financial Planning API"
source_path: "SSVWBC/cloud-financial-planning/admin/getting-started-cfp-api.html"
images: []
capability_ids: []
last_updated: "2026-07-10"
summary: ""
---
# Getting Started with Cloudability Financial Planning API

## API Authentication

You must use Frontdoor apptio-opentoken to authenticate Cloudability Financial Planning API requests. Cloudability API Keys are not supported at this time.

Permissions for API interactions to create, update, read, and delete correspond with Cloudability Financial Planning user permissions.

- API endpoint for EU instance: https://api-eu.cloudability.com/
- API endpoint for APAC instance: https://api-au.cloudability.com

All references to api.cloudability.com in this documentation should be referred to as api-eu.cloudability.com or api-au.cloudability.com by the customers hosted in the EU or the APAC region respectively

## Frontdoor apptio-opentoken

For information on how to get an apptio-opentoken, refer to Enhanced Access Administration API: Authentication via API keys

## API Interactions

API interactions with Cloudability are secured over HTTPS. You must pass the Apptio-Opentoken and Apptio-Current-Environment in header.

The following API returns a list of all plans in the specified view.

```
curl https://api.cloudability.com/v3/planning/plans?viewId=0 \
	-H "Accept-Language: en-US" \
	-H "apptio-opentoken: [apptio opentoken]" \
	-H "apptio-current-environment: [apptio Frontdoor environment id]"
```

## Headers

## Cloudability end point examples

The documentation for each end point will include a number of examples which will show how to interact with the API. The examples will use cURL for HTTP interactions and jq for parsing JSON. Both of these CLI tools are widely used and can be easily employed to interact with a RESTful API.
