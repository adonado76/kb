---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Configurar o aprendizado de máquina para pools de custos"
breadcrumb: []
source_path: "studio/data_studio/configuremachinelearning.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Configurar o aprendizado de máquina para pools de custos

**Aplica-se a** : TBM Studio 12.7 e posterior

Apptio usa técnicas de aprendizado de máquina para prever o pool de custos aplicável com base nas informações da conta. Uma nova etapa do pipeline, **Assign Cost Pools (Atribuir grupos de custos** ), é adicionada automaticamente às tabelas que são mapeadas para os dados mestre do plano de contas usando **Map Columns (Mapear colunas** ).

**Pré-requisitos**

- Costing Standard Componente de origem de custos, atualizado para 12.6, ou mais recente.
- Plano de contas: As informações da conta geralmente estão disponíveis em um sistema financeiro.
  - As colunas obrigatórias são Conta, Descrição da conta e Tipo de despesa. Entretanto, as colunas Account Group e Account Subgroup são recomendadas.
  - Use a etapa **Map Columns (Mapear colunas** ) com um destino de dados mestre do plano de contas.

## Mapear o plano de contas para os pools de custos

Conclua as seguintes tarefas.

## Configurar a etapa Atribuir pools de custos

Na tabela do plano de contas para a qual você deseja mapear os pools de custos, adicione a etapa **Mapear colunas**. Selecione um destino para os dados mestre do plano de contas. Consulte [Map Columns](mapcolumns.htm "(Abre em uma nova guia ou janela)") para obter mais informações sobre como usar o Map Columns.

A etapa **Atribuir pools de custos** é exibida.

![Atribuir pools de custos](../../resources/images/studio_images/studioimages/studio_charts%20of%20accounts_map%20columns.png)

## Configurar dados de referência

1. Quando você usa Assign Cost Pools pela primeira vez, utiliza a guia **Configuration (Configuração** ). Clique em **Configure Now (Configurar agora** ) para obter as informações de referência sobre pools de custos. A tela é atualizada automaticamente depois que todas as informações são recuperadas. As tabelas **ATUM Cost Classification Reference List** e **OpEx CapEx Classification Reference** aparecem na categoria Reference Tables (Tabelas de referência) à esquerda.
2. Faça o check-in dessas novas tabelas e da tabela do plano de contas ao mesmo tempo.

   ![Configurar dados de referência](../../resources/images/studio_images/studioimages/studio_chart%20of%20accounts_map%20columns.png)

   Se uma atualização estiver disponível, uma notificação será exibida na guia **Configuração**.
3. Para atualizar as tabelas de referência a qualquer momento, verifique a tabela que deseja atualizar. Navegue até a tabela ou clique nos dados de referência que deseja atualizar na guia **Configuração**. As atualizações são exibidas com um ícone de aviso amarelo.
4. Clique em **Update Reference Data (Atualizar dados de referência** ).

   ![Atualizar dados de referência](../../resources/images/studio_images/studioimages/studio_reference%20table_update.png)

## Atualizar o modelo

O aprendizado de máquina se baseia em um modelo que produz previsões de pools de custos com base em seus dados. Quando você configura inicialmente sua tabela com Assign Cost Pools, a última versão publicada é identificada e usada para prever seus dados. Esse modelo não será atualizado ao longo do tempo para essa tabela, a menos que você tome uma ação explícita.

1. Para ver o modelo em que você está, clique na guia **Configuration (Configuração** ).
2. Se uma atualização estiver disponível, uma notificação será exibida na guia Configuração. Para atualizar para a versão mais recente, clique em **Update Now (Atualizar agora)**.

   Observação: A reversão do documento retornará o modelo à versão de check-in.

## Ajustar a confiança

O Confidence destina-se apenas ao uso avançado. O ajuste da confiança para cima geralmente reduzirá o número de registros atribuídos. Para ajustar a confiança:

1. Clique na guia **Configuration (Configuração** ).
2. Edite o número na caixa **Min Confidence %** e pressione **Enter**.
3. Salvar a tabela. Os mapeamentos serão atualizados.

## Usar o mapa em árvore e o painel de visualização

Use o mapa em árvore para explorar os dados que estão sendo atribuídos. As imagens a seguir mostram todas as iterações disponíveis.

À direita do mapa em árvore estão os KPIs que indicam como as linhas são atribuídas. Quando um usuário interage com o mapa em árvore, os KPIs e a tabela a seguir são atualizados. Os filtros aplicados diretamente à tabela não afetarão o mapa da árvore.

O mapa da árvore tem os seguintes elementos e recursos:

![Usar o mapa da árvore](../../resources/images/studio_images/studioimages/studio_chart%20of%20accounts_assign%20cost%20pools.png)

**(1) Visualização do mapa em árvore** - Clique em qualquer caixa para filtrar toda a guia **Overview (Visão geral** ) desta etapa pelo valor contido nessa caixa.

