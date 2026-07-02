---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Relações entre front-end e endpoint"
breadcrumb:
  - "Billing"
  - "Administração e Operações"
  - "Arquitetura da solução e dependências"
source_path: "boit/billing/sol-arch-depend/fe-endpoint-relation.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Relações entre front-end e endpoint

Embora este guia não aprofunde o Frontdoor, é importante entender como os usuários acessam o Billing.

- **Fundamentos de faturamento**
  - Os usuários abrem o front-end do Costing Essentials.
  - O Billing Essentials aparece como uma **coleção de relatórios de faturamento** dentro desse projeto.
  - Não há uma entrada separada para o aplicativo Billing Essentials.
- **Padrão de faturamento**
  - Os usuários veem uma **entrada separada de Faturamento** no aplicativo front-end ou no seletor de endpoint.
  - Ao selecionar esta entrada, abre-se o front-end do Padrão de Faturamento, que é suportado pelos componentes de Faturamento instalados no projeto Padrão de Custeio.
  - O acesso do usuário ao Padrão de Faturamento é controlado no nível do terminal e dentro das coleções de relatórios.

As dependências subjacentes do projeto (componentes, modelos, tabelas) são sempre mantidas no TBM Studio. Os pontos finais simplesmente definem como esse conteúdo é agrupado e apresentado aos usuários.
