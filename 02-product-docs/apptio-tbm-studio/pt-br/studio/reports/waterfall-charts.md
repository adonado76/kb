---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Gráficos em cascata"
breadcrumb: []
source_path: "studio/reports/waterfall-charts.html"
images:
  - "resources/images/studio_images/studioimages/icons/check.png"
  - "resources/images/studio_images/studioimages/reports/rep273.png"
  - "resources/images/studio_images/studioimages/reports/rep291.png"
  - "resources/images/studio_images/studioimages/reports/rep292.png"
  - "resources/images/studio_images/studioimages/reports/rep293.png"
  - "resources/images/studio_images/studioimages/reports/rep295.png"
  - "resources/images/studio_images/studioimages/reports/rep296.png"
  - "resources/images/studio_images/studioimages/reports/rep297.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Gráficos em cascata

**Aplica-se a** : TBM Studio 12.2 e posterior

Os gráficos em cascata mostram o impacto de valores positivos e negativos em um valor inicial. Normalmente, o primeiro e o último valores são exibidos como colunas inteiras. Em alguns gráficos, serão exibidas colunas inteiras adicionais. Os valores intermediários são exibidos entre as colunas inteiras, como colunas flutuantes que indicam alterações positivas e negativas. Os valores intermediários geralmente são chamados de etapas. Por exemplo, pode haver colunas inteiras para Q1, Q2, Q3 e Q4 com valores intermediários flutuantes entre as colunas trimestrais.

Um exemplo de gráfico em cascata é mostrado na imagem a seguir:

![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep273.png)

Observação: Os valores nos gráficos em cascata são sempre exibidos na moeda base definida para o projeto. Os gráficos em cascata não são compatíveis com várias moedas.

## Use um gráfico em cascata com vários colaboradores

Se estiver criando um gráfico em cascata e quiser que vários colaboradores insiram etapas intermediárias para o gráfico, você poderá definir um fatiador para o gráfico. Os indivíduos podem selecionar um valor de fatiador e inserir etapas para esse valor. Por exemplo, você deseja criar um gráfico em cascata que resuma a alteração dos custos em vários departamentos. Você deseja que os chefes de cada departamento insiram as etapas intermediárias do respectivo departamento. Você cria um slicer que exibe os departamentos. Cada chefe de departamento seleciona seu departamento e insere as etapas.

