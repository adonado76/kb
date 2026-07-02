---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Sobre os modelos"
breadcrumb: []
source_path: "studio/model_studio/about-models.html"
images:
  - "resources/images/studio_images/studioimages/studio/stu573.png"
  - "resources/images/studio_images/studioimages/studio/stu574.png"
  - "resources/images/studio_images/studioimages/studio/stu575.png"
  - "resources/images/studio_images/studioimages/studio/stu576.png"
  - "resources/images/studio_images/studioimages/studio/stu577.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Sobre os modelos

**Aplica-se a** : TBM Studio 12.0 e posterior

Um modelo de dados é uma representação lógica e gráfica do fluxo de dados relevantes para o custo, o orçamento, a utilização, os níveis de serviço, o consumo ou outras métricas de seus serviços de TI. Um modelo de amostra é mostrado na imagem a seguir.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu577.png)

Em TBM Studio, geralmente são atribuídas várias métricas a um modelo, sendo que uma métrica é um valor. As métricas mostram como uma ampla gama de dados financeiros ou operacionais está relacionada ao custo e ao desempenho dos produtos e serviços que a TI fornece à empresa.

Por exemplo:

- Um modelo poderia representar os custos mensais totais de TI, com outras métricas representando vários centros de custo dentro da organização de TI, como hardware, licenças de software e mão de obra. A imagem anterior representa a métrica de custo.
- Uma métrica de disponibilidade pode conter dados e relações relevantes que representam o tempo de atividade dos serviços ou a infraestrutura subjacente que os suporta.
- Uma métrica de utilização pode representar a utilização de CPU, rede, E/S ou disco em um farm de servidores ou conjunto de data centers.
- Uma métrica de volume ou consumo pode representar o uso de vários serviços de TI ou da infraestrutura subjacente por serviços ou unidades de negócios.

## Etapas para criar um modelo

Antes de criar um modelo, você deve carregar tabelas de dados no aplicativo. Para obter informações sobre o upload de dados, consulte [Aquisição e transformação de dados](../data%20studio/about-data-transforms.htm "(Abre em uma nova guia ou janela)").

Depois de fazer o upload dos dados, há quatro etapas principais para criar um modelo.

1. Adicione uma etapa de modelo ao pipeline de transformação de cada tabela que fará parte do modelo.
2. Adicione drivers às tabelas de origem na parte inferior do modelo.
3. Alocar valores das tabelas de origem para as tabelas de destino mais acima no modelo.
4. Criar relatórios de modelos para ajudar a analisar os dados.

## Visualizações de modelos

Há três maneiras de visualizar um modelo:

- Ao criar um modelo, você trabalhará com uma tabela individual e seus drivers e alocações. A visualização usa um diagrama Sankey como o mostrado na imagem a seguir. Para exibir o modelo, clique na etapa do modelo em um pipeline de transformação de tabela.

  ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu573.png)
- Quando quiser rastrear o fluxo de uma métrica por meio de um modelo, você pode usar a visualização **Modeled Metric**, como a mostrada na imagem a seguir:

  ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu575.png)
- Quando quiser ver um conjunto selecionado de tabelas exibidas em camadas, você pode usar um relatório modelo como o mostrado na imagem a seguir. No exemplo abaixo, as camadas são Financeiras, Pools de custos, Infraestrutura e Serviços.

  ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu576.png)

## Diagrama Sankey

As visualizações individuais e de nível do modelo usam um diagrama Sankey. No diagrama, o valor flui da esquerda para a direita. A largura das linhas de alocação é proporcional ao valor. O diagrama Sankey garante um layout consistente para todos os modelos.

Assista a este vídeo de demonstração do Apptio Education Services: [Model Studio: Sankey Layout](https://community.apptio.com/videos/1484 "(Abre em uma nova guia ou janela)"). Ou navegue por [todos os vídeos do site Apptio](https://community.apptio.com/docs/DOC-7714 "(Abre em uma nova guia ou janela)").

## Tabelas e alocações: blocos de construção de um modelo

As tabelas incluem dados sobre operações, finanças ou entidades organizacionais em uma organização. As tabelas podem ser adicionadas a um modelo adicionando uma etapa de Modelo à transformação da tabela. As tabelas típicas incluem dados de servidores, redes, aplicativos, GL (registro geral), instalações, data centers, e-mail e unidades de negócios.

As alocações determinam o fluxo de valor entre as tabelas. Nos modelos, as alocações são representadas por linhas desenhadas entre as tabelas. Na imagem anterior, há alocações da tabela Cost Source Actuals para as tabelas Labor Actuals, Facilities Actuals e Fixed Assets Actuals.

## Um modelo, várias métricas

Há um modelo por projeto, mas um modelo pode ter mais de uma métrica de modelo. As métricas são cálculos que definem um aspecto, como custo, orçamento ou quantidade. Ao visualizar um modelo, você pode alternar a métrica exibida usando o campo na parte superior do painel do modelo, conforme mostrado na imagem a seguir. Para obter informações sobre como definir métricas, consulte [Métricas](introduction-to-metrics.htm "(Abre em uma nova guia ou janela)").

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu574.png)
