---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "DataLink Conexões"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Data Studio Referência"
source_path: "studio/new-uc/reference/datalink-connections.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# DataLink Conexões

## DataLink Visão geral

DataLink fornece conectividade entre o TBM Studio e sistemas externos, tanto para a entrada (importação) quanto para a saída (exportação) de dados.

**Tipos de conexão:**

|  |  |  |
| --- | --- | --- |
| **Tipo** | **Direção** | **Descrição** |
| Ingresso | Externo ao TBM Studio | Importar dados de sistemas externos |
| Saída | Do TBM Studio para um dispositivo externo | Exportar dados para sistemas externos |

## ServiceNow Integração

**Objetivo:** Enviar dados sobre o Custo Total de Propriedade (TCO) para ServiceNow

**Versões compatíveis do jogo " ServiceNow ":** Quebec, Paris, Orlando

**Etapas de configuração:**

1. Instale o aplicativo Apps & Services TCO na plataforma ServiceNow
2. Configurar relatórios de TCO no TBM Studio

1. Configurar um conector de saída d DataLink

**Opções de autenticação:**

|  |  |  |
| --- | --- | --- |
| **Tipo** | **Suporte ao agente** | **Notas** |
| Básico | Na nuvem e no local | Nome de usuário e senha |
| OAuth 2.0 | Apenas na nuvem | Requer o ID do cliente e a chave secreta disponíveis em ServiceNow |

**Tópico principal:** [Referência do ` Data Studio `](../../../studio/new-uc/reference/data-studio-reference.html)