As etapas exibidas no gráfico correspondem ao departamento selecionado no fatiador. Para obter mais informações, consulte [Usar slicers com gráficos em cascata](#Waterfallcharts__Useslicerswithwaterfallcharts).

Todos os gráficos em cascata devem ter pelo menos um valor inicial e um valor final. Um gráfico também pode ter outros valores intermediários. Por exemplo, um gráfico pode exibir apenas os valores iniciais e finais do ano ou pode incluir valores para cada trimestre do ano.

## Criar um gráfico em cascata

Para criar um gráfico em cascata com um valor inicial e um valor final:

1. Clique na guia **Relatório**.
2. Clique no ícone **Waterfall**. Um espaço reservado para gráfico é adicionado ao relatório e o painel **Configuração de cascata** é exibido.
3. No painel **Configuração do gráfico em cascata**, selecione um objeto de modelo na lista suspensa na parte superior do painel.
4. Na seção **Métricas** do **Project Explorer**, arraste uma métrica modelada para a área **Valores** do painel.
   - Por padrão, o período de tempo atual é inserido na área **Time (Tempo** ) da caixa de diálogo. Se você quiser alterar o período de tempo, abra o seletor de datas no cabeçalho, selecione um período de tempo diferente e crie o gráfico. Os períodos de tempo para todos os valores de base devem ser os mesmos.
5. Arraste uma segunda métrica modelada para a área **Métricas**.
   - Como antes, o Mês atual é inserido na área **Hora**. Os gráficos em cascata podem exibir uma mudança de valor ao longo do tempo. Para fazer isso, altere uma das configurações de Mês atual para um período de tempo diferente.
6. Para alterar o período de tempo, clique com o botão direito do mouse no período de tempo e clique em **Shift**.
7. Digite um número positivo ou negativo que represente o número de períodos para alterar a data e clique em **OK**. Por exemplo, suponha que seus períodos sejam meses e que o mês atual seja janeiro de 2013. Se você inserir +5, o mês será junho de 2013.
8. Se apropriado, adicione colunas adicionais que representem outros períodos no tempo (consulte [Adicionar valores intermediários](#Waterfallcharts__Addintermediatevalues) abaixo).
9. O gráfico agora exibirá as colunas inicial e final e uma coluna intermediária chamada Unexplained. A coluna Unexplained representa a alteração no valor entre as colunas inicial e final. A próxima etapa é adicionar os valores intermediários.

## Adicionar valores intermediários

A tabela de etapas intermediárias exibe os valores intermediários que contribuíram para a alteração entre os valores inicial e final. O ideal é que os valores intermediários representem a mudança total entre os valores inicial e final. Qualquer valor não identificado em uma etapa intermediária será exibido em uma coluna chamada **Unexplained (Não explicado** ). Os valores intermediários devem ser adicionados no ambiente de produção. Os valores intermediários podem ser aplicados a valores específicos do fatiador.

Para adicionar valores intermediários:

1. Mude para o ambiente de produção.
2. Abra o relatório com o gráfico de cascata.
3. Clique no botão **Add Explanation (Adicionar explicação)** na parte inferior da tabela de etapas intermediárias**.OBSERVAÇÃO** : As explicações são armazenadas no banco de dados de Planejamento de TI. Se o banco de dados de Planejamento de TI não tiver sido instalado, não será possível adicionar explicações.
4. Na linha em branco adicionada à tabela:
   - Digite um rótulo para a etapa na coluna **Etapa**.
   - Insira um valor positivo ou negativo na coluna **Value (Valor** ).
   - Insira uma explicação na coluna **Explicação**.
5. Continue adicionando valores intermediários conforme necessário.
6. Você pode alterar a ordem das etapas intermediárias entre os valores de base clicando com o botão direito do mouse e, em seguida, clicando em **Mover para cima** ou **Mover para baixo**.

## Filtrar o gráfico

Você pode aplicar filtros fixos ao gráfico em cascata adicionando um ou mais campos de dados à área **Filtros** do painel Configuração de cascata. Se quiser dar aos usuários a capacidade de selecionar seus próprios filtros, crie um fatiador para o gráfico em cascata. Para obter mais informações sobre a aplicação de segmentações, consulte [Usar segmentações com gráficos em cascata](#Waterfallcharts__Useslicerswithwaterfallcharts).

Para aplicar filtros fixos ao gráfico:

1. Arraste um campo relevante da perspectiva **Dados** ou de uma perspectiva personalizada para a área **Filtros**.
2. Clique com o botão direito do mouse na entrada do filtro e clique em **Edit Filter (Editar filtro** ).
3. Na caixa de diálogo **Edit Filter (Editar filtro** ), faça suas seleções e clique em **OK**.
4. Para adicionar mais filtros, repita as etapas acima.

## Ocultar a tabela de etapas intermediárias

A tabela de etapas intermediárias é útil quando você está construindo um gráfico em cascata, mas provavelmente desejará ocultar a tabela dos usuários que visualizarão o gráfico em cascata.

Para ocultar a tabela de etapas intermediárias:

1. Clique na guia **Waterfall (Cachoeira** ).
2. Desmarque a opção **Mostrar tabela**.

## Alterar as cores do gráfico em cascata

Você pode alterar as cores padrão usadas em um gráfico em cascata.

1. Clique na guia **Waterfall** e, em seguida, no ícone **Colors (Cores** ).
2. Clique no quadrado de cor à direita de cada item e clique em uma cor.

Você pode alterar a cor de um valor individual em um gráfico em cascata.

1. Selecione o gráfico.
2. Clique no ícone **Cores** na guia **Cascata**. A caixa de diálogo de seleção de cores é exibida.
3. Clique em **Add**.
4. Clique em **Key**.
5. Digite o nome do valor como ele aparece na coluna Etapa.
6. Clique no ícone de salvar ![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/icons/check.png).
7. Clique no ícone de cor personalizada ![imagem](../../resources/images/studio_images/studioimages/icons/custom%20color.png) e selecione uma cor.
8. Clique em **Salvar**.
9. Para excluir uma cor personalizada, clique no x vermelho na frente do nome da etapa e clique em **Salvar**.

## Definir as opções do gráfico em cascata

Quando você cria um gráfico em cascata, uma guia **Cascata** é adicionada. Nessa guia, há várias opções que podem ser aplicadas ao gráfico.

- **Mostrar tabela** - Quando marcada, exibe a tabela explicativa abaixo do gráfico. Se quiser que os usuários possam editar o gráfico em cascata, exiba a tabela de explicação. Se a tabela de explicação estiver oculta, os usuários poderão visualizar o gráfico, mas não editá-lo.
- **Show detailed rows (Mostrar linhas detalhadas** ) - Exibe as etapas intermediárias associadas a valores específicos do fatiador. As etapas são exibidas na parte inferior da tabela de etapas e são somente leitura.
- **Explicação nas dicas de ferramentas** - Quando marcada, exibe o texto do campo **Explicação** na dica de ferramenta das barras do gráfico em cascata.
- **Number (Número** ) - Formate os números em um gráfico em cascata usando as opções **Number (Número** ).

## Usar slicers com gráficos em cascata

Os fatiadores filtram os valores exibidos em um gráfico em cascata. Ao usar slicers, as etapas intermediárias podem ser exibidas ou ocultadas na tabela de etapas. Os fatiadores e os fatiadores hierárquicos têm impactos ligeiramente diferentes nos gráficos em cascata.

Os fatiadores podem limitar os valores usados para gerar um gráfico em cascata. No entanto, quando um usuário seleciona um valor em um slicer, as etapas intermediárias são substituídas por uma única coluna **Unexplained** no gráfico. Se quiser que o usuário veja as etapas intermediárias, selecione a opção **Show Detailed Rows (Mostrar linhas detalhadas** ) na guia **Waterfall (Cascata** ) do gráfico.

Observação: Os cortes numéricos e de tempo não afetam os gráficos em cascata.

## Fatiadores

Se um usuário selecionar um conjunto de valores de segmentação e, em seguida, inserir etapas intermediárias em um gráfico em cascata, as etapas só poderão ser editadas quando o mesmo conjunto de valores de segmentação for selecionado. Se o usuário selecionar um conjunto diferente de valores do fatiador ou limpar todas as seleções no fatiador, as etapas intermediárias serão exibidas como entradas somente leitura abaixo da entrada Unexplained (Sem explicação) na tabela de etapas.

Por exemplo, na imagem a seguir, as etapas de salários, telecomunicações, software e hardware foram inseridas para o data center de Chicago. Quando Chicago é selecionado no fatiador, as entradas são editáveis na tabela de etapas. A coluna **Context (Contexto** ) mostra o filtro que está sendo aplicado pelo fatiador. Cada etapa é representada por uma barra no gráfico:

![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep291.png)

Se Chicago for desmarcado no fatiador, as etapas serão alteradas para somente leitura e movidas para baixo da entrada Unexplained na tabela de etapas, conforme mostrado na imagem a seguir. As entradas na coluna **Context (Contexto** ) descrevem a configuração do fatiador que é a origem da etapa. Uma única barra **Unexplained** é exibida no gráfico. Você pode promover uma etapa somente leitura para uma etapa editável clicando com o botão direito do mouse na etapa e selecionando **Copiar para explicação**.

![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep292.png)

Se a opção **Show Detailed Rows (Mostrar linhas detalhadas)** na guia **Waterfall (Cascata** ) do gráfico não estiver selecionada, a tabela de etapas não exibirá as etapas, conforme mostrado na imagem a seguir:

![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep293.png)

## Cortadores hierárquicos

Os fatiadores hierárquicos funcionam como os fatiadores comuns, exceto pelo fato de que, quando você seleciona um elemento em um fatiador hierárquico, todas as explicações inseridas no nível atualmente selecionado do fatiador ou em um nível inferior na hierarquia são exibidas. As explicações inseridas no nível atualmente selecionado são editáveis. As explicações inseridas em níveis inferiores são somente de leitura.

## Exemplo de gráfico em cascata multiusuário

O departamento de TI da empresa ABC quer usar um gráfico em cascata para mostrar a mudança nos custos no primeiro semestre do ano. O VP criará o gráfico de base e pedirá que o chefe de cada data center insira explicações sobre as alterações em seus data centers. Será criado um fatiador de data center que os líderes poderão usar para filtrar o gráfico em cascata para seu data center. Depois que os chefes inserirem as informações das etapas, o VP do Departamento de TI consolidará as explicações em alguns valores-chave.

Há cinco data centers: Chicago, Dallas, Nova York, Phoenix e Seattle.

Há quatro centros de custo: Salários, Telecomunicações, Software e Hardware.

## Criar o gráfico base

O VP constrói o gráfico base e cria a segmentação do data center, conforme mostrado na imagem a seguir. Ele seleciona a opção **Show Detailed Rows (Mostrar linhas detalhadas** ) para o gráfico em cascata.

![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep295.png)

## Entrar nas etapas intermediárias do data center

O chefe do data center de Chicago faz login em Apptio e abre o gráfico de cascata. Ele seleciona Chicago no fatiador. Ele insere suas etapas intermediárias conforme mostrado na imagem a seguir. Os chefes dos outros data centers fazem o mesmo.

![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep296.png)

## Produzir o gráfico final

Depois que os chefes dos centros de dados inserem as etapas intermediárias, o VP combina os dados e cria uma única etapa intermediária para cada centro de custo. O gráfico final é mostrado na imagem a seguir:

![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep297.png)
