---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Table Layouts APIs"
breadcrumb:
  - "Planning"
  - "APIs"
  - "Planning REST APIs Overview"
source_path: "it-planning/planning/tab-lay-api.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Table Layouts APIs

The **Table Layouts API** provides access to layout metadata used for displaying and
organizing expense data in Apptio Planning. Layouts define how plan data is structured and presented
across different expense types.

This API allows you to retrieve both public and private layouts visible to the authenticated
user, enabling integrations that rely on consistent schema definitions or layout‑aware exports and
imports.

## GET /planning/api/v1/layouts

**Description**

Gets all the layouts (public and private) visible per user for specific expense type

**Request**

```
POST https://app.apptio.com/planning/api/v1/layouts
```

Note: Ensure the URL matches your region (e.g., app-eu.apptio.com, app-au.apptio.com).

**Headers**

|  |  |  |
| --- | --- | --- |
| **Header** | **Value** | **Description** |
| apptio-opentoken | <open-token> | Authentication token generated in step 2 of prerequisites |
| apptio-current-environment | <environment-id> | Required environment UUID retrieved from step 3 of prerequisites |

**Parameters**

|  |  |  |  |
| --- | --- | --- | --- |
| **Name** | **Allowed Values** | **Required** | **Description** |
| type | SUMMARY  LABOR\_EXISTING  LABOR\_PLANNED  LABOR\_ACTIVITY  CONTRACT  ASSET\_EXISTING  ASSET\_PLANNED  OTHER | TRUE | Type of expense to get layouts |

**Response**

```
[ 
		{ 
			"id": "_DEFAULT_VIEW_", 	
			"name": "Default Layout", 
			"isShared": true 	 
		}, 
		{ 	"id": "MyLayout", 
			  "name": "My Layout", 	
			  "isShared": false 
		}
	]
```

Returns a JSON object with the following properties:

- ***id***: Unique identifier for the layout
- ***name***: Display name of the layout
- **isShared**: true if layout is public, false if it is private

**Parent topic:** [Planning REST APIs Overview](../../it-planning/planning/plan-api.html "The Apptio Planning REST APIs provide secure, programmatic access to plans, planning data, metadata, and related artifacts within Apptio Planning. These APIs are designed to support automation and system integrations for planning, forecasting, analysis, governance, and data exchange use cases.")
