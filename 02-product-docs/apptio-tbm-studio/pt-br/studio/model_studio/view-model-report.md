---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Exibir um relatório de modelo"
breadcrumb: []
source_path: "studio/model_studio/view-model-report.html"
images:
  - "resources/images/studio_images/studioimages/icons/return.png"
  - "resources/images/studio_images/studioimages/studio/stu582.png"
  - "resources/images/studio_images/studioimages/studio/stu590.png"
  - "resources/images/studio_images/studioimages/studio/stu591.png"
  - "resources/images/studio_images/studioimages/studio/stu592.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Exibir um relatório de modelo

**Aplica-se a** : TBM Studio 12.0 e posterior

Um projeto geralmente tem um único modelo. Para visualizar um relatório de modelo, na seção **Relatórios** do **Project Explorer**, clique em **Modelos** e clique no nome do relatório. Uma amostra de relatório de modelo é mostrada na imagem a seguir:

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu582.png)

É possível visualizar um modelo na tela de relatório de modelo mostrada na imagem anterior, mas não é possível editar o modelo nessa tela. Na tela do relatório do modelo, é possível:

- Clique em um elemento da tabela no modelo para ver os drivers e as alocações. Na imagem anterior, a tabela **Cost Source Actuals** está selecionada.
- Continue a clicar nos elementos da tabela para rastrear o fluxo de valor por meio do modelo (novo em v12.1, v12.2+ ).
- Abra o menu em uma tabela e clique em **Drill Down** para ver as colunas na tabela. Você pode selecionar uma coluna para focar o relatório nessa coluna em vez de na tabela inteira.

Observação: A partir de v12.2.2, os relatórios modelo podem ser adicionados às coleções de relatórios. No exemplo abaixo, o relatório **saTestModel** foi adicionado à coleção de relatórios **do IT Finance**.

Assista a este vídeo de demonstração do site Apptio Education Services: [Uso de relatórios modelo](https://community.apptio.com/videos/1583 "(Abre em uma nova guia ou janela)"). Ou navegue por [todos os vídeos do site Apptio](https://community.apptio.com/docs/DOC-7714 "(Abre em uma nova guia ou janela)").

## Perfurar até uma coluna

Por padrão, um relatório de modelo mostra tabelas. Se quiser ver mais detalhes, você pode detalhar uma coluna específica clicando no menu no lado direito da tabela.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu590.png)

Por exemplo, suponha que você tenha o modelo de relatório mostrado na primeira imagem. Você gostaria de ver a alocação da tabela **Cost Source Actuals** dividida por pool de custos. Você pode clicar no menu e selecionar **Pool de custos**. O relatório do modelo agora se parece com a imagem a seguir:

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu591.png)

Para ver quanto de um valor específico do pool de custos é alocado para as categorias, clique no pool de custos. Na imagem a seguir, o pool de custos **Facilities & Power** foi selecionado:

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu592.png)

Para retornar à visualização da tabela, clique no ícone da seta de retorno ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/icons/return.png) no canto superior esquerdo da camada.

## Valor de rastreamento em uma camada

A partir de v12.2.2, o valor alocado entre as tabelas no mesmo nível é exibido conforme mostrado abaixo. Antes de v12.2.2, as tabelas de **Armazenamento** e **Servidores** eram alinhadas verticalmente com uma linha de alocação em loop do **Armazenamento** para os **Servidores**.

![](../../resources/images/studio_images/studioimages/studio_diagram_trace%20value%20within%20a%20tier.png)
