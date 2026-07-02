---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Como as permissões de relatório e o RLS interagem"
breadcrumb:
  - "TBM Studio"
  - "Conceitos e Arquitetura"
  - "Modelo de segurança"
  - "Permissões de relatórios e componentes"
source_path: "studio/new-uc/concepts-architecture/security-model/report-permission-rls-interact.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Como as permissões de relatório e o RLS interagem

As permissões de relatório e o RLS funcionam como camadas complementares:

1. As permissões do relatório determinam se o usuário pode acessar o relatório.
2. Se o usuário tiver acesso ao relatório, o RLS filtra os dados visíveis nele.
3. A visibilidade dos componentes refina ainda mais o que o usuário vê na interface do relatório.

**Cenário comum:** O relatório “Visão geral dos custos” está disponível para todas as funções. Um executivo tem acesso a todas as unidades de negócios (sem restrição de RLS). Um gerente de departamento vê apenas os dados do seu departamento (o RLS filtra por unidade de negócios). Ambos veem disposições diferentes dos componentes (visibilidade dos componentes por função). Tudo isso é feito com uma única definição de relatório.

Nota:

**Erro comum: ausência de RLS nos alvos de perfuração**

Se um usuário acessar uma tabela de detalhes a partir de uma tabela de resumo protegida que não tenha o RLS configurado, ele poderá visualizar dados não filtrados na visualização detalhada. Certifique-se sempre de que o RLS esteja configurado em todas as tabelas acessíveis por meio da navegação detalhada.

**Tópico principal:** [Permissões de relatórios e componentes](../../../../studio/new-uc/concepts-architecture/security-model/report-component-permission.html)
