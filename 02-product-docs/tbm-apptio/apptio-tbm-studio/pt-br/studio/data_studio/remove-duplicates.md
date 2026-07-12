---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Remover duplicatas de uma tabela"
breadcrumb: []
source_path: "studio/data_studio/remove-duplicates.html"
images:
  - "resources/images/studio_images/studioimages/studio/aug450.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Remover duplicatas de uma tabela

**Aplica-se a** : TBM Studio 12.0 e posterior

Se estiver trabalhando com um conjunto de dados que tenha entradas duplicadas na coluna chave, é possível eliminar as entradas duplicadas usando a etapa de transformação **Remove Duplicates**. Se houver entradas duplicadas com o mesmo valor, a entrada na tabela que corresponder ao tipo de comparação será selecionada.

![](../../resources/images/studio_images/studioimages/studio_remove%20dup_remove%20dup.png)

## Remover duplicados

1. Se o projeto estiver ativado por tempo, selecione o período e o ano.
2. Dê uma olhada na tabela.
3. Adicione uma etapa **Remove Duplicates** à transformação.
4. Selecione valores para os campos:
   - **Coluna principal**. Selecione a coluna a ser filtrada.
   - **Coluna de comparação**. Selecione a coluna que contém os valores usados para determinar a linha que será mantida.
   - **Tipo de comparação**. Selecione as linhas a serem mantidas: **Maior** ou **Menor**. O tipo de comparação que você escolher determina os valores mantidos. Por exemplo, a coluna poderia incluir datas. Se você escolher o tipo de comparação **Maior**, a linha com a data mais recente será mantida.

## Exemplo de filtragem de linhas exclusivas

Suponha que você tenha uma tabela que lista as compras de servidores por preço de compra e data, conforme mostrado abaixo. Você gostaria de filtrar a tabela para que apenas a compra mais recente de cada tipo de servidor seja exibida. Você definiria a coluna-chave como **Server (Servidor** ), a coluna de comparação como **Purchase Date (Data de compra** ) e o tipo de comparação como **Largest (Maior)** :

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/aug450.png)
