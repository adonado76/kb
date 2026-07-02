---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Padrões de acesso para o Billing Essentials"
breadcrumb:
  - "Billing"
  - "Introdução"
  - "Funções e permissões do usuário"
source_path: "boit/billing/getting-started/access-patters-be.html"
images:
  - "resources/images/boit_images/apbe.png"
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Padrões de acesso para o Billing Essentials

Observação: aplica-se apenas ao Billing Essentials.

O Billing Essentials é instalado no mesmo projeto que executa o Costing Essentials. Não há um endpoint separado para faturamento; os usuários acessam o faturamento por meio do front-end de custos existente.

**Padrões típicos:**

- **TAS e parceiro**
  - Tenha acesso frontal à coleção de relatórios de “Faturamento”.
  - Pode executar e validar relatórios do Billing Essentials (faturas, detalhes, resumos).
  - Tenha acesso ao TBM Studio para configuração de back-end e ajustes de dados.
- **Proprietários de serviços ou produtos, líderes seniores, partes interessadas e consumidores**
  - Acesse os relatórios de faturamento através da mesma entrada front-end que eles usam para o Costing Essentials.
  - Veja apenas os relatórios e dados relevantes para você, com base na segurança e na filtragem em nível de linha.

![](../../../../../../03-media/apptio-billing/resources/images/boit_images/apbe.png)

## Pontos principais:

- A maior parte do acesso diário é gerenciada pelo mesmo modelo de gerenciamento de usuários e permissões usado para o Costing Essentials.
- As alterações nos modelos, conjuntos de dados ou tabelas do Billing Essentials no TBM Studio são realizadas por um recurso TAS ou um parceiro.

Fig. #: Relatório de faturas apresentado com o menu de navegação visível à esquerda
