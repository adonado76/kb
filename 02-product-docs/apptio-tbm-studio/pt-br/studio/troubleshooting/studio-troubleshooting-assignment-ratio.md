---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "A tabela Assignment Ratio é muito grande"
breadcrumb: []
source_path: "studio/troubleshooting/studio-troubleshooting-assignment-ratio.html"
images:
  - "resources/images/studio_images/troubleshooting/assingment-ratio-too-large-rec.png"
  - "resources/images/studio_images/troubleshooting/assingment-ratio-too-large-solution-2.png"
  - "resources/images/studio_images/troubleshooting/assingment-ratio-too-large-solution.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# A tabela Assignment Ratio é muito grande

O limitador de taxa de atribuição impede a criação de tabelas de taxa de atribuição que sejam muito grandes.

O maior tamanho das tabelas de Taxa de Atribuição de Alocação é determinado pelos seguintes fatores:

- A contagem de linhas do identificador da tabela de origem
- A contagem de linhas do identificador da tabela de destino

  ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/troubleshooting/assingment-ratio-too-large-rec.png)

Esse erro geralmente é causado pelo não uso de uma alocação no estilo Data Relationship. Sem o uso do Data Relationship, é criado um grande número de alocações do tipo *muitos para muitos* ou *todos para todos*. Essas alocações têm baixo desempenho e reduzem a eficácia das alocações.

## A recomendação de configuração para a tabela Assignment Ratio é um erro muito grande

Para resolver esse erro, você pode executar uma ou mais das seguintes ações:

- Adicionar relacionamento de dados à alocação afetada.

  ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/troubleshooting/assingment-ratio-too-large-solution.png)
- Adicione um filtro De ou Para à alocação afetada.

  ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/troubleshooting/assingment-ratio-too-large-solution-2.png)
- Reduzir o número de linhas de identificadores nos objetos de origem.
- Reduzir o número de linhas de identificadores nos objetos de destino.
