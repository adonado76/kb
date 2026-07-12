---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Criar, gerenciar e excluir projetos"
breadcrumb: []
source_path: "studio/admin/create-deleting-projects.html"
images:
  - "resources/images/icons/icon-settings.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Criar, gerenciar e excluir projetos

**Aplica-se a** : TBM Studio 12.0 e posterior

Ao criar um novo projeto, você tem duas opções:

- **Crie um projeto de aplicativo.** Os projetos de aplicativos servem como modelos para novos projetos. Quando você cria um projeto de aplicativo, o aplicativo cria automaticamente conjuntos de dados, métricas, modelos e relatórios com base no modelo de aplicativo. Os modelos de aplicativos incluem: Costing Standard.
- **Crie um projeto personalizado.** Um projeto em branco não tem conjuntos de dados, modelos, métricas ou relatórios. Crie um novo projeto personalizado se não quiser se basear em um trabalho anterior.

Nas seções a seguir, discutiremos a criação de novos projetos personalizados. Para obter informações, consulte os diversos guias de aplicativos:

- [Criar um projeto personalizado](#Createmanageanddeleteprojects__Createacustomproject)
- [Tornar um projeto visível para os usuários](#Createmanageanddeleteprojects__Makeaprojectvisibletousers)
- [Editar informações globais do projeto](#Createmanageanddeleteprojects__Editglobalprojectinformation)
- [Navegar entre projetos](#Createmanageanddeleteprojects__Navigatebetweenprojects)
- [Excluir um projeto](#Createmanageanddeleteprojects__Deleteaproject)
- [Renomear um projeto](#Createmanageanddeleteprojects__Renameaproject)

## Criar um projeto personalizado

Quando você cria um dos tipos de projetos acima, exceto um projeto personalizado, o aplicativo cria conjuntos de dados, modelos e relatórios específicos para o tipo de projeto selecionado. Se você criar um projeto personalizado, não haverá conteúdo. Não haverá conjuntos de dados, métricas, modelos, objetos ou relatórios. Você terá que criá-los. Há muitos motivos para criar um novo projeto:

- Há vários usuários de aplicativos diferentes e cada um deles está em um departamento diferente. Você quer ter a liberdade de trabalhar em seu projeto sem se preocupar com a possibilidade de outro usuário alterar seus conjuntos de dados, modelos, métricas e relatórios.
- Você precisa abordar os custos reais, bem como prever os custos futuros. A melhor prática seria criar um projeto real e um projeto de previsão.
- Você está analisando vários produtos de software empresarial diferentes, como um sistema ERP ou CRM, e deseja fazer comparações de custo hipotéticas.

Sua licença Apptio permite que você crie um número ilimitado de projetos. Para criar um projeto personalizado:

1. Abra o menu Settings (Configurações) ![](../../../../../03-media/apptio-tbm-studio/resources/images/icons/icon-settings.png) no canto superior direito da tela e clique em **New Project (Novo projeto** ).
2. Na caixa de diálogo Novo projeto, insira as informações do novo projeto.
3. Para criar o projeto e fechar a caixa de diálogo, clique em **OK**.
4. Faça o check-in no project.When. Ao fazer o check-in do projeto, é feita uma entrada no console Access Administration , conforme mostrado abaixo. O projeto inicialmente não estará visível para os usuários (o projeto não será exibido no menu Aplicativos). Isso é útil se você quiser configurar totalmente o projeto antes de torná-lo visível para os usuários.

   ![](../../resources/images/studio_images/studioimages/studio_access%20admin_applications_sui.png)

## Tornar um projeto visível para os usuários

Quando estiver pronto para tornar um projeto visível para os usuários, siga as etapas abaixo:

1. Abra o console Access Administration clicando no menu **Settings (Configurações** ) ![](../../../../../03-media/apptio-tbm-studio/resources/images/icons/icon-settings.png) no canto superior direito da tela e, em seguida, clicando em **Access Administration**.
2. Na guia **Aplicativos**, localize seu projeto e clique em **Editar visibilidade**.
3. Clique nas funções às quais você deseja dar acesso ao projeto.
4. Clique em **Salvar**.
5. Clique em **Show**.

## Editar informações globais do projeto

Depois de criar um projeto, você pode editar as informações do projeto.

1. Confira o projeto.
2. Na guia **Projeto**, no grupo **Configuração de projeto**, clique em **Configurações de projeto**. A caixa de diálogo Editar configurações do projeto é exibida.

   ![](../../resources/images/studio_images/studioimages/studio_project%20setup_project%20settings_sui.png)
3. Faça as edições e clique em **OK**.

## Navegar entre projetos

No aplicativo, você pode ter apenas um projeto aberto por vez. Você abre projetos no menu Projetos.

![](../../resources/images/studio_images/studioimages/studio_bank%20demo%20menu_bankdemo_sui.png)

Em TBM Studio v12.3.1 e posteriores, você pode:

- Especifique a versão a ser usada para atualizações de componentes ( [specify-version-component.html](specify-version-component.html "(Abre em uma nova guia ou janela)") )
- Especifique o projeto padrão de seu domínio ( [change\_default\_project.htm](change_default_project.htm "(Abre em uma nova guia ou janela)") )

## Excluir um projeto

Somente os administradores do sistema Apptio podem excluir projetos. Se você quiser excluir um projeto, consulte o administrador.

## Renomear um projeto

Não é possível renomear um projeto de dentro do produto. Se quiser renomear um projeto, entre em contato com o administrador do sistema Apptio e solicite a alteração do nome.
