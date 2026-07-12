---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Adicionar uma coluna indicadora de status a uma tabela"
breadcrumb: []
source_path: "studio/reports/tables/add-status-indicators-to-tables.html"
images:
  - "resources/images/studio_images/studioimages/icons/arrow-down-right.png"
  - "resources/images/studio_images/studioimages/icons/arrow-up-right.png"
  - "resources/images/studio_images/studioimages/icons/circle-green.png"
  - "resources/images/studio_images/studioimages/icons/circle-pink.png"
  - "resources/images/studio_images/studioimages/icons/circle-red.png"
  - "resources/images/studio_images/studioimages/icons/circle-yellow.png"
  - "resources/images/studio_images/studioimages/icons/down-arrow-green.png"
  - "resources/images/studio_images/studioimages/icons/down-arrow.png"
  - "resources/images/studio_images/studioimages/icons/right-arrow.png"
  - "resources/images/studio_images/studioimages/icons/up-arrow-red.png"
  - "resources/images/studio_images/studioimages/icons/up-arrow.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Adicionar uma coluna indicadora de status a uma tabela

## Sobre esta tarefa

**Aplica-se a** : TBM Studio 12.0 e posterior

Nas tabelas dos relatórios, você pode adicionar indicadores de status que usam ícones coloridos para fornecer informações sobre os valores em uma coluna. Na imagem a seguir, os indicadores de status na coluna **CPU Status** fornecem informações sobre os valores na coluna **Avg CPU Util**. Os indicadores podem ser digitados em intervalos de valores. Por exemplo, uma seta verde aponta para cima para um servidor com utilização de CPU acima de 65%, uma seta amarela aponta para a direita para utilização de CPU acima de 50% e uma seta vermelha aponta para baixo para utilização de CPU abaixo de 50%.

**Ícones gerados pela função Ícone**

Os ícones de status são gerados pela seguinte função:

`=Icon(["icon_type"],conditional_expression,conditional_expression+)`

Há vários tipos de ícones disponíveis. A tabela abaixo lista os tipos, as expressões e os resultados de cada expressão. Diferentes tipos de ícones têm diferentes números de expressões. As expressões são avaliadas na ordem em que estão listadas na função. Se uma expressão for verdadeira, o resultado dessa expressão será exibido na tabela e as demais expressões serão ignoradas. O argumento icon\_type é opcional. Se você omitir o argumento, o padrão da função será o tipo de ícone redcircles. Se você incluir o tipo de ícone, coloque-o entre aspas. Os valores que não se enquadram nas expressões inseridas são atribuídos ao último ícone do conjunto.

Tabela 1.

| Tipo de ícone | Expressões e resultados |
| --- | --- |
| círculos vermelhos | Expressão 1: círculo vermelho imagem  Expressão 2: círculo rosa imagem |
| 3colorcircles | Expressão 1: círculo verde imagem  Expressão 2: círculo amarelo imagem  Expressão 3: círculo vermelho imagem |
| 3arrows | Expressão 1: seta para cima imagem  Expressão 2: seta para a direita imagem  Expressão 3: seta para baixo imagem |
| 3arrowsinv | Expressão 1: seta para cima imagem  Expressão 2: seta para a direita imagem  Expressão 3: seta para baixo imagem |
| 4arrows | Expressão 1: seta para cima imagem  Expressão 2: seta para cima e para a direitaimagem  Expressão 3: seta para baixo à direita imagem  Expressão 4: seta para baixo imagem |
| 4arrowsinv | Expressão 1: seta para cima imagem  Expressão 2: seta para cima e para a direita imagem  Expressão 3: seta para baixo à direita imagem  Expressão 4: seta para baixo imagem |
| 5arrows | Expressão 1: seta para cima imagem  Expressão 2: seta para cima e para a direita imagem  Expressão 3: seta para a direita imagem  Expressão 4: seta para baixo à direita imagem  Expressão 5: seta para baixo imagem |
| 5arrowsinv | Expressão 1: seta para cima imagem  Expressão 2: seta para cima e para a direita imagem  Expressão 3: seta para a direita imagem  Expressão 4: seta para baixo à direita imagem  Expressão 5: seta para baixo imagem |

## Procedimento

1. Navegue até a página do relatório que contém a tabela e mude para o modo **Editar**.
2. Selecione a tabela.
3. Na guia **Data (Dados** ), clique em **Insert (Inserir** ).
4. Se desejar, altere o nome da coluna clicando com o botão direito do mouse no cabeçalho da coluna, selecionando **Renomear** e inserindo um novo nome.
5. Selecione a coluna que você acabou de inserir.
6. Clique na guia **Fórmulas**, abra as funções **Avançadas** e clique na opção **Ícone**.
7. Edite a fórmula, selecionando o tipo de ícone apropriado e inserindo o número correspondente de expressões.

   Um exemplo de fórmula é mostrado abaixo.

   `Icon("3arrows",Avg CPU Util<40,Avg CPU Util<50,Avg CPU Util>70 AND Disk Image
   GB=500)`
8. Salve a fórmula clicando no ícone de salvar à esquerda do campo da fórmula. Se você tiver inserido a fórmula corretamente, os ícones de status serão exibidos na coluna. Se você tiver cometido um erro na fórmula, o aplicativo exibirá uma mensagem de erro na coluna que poderá ajudá-lo a solucionar o problema da fórmula.
