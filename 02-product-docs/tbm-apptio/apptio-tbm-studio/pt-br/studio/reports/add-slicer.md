---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Adicionar um fatiador"
breadcrumb: []
source_path: "studio/reports/add-slicer.html"
images:
  - "resources/images/studio_images/studioimages/reports/rep017.png"
  - "resources/images/studio_images/studioimages/reports/rep044.png"
  - "resources/images/studio_images/studioimages/studio/stu625.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Adicionar um fatiador

**Aplica-se a** : TBM Studio 12.0 e posterior

Você pode adicionar um número ilimitado de segmentações a um relatório. Depois de adicionar os fatiadores, você pode mover e dimensionar os fatiadores.

Os fatiadores podem ser uma lista ou um controle deslizante. Os campos de texto criam divisões de lista. Os campos numéricos criam divisores de controle deslizante.

![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep017.png)

## Adicionar um fatiador

Para adicionar um slicer a um relatório:

1. Exiba o relatório no qual você deseja adicionar o slicer.
2. Selecione **Row Slicer** na guia **Relatório**. O aplicativo adiciona um objeto slicer em branco ao relatório e exibe o painel **Slicer Configuration (Configuração do slicer** ) mostrado na imagem a seguir:

   ![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu625.png)
3. Arraste um campo de uma perspectiva (Dimensions, Calculations ou Time) para a área **Slice By**.

Os valores dos campos são exibidos no fatiador. Os campos de texto criam divisões de lista. Os campos numéricos criam controles deslizantes. Campos bloqueados são campos que foram adicionados a dimensões personalizadas. Para obter mais informações sobre perspectivas personalizadas, consulte [Criação de perspectivas personalizadas](creating-custom-perspectives.htm "(Abre em uma nova guia ou janela)").

## Mover e dimensionar fatiadores

Depois de colocar um slicer em um relatório, você pode executar as seguintes ações:

- Mova o fatiador clicando na barra de título e arrastando o fatiador para uma nova posição.
- Altere o tamanho do fatiador arrastando as bordas e os cantos esquerdo, direito e inferior.

## Alterar estilos de slicer

Há vários esquemas de cores diferentes disponíveis para fatiadores. Para aplicar um esquema de cores, selecione um estilo na guia Slicer (Fatiador).

![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep044.png)

## Definir as opções de pesquisa

Se houver muitos valores em um fatiador, os usuários poderão inserir texto na caixa de pesquisa automática na parte superior do fatiador para limitar a lista de valores. Ao adicionar o fatiador a um relatório, você pode selecionar uma das duas opções de pesquisa a seguir.

- **Contains (Contém** ) - Encontra todos os valores que incluem os caracteres inseridos. Se o usuário digitar abc, o filtro encontrará abcefg, defabc e defabcefg, mas não abdc ou adbc.
- **Starts With** - Encontra todos os valores que começam com os caracteres inseridos. Se o usuário digitar abc, o filtro encontrará abcefg e abc, mas não dabc ou 1abc.

Para obter uma discussão mais detalhada sobre essas opções, consulte [Selecionar uma opção de pesquisa](select-search-option.html "Aplica-se a: TBM Studio 12.0 e posterior").

## Ocultar o campo de pesquisa

Um campo de pesquisa é exibido na parte superior de um fatiador. Os usuários podem inserir texto no campo para limitar o número de elementos exibidos no fatiador. Se estiver criando um fatiador com um pequeno número de elementos e não houver barra de rolagem no fatiador, você poderá ocultar o campo de pesquisa. Para ocultar o campo de pesquisa:

1. Abra as **Propriedades** do fatiador clicando na seta para baixo à esquerda do nome do fatiador.
2. Desmarque a opção **Show Auto Search Filter (Mostrar filtro de pesquisa automática** ) na guia **General (Geral** ).