O mapa em árvore tem os seguintes níveis: **Pool de custos > Subpolo de custos > Grupo de contas > Subgrupo de contas > Conta**. Se algum nível estiver indisponível por não ter sido mapeado, o mapa em árvore será automaticamente detalhado até o próximo nível.

Após o detalhamento, o caminho usado para filtrar até o nível atual é exibido e todos os níveis anteriores se tornam links. Clique em **All (Todos** ) para retornar à exibição padrão, não filtrada.

O status da atribuição no mapa em árvore é codificado por cores (consulte a etapa 4) e, quando há uma combinação de linhas atribuídas automaticamente e por regras personalizadas, aparece uma mistura das duas cores:

![Visualização de mapas de árvores](../../resources/images/studio_images/studioimages/studio_assign%20cost%20pools_overview.png)

**(2) Descrição** - Passe o mouse sobre as caixas no mapa da árvore para ver as descrições e a contagem de linhas dentro dessa caixa pelo método de atribuição. Ao exibir Account (Conta), ele mostrará Account Description (Descrição da conta).

Observação: O foco é ligeiramente atrasado para não bloquear sua capacidade de interagir rapidamente com a tabela.

**(3) Criar regra** - Esse botão é ativado quando você filtra pelo menos um valor fornecido pelo cliente. Se todas as colunas estiverem preenchidas, isso ocorrerá depois que você clicar em um grupo de contas. As regras criadas serão aplicadas a todas as linhas do grupo fornecido pelo cliente e, portanto, podem afetar mais linhas do que as exibidas no mapa em árvore.

Depois de clicar em **Create Rule (Criar regra** ), navegue até a guia **Rules (Regras)** para concluir a configuração da regra.

**(4) KPIs** - Os indicadores-chave de desempenho (KPIs) à direita mostram quantas linhas são atribuídas e por qual método. As porcentagens são arredondadas normalmente. As cores nos KPIs são uma legenda das cores no gráfico.

**(5) Tabela** - A tabela mostra todas as linhas que correspondem ao estado do mapa da árvore. Para filtrar ainda mais a tabela, digite o texto no campo Search (Pesquisar) antes de cada cabeçalho. Você também pode clicar com o botão direito do mouse em qualquer valor da tabela e selecionar **Filtrar por valor** para adicionar texto ao campo **Pesquisar**.

As opções incluem:

- Por padrão, a tabela não é classificada. Clique nos cabeçalhos para exibir opções para alterar a classificação. Qualquer ação que altere o status das linhas na tabela atualizará imediatamente a tabela e reaplicará a classificação.
- A tabela permite alterações em linhas individuais. As linhas são identificadas por todos os seus valores, portanto, se houver linhas idênticas, elas serão tratadas como uma só. Clique no **pool de custos** ou no **subpool** para ver todos os mapeamentos disponíveis. Escolha uma opção para criar uma regra para essa linha.
- Para atribuir um pool de custos a uma linha, clique na coluna **Pool de custos** ou **Subpool de custos**. O menu **Atribuir a** é exibido e mostra toda a lista de pools de custos e subpools de custos disponíveis para seleção.

**(6) Status** - A coluna Status tem cinco estados possíveis:

- Não atribuído
- Conflitos
- Automático
- Regra
- Verificado

As cores correspondem à legenda do KPI ao lado do mapa em árvore, exceto as verificadas, que são verde-escuras. Além disso, você pode interagir com a coluna **Status** para alterar o status de cada linha.

As opções incluem:

- Clique no ícone de valor da coluna **Status** quando ele for atribuído automaticamente ou quando a regra personalizada for atribuída para verificar essa linha. As linhas verificadas têm valores bloqueados e não serão alteradas, mesmo que sejam atribuídas automaticamente a alterações no pool de custos.
- Clique em **Conflitos** para verificar essa linha.
- Clique em **Unassigned (Não atribuído)** para exibir o mesmo menu disponível nas colunas Cost Pool (Pool de custos) e Cost Sub Pool (Sub Pool de custos).

## Criar e gerenciar regras

Use regras para definir o pool de custos e o subpólo de custos para as linhas da tabela que podem ser aplicadas com base nos valores das linhas. As regras continuam a se aplicar a todos os uploads nessa versão da tabela.

A tabela de **regras** está no canto superior esquerdo da guia Regras. Por padrão, ele contém o nome da regra e as contagens de linhas que correspondem aos critérios da regra, divididos de acordo com a forma como a regra foi aplicada.

![Criar e gerenciar regras](../../resources/images/studio_images/studioimages/studio_assign%20cost%20pools_rules.png)

Para ver as opções para mostrar ou ocultar colunas, clique com o botão direito do mouse no cabeçalho.

## Criar uma nova regra

As regras aplicam condições à tabela e, em seguida, atribuem um pool de custos.

1. Selecione **New Rule (Nova regra** ) para criar uma regra sem condições e com pool de custos assignment.Use um nome e uma descrição da regra para ajudar a rastrear as decisões tomadas em cada regra.

   Use um nome de regra e uma descrição para ajudar a rastrear as decisões tomadas em cada regra.
2. Editar a regra.

