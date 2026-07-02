---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Herança de permissões e permissões efetivas"
breadcrumb:
  - "TBM Studio"
  - "Conceitos e Arquitetura"
  - "Modelo de segurança"
  - "Controle de acesso baseado em funções (RBAC)"
source_path: "studio/new-uc/concepts-architecture/security-model/permission-inheritance.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Herança de permissões e permissões efetivas

Quando um usuário é atribuído a várias funções, suas permissões efetivas correspondem à união de todas as permissões de todas as funções. Não existe nenhum mecanismo que permita que uma função revogue uma permissão concedida por outra função — as permissões são puramente cumulativas.

**Exemplo:** Se ao Usuário A forem atribuídos tanto o papel “Visualizador de relatórios” (com ViewObjectReports ) quanto o papel “Carregador de dados” (com AccessDev e UploadData ), o Usuário A poderá tanto visualizar relatórios quanto carregar dados.

Quando um usuário altera sua função nas configurações do perfil (Minha conta), ele deve atualizar o navegador para que a nova função entre em vigor. A função ativa determina as capacidades atuais do usuário e influencia quais componentes ficam visíveis nos relatórios.

**Tópico principal:** [Controle de acesso baseado em funções (RBAC)](../../../../studio/new-uc/concepts-architecture/security-model/role-based-access.html)
