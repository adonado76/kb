---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Padrões de acesso para o padrão de faturamento"
breadcrumb:
  - "Billing"
  - "Introdução"
  - "Funções e permissões do usuário"
source_path: "boit/billing/getting-started/access-patterns-bs.html"
images:
  - "resources/images/boit_images/apbs.png"
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Padrões de acesso para o padrão de faturamento

O Padrão de Faturamento introduz um endpoint de Faturamento separado, além do projeto de Custeio. O acesso precisa levar em conta ambos os aspectos.

Observação: aplica-se apenas ao padrão de faturamento.

**Padrões típicos:**

- **Administradores e analistas**
  - Tenha acesso front-end ao endpoint do Padrão de Faturamento e às coleções de relatórios relevantes.
  - Tenha acesso ao TBM Studio no projeto Padrão de Custeio onde os componentes “BoIT” estão instalados.
  - Coordenar com as equipes de segurança para garantir que os usuários certos vejam os relatórios e domínios de faturamento corretos.
- **Proprietários de serviços ou produtos, líderes seniores, partes interessadas e consumidores**
  - Acesse o Padrão de Faturamento através do terminal dedicado no front-end.
  - Veja apenas as coleções de relatórios e visualizações relevantes para suas responsabilidades e escopo.
  - Pode ter um controle de acesso mais refinado para áreas sensíveis, como preços de transferência ou relatórios de entidades jurídicas.

## Pontos principais:

- O acesso aos relatórios e painéis padrão de faturamento é controlado no nível do terminal e dentro das coleções de relatórios.
- O acesso ao TBM Studio continua focado nas funções de configuração; a maioria das funções comerciais permanece apenas no front-end.

![](../../../../../../03-media/apptio-billing/resources/images/boit_images/apbs.png)

Fig. #: Página inicial do Frontdoor com o endpoint Billing Standard destacado