## Editar uma regra

Para editar uma regra manualmente, adicione condições e selecione os critérios de seleção.

- Clique com o botão direito do mouse em um valor da tabela e clique em **Add to Rule (Adicionar à regra** ) para adicionar outro critério à regra. Se nenhuma regra for selecionada, será criada uma nova regra. Em seguida, adicione o critério.

  Observação: antes de remover um mapeamento em Map Columns que é usado por regras, certifique-se de remover esse critério das regras. Se você remover um mapeamento e não conseguir ajustar suas regras como deseja, adicione a coluna novamente, remova essa coluna das regras e, em seguida, remova o mapeamento novamente.

## Aplicar condições de regra

Os operadores de condição seguem essa lógica:

| Nome da operadora | Descrição | Exemplo |
| --- | --- | --- |
| Igual | Use para uma correspondência exata. | Tipo de despesa *igual a* OpEx |
| Contém | Use para valores que incluem seu texto digitado, mas que também podem incluir outras informações. | A conta *contém* 2111 |
| Começa com | Use quando você souber com o que seu valor começa. | A descrição da conta *começa com o* salário |
| Termina com | Use quando você souber com o que seu valor termina. | Descrição da conta *termina com* benefícios |
| Está dentro | Use quando seu valor for um dos textos listados separados por vírgula. | A conta *está em* 2111, 2112 |
| Diferente | Elimina as linhas que não correspondem ao texto que você digitou. | Tipo de despesa *não é igual* CapEx |
| Não contém | Elimina as linhas que não contêm o texto que você digitou. | Descrição da conta *não contém* manutenção |
| Não começa com | Elimina as linhas que não começam com o texto que você digitou. | A conta *não começa com* ACCT\_ |
| Não termina com | Elimina as linhas que não terminam com o texto que você digitou. | A conta *não termina com* 23 |
| Não está em | Elimina as linhas que não correspondem a uma das listas de cadeias de texto inseridas. | A conta *não está em* 2111,2112 |
| É nulo | Use quando seu valor estiver vazio. | Tipo de despesa *é nulo* |
| Não é nulo | Use quando seu valor não estiver vazio. | O tipo de despesa *não é nulo* |

**NOTAS** :

- Você pode adicionar condições na mesma coluna duas vezes. No entanto, depois de salvar uma regra, as condições serão condensadas em **Is In** ou **Is Not In** usando curingas para abordar outras permutações.
- As colunas operam somente por correspondências positivas (Is In, Equals, Contains, etc.) ou por correspondências negativas (Not Equals, etc.).
- Quando **Is Null** é usado em uma coluna, essa coluna não pode ser usada para outros operadores.
- As regras só podem ser criadas ou editadas na ramificação do tronco. Portanto, para criar ou editar regras, mescle sua tabela e, em seguida, conclua as edições.

## Resolver conflitos de regras

Quando mais de uma regra for aplicável a uma ou mais linhas e nenhuma regra for mais específica do que a outra, a(s) linha(s) será(ão) definida(s) com o status **Conflito** e nenhum pool ou subpolo de custos será atribuído à(s) linha(s). As regras conflitantes são listadas na guia **Conflitos**.

Uma regra conflitante pode ser resolvida de duas maneiras:

- Selecione a regra que deseja atualizar em **Select a Rule (Selecionar uma regra** ), modifique uma ou mais condições e clique em **Update Rule (Atualizar regra** ).
- Clique com o botão direito do mouse na regra que deseja substituir e selecione **Verificar**. Isso fará com que a regra escolhida anule as outras regras com as quais estava em conflito.

## Verificar linhas

Você pode verificar se qualquer linha atribuída a um pool de custos foi revisada manualmente. Isso substituirá qualquer outra maneira de alterar a linha. A linha pode ser verificada independentemente de a atribuição ter sido concluída por meio de aprendizado de máquina ou de intervenção manual usando regras. As alterações no modelo não afetarão as linhas verificadas.

## Etapa e controle de versão do Assign Cost Pools

As tabelas que contêm a etapa Atribuir pools de custos podem ter versão de tempo como qualquer outra tabela. Para obter mais informações, consulte [Versão de uma tabela](version_table.htm "(Abre em uma nova guia ou janela)").

## Ramificação ou reversão

Se você reverter um projeto em verificação no histórico, as regras voltarão ao estado em que estavam naquele momento. Todas as regras adicionadas no futuro terão como padrão um número automático mais alto, refletindo as regras que foram criadas até o momento.

As regras só podem ser criadas ou editadas na ramificação do tronco. Portanto, para criar ou editar regras, primeiro mescle sua tabela e depois conclua as edições.

**VEJA TAMBÉM** :

- [Colunas do mapa](mapcolumns.htm "(Abre em uma nova guia ou janela)")
- [Atribuir pools de custos com aprendizado de máquina](assigncostpools.htm "(Abre em uma nova guia ou janela)")
- [Perguntas frequentes sobre Map Columns](faqmapcolumns.htm "(Abre em uma nova guia ou janela)")
