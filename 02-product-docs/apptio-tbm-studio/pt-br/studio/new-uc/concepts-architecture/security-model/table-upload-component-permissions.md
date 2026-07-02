---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Permissões do componente de upload de tabelas"
breadcrumb:
  - "TBM Studio"
  - "Conceitos e Arquitetura"
  - "Modelo de segurança"
  - "Permissões de relatórios e componentes"
source_path: "studio/new-uc/concepts-architecture/security-model/table-upload-component-permissions.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Permissões do componente de upload de tabelas

O componente Table Upload oferece suporte a um controle de acesso avançado por meio de uma tabela editável que mapeia tabelas específicas a funções específicas ou usuários individuais. Isso permite que os administradores controlem quais usuários podem fazer uploads para quais tabelas sem precisar criar vários relatórios.

**Exemplo — Configuração de acesso para upload de tabelas:**

|  |  |  |
| --- | --- | --- |
| **Tabela** | **Função** | **Usuário** |
| Contratos Acme | Usuário avançado | (qualquer usuário avançado) |
| Contabilidade Geral da Acme |  | bob@acme.com |
| Contabilidade Geral da Acme |  | sally@acme.com |
| Mapeamento da Estrutura Organizacional da Acme IT |  | bob@acme.com |

Nessa configuração, Bob vê “Acme General Ledger” e “Acme IT Org Mapping” no menu suspenso de upload. Sally tem acesso aos Contratos da Acme (devido à sua função de Usuária Avançada) e ao Razão da Acme. Os usuários que não constam na lista não veem nenhuma tabela disponível para upload.

**Tópico principal:** [Permissões de relatórios e componentes](../../../../studio/new-uc/concepts-architecture/security-model/report-component-permission.html)
