---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Relatórios e alocações de desenvolvimento de aplicativos"
breadcrumb: []
source_path: "cost-transparency/reports-v103/appdevreportingallocations-6560.html"
images:
  - "resources/images/ct_images/6560_10.png"
  - "resources/images/ct_images/6560_11.png"
  - "resources/images/ct_images/6560_2.png"
  - "resources/images/ct_images/6560_3.png"
  - "resources/images/ct_images/6560_4.png"
  - "resources/images/ct_images/6560_5.png"
  - "resources/images/ct_images/6560_6.png"
  - "resources/images/ct_images/6560_7.png"
  - "resources/images/ct_images/6560_8.png"
  - "resources/images/ct_images/6560_9.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Relatórios e alocações de desenvolvimento de aplicativos

Aplica-se a : v12+

## Visão geral

Tentando descobrir por que seus custos de desenvolvimento de aplicativos estão:

- Não parece correto?
- Muito baixo?
- Não está preenchendo?

Você está fazendo as perguntas:

- Como são calculados os custos de desenvolvimento de aplicativos?
- O que é App Dev\_Cost e App Dev\_CapEx?
- Como faço para colocar dólares no modelo App Dev\_Cost?
- Como faço para garantir que os custos de desenvolvimento de aplicativos estejam fluindo pelo modelo?
- Como posso afetar diretamente o valor exibido no relatório do App Dev?

As informações a seguir o orientam sobre como os custos de desenvolvimento de aplicativos são configurados em TBM Studio v12 e como você pode editar esses custos.

## Como são criados os custos de desenvolvimento de aplicativos?

Os custos de desenvolvimento de aplicativos são criados a partir da métrica de desenvolvimento de aplicativos, que é calculada pela adição dos valores App Dev\_Cost e App Dev\_CapEx.

![desenvolvimento de aplicativos](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6560_2.png)

## O que é App Dev\_Cost e App Dev\_CapEx?

Tanto o App Dev\_Cost quanto o App Dev\_CapEx são modelos prontos para uso que são executados em paralelo ao modelo de custo pronto para uso.

![imagem](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6560_3.png)

## Como faço para colocar dólares no modelo App Dev\_Cost?

Há algumas etapas que devem ser seguidas para garantir que os valores sejam preenchidos no modelo App Dev\_Cost:

1. Clique na tabela **Origem do custo**.

   ![origem de custo](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6560_4.png)
2. Selecione a métrica **App Dev\_Cost** no menu suspenso **Modelo**.

   ![custo de desenvolvimento do aplicativo](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6560_5.png)
3. Clique no driver **OpEx Variable**.

   ![variável ope](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6560_6.png)
4. Clique no menu suspenso **Add To**.

   ![tat para imagem](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6560_7.png)
5. Certifique-se de que o botão **App Dev\_Cost** esteja selecionado.

   ![custo de desenvolvimento do aplicativo](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6560_8.png)

Você precisará adicionar o botão App Dev\_Cost a todos os drivers utilizados em seu modelo de custo. Os drivers são: OpEx Variable (variável), OpEx Fixed (fixo), CapEx Variable (variável) e CapEx Fixed (fixo).

## Como faço para garantir que os custos de desenvolvimento de aplicativos estejam fluindo pelo modelo?

Para garantir que o App Dev\_Cost Model esteja funcionando corretamente e fluindo dólares, você terá que ativar a alocação do App Dev\_Cost. Para fazer isso, selecione o botão App Dev\_Cost na janela suspensa "Allocate" da linha de alocação. Essa seleção deverá ser feita em todas as linhas de alocação que conduzem ao IT Resource Towers.

![imagem](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6560_9.png)

![imagem](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6560_10.png)

## Como posso afetar diretamente o valor exibido no relatório do App Dev?

Para afetar o valor em dólares vinculado ao relatório de desenvolvimento de aplicativos, você terá que selecionar o botão App Dev\_Cost para as linhas de alocação que saem dos roteadores de recursos de TI que lidam com os custos de desenvolvimento de aplicativos. Por exemplo, se você quiser que todos os custos da subestrutura de recursos de TI de desenvolvimento de aplicativos sejam exibidos no relatório de desenvolvimento de aplicativos, selecione o botão App Dev\_Cost para a linha de alocação entre as torres de recursos de TI e os aplicativos.

![imagem](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6560_11.png)

Os relatórios de desenvolvimento de aplicativos só exibirão o custo das linhas de alocação que tiverem o botão App Dev\_Cost selecionado. Apptio não alinhará nenhum custo ao desenvolvimento de aplicativos se o botão App Dev\_Cost não estiver selecionado na linha de alocação que flui para o objeto Aplicativos.

## Principais conclusões

- Todas as linhas de alocação abaixo de IT Resource Towers deverão ter o botão App Dev\_Cost selecionado.
- Somente as linhas de alocação que estiverem fluindo diretamente para o objeto Aplicativos e tiverem o botão App Dev\_Cost selecionado serão exibidas como custos de desenvolvimento de aplicativos no relatório.
- O valor exibido nos relatórios de desenvolvimento de aplicativos é a soma total de todas as linhas de alocação que fluem diretamente para o objeto Aplicativos com o botão App Dev\_Cost selecionado.
