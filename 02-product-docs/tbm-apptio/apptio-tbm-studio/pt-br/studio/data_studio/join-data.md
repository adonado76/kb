---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Unir dados"
breadcrumb: []
source_path: "studio/data_studio/join-data.html"
images:
  - "resources/images/studio_images/studioimages/studio/stu544.png"
  - "resources/images/studio_images/studioimages/studio/stu545.png"
  - "resources/images/studio_images/studioimages/studio/stu690.png"
  - "resources/images/studio_images/studioimages/studio_join-data_data-centers-info.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Unir dados

**Aplica-se a** : TBM Studio 12.0 e posterior

A etapa **Join** vincula a tabela atual a outras tabelas, fazendo a correspondência entre os valores de uma coluna na tabela atual e os valores de uma coluna em outra tabela. Isso pode ser útil para fins de relatório e para adicionar informações a uma tabela que servirá como um driver de unidade em um modelo. A intenção da etapa **Join** é produzir uma única tabela com todos os dados necessários para a geração de relatórios.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu544.png)

O diagrama **Join** exibe a tabela de interesse à esquerda e as tabelas relacionadas à direita. As porcentagens indicam o grau de correspondência. Quanto maior a porcentagem, maior o número de entradas correspondentes nas duas tabelas.

A etapa **Join** em um pipeline de transformação vem depois da etapa **Table**, conforme mostrado abaixo. A etapa **Table** não refletirá os resultados da união. No entanto, todas as colunas unidas serão exibidas no **Project Explorer** :

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu690.png)

## Juntar vs Anexar

Uma etapa de transformação de dados **Join** combina dados de duas ou mais tabelas nas mesmas linhas com base em valores comuns em uma ou mais colunas. Se você não quiser combinar dados nas mesmas linhas, use a etapa de transformação de dados **Append**. Uma etapa **Append** adiciona linhas à tabela.

## Exibir detalhes da coluna da tabela

Para ver os detalhes da coluna de uma tabela, clique no sinal de **mais**. A tabela se expande e mostra as porcentagens de correspondência para cada coluna.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu545.png)

## Exibir detalhes do link

Para ver os detalhes de um link, clique nele. Os itens de linha são exibidos nas colunas **Unmatched**, **Matched** e **Reference** em uma tabela abaixo do diagrama. A coluna **Referência** refere-se a itens de linha.

## Adicionar um link

Para adicionar um link entre duas tabelas, clique no botão **Add Link** e preencha os campos na caixa de diálogo **Add Link**.

## Exemplo

Suponha que você tenha as duas tabelas a seguir: **Data Centers Info** e **Data Centers Hosting**. Ambas contêm informações sobre data centers, mas as informações são diferentes em cada tabela. Você deseja combiná-los em uma única tabela. Eles têm uma coluna com os mesmos valores: Data Center. Essa coluna será usada para fazer a correspondência entre os dados das duas tabelas.

Informações sobre data centers

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio_join-data_data-centers-info.png)

Hospedagem de data centers

![](../../resources/images/studio_images/studioimages/studio_data%20centers%20hosting_table.png)

Para unir as duas tabelas:

1. Abra a tabela **Data Centers Info** no **Project Explorer** e adicione uma etapa **Join** ao pipeline, conforme mostrado abaixo:

   ![](../../resources/images/studio_images/studioimages/studio_data%20centers%20info_join.png)
2. No diagrama de relacionamento de dados, observe que há uma união entre a tabela **Data Centers Info** e a tabela **Data Centers Hosting**, mostrando uma correspondência de 100%.
3. Adicione uma etapa **de Modelo** à tabela Informações do data center. A tabela Data Centers Info no Project Explorer agora mostra todas as colunas unidas, incluindo as colunas Data Centers Hosting. Agora você pode usar as colunas unidas em uma tabela de relatório:

   ![](../../resources/images/studio_images/studioimages/studio_data%20centers%20hosting_model.png)

Observação: no pipeline, a etapa **Table (Tabela** ) não mostrará as colunas unidas.
