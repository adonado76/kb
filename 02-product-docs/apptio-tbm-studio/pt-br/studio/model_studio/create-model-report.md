---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Criar um relatório de modelo"
breadcrumb: []
source_path: "studio/model_studio/create-model-report.html"
images:
  - "resources/images/studio_images/studioimages/icons/rearrange.png"
  - "resources/images/studio_images/studioimages/studio/stu582.png"
  - "resources/images/studio_images/studioimages/studio/stu584_sui.png"
  - "resources/images/studio_images/studioimages/studio/stu585.png"
  - "resources/images/studio_images/studioimages/studio/stu586_up__arrow_icon_37x30.png"
  - "resources/images/studio_images/studioimages/studio/stu587_sui.png"
  - "resources/images/studio_images/studioimages/studio_modeling_benchmarking_sui.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Criar um relatório de modelo

**Aplica-se a** : TBM Studio 12.0 e posterior

Quando quiser visualizar um conjunto selecionado de tabelas em um modelo e seus drivers e alocações, crie um relatório de modelo. Um exemplo de relatório de modelo é mostrado na imagem a seguir. As camadas do relatório podem conter uma única coluna de uma tabela ou uma ou mais tabelas. Use uma única coluna quando quiser que o relatório modelo se concentre em um elemento específico, como pools de custos. Use uma tabela quando quiser que o usuário possa personalizar o relatório modelo selecionando uma coluna da tabela. Por exemplo, você pode incluir a tabela **Origem do custo**, que inclui **pools de custo**, mas também outras colunas, como **centros de custo**, **torres de referência** e **nomes de projetos**.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu582.png)

Assista a este vídeo de demonstração do site Apptio Education Services: [Uso de relatórios modelo](https://community.ibm.com/community/user/viewdocument/using-model-reports?CommunityKey=44bcb0d2-5ce6-4504-89eb-019253d3b5d8&tab=librarydocuments "(Abre em uma nova guia ou janela)"). Ou navegue por [todos os vídeos do site Apptio](https://community.ibm.com/community/user/groups/community-home/librarydocuments?LibraryKey=195da3d0-0c39-402e-a1a5-019253d461a2 "(Abre em uma nova guia ou janela)").

## Visualizar drivers e alocações

Para visualizar os drivers e as alocações de uma tabela, clique na tabela no relatório. Na imagem anterior, a tabela **Cost Source Actuals** foi selecionada. As alocações para as tabelas de pool de custos são exibidas.

Se quiser ver mais detalhes sobre os elementos em uma tabela, clique no menu e clique em **Drill Down**, conforme mostrado na imagem a seguir. Em seguida, você pode selecionar uma coluna da tabela. No exemplo a seguir, se você selecionar **Vendor Name (Nome do fornecedor)**, o modelo de relatório terá a aparência da imagem a seguir:

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu584_sui.png)

Você pode clicar em um **nome de fornecedor** para ver as alocações para os pools de custos.

Para retornar à exibição da tabela, clique no ícone ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu586_up__arrow_icon_37x30.png) .

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu585.png)

## Use camadas para controlar o layout

Uma camada pode conter uma única coluna de uma tabela ou uma ou mais tabelas. Ele não pode conter uma coluna e uma tabela. Você pode criar várias camadas usando colunas da mesma tabela.

Em um relatório modelo, as camadas controlam o layout das tabelas. Na primeira imagem, há quatro camadas:

- Finanças
- Recursos
- da nuvem e híbrida
- Serviços

Para criar um relatório, você define as camadas e, em seguida, arrasta as tabelas do **Project Explorer** para as camadas. Você define as camadas usando o **Tier Editor** mostrado na imagem a seguir:

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu587_sui.png)

Para exibir o **Tier Editor**, clique no menu **Exibir** na guia Página **inicial** e clique em **Mostrar Tier Editor**. Para editar a camada, verifique o relatório do modelo. Essas são as tarefas comuns que você executa no **Tier Editor** :

- **Adicionar uma camada** - Clique no ícone Add Tier (Adicionar camada) ![](../../resources/images/studio_images/studioimages/icons/add%20tier.png).
- **Excluir uma camada** - Clique no ícone Excluir camada ![](../../resources/images/studio_images/studioimages/icons/delete%20tier.png).
- Alterar **a ordem das camadas** - Clique no ícone Rearranjar ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/icons/rearrange.png) no cabeçalho da camada e arraste a camada para um novo local.
- **Adicionar uma tabela a uma camada** - Clique na tabela no **Project Explorer** e arraste-a para a camada. Você pode adicionar apenas tabelas modeladas. Você pode adicionar mais de uma tabela a uma camada, mas se tiver adicionado uma tabela a uma camada, não poderá adicionar uma coluna.
- **Adicionar uma coluna de uma tabela** - Expanda a tabela no **Project Explorer** e arraste uma coluna para a camada. Se você adicionar uma coluna a uma camada, não poderá adicionar nenhum outro elemento à camada.
- **Alterar a ordem das tabelas em uma camada** - Clique na tabela e arraste-a para a nova posição na camada.
- **Nomear uma camada** - Clique no campo **Name (Nome** ) na parte superior da camada e digite um nome.
- **Retornar à visualização do relatório** - Clique no menu **View (Exibir** ) na guia **Home (Início)** e clique em **Show Document (Mostrar documento** ).

## Atribuir um relatório modelo a uma coleção

A partir de v12.2.2, você pode atribuir um relatório modelo a uma coleção de relatórios. Quando um usuário abrir a coleção de relatórios, o relatório será exibido junto com os outros relatórios da coleção. A adição de um relatório modelo a uma coleção de relatórios facilita o acesso dos usuários ao relatório.

Para atribuir um relatório modelo a uma coleção de relatórios:

1. Clique na guia **Modelagem**.
2. Clique em **Assign to Collection (Atribuir à coleção** ).
3. Abra a lista suspensa e clique no nome da coleção de relatórios.
4. Salve o relatório.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio_modeling_benchmarking_sui.png)
