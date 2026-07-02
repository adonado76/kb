---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Planejamento: O que há de novo em 2021"
breadcrumb: []
source_path: "it-planning/release-notes/whats-new-2021.html"
images:
  - "resources/planning_images/icon-itp-apex-add-filter.png"
  - "resources/planning_images/icon-itp-apex-add-filter_20x20.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Planejamento: O que há de novo em 2021

## 3.10 - 13 de dezembro de 2021

A partir de segunda-feira, 13/12/2021, os principais locatários de produção começam a fazer upgrade para a versão 3.10. Com esta versão, o Planning terá um novo cabeçalho Plan.

## Novo cabeçalho do plano

![](../../resources/images/it%20planning_images/plan-header-21-12-13.png)

- O menu Plan foi movido para o canto superior esquerdo da tela.
- Agora você acessa as funções do Plano em Opções (![](../../resources/images/it%20planning_images/options1_34x29.png)) no canto superior direito da tela. Isso inclui Open Plan, Finalize Plan, Submit Changes, Unlock Cost Objects, Edit, Compare Shortcuts e Update Reference Data. Essas funções funcionam da mesma forma que antes.

As páginas a seguir exibem o novo cabeçalho do Plano:

- Painel
- Resumo
- despesas
- Estado
- Análise de variância
- Destinos

## 3.9 - 6 de dezembro de 2021

A partir de segunda-feira, 12/6/2021, os principais locatários de produção começarão a fazer upgrade para a versão 3.9. Esta versão adiciona as ações do Cost Transparency Integration (CTI) à lista de tipos de eventos compatíveis no Histórico de alterações e adiciona um novo cabeçalho de plano em Planning > Expenses (Planejamento > Despesas ).

## Eventos adicionais do histórico de alterações

As ações de CTI agora são registradas no Event Log do serviço Change History.

[Saiba mais sobre o histórico da Change](../planning/change-history.html)

## Novo cabeçalho do plano em despesas

Planning > Expenses usa um novo cabeçalho Plan, que será implementado de forma mais completa na versão 3.10.

![](../../resources/images/it%20planning_images/plan-header-21-12-13.png)

- O menu Plan foi movido para o canto superior esquerdo da tela.
- Agora você acessa as funções do Plano em Opções (![](../../resources/images/it%20planning_images/options1_34x29.png)) no canto superior direito da tela. Isso inclui Open Plan, Finalize Plan, Submit Changes, Unlock Cost Objects, Edit, Compare Shortcuts e Update Reference Data. Essas funções funcionam da mesma forma que antes.

## 3.8 - 15 de novembro de 2021

A partir de segunda-feira, 15/11/2021, a versão 3.8 entrará em operação nos principais ambientes de produção. Esta versão adiciona a pesquisa de texto à funcionalidade de filtro no Registro de Eventos.

[Saiba mais sobre o registro de eventos](../planning/change-history.html)

## 3.7 - 01 de novembro de 2021

## Somente versão de manutenção

Esta versão contém apenas correções de bugs e manutenção para atender aos requisitos operacionais.

## 3.6 - 18 de outubro de 2021

## Somente versão de manutenção

Esta versão contém apenas correções de bugs e manutenção para atender aos requisitos operacionais.

## 3.5 - 04 de outubro de 2021

A partir de segunda-feira, 4/10/2021, os principais locatários de produção começarão a fazer upgrade para a versão 3.5. Esta versão adiciona a funcionalidade de classificação e filtro à página Planos.

[Saiba mais sobre a página Planos](../planning/manage-plans.html "Com a página Plans, você pode gerenciar seus planos de forma fácil e intuitiva.")

## 3.4 - 20 de setembro de 2021

A partir de segunda-feira, 20/9/2021, a versão 3.4 entrará em operação nos principais ambientes de produção. Esta versão adiciona novos tipos de eventos ao Histórico de alterações de planejamento: Excluir dimensão personalizada e Excluir filtro de item de linha.

## Eventos adicionais do histórico de alterações

Os seguintes tipos de eventos foram adicionados ao serviço Change History:

- Excluir dimensão personalizada
- Excluir filtro de item de linha

