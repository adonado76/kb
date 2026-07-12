---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Account Group Entries"
breadcrumb:
  - "Cloudability API"
  - "Account Group Entries"
source_path: "SSVCLNQ/api-v3/account_group_entries.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Account Group Entries

Manage Account Group Entries

Account Group Entries are the associations between a specific account and an account group. They link the two and only admins can create, update, and delete account groups entries. All users with API access can get their information.

Account Group Entries Object

- id (number) - Unique identifier for the Account Group Entries object
- account_group_id (number) - Unique identifier for the account group the value applies to
- account_identifier (string) - the unique identifier for the AWS account, Azure subscription or GCP project
- organization_service_account_id (number) - The internal Cloudability system ID of the account/subscription/project associated with this Account Group Entry
- value (string) – the value assigned to the account group for the account

Get a list of Account Group Entries

Example Query

```
curl https://api.cloudability.com/v3/account_group_entries -u ‘[auth_token]:’

```

Example Response

```
[
	{
		"id": 1,
		"account_group_id": 4672,
		"account_identifier": "1111-1111-1111",
		"organization_service_account_id": 123,
		"value": "red1"
	},
	{
		"id": 2,
		"account_group_id": 9582,
		"account_identifier": "2222-2222-2222",
		"organization_service_account_id": 123,
		"value": "red2"
	},
	{
		"id": 3,
		"account_group_id": 4672,
		"account_identifier": "1111-1111-1111",
		"organization_service_account_id": 123,
		"value": "orange1"
	}
]
```

Get a specific Account Group Entry

Example Query

```
curl https://api.cloudability.com/v3/account_group_entries/1

```

(Replace the value “1” above with the unique id of your account group entry)

Example response

```
[
	{
		"id": 1,
		"account_group_id": 4672,
		"account_identifier": "1111-1111-1111",
		"organization_service_account_id": 123,
		"value": "red1"
	}
]
```

Create an Account Group Entry

Example Query

```
curl -X POST https://api.cloudability.com/v3/account_group_entries \\
      -H 'Content-Type: application/json' \\
      -u ‘[auth_token]:’ \\
      -d @- << EOF
 {
 "account_group_id": 5686,
 "account_identifier": "1111-1111-1111",
 "value": "marketing team"
 }
 EOF
```

Upon successful creation the API will return the account group entries object

Update an Account Group Entry

Account Group Entries can have their values adjusted to any valid string, but cannot be repointed at difference Accounts or Account Groups (no error will be returned if attempted, however the update won’t be made). To do that, create a new Account Group Entry for the Account Group or Account in question.

Example Query

```
curl -X PUT https://api.cloudability.com/v3/account_group_entries/1 \\
      -H 'Content-Type: application/json' \\
      -u ‘[auth_token]:’ \\
      -d @- << EOF
 {
  "value": "legal team"
 }
EOF
```

Upon successful update the API will return the account group entries object

(Replace the value “1” above with the unique id of your account group entry)

Delete an Account Group Entry

Example Query

```
curl -X DELETE https://api.cloudability.com/v3/account_group_entries/1
-u ‘[auth_token]:’
```

(Replace the value “1” above with the unique id of your account group entry)

This will return a HTTP 204 status with no content on successful delete.
