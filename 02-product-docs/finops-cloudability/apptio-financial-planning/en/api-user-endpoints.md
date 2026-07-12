---
source_system: "apptio-financial-planning"
practice: "tbm"
language: "en"
doc_type: "financial-planning"
title: "User Endpoints"
breadcrumb:
  - "Cloudability Financial Planning API"
  - "User Endpoints"
source_path: "SSVWBC/cloud-financial-planning/admin/user-end-points.html"
images: []
capability_ids: []
last_updated: "2026-07-10"
summary: ""
---
# User Endpoints

*APIs used to retrieve CFP user identity and environment user lists.*

## Overview

```
userID
```

| User type | ID format | Typical use in Planning APIs | How to fetch |
| --- | --- | --- | --- |
| CFP user | UUID (string) | Used where the API expects CFP identities, e.g. subscribedUsers in Alerts | GET /v3/planning/whoami GET /v3/planning/users |
| Cloudability user | integer | Used where the API expects Cloudability identities, e.g. userId in query/body parameters. | GET /v3/users (Cloudability core API) |

- If the parameter is named subscribedUsers (array of UUIDs) → CFP user IDs .
- If the parameter is named userId and is an integer → Cloudability user ID .

Always follow the specific endpoint’s docs.

## CFP User Object

| Field | Type | Description |
| --- | --- | --- |
| id | string (UUID) | Id of the user (CFP userId) |
| email | string | Email of the user |
| fullName | string | Full name of the user |
| login | string | Login of the user |

Example CFP User Object

```
{
  "id": "d4ced04e-3333-48e8-994e-a365fa68808a",
  "email": "example@apptio.com",
  "login": "example@apptio.com",
  "fullName": "John Smith"
}

```

## Get Current User (CFP)

Returns the CFP userID for the current user (useful to obtain your CFP UUID for things like subscribedUsers in Alerts).

Endpoint

```
GET /v3/planning/whoami
```

Request Example

```
curl 'https://api.cloudability.com/v3/planning/whoami' \
  -H "Content-Type: application/json" \
  -H 'Apptio-Current-Environment: [apptio Frontdoor environment id]' \
  -H 'Apptio-Opentoken: [apptio opentoken]'

```

## Get List of Users (CFP)

Returns an array of CFP user objects ( UUIDs ) for the environment

Endpoint

```
GET /v3/planning/users
```

Request Example

```
curl 'https://api.cloudability.com/v3/planning/users' \
  -H "Content-Type: application/json" \
  -H 'Apptio-Current-Environment: [apptio Frontdoor environment id]' \
  -H 'Apptio-Opentoken: [apptio opentoken]'

```

## Cloudability User Object

| Field | Type | Description |
| --- | --- | --- |
| id | integer | Id of the user (Cloudability userId) |
| email | string | User’s Frontdoor email address |
| frontdoor_login | string | Frontdoor login of the user |
| frontdoor_user_id | string (UUID) | Frontdoor user id |
| full_name | string | Full name of the user as it will appear in user lists |
| shared_dimension_filter_set_id | integer | The view filter id that will load by default when the user opens the app. |
| shared_dimension_filter_set_ids | array<integer> | IDs of the views that are available to the user, including views that are shared with the user or the organization. |

Example Cloudability User Object

```
{
   "id": 1,
   "frontdoor_user_id": "33ab2211-2b2b-4411-ee99-d90v98475n", 
   "frontdoor_login": "john@cloudability.com",
   "email": "john@cloudability.com",
   "full_name": "John Doe",
   "default_dimension_filter_set_id": null,
   "shared_dimension_filter_set_ids": [12, 999, 3646]
}

```

## Get Cloudability User IDs

Returns an array of Cloudability user objects for the environment.

Endpoint

```
GET /v3/users
```

Request Example

```
curl 'https://api.cloudability.com/v3/users' \
  -H "apptio-environmentid: [apptio Frontdoor environment id]" \
  -H "apptio-opentoken: [apptio opentoken]"

```

- Header names differ from CFP endpoints ( apptio-environmentid / apptio-opentoken vs Apptio-Current-Environment / Apptio-Opentoken ).
- Always follow the specific endpoint’s docs.
