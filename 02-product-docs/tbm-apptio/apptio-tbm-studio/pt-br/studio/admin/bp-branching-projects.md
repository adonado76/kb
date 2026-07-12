---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Práticas recomendadas: Ramificação de projetos"
breadcrumb: []
source_path: "studio/admin/bp-branching-projects.html"
images:
  - "resources/images/studio_images/ac-1.jpg"
  - "resources/images/studio_images/ac-2.jpg"
  - "resources/images/studio_images/ac-3.jpg"
  - "resources/images/studio_images/mb-1.png"
  - "resources/images/studio_images/mb-2.png"
  - "resources/images/studio_images/studio-calculation-queue_sui_1.jpg"
  - "resources/images/studio_images/studio-create-branch-from-tag_sui.jpg"
  - "resources/images/studio_images/studio-create-hotfix_sui.jpg"
  - "resources/images/studio_images/studio-merge-to-branch_sui.jpg"
  - "resources/images/studio_images/studio-navigate-branches_sui.jpg"
  - "resources/images/studio_images/studio-promote-now_sui.jpg"
  - "resources/images/studio_images/studio-verbose-view_sui.jpg"
  - "resources/images/studio_images/studio_close_branch_sui.jpg"
  - "resources/images/studio_images/studio_tag_project.png"
  - "resources/images/studio_images/studioimages/studio_diagram_branching.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Práticas recomendadas: Ramificação de projetos

**Aplica-se a** : TBM Studio 12.1 e posterior

A ramificação é um recurso avançado adicionado à plataforma para Apptio TBM Studio v.12.1. A ramificação é um recurso essencial encontrado na maioria dos sistemas modernos de controle de versão. A ramificação permite que os usuários criem uma cópia de um projeto completo, façam alterações na cópia do projeto em paralelo e, em seguida, promovam a produção dessas alterações com o projeto original. A ramificação é uma adição extremamente poderosa à experiência do site TBM Studio , e é importante entender seus usos pretendidos.

![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio_diagram_branching.png)

## Filiais e espaços de trabalho

Um *espaço de trabalho* é um ambiente específico do usuário no qual as alterações nos documentos com check-out permanecem até que seja feito o check-in novamente. Ao fazer o check-out de um documento em um espaço de trabalho, você tem um bloqueio exclusivo para esse documento. Ninguém pode fazer o check-out desse documento até que ele seja registrado.

Uma *ramificação* é uma cópia completa do projeto atual no momento em que a ramificação foi criada. Quando você faz o check-out de um documento de um branch, esse documento vai para um espaço de trabalho nesse branch. As alterações feitas em documentos nos espaços de trabalho do ramo aparecem no ramo somente depois que esses documentos são registrados. Para ver as alterações no tronco, o ramo deve ser mesclado de volta ao projeto principal.

## Por que você usaria a ramificação?

As ramificações têm como objetivo dar suporte a um dos dois casos de uso principais:

- **Configuração de longa duração** : Há um conjunto de alterações a serem feitas que levarão muito tempo antes de estarem prontas para serem promovidas à produção. Enquanto isso, alterações, como cargas mensais de dados, precisam ser feitas e enviadas para a produção. Você pode criar uma ramificação e fazer as alterações na ramificação enquanto os carregamentos de dados operacionais continuam no tronco.
- **Hotfix prod** : Há um problema com algo na produção, mas houve um desenvolvimento que não está pronto para ser promovido à produção. Você pode criar uma ramificação, corrigir o problema específico e, em seguida, mesclar a ramificação com a Produção.
- **Auditar o estado anterior ou o estado arquivado** : Há uma necessidade comercial de examinar o estado anterior de um projeto. Por exemplo, um ano fiscal anterior pode ser encerrado e são feitas alterações no modelo, mas você precisa examinar os números desse estado anterior. Usando ramificações, é possível observar o estado exato do sistema em um momento anterior.

**Conceitos de filiais:**

