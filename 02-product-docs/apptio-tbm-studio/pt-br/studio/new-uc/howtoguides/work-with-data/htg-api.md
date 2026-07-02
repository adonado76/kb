---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Guia prático: Como exportar dados via API"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "Trabalhar com dados"
  - "Exportação de dados"
source_path: "studio/new-uc/howtoguides/work-with-data/htg-api.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Guia prático: Como exportar dados via API

**Objetivo:** Recuperar dados de tabelas e relatórios do TBM Studio por meio de programação, utilizando a API da Plataforma

**Quando usar:** Quando você precisar de acesso flexível e sob demanda aos dados do TBM Studio para integrações personalizadas, pipelines de ETL ou scripts de automação

**Pré-requisitos:**

- TBM Studio versão 12.0 ou posterior
- Credenciais de autenticação da API (chaves de API ou credenciais de usuário)
- Permissões necessárias para baixar dados (permissões de AccessProd,, AccessStg,, DrillDown, e permissões de visualização relevantes)
- Conhecimento básico de solicitações do tipo ` HTTP ` e da sua linguagem de script preferida

**Tempo estimado:** 20 a 30 minutos para a configuração inicial; varia de acordo com o desenvolvimento da integração

## Entendendo a exportação baseada em API

A API da Plataforma TBM Studio oferece acesso direto e programático aos seus dados sem a necessidade do produto DataLink. Entre os motivos mais comuns para usar a API estão:

- Integração da recuperação de dados em ferramentas ETL de terceiros
- Criação de aplicativos personalizados que utilizam dados do TBM
- Automatizar a extração de dados quando não é possível instalar os agentes d DataLink
- Implementação de lógica condicional ou fluxos de trabalho complexos de recuperação de dados

## Passo 1: Configurar a autenticação

Antes de fazer chamadas à API, configure sua autenticação. O TBM Studio suporta autenticação por chave de API (recomendado) e autenticação por nome de usuário/senha.

**Para autenticação por chave de API:**

1. Na Administração de Acesso Avançado, certifique-se de que sua conta de usuário tenha chaves de API configuradas.
2. Anote os valores **da** sua chave pública e **da** sua chave secreta.
3. Certifique-se de que a chave tenha acesso ao ambiente adequado.

**Permissões necessárias para baixar dados:**

Sua conta precisa das seguintes permissões mínimas:

- AccessProd, AccessStg, DrillDown, Acesse Proactive, AllDataView
- ViewMetricReports, ViewObjectReports, ViewTransformReports
- ViewTransparencyReports, ViewUnitReports, ViewReportsSavedForEveryone

Observação: dependendo dos dados que você estiver baixando, nem todas as permissões de visualização podem ser necessárias. Teste o seu caso de uso específico.

## Passo 2: Obter um token de autenticação

Envie uma solicitação POST para obter um token de acesso:

**Link:** https://frontdoor.apptio.com/service/apikeylogin

**Títulos:**

Aceitar: application/json

Content-Type: application/json

**Corpo:**

```
{"keyAccess": "your-public-key", "keySecret":
        "your-secret-key"}
```

**Resposta:** A resposta inclui um cookie apptio-opentoken que você utilizará nas solicitações subsequentes.

## Passo 3: Obtenha seu ID de ambiente

Se você ainda não sabe qual é o seu ID de ambiente, obtenha-o com esta solicitação:

**Link:** https://frontdoor.apptio.com/api/environment/[yourdomain.com]/[yourfrontdoorenv ]

Substitua [ yourdomain.com ] pelo seu domínio e [yourfrontdoorenv] pelo nome do seu ambiente (normalmente "main").

A resposta inclui o valor do ID do ambiente necessário para as solicitações de dados.

## Passo 4: Baixar os dados da tabela

Após concluir a autenticação, você pode recuperar dados das tabelas.

**Baixe a API “ URL ” do TBM Studio:**

- Acesse a tabela no TBM Studio (em Data Studio ou Published Table).
- Selecione a guia **Página inicial**, clique em **Exportar** e, em seguida, selecione **Mostrar API URL**.
- Copie o arquivo URL no formato de sua preferência ( CSV, TSV ou JSON).

**Cabeçalhos para todas as solicitações de download:**

Content-Type: text/tab-separated-values (ou application/json para JSON)

apptio-opentoken: [seu-token]

apptio-current-environment: [seu-id-de-ambiente]

tipo de aplicativo: principal

versão do aplicativo: NA

**Observação:** Os cabeçalhos `app-type` e `app-version` são obrigatórios para o TBM Studio versão 12.9 e posteriores.

**Formatos de arquivo compatíveis:** CSV, TSV, CSV.GZ, TSV.GZ, XLS, XLSX

**Códigos de retorno e tratamento de erros**

|  |  |
| --- | --- |
| **Código** | **Significado** |
| 200 | Sucesso |
| 400 | String da API incorreta (verifique o formato URL ) |
| 500 | Erro interno do servidor (verifique as permissões ou a disponibilidade dos dados) |

## Armadilhas comuns

**Faltam os cabeçalhos obrigatórios**

Na versão 12.9 ou posterior, ignorar os cabeçalhos de tipo e versão do aplicativo causa falhas na autenticação.

**Formato incorreto do período de tempo**

Os períodos de tempo devem seguir as convenções do site Apptio (por exemplo, “ January:2024 ” ou “atual” para o mês atual).

**Expiração de token**

Os tokens de autenticação expiram. Implemente a lógica de atualização de tokens em processos de longa duração.

**Erros de permissão**

Falhas no download geralmente indicam falta de permissões. Verifique se sua conta possui o conjunto de permissões necessário indicado na Etapa 1.

## O que vem a seguir

- Para obter a documentação completa da API, incluindo recursos de upload, consulte a seção 5.5 (Referência da API)
- Para conhecer os padrões de integração do ` DataLink `, consulte a [documentação](https://www.ibm.com/docs/en/apptio-platform/datalink/saas?topic=datalink "(Abre em uma nova guia ou janela)") em DataLink
- Para configurar tabelas publicadas para feeds automatizados de BI, consulte [aqui](htg-config-pt.html).

**Tópico principal:** [Exportação de dados](../../../../studio/new-uc/howtoguides/work-with-data/data-export.html)
