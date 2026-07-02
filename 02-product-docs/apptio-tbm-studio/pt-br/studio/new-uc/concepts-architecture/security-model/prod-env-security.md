---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Segurança do ambiente de produção"
breadcrumb:
  - "TBM Studio"
  - "Conceitos e Arquitetura"
  - "Modelo de segurança"
  - "Segurança ao longo de todo o ciclo de vida"
source_path: "studio/new-uc/concepts-architecture/security-model/prod-env-security.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Segurança do ambiente de produção

O ambiente de produção é onde os usuários da empresa acessam relatórios e dados.

- **Acesso:** Requer a permissão " AccessProd ". Concedido a todas as funções que precisam visualizar relatórios de produção (incluindo usuários de negócios).
- **Somente leitura para a maioria dos usuários:** os usuários corporativos e a maioria dos usuários avançados devem apenas consultar relatórios na produção, sem modificar configurações.
- **Gestão de mudanças:** As alterações de segurança devem seguir o fluxo de trabalho padrão de implementação: modificar no ambiente de desenvolvimento, validar no ambiente de teste, implementar no ambiente de produção.

**Tópico principal:** [Segurança ao longo do ciclo de vida](../../../../studio/new-uc/concepts-architecture/security-model/security-across-lifecycle.html)
