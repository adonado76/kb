---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Visão geral e funções"
breadcrumb:
  - "Billing"
  - "Introdução"
  - "Funções e permissões do usuário"
source_path: "boit/billing/getting-started/std-custom-role.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Visão geral e funções

As funções e permissões dos usuários controlam quem pode visualizar e trabalhar com o Benchmarking. Uma função é um conjunto de permissões atribuídas a um usuário, e ninguém pode acessar um produto IBM Apptio sem ter pelo menos uma função em sua conta, que é gerenciada na Administração de Acesso. Na Administração do Access, os administradores autorizados criam e gerenciam registros de usuários, atribuem ou removem funções e controlam quais funções podem acessar cada endpoint do produto, quais endpoints estão abertos a qualquer função elegível e quais endpoints estão totalmente ocultos.

Para obter detalhes sobre como atribuir funções, gerenciar contas de usuário e acessar os produtos IBM Apptio, consulte a documentação sobre [Administração de Acesso](https://www.ibm.com/docs/en/apptio-platform/access-administration/saas "(Abre em uma nova guia ou janela)").

## Funções de usuário

Abaixo estão destacadas algumas das funções que têm acesso ao Faturamento:

- **Admin**
  - Acesso total a todos os recursos do Billing (incluindo Cálculo de Custos e TBM Studio).
  - Inclui acesso administrativo ao Frontdoor e capacidade de criar funções personalizadas.
- **Apptio Parceiro**
  - Nível de acesso semelhante ao de um administrador, mas não pode registrar, desativar ou excluir contas de usuário de um cliente, a menos que tenha uma função separada com as permissões apropriadas.
  - A função só pode ser atribuída/retirada pelo Suporte d IBM.
- **Consumidor empresarial**
  - **Aviso: Aplica-se apenas ao padrão de faturamento.**
  - Concede acesso aos relatórios na coleção de relatórios “Taxas de serviço” e ao grupo “Proprietário da empresa” que aparece no relatório inicial.
- **Proprietário do Negócio**
  - **Aviso: Aplica-se apenas ao padrão de faturamento.**
  - Concede acesso aos relatórios nas coleções de relatórios “Taxas de serviço” e “Gerenciamento de relacionamento comercial” e aos grupos “Proprietário da empresa” e “Gerente de relacionamento comercial” que aparecem no relatório inicial.
- **Gerenciador de Serviços**
  - **Aviso: Aplica-se apenas ao padrão de faturamento.**
  - Concede acesso aos relatórios nas coleções de relatórios “Taxas de serviço” e “Provedor de serviços de TI” e aos grupos “Proprietário da empresa” e “Provedor de serviços” que aparecem no relatório inicial.

Para o Billing Essentials, as funções padrão com acesso concedido a um projeto do Costing Essentials com componentes do Billing Essentials instalados terão acesso a todos os relatórios na coleção de relatórios “Faturamento”.

Revise periodicamente a Administração de Acesso (no Frontdoor) e as coleções de relatórios do Faturamento para identificar outras Funções com acesso ao conteúdo do Faturamento.

## Funções customizadas

Você pode criar funções personalizadas no Frontdoor. As funções personalizadas permitem que você adapte o acesso para atender às necessidades específicas da sua organização.