[Saiba mais sobre o histórico da Change](../planning/change-history.html)

## 3.3 - 6 de setembro de 2021

A partir de segunda-feira, 6/9/2021, a versão 3.3 entrará em operação nos principais ambientes de produção. Esta versão contém um único recurso. O Planning agora tem suporte para calendários de 13 períodos.

## suporte ao calendário de 13 períodos

O planejamento amplia o uso de calendários fiscais personalizados para incluir agora o suporte a calendários de 13 períodos.

Para obter mais informações, entre em contato com a equipe da sua conta Apptio.

## 3.2 - 23 de agosto de 2021

A partir de segunda-feira, 23/08/2021, a versão 3.2 entrará em operação nos ambientes de produção. Esta versão contém um único recurso secundário: Ações de grupo na página de status.

## Ações de grupo na página de status

As ações em nível de grupo e o status dos objetos de custo foram restaurados para Enviar, Aprovar e Devolver.

[Saiba mais sobre ações em grupo](../planning/review-approve-return.html)

## 3.1 - 9 de agosto de 2021

A partir de segunda-feira, 9/8/2021, a versão 3.1 entrará em operação nos ambientes de produção. Esta versão contém dois recursos menores: Códigos de itens de linha do plano, um recurso antecipado que atribui um código exclusivo a cada item de linha no planejamento, e a adição de novos tipos de eventos ao serviço Histórico de alterações.

## Códigos de itens planejados

Três atributos foram adicionados às tabelas no Planejamento:

- Código do item de linha
- Código do item de linha de origem
- Plano de origem

Juntos, esses três atributos ajudam os usuários a identificar um determinado item de linha e a entender como ele foi criado. Para itens de linha gerados ou entradas que não foram diretamente devidas a uma entrada direta do usuário, o código do item de linha ficará em branco. No entanto, os atributos de origem serão preenchidos conforme apropriado.

Os itens de linha nas tabelas a seguir agora têm um código exclusivo atribuído:

- Financeira
- Mão de Obra
- Contrato
- Ativo
- Alocação
- a demanda

[Saiba mais sobre os códigos de itens de linha](../planning/line-item-codes.html)

## Eventos adicionais do histórico de alterações

Os seguintes tipos de eventos foram adicionados ao serviço Change History:

- Adicionar lista personalizada
- Atualizar lista personalizada
- Excluir lista personalizada

Esses eventos agora serão exibidos no Registro de Eventos quando ocorrerem. O rastreamento desses tipos de eventos começou com essa atualização. As ocorrências desses eventos anteriores a essa atualização não serão exibidas.

[Saiba mais sobre o histórico da Change](../planning/change-history.html)

## 3.00 - 26 de julho de 2021

A partir de segunda-feira, 26 de julho de 2021, a versão do Planning 3.00 entrará em operação nos ambientes de produção. Esta versão contém três recursos: a capacidade de classificar entradas no Registro de Eventos pelo conteúdo de uma coluna, uma nova página de gerenciamento de planos e uma nova ferramenta para selecionar datas de início e término para períodos de tempo.

## Ordenação do histórico de alterações

No Registro de Eventos, você pode reordenar o histórico de alterações classificando as entradas por coluna.

Você pode classificar as entradas por essas colunas:

- Registro de data e hora
- Evento
- Área
- Tipo de item

[Saiba mais sobre o histórico da Change](../planning/change-history.html)

## Página de gerenciamento do plano

Foi adicionada uma nova página chamada Planos. Esta página é o novo local para alterar o Plano que você está visualizando no aplicativo. Você pode usar essa página para executar procedimentos de gerenciamento de planos, como arquivamento ou exclusão de planos.

Para acessar essa página, abra o painel de navegação e selecione Planning > Plans.

[Saiba mais sobre a página Planos](../planning/manage-plans.html "Com a página Plans, você pode gerenciar seus planos de forma fácil e intuitiva.")

## Seletor de tempo de período aprimorado

Em todo o aplicativo em que o tempo é periódico, foi adicionado um novo componente seletor de período de tempo. Você pode optar por visualizar um ano específico do plano ou um intervalo de tempo personalizado entre dois períodos. O seletor permanece no mesmo local.

