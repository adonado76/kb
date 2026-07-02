---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Modificar a estrutura da tabela"
breadcrumb: []
source_path: "studio/reports/tables/modify-table-structure.html"
images:
  - "resources/images/studio_images/studioimages/reports/rep202.png"
  - "resources/images/studio_images/studioimages/reports/rep330.png"
  - "resources/images/studio_images/zeroes.jpg"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Modificar a estrutura da tabela

**Aplica-se a** : TBM Studio 12.0 e posterior

Depois de adicionar uma tabela a um relatório, você pode fazer modificações, como classificar o conteúdo, ocultar colunas e congelar colunas. Faça essas modificações selecionando ícones nas guias **Tabela** e **Dados** ou clicando com o botão direito do mouse em um cabeçalho de coluna para exibir um menu pop-up.

## Renomear uma coluna

Para renomear uma coluna, clique com o botão direito do mouse no cabeçalho da coluna e selecione **Renomear** no menu pop-up. Digite um novo nome para a coluna.

## Colunas de grupo

Você pode agrupar duas ou mais colunas em uma tabela e colocar um cabeçalho acima das colunas. Na imagem a seguir, há dois grupos de colunas: **Informações** e **Custos**.

![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep202.png)

Para agrupar colunas:

1. Mantenha pressionada a tecla **Ctrl** (tecla **Alt** no Mac) e clique no cabeçalho de cada coluna que estará no grupo.
2. Clique com o botão direito do mouse e clique em **Group Columns (Agrupar colunas** ) no menu pop-up.
3. Na caixa de diálogo **Group Columns (Agrupar colunas** ), digite o cabeçalho a ser colocado acima das colunas e clique em **OK**. **OBSERVAÇÃO:** Você pode usar texto dinâmico no cabeçalho. Para obter informações sobre texto dinâmico, consulte [Inserir texto dependente do contexto em HTML](../html.html "Aplica-se a: TBM Studio 12.0 e posterior").

Para desagrupar colunas, clique com o botão direito do mouse no cabeçalho da coluna e selecione **Ungroup Columns (Desagrupar colunas** ) no menu pop-up.

## Mover uma coluna

Para mover uma coluna, clique no cabeçalho da coluna e arraste para a esquerda ou para a direita até uma nova posição na tabela.

## Redimensionar uma coluna

Para redimensionar uma coluna, execute uma das seguintes ações:

- Posicione o ponteiro do mouse sobre o limite direito da coluna. Quando o ícone do ponteiro mudar de uma mão para uma seta, clique e arraste para a esquerda ou para a direita.
- Clique com o botão direito do mouse no cabeçalho da coluna, clique em **Formatação**, clique em **Definir largura** e digite a largura em pixels.

## Exibir e ocultar colunas

Para ocultar uma coluna em uma tabela, clique com o botão direito do mouse no nome da coluna na área **Valores** do painel **Configuração de componentes** e selecione Ocultar. O nome da coluna fica em cinza.

Para exibir uma coluna oculta em uma tabela, clique com o botão direito do mouse no nome da coluna na área **Valores** do painel **Configuração de componentes** e selecione **Mostrar**.

## Congelar uma coluna

Em tabelas grandes, é possível congelar uma ou mais colunas para evitar que elas rolem horizontalmente para fora da visualização. Quando você congela uma coluna, ela se move para a borda extrema esquerda da tabela e fica travada nessa posição. Quando você rola a tabela para a direita, a coluna congelada permanece no lugar. Você pode congelar mais de uma coluna.

Para congelar uma coluna, execute uma das seguintes ações:

- Selecione a coluna e, em seguida, selecione o ícone **Congelar** na guia **Dados**.
- Clique com o botão direito do mouse no cabeçalho da coluna, clique em **Formatação** e clique em **Congelar coluna**.

Para descongelar uma coluna, clique com o botão direito do mouse no cabeçalho da coluna, clique em **Formatação** e clique em **Descongelar coluna**.

## Classificar linhas em uma tabela

Você pode classificar uma tabela por uma ou mais colunas. A classificação pode ser em ordem crescente ou decrescente. Para classificar uma tabela, use os controles **Sort (Classificar** ) na guia **Data (Dados)**.

Para classificar uma tabela por uma única coluna, selecione a coluna e clique no ícone **Ascendente** ou **Descendente**.

Para classificar uma tabela por várias colunas, clique no ícone **Classificar**. O aplicativo exibe uma caixa de diálogo na qual você pode selecionar até quatro colunas para usar na classificação.

## Zeros em uma tabela

Você pode usar esse filtro para remover os valores zero de seus relatórios. Para usar isso, navegue até a guia **Data (Dados** ) de um relatório editável e selecione **Zeroes (Zeros** ).

![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/zeroes.jpg)

Digite o nome do relatório ou selecione a caixa de seleção dos relatórios e clique em **OK**. Você também pode selecionar **All** / **None** para marcar / desmarcar todos os relatórios.

Para remover o filtro de zeros aplicado aos relatórios, selecione os relatórios e clique em **Reverter tudo**.

## Ocultar a linha Total

Por padrão, as tabelas exibem uma linha **Total** na parte inferior. Para ocultar uma linha **Total**, clique na guia **Data (Dados)**, clique em **Sum (Soma** ) e desmarque a opção **Show Total Row (Mostrar linha total** ).

A linha Total é inteligente o suficiente para escolher a ação apropriada para as colunas em uma tabela. Ele soma apenas colunas numéricas. Além disso, as colunas calculadas exibem o resultado dos totais. Por exemplo, suponha que você tenha a tabela mostrada abaixo:

![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep330.png)

A coluna **Custo por servidor** é calculada dividindo-se o custo total pelo número de servidores. O valor de Custo por servidor na linha **Total** também é calculado com base em 5 servidores com um custo total de US$ 300: US$ 300/5 = US$ 60. A linha Total exibe um valor de US$ 60 em vez de US$ 150.

## Exibir a coluna Totais

Por padrão, as tabelas não exibem uma coluna de **totais**. Para exibir a coluna, clique em **Sum (Soma** ) na guia **Data (Dados)** e marque a opção **Show Total Column (Mostrar coluna total** ).

## Exibir a linha Outro

Se houver muitas linhas em uma tabela e você quiser limitar o número de linhas exibidas, poderá adicionar uma linha **Other**. Para adicionar a linha, clique em **Soma** na guia **Dados** e marque a opção **Mostrar outra linha**. A linha Outros é exibida na parte inferior da tabela. Ele mostra o total de toda a tabela menos os valores exibidos na página atual da tabela.
