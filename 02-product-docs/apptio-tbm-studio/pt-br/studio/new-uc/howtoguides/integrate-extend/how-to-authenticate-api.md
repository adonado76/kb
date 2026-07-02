---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Como fazer: Autenticar-se na API"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "Integrar e ampliar"
  - "Integração de API"
source_path: "studio/new-uc/howtoguides/integrate-extend/how-to-authenticate-api.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Como fazer: Autenticar-se na API

**Objetivo:** Obter um token de autenticação para realizar solicitações autorizadas à API

**Tempo estimado:** 15 a 30 minutos (configuração inicial)

**Quando usar:** Antes de qualquer operação de upload ou download. São necessários tokens para todas as chamadas de API.

**Pré-requisitos**

- Uma conta de usuário na Administração de Acesso Avançado com acesso à API
- Chaves de API geradas e com acesso concedido ao seu ambiente de destino
- Acesso à rede em frontdoor.apptio.com

## Permissões necessárias

**Para operações de upload,** sua conta precisa de:

- AccessDev
- UploadData

**Para realizar downloads,** sua conta precisa de:

- AccessProd, AccessStg
- AllDataView, DrillDown
- ViewMetricReports, ViewObjectReports, ViewTransformReports, ViewTransparencyReports, ViewUnitReports
- ViewReportsSavedForEveryone

Dica: algumas permissões de visualização podem não ser necessárias, dependendo dos produtos instalados e dos tipos de dados que estão sendo baixados. Em caso de dúvida, teste sua configuração.

## Método 1: Autenticação usando chaves de API (recomendado)

As chaves de API são o método de autenticação preferido por motivos de segurança. Elas permitem um controle de acesso detalhado e podem ser revogadas sem a necessidade de alterar as senhas dos usuários.

**Passo 1: Gerar chaves de API na Administração de Acesso Avançado**

1. Faça login na Administração de Acesso Avançado
2. Acesse as configurações da sua conta de usuário
3. Gerar um novo par de chaves de API (pública e secreta)
4. Clique em “Conceder acesso” ao lado do nome da chave para autorizar o acesso ao ambiente
5. Guarde a chave secreta em um local seguro — ela não poderá ser recuperada após a criação

**Passo 2: Solicitar um token de autenticação**

**cURL:**

```
curl -X POST https://frontdoor.apptio.com/service/apikeylogin \
 -H "Content-Type: application/json" \
 -H "Accept: application/json" \
 -d '{"keyAccess":"YOUR_PUBLIC_KEY","keySecret":"YOUR_SECRET_KEY"}'
```

**Python:**

```
import requests
import json
 
def get_auth_token(public_key, secret_key):
 """Authenticate with TBM Studio API using API keys."""
 url = "https://frontdoor.apptio.com/service/apikeylogin"
 headers = {
 "Content-Type": "application/json",
 "Accept": "application/json"
 }
 payload = {
 "keyAccess": public_key,
 "keySecret": secret_key
 }
 
 response = requests.post(url, headers=headers, json=payload)
 response.raise_for_status()
 
 # Token is returned in cookies
 token = response.cookies.get('apptio-opentoken')
 return token
 
# Usage
token = get_auth_token("your_public_key", "your_secret_key")
```

**Passo 3: Obtenha seu ID de ambiente**

O ID do ambiente é necessário para as chamadas de API subsequentes. Esse valor permanece constante, a menos que a configuração da Administração de Acesso Aprimorado seja alterada.

```
curl -X GET "https://frontdoor.apptio.com/api/environment/yourdomain.com/main" \
 -H "Content-Type: application/json" \
 -H "apptio-opentoken: YOUR_TOKEN"
```

**Python:**

```
def get_environment_id(token, domain, frontdoor_env="main"):
 """Get the environment ID for API calls."""
 url = f"https://frontdoor.apptio.com/api/environment/{domain}/{frontdoor_env}"
 headers = {
 "Content-Type": "application/json",
 "apptio-opentoken": token
 }
 
 response = requests.get(url, headers=headers)
 response.raise_for_status()
 
 return response.json()["id"]
 
# Usage
env_id = get_environment_id(token, "yourdomain.com")
```

## Método 2: Autenticar usando nome de usuário/senha

Aviso: A autenticação por nome de usuário/senha é compatível, mas não é recomendada para sistemas de produção. Sempre que possível, use chaves de API para garantir maior segurança.

**cURL:**

```
curl -X POST https://frontdoor.apptio.com/service/apikeylogin \
  -H "Content-Type: application/json" \
  -H "Accept: application/json" \
  -d '{"userId":"user@domain.com","password":"your_password"}'
```

**Python:**

```
def get_auth_token_password(user_id, password):
    """Authenticate using username and password."""
    url = "https://frontdoor.apptio.com/service/apikeylogin"
    headers = {
        "Content-Type": "application/json",
        "Accept": "application/json"
    }
    payload = {
        "userId": user_id,
        "password": password
    }
    
    response = requests.post(url, headers=headers, json=payload)
    response.raise_for_status()
    
    return response.cookies.get('apptio-opentoken')
```

## Resultados esperados

- Se a autenticação for bem-sucedida, um apptio-opentoken é retornado nos cookies da resposta
- O endpoint de ID do ambiente retorna uma resposta JSON contendo o ID numérico do ambiente
- Ambos os valores são obrigatórios para todas as operações de API subsequentes

## Armadilhas comuns

- **A chave não tem acesso concedido aos ambientes:** Após criar uma chave de API, é necessário conceder explicitamente acesso aos ambientes por meio do link “Conceder acesso”.
- **Permissões ausentes:** certifique-se de que a permissão " UploadData " esteja atribuída.
- **Validade do token:** os tokens de autenticação expiram. Implemente a lógica de atualização de tokens em processos de longa duração.

**Tópico principal:** [Integração de API](../../../../studio/new-uc/howtoguides/integrate-extend/api-integration.html)
