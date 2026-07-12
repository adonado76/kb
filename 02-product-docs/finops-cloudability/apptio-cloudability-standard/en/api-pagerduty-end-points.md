---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "PAGERDUTY End Points"
breadcrumb:
  - "Cloudability API"
  - "PAGERDUTY End Points"
source_path: "SSVCLNQ/api-v3/pagerduty_api.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# PAGERDUTY End Points

Summary

Following are the list of public APIs specific to Pagerduty.

With Cloudability being available in multiple regions, all references to api.cloudability.com in this API documentation should be referred to as mentioned in Getting started with Cloudability API V3 .

End Point Particulars

end point : /v3/pagerduty/credentials for RESTful CRUD interactions

end point : /v3/pagerduty/credentials

end point : /v3/pagerduty/credentials/test

end point : v3/pagerduty/credentials/:incidentKeyId

Parameters

- incidentKeyId (string): generated uuid after adding the pagerduty integration
- incidentKeyName (string): Pagerduty incident key name
- incidentKey (string): Pagerduty incident key
- incidentKeyLast4 (string): Last 4 digit of incident key

List Pagerduty integrations

```
curl 'https://api.cloudability.com/v3/pagerduty/credentials' \\ 
 -u ‘[auth_token]:’ 
```

```
{ 
 "result": [ 
 { 
 "incidentKeyId": "a1a1a11a-1111-1111-1aa1-aa1a11aa111a", 
 "incidentKeyName": "Anomaly PagerDuty Testing", 
 "incidentKeyLast4": "1a11" 
 }, 
 { 
 "incidentKeyId": "b1b1b11b-1111-1111-1aa1-aa1a11aa111b", 
 "incidentKeyName": "ab-test-integration", 
 "incidentKeyLast4": "1b11" 
 } 
 ] 
}
```

Update pagerduty integration

end point

/v3/pagerduty/credentials/ :incidentKeyId

```
curl -X PUT 'https://api.cloudability.com/v3/pagerduty/credentials/:incidentKeyId  
-H 'Content-Type: application/json' \\ 
-u ‘[auth_token]:’ \\ 
-d @- << EOF 
{ 
 "incidentKey": "incident-key", 
 "incidentKeyName": "incident-key-name" 
}
```

Test pagerduty integration

end point

/v3/pagerduty/credentials/test

```
curl -X POST 'https://api.cloudability.com/v3/pagerduty/credentials/test 
-H 'Content-Type: application/json' \\ 
-u ‘[auth_token]:’ \\ 
-d @- << EOF 
{ 
 "incidentKey": "incident-key", 
 "incidentKeyId": "" 
}
```

Save pagerduty integration

end point

/v3/pagerduty/credentials

```
curl -X POST 'https://api.cloudability.com/v3/pagerduty/credentials 
-H 'Content-Type: application/json' \\ 
-u ‘[auth_token]:’ \\ 
-d @- << EOF 
{ 
 "incidentKey": "incident-key", 
 "incidentKeyName": "incident-key-name" 
}
```

Retrieve pagerduty integration

end point

/v3/pagerduty/credentials/ :incidentKeyId

```
curl 
'https://api.cloudability.com/v3/pagerduty/credentials/:incidentKeyId  
-u ‘[auth_token]:’
```

Delete pagerduty integration

end point

/v3/pagerduty/credentials/ :incidentKeyId

```
Curl -X DELETE 
'https://api.cloudability.com/v3/pagerduty/credentials/:incidentKeyId 
-u ‘[auth_token]:’
```
