---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Guia prático: Como enviar dados via API"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "Integrar e ampliar"
  - "Integração de API"
source_path: "studio/new-uc/howtoguides/integrate-extend/upload-data-via-api.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Guia prático: Como enviar dados via API

**Objetivo:** Carregar arquivos de dados nas tabelas do TBM Studio por meio de programação

**Tempo estimado:** 10 a 20 minutos por integração

**Quando usar: para** automatizar carregamentos mensais de dados, integrar-se a pipelines de ETL ou fazer uploads a partir de sistemas nos quais não é possível instalar os agentes d DataLink.

**Pré-requisitos**

- Token de autenticação válido e ID do ambiente (consulte Autenticação com a API)
- Permissões de upload atribuídas à sua conta da API
- Arquivo de dados em formato compatível ( CSV, TSV, CSV.GZ ou TSV.GZ )

## Estrutura da API ` URL `

`https://[customerid].apptio.com/biit/api/v1/[domain]/[project]/[table]/[time-period]/[action]`

**URL Parâmetros:**

|  |  |  |
| --- | --- | --- |
| **Parâmetro** | **Necessário** | **Descrição** |
| ID do cliente | Sim | Seu ID de cliente do Apptio (por exemplo, acme) |
| domínio | Sim | Seu domínio de cliente (por exemplo, acme.com ) |
| projeto | Sim | Nome do projeto de destino (codificado em URL, caso contenha espaços) |
| tabela | Sim | Nome da tabela de destino (codificado em URL, caso contenha espaços) |
| período | Sim | Apptio formato de data (por exemplo, January:2024 ) ou atual |
| ação | Não | anexar ou sobrescrever (o padrão é sobrescrever) |

**Parâmetros adicionais:**

|  |  |  |
| --- | --- | --- |
| **Parâmetro** | **Valores** | **Descrição** |
| forçar | verdadeiro/falso | Ignorar as verificações de validação de dados. Não é possível combinar com a ação em URL — use o corpo da solicitação POST em vez disso. |

## Passos

**Passo 1: Prepare seu arquivo de dados**

- Certifique-se de que os dados estejam no formato CSV ou TSV
- Os nomes das colunas devem corresponder ao esquema da tabela de destino
- Para arquivos grandes, compacte-os usando o gzip (. csv.gz ou. tsv.gz )

**Passo 2: Carregue o arquivo**

**cURL:**

```
curl -X POST "https://customer.apptio.com/biit/api/v1/customer.com/Cost%20Transparency/GL%20Data/January:2024/overwrite" \
 -H "apptio-opentoken: YOUR_TOKEN" \
 -H "apptio-current-environment: YOUR_ENV_ID" \
 -H "app-type: Flagship" \
 -H "app-version: NA" \
 -F "myfile=@/path/to/data.csv"
```

**Python:**

```
import requests
import urllib.parse
 
def upload_data(token, env_id, customer_id, domain, project, table, 
 time_period, file_path, action="overwrite"):
 """
 Upload data to TBM Studio via API.
 
 Args:
 token: Authentication token from login
 env_id: Environment ID
 customer_id: Your Apptio customer ID
 domain: Your domain (e.g., 'customer.com')
 project: Target project name
 table: Target table name
 time_period: Time period (e.g., 'January:2024' or 'current')
 file_path: Path to the data file
 action: 'append' or 'overwrite' (default: 'overwrite')
 
 Returns:
 dict: Response containing md5, length, and fileName
 """
 # URL-encode project and table names
 project_encoded = urllib.parse.quote(project)
 table_encoded = urllib.parse.quote(table)
 
 url = (f"https://{customer_id}.apptio.com/biit/api/v1/"
 f"{domain}/{project_encoded}/{table_encoded}/"
 f"{time_period}/{action}")
 
 headers = {
 "apptio-opentoken": token,
 "apptio-current-environment": str(env_id),
 "app-type": "Flagship",
 "app-version": "NA"
 }
 
 with open(file_path, 'rb') as f:
 files = {'myfile': f}
 response = requests.post(url, headers=headers, files=files)
 
 response.raise_for_status()
 return response.json()
 
# Usage example
result = upload_data(
 token=token,
 env_id=env_id,
 customer_id="acme",
 domain="acme.com",
 project="Cost Transparency",
 table="GL Data",
 time_period="January:2024",
 file_path="/path/to/gl_data.csv"
)
print(f"Upload complete: {result['fileName']}, {result['length']} bytes")
```

## Resultados esperados

Um envio bem-sucedido retorna uma resposta JSON:

```
{
 "md5": "3727119d89edcdd71377e39e18f3a5e1",
 "length": 13,
 "fileName": "data.csv"
}
```

Após o upload, a guia Dados > Visão geral no TBM Studio exibe “Dados da API” no campo Origem.

## Usar “Anexar” versus “Substituir”

|  |  |  |
| --- | --- | --- |
| **Ação** | **Comportamento** | **Caso de uso** |
| sobrescrever | Substitui todos os dados existentes no período de tempo em questão | Atualização mensal completa dos dados |
| anexação | Adiciona dados aos registros existentes | Atualizações incrementais, adicionando novos registros |

Dica: Para usar os parâmetros `action` e `force`, inclua-os no corpo da solicitação POST como campos de formulário, em vez de usá-los no parâmetro ` URL `: --form "action=append" --form "force=true"

## Armadilhas comuns

- **URL codificação:** Os nomes de projetos e tabelas que contêm espaços devem ser codificados no formato " URL " (os espaços são substituídos por %20 ou +).
- **Formato da data:** Use o formato exato Mês:Ano (por exemplo, January:2024 ). "current" utiliza o mês atual do calendário.
- **Tipo MIME:** O único tipo MIME compatível é multipart/form-data.
- **Criação da tabela:** Se a tabela de destino não existir, a API a cria no primeiro período do projeto, com os dados aparecendo no período especificado.

**Tópico principal:** [Integração de API](../../../../studio/new-uc/howtoguides/integrate-extend/api-integration.html)
