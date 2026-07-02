---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "admin"
title: "Gerenciar usuários, visualizações de usuários e painéis"
breadcrumb:
  - "Cloudability Premium"
  - "Administração"
  - "Gerenciar usuários e grupos de usuários"
source_path: "admin/create-and-manage-users.html"
images:
  - "images/Manage-Users.png"
  - "images/Picture2.png"
  - "images/add_and_manage_users_4.png"
  - "images/pencil-icon.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Gerenciar usuários, visualizações de usuários e painéis

## Visão geral

Como administrador do Cloudability, você pode gerenciar o acesso de um usuário a exibições e painéis no Cloudability. Isso inclui a configuração da visualização padrão, a definição de um painel padrão e a concessão de acesso a visualizações específicas. Outras tarefas de gerenciamento de usuários, como adicionar ou remover funções, são realizadas por meio do **Access Administration**.

[Funções e permissões em Cloudability](iam.html)

[Saiba como gerenciar as permissões e funções dos usuários em Access Administration](https://www.ibm.com/docs/en/apptio-platform/access-administration/saas?topic=management-manage-user-permissions-roles "(Abre em uma nova guia ou janela)") .

## Gerenciar visualizações e painéis de usuários

1. Navegue até a guia **Settings** > **Users & Groups > **Users****.
2. Marque a caixa de seleção ao lado do nome do usuário que deseja gerenciar e, em seguida, selecione ![ícone de lápis](../../../../03-media/cloudability-premium/images/pencil-icon.jpg) .
3. Você também pode pesquisar o usuário usando o nome de usuário ou o e-mail.
4. Para editar exibições e painéis de vários usuários, selecione pelo menos dois usuários e, em seguida, selecione **Edit Multiple**.

   ![captura de tela dos usuários](../../../../03-media/cloudability-premium/images/Manage-Users.png)
5. No painel **Editar um usuário** que aparece, você pode definir as seguintes configurações para o usuário:
   - **Visualização padrão** - Define a visualização que o usuário vê por padrão no login
   - **Default Dashboard (Painel padrão** ) - Especifica o painel padrão atribuído ao usuário
   - **Acesso à visualização** – Concede ao usuário acesso a visualizações específicas. Você pode filtrá-los com base nos critérios “Selecionados”, “Não selecionados” e “Todos”.

     Observação: as visualizações hierárquicas só podem ser atribuídas/desatribuídas através da página Permissões de visualização.

   ![editar captura de tela do usuário](../../../../03-media/cloudability-premium/images/add_and_manage_users_4.png)

   Nota:

   Quando uma visualização é atribuída aos usuários, eles não podem ver nenhum dado até que tenham a ViewsFeatureFullAccess permissão. Para obter mais informações, acesse [Gerenciando permissões e funções do usuário.](https://www.ibm.com/docs/en/apptio-platform/access-administration/saas?topic=management-manage-user-permissions-roles "(Abre em uma nova guia ou janela)")
6. Selecione Salvar.

## Definição de uma visualização padrão para um novo usuário

Cloudability permite configurar uma **visualização padrão** que os novos usuários veem quando fazem login pela primeira vez, desde que tenham recebido acesso a essa visualização. Essa visualização padrão costuma ser chamada de **visualização padrão em nível de organização**.

Se um administrador não tiver definido uma visualização padrão para um usuário, ou se o usuário não tiver configurado uma em seu perfil (*Manage Profile > Preferences* ), o Cloudability automaticamente o colocará como padrão para essa visualização padrão em nível de organização no login.

Para configurar a visualização padrão, selecione um valor no menu suspenso **Visualização padrão do novo usuário**.

![captura de tela da visualização do novo usuário](../../../../03-media/cloudability-premium/images/Picture2.png)

Observação: Os usuários iniciantes estão restritos a essa visualização. Após o login inicial, outras visualizações podem ser acessadas ou permissões adicionais podem ser concedidas pelos administradores.

**Tópico pai:** [Gerenciar usuários e grupos de usuários](../admin/manage-users-and-user-groups.html)
