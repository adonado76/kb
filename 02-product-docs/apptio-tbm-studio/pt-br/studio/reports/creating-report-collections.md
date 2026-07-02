---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Criar coleções de relatórios"
breadcrumb: []
source_path: "studio/reports/creating-report-collections.html"
images:
  - "resources/images/studio_images/ccp-rcpopup.png"
  - "resources/images/studio_images/rc-1_697x318.png"
  - "resources/images/studio_images/rc-2_732x350.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Criar coleções de relatórios

**Aplica-se a** : TBM Studio 12.0 e posterior

No sistema Apptio, as coleções de relatórios agrupam relatórios relacionados para que os usuários possam navegar facilmente entre os relatórios em um tópico ou perspectiva semelhante. Os administradores configuram coleções de relatórios para limitar quais funções de usuário podem acessar os relatórios de uma coleção. Os administradores podem definir permissões de função para coleções de relatórios e criar ou excluir coleções de relatórios personalizadas.

Para obter mais informações sobre:

- Funções, consulte [Permissões e funções do Frontdoor](https://community.ibm.com/community/user/viewdocument/manage-user-permissions-and-roles?CommunityKey=44bcb0d2-5ce6-4504-89eb-019253d3b5d8&tab=librarydocuments "(Abre em uma nova guia ou janela)").
- Permissões de relatório, consulte [Trabalhar com permissões de relatório](control-access-reports-11755.html "Aplica-se a: Apptio TBM Studio 12.7 e posterior.").

## Criar uma coleção de relatórios personalizados

Somente os administradores podem criar coleções de relatórios, e somente no projeto Costing Standard . Uma vez criadas, as coleções de relatórios ficam disponíveis em todo o projeto, e outros usuários podem adicionar e excluir relatórios de uma coleção.

1. Na guia **Projeto**, no grupo **Dados do projeto**, clique em **Coleções de relatórios**.
2. Na caixa de diálogo **Gerenciar coleções de relatórios**, clique em **Adicionar coleção**.![imagem](../../resources/images/studio_images/studioimages/studio_manage%20report%20collections_add%20collection.png)Uma nova entrada é adicionada à lista de coleções. A entrada é denominada **Nova coleção de relatórios**. A nova coleção é exibida no campo **Coleção selecionada**.

   ![imagem](../../resources/images/studio_images/studioimages/studio_manage%20report%20coll_new.png)
3. Para alterar o nome da coleção, clique na entrada **Nova coleção de relatórios** na lista de coleções e, em seguida, clique no nome da coleção no campo **Coleção selecionada**.

   ![imagem](../../resources/images/studio_images/studioimages/studio_manage%20report%20collections_selected%20collection.png)

## Excluir uma coleção de relatórios personalizados

Selecione o relatório na caixa de diálogo **Gerenciar coleções de relatórios**.

Clique no botão **Excluir coleção**.

**:NONE.**

- Os usuários só podem excluir coleções de relatórios personalizados.
- Como alternativa, em TBM Studio 12.7 e posteriores, você pode explorar outras opções descritas em [Desativar relatórios](disablereports.html "aplica-se a: TBM Studio 12.7 e posterior") e [Trabalhar com permissões de relatório](control-access-reports-11755.html "Aplica-se a: Apptio TBM Studio 12.7 e posterior.").

## Adicionar um relatório a uma coleção

1. Clique no relatório no **Project Explorer**.
2. Na guia **Relatório**, no grupo **Agrupamento**, clique em **Atribuir à coleção**.

   ![imagem](../../resources/images/studio_images/studioimages/studio_report_assign%20to%20collection.png)
3. Abra a lista suspensa e selecione a coleção à qual o relatório deve ser adicionado. Um relatório só pode ser atribuído a uma coleção de relatórios.

## Remover um relatório de uma coleção

1. Navegue até o relatório e verifique o relatório.
2. Na guia **Relatório**, no grupo **Agrupamento**, clique em **Atribuir à coleção**.
3. No menu que aparece, clique no X vermelho ao lado do nome da coleção.

![imagem](../../resources/images/studio_images/studioimages/studio_report%20collection_custom.png)

Dica: Se você tiver acesso à criação de conteúdo, poderá excluir um relatório de uma coleção usando a caixa de diálogo **Manage Report Collections (Gerenciar coleções de relatórios** ). Para remover um relatório dessa forma, clique no X vermelho no lado direito do registro desse relatório na coleção:

![imagem](../../resources/images/studio_images/studioimages/studio_manage%20report%20collections_custom%20finance%20report.png)

## Ocultar ou mostrar um relatório em uma coleção

Em vez de excluir um relatório de uma coleção de relatórios, você pode ocultar um relatório em uma coleção de relatórios. Por exemplo, você pode fazer isso para relatórios prontos que não deseja que os usuários acessem porque os dados do relatório ainda não estão disponíveis. Em seguida, quando os dados para iluminar o relatório forem carregados, você poderá mostrar o relatório.

Nunca exclua um relatório pronto para uso de uma coleção de relatórios. Em vez disso, oculte o relatório.

## Ocultar um relatório em uma coleção de relatórios

1. Na guia **Projeto**, no grupo **Dados do projeto**, clique em **Coleções de relatórios**. A caixa de diálogo Gerenciar coleções de relatórios é exibida.
2. Na lista **Available Collections (Coleções disponíveis** ) à esquerda, selecione a coleção de relatórios que contém o relatório a ser ocultado. A lista de relatórios existentes na coleção de relatórios selecionada é exibida à direita.
3. Para o(s) relatório(s) que você deseja ocultar, desmarque a caixa de seleção **Mostrar no navegador** ao lado do nome do relatório:![imagem](../../resources/images/studio_images/studioimages/studio_manage%20report%20collections_cost%20center%20trend.png)
4. Clique no botão **Fechar**.

## Mostrar um relatório oculto em uma coleção de relatórios

1. Na guia **Projeto**, no grupo **Dados do projeto**, clique em **Coleções de relatórios**. A caixa de diálogo Gerenciar coleções de relatórios é exibida.
2. Na lista **Available Collections (Coleções disponíveis** ) à esquerda, selecione a coleção de relatórios que contém o relatório a ser exibido.
3. Para o(s) relatório(s) que você deseja mostrar, marque a caixa de seleção **Mostrar no navegador** ao lado do nome do relatório e clique em **OK**.

## Adicionar um navegador de coleção de relatórios a um relatório

O navegador de coleção de relatórios é um componente de relatório que oferece aos usuários uma maneira fácil de se deslocar entre os relatórios de uma coleção. Quando você adiciona um relatório a uma coleção, o componente do navegador é automaticamente adicionado ao relatório.

![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/rc-1_697x318.png)

![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/rc-2_732x350.png)

## Paletas de cores personalizadas

Aplica-se a R12.10.10 e posterior.

O administrador (administrador do cliente, administrador do Apptio, administrador do parceiro) pode criar cores corporativas e ter uma paleta de cores definida para escolher as cores dos gráficos, para melhorar a experiência do usuário com informações visualmente atraentes.

Para saber mais sobre a aplicação da paleta de cores, consulte [Paletas de cores personalizadas](../admin/color-enhancement.html).

![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ccp-rcpopup.png)

Observação: Se uma paleta de cores for selecionada para uma coleção de relatórios e uma paleta de cores diferente for selecionada para um relatório dentro dela, a paleta de cores desse relatório será alterada.
