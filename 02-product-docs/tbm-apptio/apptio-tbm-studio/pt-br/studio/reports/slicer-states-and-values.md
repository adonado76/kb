---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Estados e valores do fatiador"
breadcrumb: []
source_path: "studio/reports/slicer-states-and-values.html"
images:
  - "resources/images/studio_images/studioimages/reports/rep018.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Estados e valores do fatiador

**Aplica-se a** : TBM Studio 12.0 e posterior

## Estados do fatiador

A cor dos valores em um slicer indica seu estado:

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep018.png)

Os valores relacionados estão relacionados aos dados exibidos no relatório. Quando você seleciona um valor relacionado, isso afeta a exibição dos dados. Os valores não relacionados não estão relacionados aos dados exibidos atualmente no relatório. Quando você seleciona um valor não relacionado, ele não afeta a exibição dos dados, se selecionado.

Clicar em um valor em um fatiador alterna o estado selecionado/deselecionado. Para selecionar mais de um valor, mantenha pressionada a tecla **Ctrl** e clique nos valores.

As seleções em um slicer podem alterar o estado dos valores em outros slicers para Não relacionado.

Você pode limpar todas as seleções em um fatiador clicando no ícone de redefinição ![](../../resources/images/studio_images/studioimages/icons/filter%20reset.png) no cabeçalho do fatiador.

## Criação de um conjunto padrão de valores

Você pode criar um conjunto padrão de valores para um slicer selecionando valores em um slicer e salvando o relatório. Quando um usuário abre o relatório, as segmentações são exibidas com o conjunto padrão de valores selecionados.

## Classificação dos valores do slicer

Há duas opções para classificar os valores em um slicer:

- **Por estado** - Os valores são agrupados por estado (Selecionado, Relacionado, Não relacionado) e, em seguida, classificados alfanumericamente.
- **abc/123** - Os valores são classificados em ordem alfanumérica. O estado é ignorado.

Defina os valores usando as opções **Sort (Classificar** ) na guia **Slicer (Fatiador** ).

Os usuários que visualizam o relatório não podem alterar a opção de classificação.

Por padrão, os valores nas três seções (Selected, Related, Unrelated) são classificados da seguinte forma:

- **Texto** - em ordem alfabética
- **Números** - ascendentes
- **Datas** - cronológicas
