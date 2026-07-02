---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Referência Rápida"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "Integrar e ampliar"
  - "Integração de API"
source_path: "studio/new-uc/howtoguides/integrate-extend/quick-ref.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Referência Rápida

## Cabeçalhos obrigatórios para todas as chamadas de API ( v12.9+ )

|  |  |  |
| --- | --- | --- |
| **Cabeçalho** | **Valor** | **Propósito** |
| apptio-opentoken | Seu token de autenticação | Autenticação |
| apptio-ambiente-atual | ID do ambiente | Ambiente de Destino |
| tipo de aplicativo | Modelo principal | Requisitos para o v12.9+ |
| versão do aplicativo | N/D | Requisitos para o v12.9+ |
| Tipo de Conteúdo | Varia de acordo com a operação | Formato do corpo da solicitação |

## Formatos de arquivo compatíveis

|  |  |  |
| --- | --- | --- |
| **Formato** | **Extensão** | **Notas** |
| CSV | .csv | Valores separados por vírgulas |
| TSV | .tsv | Valores separados por tabulação |
| CSV compactado | .csv.gz | CSV compactado com Gzip |
| TSV compactado | .tsv.gz | TSV compactado com Gzip |
| Excel | .xlsx | Fazer download somente |

## Documentação relacionada

- Seção Referência da API do 5.5 : documentação completa dos endpoints, detalhes dos parâmetros e esquemas de resposta
- [Importação e gerenciamento de dados](../work-with-data/data-import-mgmt.html) : procedimentos de upload manual de dados e configuração d DataLink
- [Gerenciamento de usuários](../manage-users-permission/manage-up-intro.html) : Configuração de contas de usuário da API e atribuição de permissões
- [Modelo de segurança](../../concepts-architecture/studio-model/security-architecture.html) : arquitetura de autenticação e melhores práticas de segurança

**Tópico principal:** [Integração de API](../../../../studio/new-uc/howtoguides/integrate-extend/api-integration.html)
