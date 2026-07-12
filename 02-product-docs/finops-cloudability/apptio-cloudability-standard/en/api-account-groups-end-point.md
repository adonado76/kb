---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Account Groups End Point"
breadcrumb:
  - "Cloudability API"
  - "Account Groups End Point"
source_path: "SSVCLNQ/api-v3/account_groups_end_point.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Account Groups End Point

Manage Account Groups

Account Groups function like tags for AWS accounts, Azure Subscriptions and GCP projects. They allow you to assign a key/value pair where Account Group is the key and Account Group Entry maps the value. For example, you might create an Account Group of Environment and use Account Group Entries to assign a value of "Production", "Staging" or "Development" to individual cloud accounts in Cloudability.

In the Cloudability UI you can define Account Groups and Account Group Entries on the Accounts page. The API lets you perform programmatic CRUD-ing of the Account Groups and account group entries. Only admins can create, update, and delete Account Groups and Entries through the UI and API, while all other users can access the generated dimensions in dashboards and reports.

An Account Group can have many Account Group Entries, each entry mapping an account/project/subscription’s value for the group. Users are then able to report and filter against these defined account group keys with each one available as a reporting dimension throughout Cloudability.

End Point Particulars

/account_groups for all RESTful CRUD interactions

The Account Groups Object

id (number) - Unique identifier for the Account Group object

position (number) – The position of the account group in relation to all other account groups

name (string) – the name of the account group as it will appear throughout Cloudability

account_group_entry_values (array) – An informative list of current values for the account group. These values are updated via the Account Group Entries endpoint

Example Account Groups Object

```
{
	"id": 1,
	"position": 1,
	"name": "Project",
	"account_group_entry_values": [
		"Project timelapse",
		"Sunset",
		"Corporate"
	]
}
```

List Account Groups

List all current account groups

Example Request

curl https://api.cloudability.com/v3/account_groups -u ‘[auth_token]:’

Example Response

```
[
	{
		"id": 5784,
		"position": 1,
		"name": "Project",
		"account_group_entry_values": [
			"Project timelapse",
			"Sunset",
			"Corporate"
		]
	},
	{
		"id": 5785,
		"position": 2,
		"name": "Environment",
		"account_group_entry_values": [
			"Production",
			"Test",
			"Staging"
		]
	}
]
```

Get a specific Account Group

Example Request

curl https://api.cloudability.com/v3/account_groups/1 -u ‘[auth_token]:’ Copy

NOTE: This is the Account Group unique id assigned when it was created, not the Account Group position shown in app. The Account Group unique id can be found by using the API to make a GET request to list all the Account Groups.

Example Response

```
{
	"id": 1,
	"position": 2,
	"name": "Environment",
	"account_group_entry_values": [
		"Production",
		"Test",
		"Staging",
	]
 }
```

Create an Account Group

Example Request

```
curl -X POST https://api.cloudability.com/v3/account_groups \\
	 -H 'Content-Type: application/json' \\
     -u '[auth_token]:' \\
	 -d @- 
{
"position": 1,
"name": "Environment"
} 
EOF 
```

Upon successful creation the API will return the account group object

Note: The values associated with an Account Group are the values of the related Account Group Entries. As such, they cannot be modified via Account Group creation/modification, but rather via the Account Group Entries end point. You must also know the next available free slot (eg: position 1) and denote it for this to work.

Update an Account Group

You can use the API to update the name of any account group. You may have to do a GET request first to get the individual Account Group ID and then do a PUT request with that Account Group ID.

Example Requests

```
curl -X PUT https://api.cloudability.com/v3/account_groups/1 \\
	 -H 'Content-Type: application/json' \\
	 -u '[auth_token]:' \\
	 -d @- 
{
	"name": "Env"
}		
EOF		
```

Upon successful creation the API will return the account group object

Delete an Account Group

Note : You can only delete an Account Group when all Account Group Entries have been removed. You may have to do a GET request first to get the individual Account Group ID and then do a DELETE request with that Account Group ID.

Example Request

Curl -X DELETE https://api.cloudability.com/v3/account_groups/:id -u '[auth_token]:'

A successful deletion returns a 200OK status code with the deleted object in the body payload
