---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "API URL for uploading and editing user data in pre-Enhanced Access Administration systems"
breadcrumb: []
source_path: "studio/apis/studio_api_url_upload_edit.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# API URL for uploading and editing user data in pre-Enhanced Access Administration systems

Applies to: v11.x, v12.0, v12.1

Use the URL described below to bulk upload user data and to edit existing user data in
pre-Enhanced Access Administration systems

## URL

Use the following URL to upload a user table to
Apptio:

`https://[instance].apptio.com/biit/api/v1/[domain]/users/[userid]`

For
example, if your company is called abccompany and you wanted to automate your dev instance,
you would
use:

`https://[abccompany-dev].apptio.com/biit/api/v1/[abccompany.com]/users/[user@abccomany.com]user@abccomany.com]`

The
attributes used in the URL are described below.

| Attribute | Description |
| --- | --- |
| domain | The customer domain (e.g.: customer.com) |
| username | The ID of the account to create, formed as an email address (e.g.: joe@customer.com) |

To update a user with the API, perform an HTTP post of parameter-value pairs to the above
URL. The parameters that can be passed are described below.

| Parameter | Description |
| --- | --- |
| password | The new password to set for the user. NOTE: Setting a password of SSO, in any case, will trigger the user to become a Single Sign-On(SSO) user. |
| oldpassword | The old password to set for the user. Required when updating your own password. Optional for admins. |
| fullname | The full name of the user. |
| roles | A comma-separated list of roles that apply to this user. Users not available in the AdminDB will be removed. |
| lastproject | A domain:project string specifying the project to use as the user's last project. |
| lasttimeperiod | A month:year string specifying the period to use as the user's last selected time period. |
| singleusepassword | Designates if the password you are setting is a single-use password. Values: True, False. |

## Return codes

| Code | Description |
| --- | --- |
| 200 | Get Successful |
| 202 | Update Successful |
| 201 | Creation Successful |
| 400 | Incorrect API String |
| 500 | Internal Server Error |

## Responses

Responses are returned in JavaScript Object Notation (JSON). Successful responses will include
the username, full name, roles, and whether the user is set for SSO. Below is an example
response:

```
{
"username":"newUser@customer.com",
"roles":"Admin",
"issso":true,
"fullname":"Joe User"
}
```

Responses which are returned in case of error, simply return the message which describes the
error. Below is an example of an attempt to get information about a user that does not exist.

```
{
"message":"user newUser@customer.com does not exist"
}
```

## Curl examples

The following examples use Curl to interact with the Apptio user API. The –data-url-encode
argument to Curl tells it that the next argument in the command line is a parameter/value pair that
should be sent to Apptio.

Create
user:

```
curl -k -u 'api@customer.com:password' --data-urlencode "password=Password" --data-urlencode "fullname=Joe User" --data-urlencode "Roles=Admin" 
https://customer.apptio.com/biit/api/v1/customer.com/users/joe@customer.com//customer.apptio.com/biit/api/v1/customer.com/users/joe@customer.com
```

Edit
user:

```
curl -k -u 'api@customer.com:password' --data-urlencode "fullname=Joe The Plumber" 
https://customer.apptio.com/biit/api/v1/customer.com/users/joe@customer.com//customer.apptio.com/biit/api/v1/customer.com/users/joe@customer.com
```

Get user:

```
curl -k -u 'api@customer.com:password' 
https://customer.apptio.com/biit/api/v1/customer.com/users/joe@customer.com//customer.apptio.com/biit/api/v1/customer.com/users/joe@customer.com
```
