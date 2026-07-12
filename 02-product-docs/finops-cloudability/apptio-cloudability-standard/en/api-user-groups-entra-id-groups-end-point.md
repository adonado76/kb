---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "User Groups and Entra ID Groups End Point"
breadcrumb:
  - "Cloudability API"
  - "User Groups and Entra ID Groups End Point"
source_path: "SSVCLNQ/api-v3/user_entraid_groups_end_points.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# User Groups and Entra ID Groups End Point

## Summary

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

## User Groups APIs

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

## Entra ID Groups APIs

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
