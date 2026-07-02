---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Gerenciamento de usuários"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "Gerenciar usuários e permissões"
source_path: "studio/new-uc/howtoguides/manage-users-permission/manage-up-intro.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Gerenciamento de usuários

|  |  |
| --- | --- |
| **Tipo de conteúdo:** | Guia prático |
| **Público-alvo:** | Administradores |
| **Pré-requisitos:** | Função de administrador ou usuário avançado, acesso à Administração de Acesso Avançado |
| **Seções relacionadas:** | Seção 3.4.2 (Controle de acesso), Seção 6.2 (Referência de gerenciamento de usuários) |

## Introdução

O gerenciamento de usuários é fundamental para controlar quem pode acessar o TBM Studio e quais ações pode realizar. Esta seção aborda as tarefas diárias que os administradores precisam realizar para configurar e manter o acesso dos usuários, incluindo a criação de usuários, a atribuição de funções e a configuração de funções personalizadas para necessidades específicas.

O TBM Studio utiliza **o Enhanced Access Administration** (também conhecido como Frontdoor) como interface central para gerenciar usuários e funções em todas as aplicações do Apptio. Os usuários são definidos no nível do domínio, e seu acesso a projetos e recursos específicos é controlado por meio da atribuição de funções.

## Entendendo as funções padrão

O TBM Studio oferece várias funções padrão que abrangem padrões de acesso comuns. Compreender essas funções ajuda a atribuir níveis de acesso adequados e a determinar quando são necessárias funções personalizadas.

|  |  |  |
| --- | --- | --- |
| **Função** | **Descrição** | **Utilização típica** |
| **Admin** | Acesso administrativo total a todos os recursos, incluindo gerenciamento de usuários, configuração de projetos e todos os dados. | Administradores do TBM, proprietários do sistema, administradores de segurança. |
| **Usuário avançado** | É possível configurar modelos, criar relatórios, fazer upload de dados e acessar ambientes de desenvolvimento. Não é possível gerenciar usuários ou configurações de domínio. | TBM Architects, analistas de finanças de TI que elaboram modelos e relatórios. |
| **Usuário corporativo** | Visualizar relatórios e dados de produção. Pode interagir com tabelas editáveis, se tiver permissão para isso. Sem acesso à configuração. | Partes interessadas da empresa, executivos e gerentes de departamento que consultam relatórios. |
| **Analista** | Acesso à visualização e capacidade de criar relatórios pessoais. Tem permissão para editar relatórios pessoais. | Analistas de negócios que precisam criar relatórios ad hoc para uso pessoal. |

Observação: Comece com as funções padrão que melhor atendam às necessidades dos seus usuários. Você pode criar funções personalizadas posteriormente para usuários que precisem de uma combinação específica de permissões que não corresponda a nenhuma função padrão.

- **[Criar e gerenciar usuários](../../../../studio/new-uc/howtoguides/manage-users-permission/create-manage-users.html)**
- **[Atribuir funções aos usuários](../../../../studio/new-uc/howtoguides/manage-users-permission/assign-roles-users.html)**
- **[Configurar funções personalizadas](../../../../studio/new-uc/howtoguides/manage-users-permission/config-custom-roles.html)**