## 2.99 - 12 de julho de 2021

Versão de manutenção

## Somente versão de manutenção

Esta versão contém apenas correções de bugs e manutenção para atender aos requisitos operacionais.

## 2.98 - 28 de junho de 2021

A versão do Planning 2.98 já está disponível em ambientes de produção. Esta versão contém um recurso secundário, *Enhanced Configuration Experience (Experiência de configuração aprimorada* ).

## Experiência de configuração aprimorada

O planejamento está fazendo a transição para uma nova experiência de configuração. Todas as funcionalidades da página de dados de referência serão migradas para o módulo Configuration por meio da navegação à esquerda.

Em Configuration (Configuração ), agora você pode encontrar as seguintes páginas:

- Dados de referência : você ainda pode gerenciar todas as dimensões usando a página Dados de referência com algumas pequenas alterações. Uma nova tela de navegação foi adicionada para separar os diferentes tipos de dimensões no aplicativo. Agora você pode gerenciar os atributos de dimensão individuais usando a página Schema.
- Schema : essa nova página usa uma interface de navegação semelhante à da nova página Reference Data. Ele permite que você configure os atributos individuais nas tabelas de dimensões e de itens de linha.
- Listas personalizadas, filtros de itens de linha, configuração de calendário : nenhuma alteração. A página para gerenciar os filtros de itens de linha permanece aqui em Configuration (Configuração).
- Permissões de objeto de custo, regras de alocação de mão de obra (anteriormente incluídas em Dados de referência )

## Como esse recurso pode ajudá-lo

*A experiência de configuração aprimorada* oferece uma experiência de usuário mais intuitiva para a configuração do aplicativo. Continuaremos a fazer melhorias incrementais no Configuration nas próximas versões para oferecer suporte a novos recursos.

## 2.97 - 14 de junho de 2021

