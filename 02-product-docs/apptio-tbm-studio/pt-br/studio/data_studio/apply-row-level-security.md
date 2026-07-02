---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Aplicar segurança no nível da linha"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "Trabalhar com dados"
  - "Segurança de dados"
source_path: "studio/data_studio/apply-row-level-security.html"
images:
  - "resources/images/studio_images/studioimages/icons/setting-icon.png"
  - "resources/images/studio_images/studioimages/studio_bu-access_table_sui.jpg"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Aplicar segurança no nível da linha

aplica-se a: TBM Studio 12.2 e posterior

Para fornecer segurança de dados no nível da linha, é possível filtrar tabelas e relatórios com base no usuário atual. As linhas que não estão associadas ao usuário atual ficam ocultas. A segurança em nível de linha está disponível nas tabelas. A filtragem no nível da linha era chamada de "View Filters" em TBM Studio 11.

Assista a este vídeo de demonstração: [Segurança em nível de linha em R12](https://community.ibm.com/community/user/viewdocument/demo-video-row-level-security-in-r "(Abre em uma nova guia ou janela)"). Ou navegue por [todos os vídeos do site Apptio](https://community.ibm.com/community/user/groups/community-home/librarydocuments?LibraryKey=c5be284a-1f80-41dd-a913-019253cf761a "(Abre em uma nova guia ou janela)").

Para obter informações sobre como usar o site DataLink para carregar dados de segurança em nível de linha, consulte [Carregar dados no projeto Row-Level Security usando o site DataLink](load-low-level-security-data-datalink.htm "(Abre em uma nova guia ou janela)").

Embora todas as tabelas que podem ser criadas com o Ad Hoc Query sejam editadas, algumas tabelas legadas não são.

Observação: a segurança em nível de linha afeta todos os usuários. Não confie na segurança em nível de linha para proteger os dados dos usuários administradores, uma vez que eles têm acesso ao modo Studio e podem criar relatórios que o contornam, adicionar-se às tabelas de segurança em nível de linha e desativar totalmente a segurança em nível de linha.

Os itens que cada usuário pode ver são especificados em um projeto separado chamado **Row-Level Security**. O projeto **Row-Level Security** é instalado automaticamente quando uma nova instância do Apptio é criada. O projeto é usado para segurança em nível de linha em todos os projetos em um domínio.

Para acessar o projeto, abra o menu Settings (Configurações) ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/icons/setting-icon.png) e clique em **Configure Row-Level Security (Configurar segurança em nível de linha** ).

## Configurar a segurança em nível de linha

Há duas etapas principais para configurar a segurança em nível de linha:

- **Etapa 1** : No projeto **Row-Level Security**, crie uma ou mais tabelas de mapeamento que identifiquem os itens (linhas em uma tabela) que cada usuário poderá visualizar.
- **Etapa 2** : defina os filtros de visualização para as tabelas que serão protegidas adicionando uma etapa **de segurança em nível de linha** ao pipeline de transformação.

Exploraremos a configuração com um exemplo abordado nas seções a seguir. Neste exemplo, configuramos a segurança em nível de linha na origem de custos e nas torres de recursos de TI em um modelo simplificado. As configurações limitarão a visibilidade dos dados da unidade de negócios com base no usuário. Em seguida, examinamos os efeitos sobre os relatórios a partir da perspectiva do nosso usuário de teste " [bob@acme.com](mailto:bob@acme.com "(Abre em uma nova guia ou janela)") " para ver como a limitação das tabelas drillTo mencionada acima entra em ação.

## Criar as tabelas de mapeamento

As tabelas de mapeamento identificam os itens que cada usuário pode visualizar. Uma tabela de mapeamento deve ter duas colunas:

- **ID** : o ID do usuário. O ID deve corresponder a um nome de usuário na tabela Usuários do projeto de redação.
- **Item:** O nome do item que um usuário pode acessar, conforme aparece na tabela do projeto de trabalho. Por exemplo, se você tivesse uma tabela com informações sobre data centers, digitaria o nome do data center.

Observe que você não precisa se preocupar com o nome da tabela ou com o nome da coluna na tabela de mapeamento que contém o item. O nome da tabela e o nome da coluna serão fornecidos quando você definir os filtros.

Você pode criar uma ou mais tabelas de mapeamento. Se você tiver apenas uma regra para controlar a segurança no nível da linha, uma tabela provavelmente será tudo o que você precisa. Se você tiver mais de uma regra, por exemplo, usuários que devem poder acessar todos os data centers, talvez queira criar mais de uma tabela para ajudá-lo a organizar os itens.

Em geral, você criará as tabelas de mapeamento fora do aplicativo Apptio e, em seguida, fará o upload das tabelas.

A tabela de mapeamento mostrada abaixo define o acesso a unidades de negócios para quatro usuários. Observe que bob@acme.com está configurado para ter acesso somente à BU 2. Além disso, observe que rachel@acme.com tem acesso a duas BUs.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio_bu-access_table_sui.jpg)

Embora seja possível dar aos usuários que devem ter acesso a todas as BUs três entradas (uma para cada BU 1, BU 2 e BU 3), neste exemplo, se outras BUs forem adicionadas, precisaremos continuar adicionando entradas para esses usuários. Portanto, neste exemplo, também criamos a tabela BU Full Access para que possamos dar a sally@acme.com acesso a todos os dados da BU, independentemente de serem adicionadas outras BUs.

Observe que a palavra Admin é usada nas colunas dessa tabela e nos filtros mais adiante neste exemplo. Isso é diferente das **permissões de função** do administrador mencionadas na seção de limitações acima.