- Cada ramificação é uma cópia completa do projeto tronco. Isso tem implicações de desempenho, conforme discutido na seção Práticas recomendadas e considerações de desempenho a seguir.
- O número de filiais de um ambiente é limitado a cinco (5)
- Para abrir e fechar filiais, você deve ser atribuído a uma função que tenha a permissão *Criar e fechar filiais*.
- O fechamento de uma ramificação remove o projeto da ramificação juntamente com todos os projetos de compilação, espaços de trabalho e assim por diante. Uma ramificação não pode ser fechada se tiver uma compilação usada na produção. Quando uma compilação de teste do tronco for promovida para produção, a ramificação poderá ser fechada. Consulte também [Solução de problemas de um projeto ramificado que não pode ser fechado](https://community.ibm.com/community/user/viewdocument/troubleshoot-a-branched-project-tha "(Abre em uma nova guia ou janela)").
- Ao mesclar alterações em um ramo, você pode:
  - Selecione os documentos que você deseja mesclar.
  - Veja uma lista de conflitos, se houver algum (um conflito ocorre quando são feitas alterações no mesmo documento em duas ramificações diferentes).
- Não é possível mesclar um documento se ele tiver *sido verificado* por outro usuário trabalhando no trunk.
- Todos os documentos em um ramo devem ser *verificados* antes que você possa mesclar o ramo.
- Existem tags para todas as compilações, e tags personalizadas podem ser criadas para identificar compilações específicas.
- Para ramificações de hotfix, quando a ramificação é promovida para produção, ela substitui a ramificação do tronco.

## Práticas recomendadas e considerações sobre o desempenho

As ramificações usam a mesma quantidade de recursos (por exemplo, memória, CPU e assim por diante) que o projeto do qual são ramificadas. Portanto, quando você cria uma ramificação, está adicionando uma carga ao seu ambiente Apptio igual à carga de qualquer atividade em que possa se envolver com o seu projeto principal. Portanto, é importante dimensionar corretamente o tempo em sua filial. Para fazer isso, você deve alterar o "Início do projeto" e o "Fim do projeto" nas "Configurações de tempo" do projeto para restringir o tempo a um número apropriado de períodos. Por exemplo, se estiver trabalhando com modelagem, provavelmente só precisará de um período de tempo. Se estiver trabalhando em relatórios com tendências, poderá testá-los com 3 períodos. Se você precisar validar as alterações com o período de tempo completo, poderá alterar o tempo de volta para o intervalo original ou final para um teste final quando terminar.

Ao criar uma ramificação, considere o impacto nos cálculos de estágio e na carga do espaço de trabalho e certifique-se de dimensionar o tempo certo para sua ramificação. Para obter mais informações sobre os impactos das ramificações no desempenho do espaço de trabalho, consulte [Gerenciamento do desempenho em seu ambiente de desenvolvimento](https://community.ibm.com/community/user/viewdocument/manage-performance-in-your-developm?CommunityKey=44bcb0d2-5ce6-4504-89eb-019253d3b5d8&tab=librarydocuments "(Abre em uma nova guia ou janela)").

Além disso, com exceção das ramificações de hotfix, os cálculos das ramificações serão enfileirados com os cálculos do projeto do qual elas são ramificadas. Se você criar uma ramificação a partir de uma versão do projeto que levou três horas para ser calculada, no momento em que a ramificação for criada, os cálculos de desenvolvimento e estágio serão iniciados. Se alguém fizer o check-in de uma alteração no tronco depois que você tiver feito a ramificação, os cálculos de desenvolvimento e estágio resultantes para o tronco serão enfileirados atrás do cálculo da ramificação.

A imagem a seguir mostra a visualização do projeto AdminDB dos cálculos para todos os cálculos de ramificação de projetos. Observe os dois conjuntos de cálculos de ramificação em amarelo e laranja, e o cálculo do tronco para o projeto no qual essas ramificações se baseiam em verde:

![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studio-calculation-queue_sui_1.jpg)

Os TBMAs que desejarem navegar para essa visualização devem acessar Enhanced Access
Administration, selecionar o **TBM Studio** e, em seguida, abrir a **fila de cálculo**.

## Criar uma ramificação com base na compilação concluída mais recente

No ambiente Stage, crie uma ramificação usando o comando **Create branch (Criar ramificação** ) na guia Project (Projeto), grupo Manage (Gerenciar).

Quando estiver no ambiente de desenvolvimento, você poderá usar o comando **Criar ramificação** somente se não tiver feito check-out de nada. Essa restrição é intencional. A implicação é que você pode desejar que as alterações em seu espaço de trabalho façam parte da ramificação, mas elas não farão isso até que todos os materiais sejam registrados e calculados.

## Aplicar uma tag personalizada a uma compilação

Embora todas as compilações tenham tags padrão, conforme indicado em [Criar uma ramificação de uma compilação anterior que não tenha uma tag personalizada aplicada](#BestpracticesBranchingprojects__Createabranchbasedonthemostrecentcompletedbuild), depois que você bloquear o estágio, o botão **Tag Project** ficará disponível. Você pode selecionar **Tag Project** para aplicar uma tag personalizada a uma compilação, o que pode ajudar a encontrar uma compilação com muito mais facilidade.

![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studio_tag_project.png)

Essa tag aparecerá na página Builds para que você possa procurá-la facilmente e usá-la para ramificação.

Nota:

No momento da redação deste texto, o botão Tag Project *não* estará disponível depois que você promover uma compilação.

## Criar uma filial com a opção de check-out automático

Ao trabalhar com relatórios que contêm tabelas editáveis, o recurso de check-out automático faz o check-out automático da tabela subjacente quando um relatório é modificado, eliminando a necessidade de check-out manual. Esse recurso está disponível somente no projeto da filial e oferece vários benefícios, incluindo melhor experiência do usuário, maior produtividade e menos erros. Se uma tabela editável for verificada por outra pessoa, será exibida uma mensagem de erro para evitar conflitos e garantir a transparência.

1. Navegue até a filial.

   ![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ac-1.jpg)
2. Atualize o valor da coluna IT para IT Extension e **salve** as alterações.

   ![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ac-2.jpg)
3. O botão **Check in** é ativado e a tabela editável subjacente é verificada.

   ![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ac-3.jpg)

## Criar uma ramificação a partir de uma tag

Para ramificar a partir de uma tag:

1. Localize a tag no histórico de check-in.
2. Clique com o botão direito do mouse na tag e selecione **Criar ramificação a partir deste ponto**.

   ![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studio-create-branch-from-tag_sui.jpg)

## Criar uma ramificação a partir de uma compilação padrão que não tenha uma tag personalizada aplicada

Às vezes, você pode querer criar uma ramificação de uma compilação anterior que não foi marcada. Por exemplo, se você descobrir que algo foi alterado e precisar descobrir quando essa alteração foi introduzida. Para criar uma ramificação a partir de uma compilação padrão

1. Selecione a guia **Projeto** e clique em Check In History.
2. Clique com o botão direito do mouse na guia Check In History na parte inferior e selecione Verbose View. Quando estiver no Verbose View, você poderá ver todas as compilações padrão sem tags personalizadas marcadas em verde.

   ![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studio-verbose-view_sui.jpg)
3. Clique com o botão direito do mouse em uma compilação padrão e selecione **Criar ramificação a partir deste ponto**.

## Navegar entre as ramificações e o tronco

Quando existe uma ramificação para um projeto, você pode navegar para a ramificação ou voltar para o tronco, usando o menu suspenso na barra de menus:

![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studio-navigate-branches_sui.jpg)

## Use uma filial

- **Limitar os check-ins em filiais a ~30 documentos** - Ao trabalhar em uma filial, a prática recomendada atualmente é limitar os check-ins a aproximadamente trinta (30) documentos. **Exemplo** : você tem 100 documentos retirados na filial. Registre aproximadamente trinta documentos, depois registre outros trinta documentos e assim por diante. Essa ação fornece um limite para os tamanhos individuais de check-in. Essa prática é recomendada para resolver uma limitação ao mesclar os check-ins com o tronco.
- **Fazer alterações** - depois que uma ramificação é criada, as alterações são feitas da mesma forma que são feitas no tronco. Os documentos podem ser retirados, modificados e devolvidos à filial.
- **Ramificações e espaços de trabalho** - Seu espaço de trabalho no tronco é separado do seu espaço de trabalho nas ramificações. Se você fizer check-out de um documento em uma ramificação e, em seguida, navegar para o tronco, não verá o documento que fez check-out lá porque é um *espaço de trabalho separado*.
- **Considerações sobre o check-out** - É possível fazer o check-out do mesmo documento na filial e no tronco ao mesmo tempo. A implicação é que uma pessoa pode estar trabalhando no documento e fazer alterações no tronco que não estão na ramificação.

## Mesclar uma ramificação de volta ao tronco

Antes de fazer a fusão, há alguns pré-requisitos:

- Nenhum dos documentos a serem mesclados pode ser verificado no tronco.
- O usuário que executa a mesclagem não pode ter nenhum documento verificado no tronco.
- Não faça a fusão do tronco com os galhos ou entre os galhos.

Embora a interface do usuário ofereça suporte à mesclagem entre ramificações e do tronco para as ramificações, há limitações que tornam essa ação fora das práticas recomendadas atualmente.

## Executar a mesclagem

Após o check-in das alterações em uma ramificação, os check-ins, conforme visualizados no Histórico de check-ins, podem ser selecionados para serem mesclados no tronco:

1. Selecione um ou mais check-ins no histórico de check-ins usando **Ctrl+clique** ou **Shift+clique**.
2. Clique com o botão direito do mouse nos registros selecionados e selecione **Merge changes to branch (Mesclar alterações na ramificação** ). Nesse momento, é recomendável mesclar as alterações da ramificação com o tronco.

   ![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studio-merge-to-branch_sui.jpg)

## Resolver conflitos

Quando você executa uma mesclagem, uma janela de diálogo de mesclagem pode ser exibida indicando que há conflitos. Os conflitos ocorrem quando o tronco tem uma versão de documento que foi modificada desde o momento em que a ramificação foi criada. Portanto, se você fosse mesclar o documento *e* fazer o check-in, o documento da ramificação substituiria o documento do tronco. Para resolver esses conflitos, você deve integrar manualmente as alterações presentes na cópia do documento no *tronco* à cópia do documento na *ramificação* ou deve estar disposto a permitir que as alterações sejam substituídas.

## Check-in após a fusão

Depois que você mesclar as alterações, elas serão verificadas no tronco. Você deve verificá-los no tronco antes que a operação de mesclagem seja concluída. Além disso, observe que há um documento com o nome da própria filial, que também deve ser registrado.

## Gerenciar filiais

Os administradores podem usar esse recurso para evitar a exclusão acidental de uma ramificação, eliminando assim a necessidade de backup para recuperar uma ramificação excluída.

Em TBM Studio, navegue até a guia **Project (Projeto** ), selecione a opção **Manage Branches (Gerenciar ramificações** ) e, em seguida, selecione "X" para fechar uma ramificação.

![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/mb-1.png)

É exibida uma caixa de diálogo de confirmação. O administrador deve digitar "delete" e, em seguida, selecionar o botão OK.

![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/mb-2.png)

## Fechar a filial

Após concluir a mesclagem dos documentos alterados no tronco, feche a ramificação. O fechamento da filial economiza recursos.

![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studio_close_branch_sui.jpg)

## Usar uma ramificação para fazer o hotfix da versão prod

Ocasionalmente, uma mudança pode ser necessária no produto rapidamente e as mudanças no estágio podem não estar prontas para a implementação. Nesse cenário, um *hotfix* pode ser apropriado. Para aplicar um hotfix a um documento no prod, siga estas etapas:

1. Navegue até o documento no prod.
2. *Confira* o documento. Quando a caixa de diálogo for exibida, você poderá selecionar **Desenvolvimento** ou **Hotfix**
3. Selecione **Hotfix**.

   ![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studio-create-hotfix_sui.jpg)
4. Aguarde até que a ramificação do hotfix calcule no estágio. O sistema calculará as ramificações de hotfix em paralelo com outros cálculos, portanto, o enfileiramento normal de compilação não se aplica.
5. Selecione **Lock** para bloquear a ramificação do hotfix no estágio.
6. Selecione **Promote Now (Promover agora** ) para promover a ramificação do hotfix para a produção:

   ![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studio-promote-now_sui.jpg)

   O sistema gerará uma ramificação chamada Hotfix, na qual você poderá fazer a alteração.

Se você tentar fechar a ramificação do hotfix nesse momento, receberá um erro. Isso ocorre porque a compilação na produção não se baseia na compilação do hotfix e o sistema não permitirá que a ramificação do hotfix seja fechada.

Para encerrar o processo de hotfix:

1. Faça a fusão das alterações no tronco. Consulte a seção [Mesclar uma ramificação de volta ao tronco](bp-branching-projects.html#BestpracticesBranchingprojects__Mergeabranchbackintothetrunk) acima para obter detalhes.
2. Promova a compilação com as alterações do hotfix para o prod.
3. Feche a ramificação do hotfix.

Consulte também [Solução de problemas de um projeto ramificado que não pode ser fechado](https://community.ibm.com/community/user/viewdocument/troubleshoot-a-branched-project-tha "(Abre em uma nova guia ou janela)").

## Arquivar períodos de tempo e acessar arquivos

Periodicamente, é útil arquivar períodos de tempo passados. Por exemplo, quando você deseja desativar o cálculo para um ou mais exercícios fiscais anteriores para reduzir o tempo de cálculo.

Para arquivar períodos de tempo:

1. Antes de alterar as configurações de hora, aplique uma tag personalizada. Use uma convenção de nomenclatura para a tag, como adicionar um prefixo ao nome da tag com a palavra "Archive" (Arquivo), para que seja fácil encontrar todas as compilações que correspondem a eventos arquivados.
2. Ajuste as configurações de horário para que a data de início do projeto seja a que você deseja e, em seguida, faça o check-in. Isso fechará os períodos de tempo antigos.

Se quiser acessar os períodos de tempo arquivados, pesquise as tags de arquivo e gere uma ramificação a partir da tag de arquivo.

## Perguntas frequentes sobre ramificação

**Por que o Create Branch não está disponível?**

Se o botão **Criar ramificação** não estiver disponível ou se ele não aparecer no menu de contexto quando você clicar com o botão direito do mouse em uma tag de compilação, talvez você tenha excedido o número de ramificações permitido para o seu ambiente. O limite de filiais é de cinco filiais para o ambiente (incluindo todos os projetos).

**Por que não consigo fechar um projeto ramificado?**

Se você clicar em **Fechar ramificação** na guia **Projeto** e aparecer uma mensagem de aviso informando que o projeto ramificado não pode ser fechado, consulte [Solucionar problemas de um projeto ramificado que não pode ser fechado](https://community.ibm.com/community/user/viewdocument/troubleshoot-a-branched-project-tha "(Abre em uma nova guia ou janela)").
