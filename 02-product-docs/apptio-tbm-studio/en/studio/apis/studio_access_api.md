---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "How to access R12 API through Enhanced Access Administration via curl"
breadcrumb: []
source_path: "studio/apis/studio_access_api.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# How to access R12 API through Enhanced Access Administration via curl

## Requirements:

- Basic command line know-how
- Proper accounts, permissions API keys, and such
- cURL

## Get opentoken

curl -i -X POST https://frontdoor.apptio.com/service/apikeylogin -H 'Accept:application/json' -H
'content-type:application/json' -d
'{"keyAccess":"adsfasdf-fasd-fasd-asd-fasdfa","keySecret":"fasdfasdfasdfasdfasdfasdfasdfasdfadsf"}'

## Returns

apptio-opentoken: asdfasdfasdfasdfasdfasdfasdfasdfasdfa

## Get a env ID (use opentoken)

curl -i -X GET https://frontdoor.apptio.com/api/environment/apptiosupport.com/cs -H
'apptio-opentoken: asdfasdfasdfasdfasdfasdfasdfasdfasdfa' -H 'content-type: application/json'

## Returns

In the return text, find first mention of "id":"134123413-41414-4124-4123-4123414314"

## Get the table (use id and opentoken):

```
curl -i -X GET https://csbox2-r12.apptio.com/biit/api/v2/domains/support.apptio.com/projects/Cost%20Transparency/tables/Cost%20Pool%20Reference%20List/dates/Jun:FY2017 -H 'apptio-current-environment: 134123413-41414-4124-4123-4123414314' -H 'apptio-opentoken: asdfasdfasdfasdfasdfasdfasdfasdfasdfa'
```

## Returns

Table data

## Upload a table: version with + characters for space and one with html encoding (use opentoken and env id)

```
curl -i -X POST 'https://csbox2-r12.apptio.com/biit/api/v2/domains/support.apptio.com/projects/Cost+Transparency/tables/Cost+Pool+Reference+List/dates/Jun:FY2017/overwrite' -H 'apptio-current-environment: 134123413-41414-4124-4123-4123414314' -H 'apptio-opentoken: asdfasdfasdfasdfasdfasdfasdfasdfasdfa' -F fileName=@upload.csv
```

```
curl -i -X POST 'https://csbox2-r12.apptio.com/biit/api/v2/domains/support.apptio.com/projects/Cost%20Transparency/tables/Cost%20Pool%20Reference%20List/dates/Jun:FY2017/overwrite' -H 'apptio-current-environment: 134123413-41414-4124-4123-4123414314' -H 'apptio-opentoken: asdfasdfasdfasdfasdfasdfasdfasdfasdfa' -F fileName=@upload.csv
```