![](../../resources/images/studio_images/studioimages/studio_bu%20full%20access_table_sui.jpg)

## Configurar os filtros de segurança em nível de linha

Para aplicar a segurança em nível de linha a uma tabela, você deve adicionar uma etapa **de segurança em nível de linha** ao pipeline de transformação da tabela. O filtro fará referência às tabelas de mapeamento que você criou na etapa anterior. Uma tabela de transformação filtrada pode ser adicionada a um relatório e a segurança em nível de linha estará em vigor para a tabela.

Para definir a segurança em nível de linha para uma tabela:

1. Abra a tabela no **Project Explorer**.
2. Inserir uma etapa **de segurança em nível de linha** [(Como?](transform-workspace.htm "(Abre em uma nova guia ou janela)") ).
3. Adicionar entradas ao filtro. Você pode adicionar mais de uma entrada. As entradas normalmente usam a lógica "ou". Se qualquer uma das entradas for verdadeira, o usuário poderá ver a entrada.
   - **Primeiro campo:** Selecione a coluna na tabela que contém os itens a serem filtrados.
   - **Segundo campo (interseções):** Selecione a tabela de mapeamento que contém as informações de segurança em nível de linha. Essa é a tabela que você carregou na Etapa 1.
   - **Terceiro campo:** O nome da coluna na tabela de mapeamento que contém os itens que um usuário tem permissão para visualizar.
   - **Quarto campo (onde está o usuário)** : O nome da coluna na tabela de mapeamento que contém IDs de usuário.

     Dica: A adição de uma etapa do pipeline Row-Level Security adicionará automaticamente uma etapa de modelagem. Somente tabelas modeladas e tabelas editáveis podem ter a segurança em nível de linha aplicada a elas.

Aqui, vemos o filtro para Origem de custo configurado com uma regra que abrange os usuários regulares na tabela BU Access. A regra fornece acesso às linhas da tabela em que os valores da coluna Cost Source.BU correspondem aos valores da coluna BU Access.BU em que a coluna BU Access.User ID é igual ao ID do usuário conectado que está visualizando a tabela.

![](../../resources/images/studio_images/studioimages/studio_cost%20source_looking%20at%20row-level%20security_sui.jpg)

Agora, queremos testar nosso filtro para ter certeza de que está funcionando. Aqui vemos o filtro de visualização sendo usado para visualizar as linhas que Bob conseguiria ver:

![](../../resources/images/studio_images/studioimages/studio_cost%20source_row-level%20security_sui.jpg)

Agora, queremos adicionar acesso à Sally. Para fazer isso, devemos adicionar uma coluna de fórmula à tabela que tenha o valor que aparece na coluna "BU Full Access.Is Admin". Esse valor é "Sim", portanto, fazemos isso:

![](../../resources/images/studio_images/studioimages/studio_cost%20source_formulas_sui.jpg)

Nesse ponto, modificamos a etapa do pipeline Row-Level Security para usar a lógica OR, de modo que, se o usuário aparecer na tabela "BU Full Access.Is Admin", ele terá acesso a todas as linhas. A captura de tela a seguir mostra esse filtro adicional e o resultado de colocar sally@acme.com no filtro de visualização.

![](../../resources/images/studio_images/studioimages/studio_row-level%20security_cost%20source%20admin_sui.jpg)

Observação: As tabelas não herdam automaticamente as configurações de RLS. Você deve adicionar uma etapa RLS para cada etapa do modelo.

## Segurança em nível de linha em relatórios

Agora que configuramos o Row-Level Security para nossas tabelas modeladas, queremos ver os efeitos nos relatórios e entender a limitação listada acima. Para isso, criamos um relatório que contém um resumo do objeto Torres de recursos de TI, uma pesquisa das Torres de recursos de TI para a Fonte de custos e um resumo do objeto Fonte de custos. Aqui está uma captura de tela desse relatório sendo visualizado por meio da função Admin. Observe que a tabela de pesquisa mostra dados de todas as unidades de negócios.

![](../../resources/images/studio_images/studioimages/studio_demo%20reports_row%20level%20security%20demo_sui.jpg)

Antes de vermos o que Bob veria, observe que as alocações nesse exemplo incluem uma alocação da BU 3 para a BU 2:

![](../../resources/images/studio_images/studioimages/studio_it%20resource%20towers_model_sui.jpg)

Agora, nós nos fazemos passar por [(como?)](https://community.apptio.com/docs/DOC-6891 "(Abre em uma nova guia ou janela)") bob@acme.com para ver o que Bob veria. A captura de tela a seguir mostra isso.

![](../../resources/images/studio_images/studioimages/studio_demo%20reports_cost%20source%20bu_sui.jpg)

## Segurança em nível de linha nos relatórios de visão geral do modelo

Em um relatório de visão geral do modelo, uma camada reflete a segurança em nível de linha se a segurança em nível de linha tiver sido aplicada à tabela. No entanto, os valores nas camadas aplicarão somente a segurança em nível de linha aplicada à camada específica. No exemplo abaixo, a segurança em nível de linha foi aplicada somente ao nível do centro de custo. Observe que os valores nesse nível somam menos do que os US$ 5.097.741 mostrados para as Torres de Recursos de TI.

![](../../resources/images/studio_images/studioimages/studio_row-level%20security_model%20overview%20reports_sui.png)

**Tópico principal:** [Segurança de dados](../../studio/new-uc/howtoguides/work-with-data/data-security.html)
