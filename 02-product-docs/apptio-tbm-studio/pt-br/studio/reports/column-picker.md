---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Componente de seleção de colunas"
breadcrumb: []
source_path: "studio/reports/column-picker.html"
images:
  - "resources/images/studio_images/studioimages/reports/rep034.png"
  - "resources/images/studio_images/studioimages/reports/rep325.png"
  - "resources/images/studio_images/studioimages/reports/rep327.png"
  - "resources/images/studio_images/studioimages/studio/stu516.png"
  - "resources/images/studio_images/studioimages/studio/stu517.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Componente de seleção de colunas

**Aplica-se a** : TBM Studio 12.0 e posterior

Um seletor de colunas permite que os usuários personalizem uma tabela em um relatório adicionando colunas à tabela. A imagem a seguir mostra um exemplo de seletor de coluna e a tabela que o acompanha. Um seletor de coluna se aplica a todas as tabelas em um relatório, a menos que esteja contido em um objeto de grupo. Se o seletor estiver em um objeto de grupo, ele se aplicará somente às tabelas dentro do grupo.

![Seletor de colunas](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep034.png)

**Pontos principais** :

Abaixo estão os principais pontos sobre a criação de selecionadores de coluna:

- Os campos de rótulo adicionados a um seletor são adicionados a tabelas como linhas (no contexto do painel **Configuração de componentes** ) agrupadas pelos valores na primeira coluna da tabela. Um seletor de coluna horizontal com opções de rótulo é mostrado na imagem a seguir:

  ![Configuração de componentes](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep327.png)
- Os campos numéricos adicionados a um seletor são adicionados às tabelas como valores (no contexto da caixa de diálogo **Configuração de componentes** ) em colunas separadas. Se as colunas da tabela estiverem agrupadas, uma coluna será adicionada a cada grupo.
- Os campos bloqueados fornecem os resultados mais previsíveis. No entanto, em geral, você obterá resultados satisfatórios se usar campos desbloqueados.
- Um seletor de coluna pode ser exibido como um conjunto de caixas de seleção ou como botões de rádio. Use caixas de seleção para múltiplas seleções. Use botões de rádio para seleções únicas.
- As caixas de seleção e os botões de rádio podem ser orientados vertical ou horizontalmente.

## Adicionar um seletor de coluna

1. Na guia **Relatório**, clique em **Seletor de colunas**. Um componente **Column Picker** é adicionado ao relatório. O painel Column Picker Configuration é exibido como mostra a imagem a seguir:

   ![Adicionar um seletor de coluna](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu516.png)
2. No campo na parte superior da caixa de diálogo, selecione o objeto que representa a tabela em que as colunas serão adicionadas.
3. No **Project Explorer**, arraste um ou mais valores para a área **Campos disponíveis**.
4. Feche a caixa de diálogo clicando em uma área em branco do relatório.

## Escolha caixas de seleção ou botões de rádio

Em um seletor de colunas, as colunas podem ser exibidas como um conjunto de caixas de seleção ou botões de rádio. As caixas de seleção permitem que o usuário selecione uma ou mais colunas. Os botões de rádio permitem que o usuário selecione uma única coluna. A opção **Seleção múltipla** exibe caixas de seleção. A opção **Single Selection** exibe botões de rádio.

Para alterar a opção de exibição:

1. Selecione o componente selecionador de coluna no relatório.
2. Na guia **Picker**, selecione a opção **Single Selection (Seleção única** ) ou **Multiple Selection (Seleção múltipla** ).

## Orientação vertical ou horizontal

As opções do seletor podem ser orientadas vertical ou horizontalmente usando as opções de **Layout** na guia **Seletor**.

## Usar como um seletor de datas

Você pode usar um seletor de coluna para dar aos usuários a capacidade de filtrar uma tabela por datas. No relatório mostrado na imagem a seguir, o usuário pode selecionar entre Mês atual, Semestre atual e Ano até a data. A seleção é refletida no título Jun FY2014 acima das duas colunas agrupadas: Custo e Orçamento.

![selecionador de data](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep325.png)

Para criar esse tipo de relatório:

1. Agrupe as colunas na tabela e digite o seguinte texto dinâmico para o título do grupo: <%=CurrentDate( )%>.
2. Adicione o seletor de coluna usando os valores de data, conforme mostrado na imagem a seguir:

   ![Configuração do selecionador de colunas](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu517.png)
