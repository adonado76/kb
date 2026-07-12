---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Users End Point"
breadcrumb:
  - "Cloudability API"
  - "Users End Point"
source_path: "SSVCLNQ/api-v3/users-end-point.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Users End Point

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

## Get Details of a User

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

## Getting List of Users

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

## Update User

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
