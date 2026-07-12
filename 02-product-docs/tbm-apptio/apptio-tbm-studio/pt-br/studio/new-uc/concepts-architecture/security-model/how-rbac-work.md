---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Como funciona o RBAC"
breadcrumb:
  - "TBM Studio"
  - "Conceitos e Arquitetura"
  - "Modelo de segurança"
  - "Controle de acesso baseado em funções (RBAC)"
source_path: "studio/new-uc/concepts-architecture/security-model/how-rbac-work.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Como funciona o RBAC

O modelo RBAC possui três componentes que funcionam em conjunto:

1. **As permissões** definem capacidades específicas (como “EditModels,”, “ViewReports,” ou “UploadData” ).
2. **As funções** agrupam permissões em conjuntos significativos que correspondem a funções de trabalho (como “Administrador”, “Usuário avançado” ou “Usuário corporativo”).
3. **Os usuários** são atribuídos a uma ou mais funções. As permissões efetivas de um usuário são a combinação de todas as permissões das funções que lhe foram atribuídas.

Essa abordagem apresenta vantagens significativas em relação à atribuição direta de permissões aos usuários: auditoria mais fácil, padrões de acesso consistentes, integração simplificada (atribuir uma função em vez de configurar dezenas de permissões individuais) e atualizações mais rápidas quando as necessidades da organização mudam.

**Tópico principal:** [Controle de acesso baseado em funções (RBAC)](../../../../studio/new-uc/concepts-architecture/security-model/role-based-access.html)
