---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "About the Cloudability API"
breadcrumb:
  - "Cloudability API"
  - "About the Cloudability API"
source_path: "SSVCLNQ/api-v3/aboutcloudabilityapiv3.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# About the Cloudability API

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
