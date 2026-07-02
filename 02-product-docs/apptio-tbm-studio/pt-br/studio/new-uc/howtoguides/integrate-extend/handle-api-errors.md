---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Guia prático: Como lidar com erros de API"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "Integrar e ampliar"
  - "Integração de API"
source_path: "studio/new-uc/howtoguides/integrate-extend/handle-api-errors.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Guia prático: Como lidar com erros de API

**Objetivo:** Implementar um tratamento robusto de erros e uma lógica de repetição de tentativas para integrações de API em produção

**Tempo estimado:** 30 a 45 minutos para implementar

**Quando usar:** Ao criar integrações de produção que precisam lidar com problemas de rede, expiração de autenticação e interrupções de serviço de maneira adequada.

## Códigos de retorno da API

|  |  |  |
| --- | --- | --- |
| **Código** | **Descrição** | **Ação** |
| 200 | Sucesso (GET) | Processar dados de resposta |
| 201 | Criação bem-sucedida | Recurso criado com sucesso |
| 202 | Atualização com sucesso | Recurso atualizado com sucesso |
| 400 | String de API incorreta / Solicitação inválida | Verifique o formato, os parâmetros e o corpo da solicitação de URL |
| 401 | Desautorizado | Faça a autenticação novamente e tente novamente |
| 403 | Proibido | Verificar as permissões do usuário |
| 404 | Não localizadas | Verificar se o recurso existe (projeto, tabela, período) |
| 500 | Erro interno do servidor | Tente novamente com intervalo exponencial; entre em contato com o suporte se o problema persistir |

## Entendendo as respostas de erro

As respostas de erro retornam JSON com um campo de mensagem que descreve o problema:

```
{
 "message": "Poorly formatted date string: 'SOMEDATE:2010'. Ought to be of the form 'granularity':'year'."
}
```

## Mensagens de erro comuns:

|  |  |  |
| --- | --- | --- |
| **Padrão de mensagem** | **Causa** | **Solução** |
| Formato incorreto da sequência de data | Formato de período inválido | Use o formato Mês:Ano (por exemplo, January:2024 ) |
| O usuário X não existe | Nome de usuário inválido na solicitação | Verifique se o formato do nome de usuário está correto e se a conta existe |
| Acesso negado | Permissões insuficientes | Verifique se a conta possui os conjuntos de permissões necessários |
| Tabela não encontrada | A tabela de destino não existe | Verifique a grafia do nome da tabela e o projeto |

## Implementação da lógica de repetição

As integrações de produção devem implementar o backoff exponencial para falhas transitórias:

```
import requests
import time
import logging
 
class TBMStudioAPIClient:
 """Production-ready TBM Studio API client with retry logic."""
 
 def __init__(self, customer_id, domain, max_retries=3, base_delay=1.0):
 self.customer_id = customer_id
 self.domain = domain
 self.max_retries = max_retries
 self.base_delay = base_delay
 self.token = None
 self.env_id = None
 self.logger = logging.getLogger(__name__)
 
 def authenticate(self, public_key, secret_key):
 """Authenticate and store token."""
 url = "https://frontdoor.apptio.com/service/apikeylogin"
 response = self._make_request(
 "POST", url,
 json={"keyAccess": public_key, "keySecret": secret_key},
 headers={"Content-Type": "application/json"}
 )
 self.token = response.cookies.get('apptio-opentoken')
 
 # Get environment ID
 env_url = f"https://frontdoor.apptio.com/api/environment/{self.domain}/main"
 env_response = self._make_request("GET", env_url)
 self.env_id = env_response.json()["id"]
 
 def _make_request(self, method, url, **kwargs):
 """Make HTTP request with retry logic."""
 last_exception = None
 
 for attempt in range(self.max_retries):
 try:
 # Add auth headers if authenticated
 if self.token and 'headers' not in kwargs:
 kwargs['headers'] = {}
 if self.token:
 kwargs['headers'].update({
 "apptio-opentoken": self.token,
 "apptio-current-environment": str(self.env_id) if self.env_id else "",
 "app-type": "Flagship",
 "app-version": "NA"
 })
 
 response = requests.request(method, url, **kwargs)
 
 # Check for retryable status codes
 if response.status_code == 401:
 self.logger.warning("Token expired, re-authentication required")
 raise AuthenticationError("Token expired")
 
 if response.status_code >= 500:
 response.raise_for_status() # Will be caught and retried
 
 response.raise_for_status()
 return response
 
 except requests.exceptions.RequestException as e:
 last_exception = e
 
 if attempt < self.max_retries - 1:
 delay = self.base_delay * (2 ** attempt) # Exponential backoff
 self.logger.warning(
 f"Request failed (attempt {attempt + 1}/{self.max_retries}), "
 f"retrying in {delay}s: {e}"
 )
 time.sleep(delay)
 
 raise last_exception
 
 def upload(self, project, table, time_period, file_path, action="overwrite"):
 """Upload data with error handling."""
 import urllib.parse
 
 project_enc = urllib.parse.quote(project)
 table_enc = urllib.parse.quote(table)
 
 url = (f"https://{self.customer_id}.apptio.com/biit/api/v1/"
 f"{self.domain}/{project_enc}/{table_enc}/{time_period}/{action}")
 
 with open(file_path, 'rb') as f:
 response = self._make_request("POST", url, files={'myfile': f})
 
 return response.json()
 
 
class AuthenticationError(Exception):
 """Raised when authentication fails or token expires."""
 pass
 
 
# Usage with error handling
def main():
 logging.basicConfig(level=logging.INFO)
 
 client = TBMStudioAPIClient("acme", "acme.com")
 
 try:
 client.authenticate("public_key", "secret_key")
 result = client.upload(
 project="Cost Transparency",
 table="GL Data",
 time_period="January:2024",
 file_path="data.csv"
 )
 print(f"Upload successful: {result}")
 
 except AuthenticationError:
 print("Authentication failed. Check API credentials.")
 except requests.exceptions.HTTPError as e:
 print(f"API error: {e.response.status_code} - {e.response.text}")
 except Exception as e:
 print(f"Unexpected error: {e}")
```

## Estratégia de atualização de tokens

Para processos de longa duração, implemente a atualização proativa de tokens:

```
import time
from datetime import datetime, timedelta
 
class TokenManager:
 """Manage API token lifecycle."""
 
 def __init__(self, client, refresh_margin_minutes=5):
 self.client = client
 self.refresh_margin = timedelta(minutes=refresh_margin_minutes)
 self.token_expiry = None
 self.token_lifetime = timedelta(hours=1) # Adjust based on actual expiry
 
 def get_valid_token(self, public_key, secret_key):
 """Get a valid token, refreshing if necessary."""
 now = datetime.now()
 
 if (self.token_expiry is None or 
 now >= self.token_expiry - self.refresh_margin):
 self.client.authenticate(public_key, secret_key)
 self.token_expiry = now + self.token_lifetime
 
 return self.client.token
```

## Melhores práticas de extração florestal

- **Registre todas as chamadas de API:** inclua data e hora, endpoint, HTTP método e status da resposta
- **Registrar os tempos de resposta:** monitorar a queda no desempenho
- **Nunca registre credenciais:** oculte tokens, chaves de API e senhas dos registros
- **Registrar respostas de erro:** Capturar mensagens de erro completas para fins de solução de problemas
- **Use registro estruturado:** formate os registros em JSON para facilitar a interpretação e a análise

Aviso: Evite registrar dados confidenciais, como chaves de API, tokens ou informações de identificação pessoal (PII). Use substitutos ou codificação para informações identificáveis nos registros.

## Armadilhas comuns

- **Não tentar novamente em caso de erros 500:** os erros de servidor costumam ser temporários. Sempre implemente a repetição com intervalo de espera.
- **Ignorando os limites de taxa:** Embora isso não esteja explicitamente documentado, evite enviar solicitações em rápida sucessão. Insira intervalos entre as operações em lote.
- **Não lidar com a expiração do token:** sempre trate as respostas 401 realizando uma nova autenticação e tentando novamente.
- **Falha na análise de erros:** sempre analise e registre o campo de mensagem das respostas de erro para obter diagnósticos significativos.

**Tópico principal:** [Integração de API](../../../../studio/new-uc/howtoguides/integrate-extend/api-integration.html)
