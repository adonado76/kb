---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Cómo acceder a la API R12 a través de Enhanced Access Administration mediante curl"
breadcrumb: []
source_path: "studio/studio/apis/studio_access_api.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Cómo acceder a la API R12 a través de Enhanced Access Administration mediante curl

## Requisitos:

- Conocimientos básicos de línea de comandos
- Cuentas adecuadas, permisos, claves API, etc
- cURL

## Obtener opentoken

curl -i -X POST https://frontdoor.apptio.com/service/apikeylogin -H 'Accept:application/json' -H 'content-type:application/json' -d ' {"keyAccess":"adsfasdf-fasd-fasd-asd-fasdfa","keySecret":"fasdfasdfasdfasdfasdfasdfasdfasdfadsf"} '

## Devuelve

apptio-opentoken: asdfasdfasdfasdfasdfasdfasdfasdfasdfasdfasdfasdfasdfasdfasdfasdfasdfasdfasdfasdfasdfasdfasdfasdfasdfasdfasdfasdfasdfasdfasdfasdfasdfasdfasdfasdfasdfasdfasdfasdfasdfasdfasdfasdfasdfas

## Obtener un env ID (usar opentoken)

curl -i -X GET https://frontdoor.apptio.com/api/environment/apptiosupport.com/cs -H 'apptio-opentoken: asdfasdfasdfasdfasdfasdfasdfasdfasdfa' -H 'content-type: application/json'

## Devuelve

En el texto de retorno, encontrar la primera mención de "id": "134123413-41414-4124-4123-4123414314"

## Obtener la tabla (usar id y opentoken):

```
curl -i -X GET https://csbox2-r12.apptio.com/biit/api/v2/domains/support.apptio.com/projects/Cost%20Transparency/tables/Cost%20Pool%20Reference%20List/dates/Jun:FY2017 -H 'apptio-current-environment: 134123413-41414-4124-4123-4123414314' -H 'apptio-opentoken: asdfasdfasdfasdfasdfasdfasdfasdfasdfa'
```

## Devuelve

Datos de la tabla

## Sube una tabla: versión con + caracteres para el espacio y otra con codificación html (usa opentoken y env id)

```
curl -i -X POST 'https://csbox2-r12.apptio.com/biit/api/v2/domains/support.apptio.com/projects/Cost+Transparency/tables/Cost+Pool+Reference+List/dates/Jun:FY2017/overwrite' -H 'apptio-current-environment: 134123413-41414-4124-4123-4123414314' -H 'apptio-opentoken: asdfasdfasdfasdfasdfasdfasdfasdfasdfa' -F fileName=@upload.csv
```

```
curl -i -X POST 'https://csbox2-r12.apptio.com/biit/api/v2/domains/support.apptio.com/projects/Cost%20Transparency/tables/Cost%20Pool%20Reference%20List/dates/Jun:FY2017/overwrite' -H 'apptio-current-environment: 134123413-41414-4124-4123-4123414314' -H 'apptio-opentoken: asdfasdfasdfasdfasdfasdfasdfasdfasdfa' -F fileName=@upload.csv
```