A versão do Planning 2.97 já está disponível em ambientes de produção. Seu ambiente é atualizado na semana que começa em 14 de junho, no [dia de atualização escolhido](https://community.apptio.com/communities/community-home/librarydocuments/viewdocument?DocumentKey=9add9ee9-7c11-446b-a6cc-98ab6eecf71b "(Abre em uma nova guia ou janela)"). Essa versão consiste principalmente em dois recursos: Histórico de alterações e amortização de mão de obra por dia útil.

## Histórico de alterações

Um novo serviço e uma nova página no Planning permitem que você veja um registro de todas as alterações feitas em um plano. O registro de eventos mostra quem, o quê e quando de qualquer alteração feita no aplicativo.

![](../../resources/images/it%20planning_images/release-notes/change-history.png)

## Como esse recurso pode ajudá-lo

Os usuários precisam entender como um plano evolui com novas informações, uma mudança nas prioridades ou uma decisão tomada durante um processo de aprovação. O uso desse recurso para visualizar as alterações aumenta a probabilidade de que erros menores e difíceis de encontrar sejam encontrados e corrigidos.

## Mais informações sobre esse recurso

Para acessar esse recurso, navegue até Change History (Histórico de alterações) > Event Log (Registro de eventos ).

[Visualizar e exportar o histórico de alterações](../planning/change-history.html)

## Amortização da jornada de trabalho

Com um novo método de amortização para itens de linha de mão de obra, os usuários agora podem configurar o aplicativo para calcular as despesas de amortização com base no cronograma exclusivo de dias úteis da empresa. O recurso suporta qualquer número de programações exclusivas. Esse método leva em conta os dias úteis reais, calculando uma média ponderada de dias úteis por mês.

Para obter mais informações, consulte [Dados de referência da configuração do trabalho](../planning/manage-labor-configuration.html "As tarefas abaixo só podem ser executadas por usuários atribuídos às funções Admin ou Budget Process Owner. Para obter mais informações sobre funções, consulte Permissões e funções do Frontdoor.").

## Configuração do calendário

Em apoio a esse novo método de amortização de mão de obra por dia útil, uma nova página foi adicionada ao Configuration para criar calendários personalizados de dias úteis.

Para acessar esse recurso, navegue até Configuration > Calendar setup (Configuração > Configuração do calendário ).

## 2.96 - 31 de maio de 2021

## Liberação cancelada

Esse lançamento programado foi cancelado. Esse cancelamento não afetará as versões futuras.

## 2.95 - 10 de maio de 2021

## Somente versão de manutenção

Esta versão contém apenas correções de bugs e manutenção para atender aos requisitos operacionais.

## 2.94 - 3 de maio de 2021

A versão do Planning 2.94 já está disponível em ambientes de produção. Seu ambiente é atualizado na semana que começa em 3 de maio, no [dia de atualização](https://community.apptio.com/communities/community-home/librarydocuments/viewdocument?DocumentKey=9add9ee9-7c11-446b-a6cc-98ab6eecf71b "(Abre em uma nova guia ou janela)") escolhido. Esta versão contém o primeiro item de um conjunto de alterações de várias versões chamado *Enhanced Configuration Experience (Experiência de configuração aprimorada* ).

## Experiência de configuração aprimorada: Filtros de itens de linha

Nas próximas versões, o Planning está fazendo a transição para uma nova experiência de configuração. Os itens encontrados na página Reference Data serão migrados para a página Configuration, com suporte da experiência de edição *do Apex*. Nesta versão, a página Filtros de itens de linha foi migrada para a página Configuração.

## Para acessar os filtros de itens de linha

1. No menu de navegação à esquerda, selecione Configuration>Line Item Filters (Configuração>Filtros de itens de linha ).

   ![](../../../../../03-media/apptio-planning/resources/planning_images/icon-itp-apex-add-filter.png)

   Agora você pode adicionar filtros, classificando por dimensões ou colunas de atributos. Para adicionar um novo filtro, selecione ![](../../../../../03-media/apptio-planning/resources/planning_images/icon-itp-apex-add-filter_20x20.png). Para obter mais informações, consulte [Filtros de itens de linha](../planning/itp-dependent-picklists.html "A interface de usuário do Apptio Planning usa listas suspensas para permitir que os usuários insiram dados de uma lista de opções aprovadas. Os filtros de itens de linha permitem restringir as opções que podem ser selecionadas em uma lista suspensa com base no valor já inserido em outra coluna. Isso facilita para o usuário selecionar a opção certa, pois ele não fica sobrecarregado com uma lista de opções irrelevantes.").

## 2.93 - 19 de abril de 2021

A versão do Planning 2.93 já está disponível em ambientes de produção. Seu ambiente é atualizado na semana que começa em 19 de abril, no [dia de atualização](https://community.apptio.com/communities/community-home/librarydocuments/viewdocument?DocumentKey=9add9ee9-7c11-446b-a6cc-98ab6eecf71b "(Abre em uma nova guia ou janela)") escolhido. Essa versão consiste principalmente em um único recurso secundário: Substituição do método de depreciação padrão do ativo.

## Substituição do método de depreciação padrão do ativo

Esse recurso permite que os usuários selecionem o método de depreciação a ser aplicado a itens de linha de ativos individuais.

Anteriormente, os itens de linha do ativo usavam o método de depreciação configurado para a classe de ativo selecionada, e o método de depreciação não podia ser alterado na granularidade da linha do ativo. Agora, os usuários podem alterar o método de depreciação na tabela Expenses > Assets (Despesas > Ativos ) no aplicativo. Nenhuma configuração precisa ser alterada na configuração para ativar esse recurso.

Por padrão, as partidas individuais do ativo continuam a usar o método de depreciação definido nos dados de referência de configuração para a classe do ativo.

Para obter mais informações, consulte [Planejar a redução dos valores do imobilizado com métodos de depreciação](../planning/depreciation-method.html "Apptio Os aplicativos de planejamento usam métodos de depreciação para modelar como o valor de um ativo diminui ao longo do tempo.")

## 2.92 - 22 de março de 2021

A versão do Planning 2.92 está seguindo um cronograma de lançamento exclusivo. A [postagem da comunidade](https://community.apptio.com/blogs/debbie-hagen1/2021/02/25/financial-management-292-simplified-versioning "(Abre em uma nova guia ou janela)") a seguir descreve o cronograma de lançamento.

Para ambientes de clientes que fazem upgrade durante a semana, sua janela de manutenção ocorrerá durante o [dia de upgrade](https://community.apptio.com/communities/community-home/librarydocuments/viewdocument?DocumentKey=9add9ee9-7c11-446b-a6cc-98ab6eecf71b "(Abre em uma nova guia ou janela)") escolhido, como de costume.

Para alguns clientes selecionados, sua janela de manutenção ocorrerá em um dos próximos fins de semana: 20/03, 27/03, 3/04 ou 10/04. Você já deve ter sido notificado sobre esse dia de atualização. Entre em contato com suas equipes de conta para obter mais informações.

## Novo editor de listas personalizadas

A criação, edição e exclusão de listas personalizadas foram removidas dos dados de referência e colocadas em uma guia chamada configuração na navegação à esquerda recentemente adicionada.

## Atualização do layout público

O comportamento de como os layouts públicos seriam atualizados para outros usuários foi alterado para ser mais intuitivo. Quando um layout for atualizado, o novo layout será enviado diretamente a todos os usuários na próxima atualização da página da Web.

## Edição de grupo

Devido à nova experiência de usuário de controle de versão simplificada introduzida no verão de 2020, dois recursos de edição de grupo regrediram. Esta versão apresenta grandes alterações no back-end do Simplified Versioning que nos permitiram reintroduzir a edição em grupo.

Os seguintes recursos de edição de grupos foram adicionados em todos os ambientes.

- Os usuários agora podem processar itens de linha que abrangem vários objetos de custo em uma tabela de itens de linha.
- Na página de status, as ações de envio/aprovação/rejeição agora podem ser executadas em objetos de custo de grupo.

Agora, as linhas de objetos de custo enviados são somente de leitura em nível de grupo e só podem ser editadas entrando no modo Editar

## 2.91 - 8 de março de 2021

A versão do Planning 2.91 já está disponível em ambientes de produção. Seu ambiente é atualizado na semana que começa em 8 de março, no [dia de atualização escolhido](https://community.apptio.com/communities/community-home/librarydocuments/viewdocument?DocumentKey=9add9ee9-7c11-446b-a6cc-98ab6eecf71b "(Abre em uma nova guia ou janela)"). Esta versão consiste principalmente em dois recursos não relacionados: Comentários baseados em planos e atualização automática do total do contrato.

## Comentários baseados em planos

Apptio agora está ativado no Planning. Os usuários agora podem inserir comentários e colaborar no nível do plano com outros usuários. [Saiba mais sobre o uso de comentários](../../cnc/using-comments.html).

No Planning, o ícone de comentários está alinhado à direita na barra de menu superior, como mostrado abaixo:

![](../../resources/images/it%20planning_images/release-notes/comments-icon.png)

## Total do contrato de atualização automática

O segundo recurso, Auto-update Contract Total (Atualização automática do total do contrato), é uma alteração relativamente pequena na experiência do usuário solicitada por nossa base de usuários. Os usuários expressaram que, quando o método de amortização manual é definido em um item de linha de contrato, há confusão sobre se a coluna do valor do contrato reflete os custos periódicos totais do contrato. Além disso, alguns clientes querem que o valor do contrato seja obtido de um sistema diferente e gostariam de manter esse número independente do cronograma de amortização do custo do período. Esse recurso atende a ambas as solicitações.

Para ativar ou desativar a atualização automática do total do contrato, acesse ![](../../resources/images/it%20planning_images/release-notes/settings-icon.png) > Perfil da empresa, role para baixo até Ativar recursos e selecione o botão de rádio Atualizar automaticamente o total do contrato.

![](../../resources/images/it%20planning_images/release-notes/auto-update.png)

Quando a atualização automática do total do contrato estiver ativada :

- A coluna Valor somará automaticamente os custos periódicos totais entre as datas de início e término do contrato.
- Quando a data inicial ou final for alterada, o valor será atualizado de acordo.
- Ao importar itens de linha de contrato via csv, o valor será sobrescrito e substituído pelo valor calculado usando as datas de início e término fornecidas.

Quando a atualização automática do total do contrato estiver desativada :

- A coluna Amount funcionará como antes. Ele não somará automaticamente os custos periódicos totais entre as datas de início e término do contrato. A alteração da data inicial ou final não terá efeito sobre o valor total.
- Esse recurso será desativado por padrão. Quando os ambientes forem atualizados, esse recurso será inicialmente desativado.
- Ao importar itens de linha de contrato via csv, o valor deve ser incluído, pois não será calculado automaticamente.

## 2.90 - 22 de fevereiro de 2021

A versão do Planning 2.90 já está disponível em ambientes de produção. Seu ambiente é atualizado na semana que começa em 22 de fevereiro, no [dia de atualização escolhido](https://community.apptio.com/communities/community-home/librarydocuments/viewdocument?DocumentKey=9add9ee9-7c11-446b-a6cc-98ab6eecf71b "(Abre em uma nova guia ou janela)"). Essa versão consiste principalmente no tratamento de bônus/outras compensações.

## Manuseio de bônus/outras compensações

O manuseio de Bônus/Outras Remunerações permite que o Planejamento inclua outros componentes da remuneração do trabalho, além do salário-base, em um plano. Os usuários agora podem entender e acompanhar a remuneração total da mão de obra no Planning.

## Para usar o tratamento de bônus/outras compensações

1. Na página Despesas, navegue até a tabela Trabalho.

   Se a coluna Outra remuneração não for exibida, clique com o botão direito do mouse em uma coluna de cabeçalho ou selecione a seta suspensa para exibir um menu suspenso.
2. Selecione Show/Hide Columns (Mostrar/Ocultar colunas ).

   ![](../../resources/images/it%20planning_images/release-notes/other_comp_handling_showing_column.png)
3. Selecione Other Compensation e clique em Show.

   ![](../../resources/images/it%20planning_images/release-notes/other_comp_handling_selecting_other_comp.png)

   A coluna Outra remuneração agora está visível na tabela Trabalho. A compensação adicionada afeta as colunas de resumo. Abaixo, um bônus de US$ 10.000 é concedido a Andreas Delorbe. Seu custo para FY22 agora inclui o valor de Outras Compensações.

   ![](../../resources/images/it%20planning_images/release-notes/other_comp_handling_shown.png)

Também é possível alocar a taxa de Outras remunerações para contas diferentes.

1. Para alocar Outras remunerações a diferentes contas, acesse as Regras de alocação de mão de obra em Dados de referência.
2. No menu suspenso Tipo de valor de saída, selecione Percentual de outra taxa.

   O método de amortização de mão de obra e as regras avançadas funcionam da mesma forma que anteriormente.

   ![](../../resources/images/it%20planning_images/release-notes/other_comp_handling_percentage.png)
3. Publique as alterações e atualize os dados de referência na página Expenses (Despesas ).

   A despesa é atualizada conforme mostrado abaixo. O Plano de Incentivo de Bônus é definido como 7% da Outra Taxa.

   ![](../../resources/images/it%20planning_images/release-notes/other_comp_handling_bonus_incentive_plan.png)

A porcentagem de ajuste e as datas de início e término da remuneração não afetam Outras remunerações. O valor de Outras remunerações é um valor de ano fiscal. Se o plano abranger vários anos, o mesmo valor de bônus se aplica a cada ano fiscal.

## 2.89 - 8 de fevereiro de 2021

A versão do Planning 2.89 já está disponível em ambientes de produção. Seu ambiente é atualizado na semana que começa em 8 de fevereiro, no [dia de atualização escolhido](https://community.apptio.com/communities/community-home/librarydocuments/viewdocument?DocumentKey=9add9ee9-7c11-446b-a6cc-98ab6eecf71b "(Abre em uma nova guia ou janela)"). Essa versão consiste principalmente em Logs de erros detalhados, um recurso para ajudar os usuários a solucionar erros ao fazer upload de dados para o aplicativo. Um arquivo para download é fornecido para auxiliar os usuários na solução de problemas, caso ocorram erros no upload de dados para Reference Data, Spend Management e itens individuais. O arquivo destaca as linhas problemáticas anexando mensagens de erro em linha.

## Registros de erros detalhados

Os registros detalhados de erros ajudam os usuários a solucionar rapidamente seus próprios problemas de importação, reduzindo o tempo necessário para a entrada de dados e tarefas de serviço.

O arquivo de ajuda que contém os registros de erros pode ser acessado em Costing Standard Integration, Reference Data Dimension, Spend Management e importações de itens de linha, incluindo itens externos. O arquivo de ajuda não é fornecido quando são fornecidas entradas inválidas na importação da Listagem de Projetos. O arquivo de ajuda que está sendo fornecido para entradas válidas será corrigido em uma próxima versão.

Os registros detalhados de erros no arquivo de ajuda incluem apenas erros baseados em linhas, não em colunas. Se uma coluna inválida for fornecida na tentativa de importação, o arquivo de ajuda não fornecerá informações detalhadas sobre como solucionar o problema da coluna inválida. Os usuários podem fazer as alterações apropriadas diretamente no arquivo de ajuda e importá-lo para o aplicativo. O carregador ignora as colunas de erro.

Independentemente do estágio de importação durante o qual os erros são detectados, o botão Exportar arquivo de ajuda é exibido na caixa de diálogo de importação antes de aceitar uma importação. Você pode clicar no botão quando um arquivo com mensagens de erro estiver disponível para download.

![Modal de diálogo com o botão Exportar arquivo de ajuda](../../resources/images/it%20planning_images/release-notes/itp-r289-1.png)

## Como trabalhar com os registros de erros aprimorados

Para entender o recurso, considere o exemplo a seguir:

- Para ser uma entrada válida, os valores de Objeto de custo e Centro de custo da linha 2 devem corresponder. Cometemos um erro proposital para acionar o registro de erros.

  ![Entrada inválida simples](../../resources/images/it%20planning_images/release-notes/itp-r289-2.png)
- Quando importado, é exibida uma caixa de diálogo com as notificações de aviso. As notificações a serem abordadas no arquivo de ajuda podem ser encontradas no final da mensagem.

  ![Uma caixa de diálogo mostrando uma única entrada inválida](../../resources/images/it%20planning_images/release-notes/itp-r289-3.png)
- O arquivo de ajuda exportado anexa colunas a um arquivo csv da tabela aplicável. Essas novas colunas destacam os diferentes erros encontrados. Metadados adicionais estão disponíveis para a linha em que o erro ocorreu.

  ![Um exemplo de um arquivo de ajuda para uma única entrada inválida](../../resources/images/it%20planning_images/release-notes/itp-r289-4.png)

  Para entradas com vários erros, colunas adicionais são anexadas no final do arquivo de ajuda para tratar de cada um dos erros.
- Uma entrada adicional de moeda inválida é feita abaixo.

  ![Um exemplo de arquivo de importação com várias entradas inválidas](../../resources/images/it%20planning_images/release-notes/itp-r289-5.png)
- A caixa de diálogo agora exibe vários erros incluídos no arquivo de ajuda.

  ![Uma caixa de diálogo mostrando várias entradas inválidas](../../resources/images/it%20planning_images/release-notes/itp-r289-6.png)
- O arquivo de ajuda contém outra coluna com a entrada inválida adicional.

  ![Um exemplo de um arquivo de ajuda para várias entradas inválidas](../../resources/images/it%20planning_images/release-notes/itp-r289-7.png)

Além de importar locais no Planning, esse recurso também está disponível na página Costing Standard Integration. Ele funciona de forma idêntica à mostrada anteriormente. A imagem abaixo é um exemplo de uma caixa de diálogo que aparece quando uma entrada inválida é encontrada em Costing Standard Integration.

![Uma caixa de diálogo para uma entrada inválida na Integração da transparência de custos](../../resources/images/it%20planning_images/release-notes/itp-r289-8.png)

## 2.88 - 25 de janeiro de 2021

Somente versão de manutenção
:   Esta versão contém apenas correções de bugs e manutenção para atender aos requisitos operacionais.

## 2.87 - 11 de janeiro de 2021

Somente versão de manutenção
:   Esta versão contém apenas correções de bugs e manutenção para atender aos requisitos operacionais.
