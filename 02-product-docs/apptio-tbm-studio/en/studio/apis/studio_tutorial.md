---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "API tutorial: Download and upload v.12 Costing Standard table using Postman tool"
breadcrumb: []
source_path: "studio/apis/studio_tutorial.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# API tutorial: Download and upload v.12 Costing Standard table using Postman tool

## Requirements

- A user account in Enhanced Access Administration configured with API keys. For more information,
  see [Enhanced Access Administration API: Overview of API keys and
  FAQ](https://help.apptio.com/en-us/frontdoor/admin-guide/eaa-api/overview-api-keys-faq.html "(Opens in a new tab or window)").
  - The user account must be in the Enhanced Access Administration auth domain where the Costing
    Standard (CT) application resides.
  - The key must be granted access to the appropriate environment after it is created. Click the
    Grant Access link next to key name.
  - The user must have a Power User role for CT access, and possibly Datalink (Classic) Admin
    privileges if the same account is to be used in both applications. If the Power User role is not
    standard one or was modified, be sure permissions are set for the role to Allow Access to
    environments and Allow Export.
- The Costing Standard application with the user access (mentioned above) to the environment.
- The Postman application for this example. Similar applications, such as SoapUI, can be used via
  the same principals.

## User in Enhanced Access Administration

![](../../../resources/images/studio_images/studioimages/studio_11_800x683.png)

## Set up a Postman environment

This procedure
allows you to save environment variables within Postman. This is useful to chaining together
different requests in support of testing so that you don't have to copy and paste the
Apptio-opentoken repeatedly.

To set up the environment:

1. [Create a new Postman environment](https://learning.postman.com/docs/postman/variables-and-environments/variables/ "(Opens in a new tab or window)").

   ![](../../../resources/images/studio_images/studioimages/studio%2012.png)
2. Set the appropriate environment variables. In the following images, we use env, pub, secret, and
   token.

- env - This is blank to start - it gets populated later.
- pub - The public component of your API key.
- secret - The secret component of your API key.
- token - This is blank to start - it gets populated later.

![](../../../resources/images/studio_images/studioimages/studio%2013.png)

## Obtain an Opentoken from Frontdoor

For documentation about this example, see [Enhanced Access
Administration API: Authentication via API keys](https://community.apptio.com/docs/DOC-10522 "(Opens in a new tab or window)").

Post request URL: [https://frontdoor.apptio.com/service/apikeylogin](https://frontdoor.apptio.com/service/apikeylogin "(Opens in a new tab or window)")

Headers:

- Accept: application/json
- Content-Type: application/json

![](../../../resources/images/studio_images/studioimages/studio%2014_800x289.png)

Body (NOTE: Set body to raw format by selecting proper radio
button):

`{"keyAccess":"{{pub}}","keySecret":"{{secret}}"}`

![](../../../resources/images/studio_images/studioimages/studio%2015_800x266.png)

Under
Tests, set the following. This will set the value of your Token environment variable
when the POST executes:

`pm.environment.set("token",
pm.cookies.get('apptio-opentoken'));`

![](../../../resources/images/studio_images/studioimages/studio%2016_800x256.png)

Click
Save and then click Send for this POST. You should now see the Apptio-opentoken in the
cookies:

![](../../../resources/images/studio_images/studioimages/studio%2017_800x531.png)

And in your
environment variables:

![](../../../resources/images/studio_images/studioimages/studio%2018.png)

## Using Username/Password to authenticate

Using API Keys is the preferred method for authentication for security
reasons. However, if you are using a username and password instead of API Keys, you must create
environment variables for the user ID and password. Then, the body will appear similar to the
following example.

![](../../../resources/images/studio_images/studioimages/studio%2019.png)

For more
information, see [Frontdoor API: Basic authentication using a user name and
password](https://community.apptio.com/docs/DOC-10529 "(Opens in a new tab or window)").

## GET the Environment ID

The call to get an
environment ID is not needed if you already know what the ID is. The ID does not change unless an
application like CT Enhanced Access Administration configuration is modified. For more information,
see [Frontdoor API: Get user environment information](https://community.apptio.com/docs/DOC-10459 "(Opens in a new tab or window)").

NOTE: Be sure to substitute
your domain name for the placeholder yourdomain.com and your Enhanced Access Administration
environment name (this is typically main) for the placeholder yourfrontdoorenv in the
following URL:

GET request URL: [https://frontdoor.apptio.com/api/environment/yourdomain.com/yourfrontdoorenv](https://frontdoor.apptio.com/api/environment/yourdomain.com/yourfrontdoorenv "(Opens in a new tab or window)")

Headers:

- content-type: application/json
- apptio-opentoken: {{token}}

![](../../../resources/images/studio_images/studioimages/studio%2020.png)

Use the
following in the Tests:

```
var jsonData = pm.response.json();

pm.environment.set("env", jsonData.id);
```

Click Save and then click
Send. You should see the environment ID in the body:

![](../../../resources/images/studio_images/studioimages/studio%2021.png)

And in your
environment's variables:

![](../../../resources/images/studio_images/studioimages/studio%2022.png)

## Upload a Table

For more information, see the examples in
Introduction to the [../../admin/the-apptio-api.html](../../admin/the-apptio-api.html "(Opens in a new tab or window)")[Platform
API](../../admin/the-apptio-api.html "(Opens in a new tab or window)").

POST request URL: [https://domain.apptio.com/biit/api/v1/domain.com/Project%20Name/Test%20Table/Jan%3AFY2017/overwrite](https://domain.apptio.com/biit/api/v1/domain.com/Project%20Name/Test%20Table/Jan:FY2017/overwrite "(Opens in a new tab or window)")

Headers:

- content-type: application/json
- apptio-opentoken: {{token}}
- apptio-current-environment: {{env}}

![](../../../resources/images/studio_images/studioimages/studio%2023.png)

In the
Body, specify the file to upload:

![](../../../resources/images/studio_images/studioimages/studio%2024.png)

Click Save,
and then click Send. If everything is set correctly, you should get some json in the response
body that looks similar to this example.

![](../../../resources/images/studio_images/studioimages/studio%2025.png)

## Download a Table

For more information, see the
examples in Introduction to the [Platform API](../../admin/the-apptio-api.html "(Opens in a new tab or window)").

Note: Be sure to substitute values appropriate to your
situation in the following sample URL:

GET request URL: See the Table section of [studio\_api\_download\_data.htm](studio_api_download_data.htm "(Opens in a new tab or window)")[API: Downloading data](studio_api_download_data.htm "(Opens in a new tab or window)") for
details on how to obtain a table API URL.

Headers:

- content-type: text/tab-separated-values
- apptio-opentoken: {{token}}
- apptio-current-environment: {{env}}

![](../../../resources/images/studio_images/studioimages/studio%2026.png)

## Download a Report Table

GET request URL: See
[studio\_api\_download\_data.htm](studio_api_download_data.htm "(Opens in a new tab or window)")[API: Downloading data](studio_api_download_data.htm "(Opens in a new tab or window)") for
details on how to obtain a reportAPI URL.

Headers:

- content-type: text/tab-separated-values
- apptio-opentoken: {{token}}
- apptio-current-environment: {{env}}

![](../../../resources/images/studio_images/studioimages/studio%2027.png)

For more
API information, see [../../admin/the-apptio-api.html](../../admin/the-apptio-api.html "(Opens in a new tab or window)")[Platform
API](../../admin/the-apptio-api.html "(Opens in a new tab or window)").
