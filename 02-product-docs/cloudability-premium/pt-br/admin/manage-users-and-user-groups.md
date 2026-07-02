---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "admin"
title: "Gerenciar usuários e grupos de usuários"
breadcrumb:
  - "Cloudability Premium"
  - "Administração"
source_path: "admin/manage-users-and-user-groups.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Gerenciar usuários e grupos de usuários

Em Cloudability, os usuários e grupos de usuários ajudam a definir quem pode acessar a plataforma e o que eles podem ver ou fazer. Há três componentes principais:

Um ***Usuário*** emCloudability é um indivíduo a quem foi concedido acesso à plataforma. Cada usuário tem uma identidade exclusiva, normalmente vinculada a um endereço de e-mail. Os usuários são criados e autenticados por meio do **FrontDoor**, que cuida da autenticação e da autorização. Uma vez provisionado em FrontDoor,, o usuário pode ser atribuído a funções específicas em Cloudability, como MSP Admin, Billing Manager ou Cloudability User/Admin. Essas funções determinam as permissões e os níveis de acesso do usuário na plataforma.

Saiba mais **[Gerenciar usuários, visualizações de usuários e painéis](create-and-manage-users.html)**

Um ***Grupo de usuários*** em Cloudability é um conjunto de usuários agrupados para simplificar o gerenciamento de acesso e a atribuição de visualizações. Os administradores podem criar grupos de usuários e adicionar usuários individuais a eles. Depois de criados, esses grupos podem ser atribuídos a visualizações específicas para controlar a visibilidade e o acesso de forma eficiente.

Saiba mais **[Gerenciar grupos de usuários](manage-user-groups.html)**

Um ***Grupo Entra ID*** em Cloudability refere-se ao grupo de usuários gerenciado no Microsoft Entra ID (anteriormente Azure Active Directory), o serviço de gerenciamento de identidade e acesso baseado em nuvem da Microsoft. Em vez de criar manualmente grupos de usuários em Cloudability, as organizações podem importar Entra ID Groups juntamente com seus usuários associados.

Saiba mais **[Gerenciar grupos Entra ID](manage-entra-id-groups.html)**

- **[Gerenciar usuários, visualizações de usuários e painéis](../admin/create-and-manage-users.html)**
- **[Gerenciar grupos de usuários](../admin/manage-user-groups.html)**
- **[Gerenciar grupos de IDs Entra](../admin/manage-entra-id-groups.html)**
- **[Perguntas frequentes sobre usuários e grupos de usuários](../admin/users-and-user-groups-faqs.html)**
