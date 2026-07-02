---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Segurança em nível de linha (RLS)"
breadcrumb:
  - "TBM Studio"
  - "Conceitos e Arquitetura"
  - "Modelo de segurança"
source_path: "studio/new-uc/concepts-architecture/security-model/row-level-security.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Segurança em nível de linha (RLS)

A segurança no nível da linha (RLS) é o mecanismo de segurança no nível dos dados do TBM Studio. Enquanto as funções e permissões controlam quais recursos e relatórios um usuário pode acessar, o RLS controla quais linhas de dados um usuário pode ver nesses relatórios e tabelas. O RLS garante que os usuários vejam apenas os dados relevantes para o âmbito da sua organização — mesmo quando acessam os mesmos relatórios.

## O que é segurança no nível da linha?

O RLS funciona filtrando dados com base na identidade do usuário conectado. Quando um usuário abre um relatório ou visualiza uma tabela, o sistema verifica a configuração do RLS para determinar quais linhas esse usuário específico está autorizado a ver. As linhas que não estão associadas ao usuário atual ficam ocultas.

**Por que a RLS é importante**

- **Dados multilocatários:** quando várias unidades de negócios compartilham a mesma instância do TBM Studio, o RLS garante que cada unidade de negócios visualize apenas seus próprios dados.
- **Limites organizacionais:** os gerentes podem ter acesso restrito aos dados de custos de seu próprio departamento ou região, enquanto os executivos têm acesso a dados agregados de toda a organização.
- **Conformidade regulatória:** o RLS ajuda a garantir o cumprimento das políticas de acesso a dados que possam ser exigidas pela governança interna ou por regulamentações externas.

Nota:

**RLS vs. Permissões de relatório**

As permissões RLS e de relatório são complementares, não alternativas. As permissões de relatório determinam se um usuário pode acessar um relatório. O RLS controla quais dados aparecem nos relatórios aos quais o usuário tem acesso. Normalmente, são necessários ambos: permissões de relatório para organizar a experiência do usuário e o RLS para impor limites aos dados.

- **[Como funciona a RLS](../../../../studio/new-uc/concepts-architecture/security-model/how-rls-worls.html)**
- **[RLS Arquitetura](../../../../studio/new-uc/concepts-architecture/security-model/rls-arch.html)**
- **[Âmbito do RLS: Onde o RLS se aplica](../../../../studio/new-uc/concepts-architecture/security-model/rls-scope.html)**
- **[Herança e fluxo na RLS](../../../../studio/new-uc/concepts-architecture/security-model/rls-inheritance.html)**
