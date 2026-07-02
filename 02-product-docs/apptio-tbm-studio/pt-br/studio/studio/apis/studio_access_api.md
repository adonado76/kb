---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Como acessar a API R12 por meio da Administração de Acesso Avançado via curl"
breadcrumb: []
source_path: "studio/studio/apis/studio_access_api.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Como acessar a API R12 por meio da Administração de Acesso Avançado via curl

## Requisitos:

- Conhecimento básico de linha de comando
- Contas adequadas, permissões, chaves de API, etc
- cURL

## Obter opentoken

curl -i -X POST https://frontdoor.apptio.com/service/apikeylogin -H 'Accept:application/json' -H 'content-type:application/json' -d ' {"keyAccess":"adsfasdf-fasd-fasd-asd-fasdfa","keySecret":"fasdfasdfasdfasdfasdfasdfasdfasdfadsf"} '

## Retorna

abertura do aplicativo: asdfasdfasdfasdfasdfasdfasdfasdfasdfasdfa

## Obter uma ID de ambiente (usar opentoken)

curl -i -X GET https://frontdoor.apptio.com/api/environment/apptiosupport.com/cs -H 'apptio-opentoken: asdfasdfasdfasdfasdfasdfasdfasdfasdfa' -H 'content-type: application/json'

## Retorna

No texto de retorno, encontre a primeira menção de "id": "134123413-41414-4124-4123-4123414314"

## Obtenha a tabela (use id e opentoken):

```
curl -i -X GET https://csbox2-r12.apptio.com/biit/api/v2/domains/support.apptio.com/projects/Cost%20Transparency/tables/Cost%20Pool%20Reference%20List/dates/Jun:FY2017 -H 'apptio-current-environment: 134123413-41414-4124-4123-4123414314' -H 'apptio-opentoken: asdfasdfasdfasdfasdfasdfasdfasdfasdfa'
```

## Retorna

Dados da tabela

## Faça upload de uma tabela: versão com + caracteres para espaço e outra com codificação html (use opentoken e env id)

```
curl -i -X POST 'https://csbox2-r12.apptio.com/biit/api/v2/domains/support.apptio.com/projects/Cost+Transparency/tables/Cost+Pool+Reference+List/dates/Jun:FY2017/overwrite' -H 'apptio-current-environment: 134123413-41414-4124-4123-4123414314' -H 'apptio-opentoken: asdfasdfasdfasdfasdfasdfasdfasdfasdfa' -F fileName=@upload.csv
```

```
curl -i -X POST 'https://csbox2-r12.apptio.com/biit/api/v2/domains/support.apptio.com/projects/Cost%20Transparency/tables/Cost%20Pool%20Reference%20List/dates/Jun:FY2017/overwrite' -H 'apptio-current-environment: 134123413-41414-4124-4123-4123414314' -H 'apptio-opentoken: asdfasdfasdfasdfasdfasdfasdfasdfasdfa' -F fileName=@upload.csv
```
