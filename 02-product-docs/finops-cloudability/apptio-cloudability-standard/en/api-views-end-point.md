---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Views End Point"
breadcrumb:
  - "Cloudability API"
  - "Views End Point"
source_path: "SSVCLNQ/api-v3/views_end_point.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Views End Point

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

## Create a View

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

## Get Details of a View

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

## Getting List of Views for a User

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

## Update a View

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

## Delete a View

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

## Error Responses for View APIs

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
