---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Como fazer: Baixar dados via API"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "Integrar e ampliar"
  - "Integração de API"
source_path: "studio/new-uc/howtoguides/integrate-extend/download-data-api.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Como fazer: Baixar dados via API

**Objetivo:** Extrair dados das tabelas e relatórios do TBM Studio por meio de programação

**Tempo estimado:** 10 a 15 minutos por integração

**Quando usar: para** extrair dados para análise externa, alimentar data warehouses ou integrar com ferramentas de BI.

**Pré-requisitos**

- Token de autenticação válido e ID do ambiente
- Permissões de download/visualização atribuídas à sua conta da API
- URL e da API para a tabela ou relatório de destino (obtido na interface do usuário do TBM Studio)

## Passo 1: Obtenha a API URL no TBM Studio

**Para tabelas:**

1. Acesse a tabela no TBM Studio
2. Selecione a guia Página inicial, clique em Exportar e, em seguida, selecione Mostrar API URL
3. Copie o URL URL da janela modal

**Para tabelas e gráficos de relatórios:**

1. Clique com o botão direito do mouse no elemento do relatório (tabela ou gráfico)
2. Selecione “Mostrar API” ( URL ) no menu de contexto
3. Copie o link URL para o formato desejado (TSV, JSON ou Excel)

## Passo 2: Baixe os dados

**cURL:**

```
# Download as TSV
curl -X GET "https://customer.apptio.com/biit/api/v2/domains/customer.com/projects/Cost%20Transparency/tables/GL%20Data/dates/Jan:FY2024.tsv" \
 -H "Content-Type: text/tab-separated-values" \
 -H "apptio-opentoken: YOUR_TOKEN" \
 -H "apptio-current-environment: YOUR_ENV_ID" \
 -o output.tsv
```

**Python:**

```
import requests
 
def download_data(token, env_id, api_url, output_path, format="tsv"):
 """
 Download data from TBM Studio via API.
 
 Args:
 token: Authentication token
 env_id: Environment ID
 api_url: API URL obtained from TBM Studio
 output_path: Path to save the downloaded file
 format: Output format ('tsv', 'json', 'xlsx')
 
 Returns:
 str: Path to downloaded file
 """
 content_types = {
 "tsv": "text/tab-separated-values",
 "json": "application/json",
 "xlsx": "application/vnd.openxmlformats-officedocument.spreadsheetml.sheet"
 }
 
 headers = {
 "Content-Type": content_types.get(format, "text/tab-separated-values"),
 "apptio-opentoken": token,
 "apptio-current-environment": str(env_id),
 "app-type": "Flagship",
 "app-version": "NA"
 }
 
 response = requests.get(api_url, headers=headers)
 response.raise_for_status()
 
 with open(output_path, 'wb') as f:
 f.write(response.content)
 
 return output_path
 
# Usage example
download_data(
 token=token,
 env_id=env_id,
 api_url="https://customer.apptio.com/biit/api/v2/domains/customer.com/projects/Cost%20Transparency/tables/GL%20Data/dates/Jan:FY2024.tsv",
 output_path="gl_data.tsv"
)
```

## Personalização do download

**Alterar o delimitador:**

Adicione o parâmetro delimitador com um caractere codificado em URL :

# Use o símbolo de barra vertical como delimitador ( %7C = |)

...tables/GL%20Data/dates/Jan:FY2024.tsv?delimiter=%7C

**Substituição de caracteres delimitadores nos dados:**

Se seus dados contiverem o caractere delimitador, use delimiterReplacement:

# Substituir os caracteres de barra vertical nos dados por vírgulas

...?delimiter=%7C&delimiterReplacement=%2C

## Baixando de tabelas publicadas

As tabelas publicadas fornecem conjuntos de dados estáveis e controlados por esquema, ideais para integrações externas.

1. No Explorador de Projetos, clique com o botão direito do mouse na tabela publicada
2. Selecione “Mostrar API URL ” e copie o link URL
3. Use o link URL com o mesmo código de download indicado acima

Dica: As tabelas publicadas são pré-calculadas por padrão, garantindo tempos de resposta rápidos da API. Use-os em vez de exportações de relatórios pontuais para integrações de produção.

## Formatos de download compatíveis

|  |  |  |  |
| --- | --- | --- | --- |
| **Formato** | **Extensão** | **Tipo de Conteúdo** | **Ideal para** |
| Separado por tabulação | .tsv | texto/valores separados por tabulação | Arquivos grandes, processamento de dados |
| JSON | .json | application/json | Integrações de API, aplicativos web |
| Excel | .xlsx | application/vnd.openxmlformats-officedocument.spreadsheetml.sheet | Análise de fácil utilização |

## Armadilhas comuns

- **Formato de data no URL :** As URLs de download utilizam o formato do ano fiscal (por exemplo, Jan:FY2024 ), que pode diferir do formato de upload.
- **Limites de tempo para arquivos grandes:** para conjuntos de dados muito grandes, use o formato TSV em vez do Excel. Considere ativar o pré-cálculo para tabelas publicadas.
- **URLs de relatórios:** As URLs da API de relatórios são específicas do elemento de relatório. Alterações na estrutura do relatório podem invalidar o código de identificação do relatório ( URL ).

**Tópico principal:** [Integração de API](../../../../studio/new-uc/howtoguides/integrate-extend/api-integration.html)
