---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Partição de dados por data"
breadcrumb: []
source_path: "studio/data_studio/partition-data-by-date.html"
images:
  - "resources/images/studio_images/studioimages/studio/aug103.png"
  - "resources/images/studio_images/studioimages/studio/aug104.png"
  - "resources/images/studio_images/studioimages/studio/stu305.png"
  - "resources/images/studio_images/studioimages/studio/stu306.png"
  - "resources/images/studio_images/studioimages/studio/stu307.png"
  - "resources/images/studio_images/studioimages/studio/stu308.png"
  - "resources/images/studio_images/studioimages/studio/stu309.png"
  - "resources/images/studio_images/studioimages/studio/stu507.png"
  - "resources/images/studio_images/studioimages/studio/stu508.png"
  - "resources/images/studio_images/studioimages/studio/stu509.png"
  - "resources/images/studio_images/studioimages/studio/stu510.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Partição de dados por data

**Aplica-se a** : TBM Studio 12.0 e posterior

Quando você traz dados para o aplicativo, geralmente os traz para um período e ano específicos. Por exemplo, os dados de utilização e os dados de serviços em nuvem geralmente são atualizados mensalmente. No entanto, há ocasiões em que você trará dados para o aplicativo com data marcada e desejará distribuir esses dados entre períodos com base nas datas. Um exemplo seria um registro geral.

Na maioria das vezes, você desejará distribuir os dados com base na data da transação. Quando estiver trabalhando com dados com carimbo de data, use a função **Partição de data** para distribuir os dados nos períodos de tempo corretos. Os dados com registro de data e hora são exibidos com base no período selecionado no seletor de datas na parte superior da janela do aplicativo:

![partição de data](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu305.png)

Quando você particiona uma tabela com data, uma ou mais colunas são adicionadas à tabela que contém os valores do período selecionado.

## Formatos de dados

Os dados com registro de data e hora geralmente têm um de dois formatos: baseado em linhas ou baseado em colunas. Às vezes, pode incluir ambos. Um exemplo típico de dados baseados em linhas é um livro-razão como o mostrado abaixo. Há uma coluna que contém as datas, e há uma data para cada linha:

![formatos de dados](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/aug103.png)

Os dados baseados em colunas incluem uma coluna para cada mês em um ano. Os dados orçamentários e salariais são frequentemente apresentados nesse formato. Um exemplo de dados orçamentários baseados em colunas é mostrado abaixo:

![formatos de dados](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/aug104.png)

Menos comuns são os dados com registro de data e hora que também incluem datas em linhas e colunas. Os tíquetes da central de serviços são um exemplo. As datas de início e término seriam representadas em linhas, e o custo por mês seria representado em colunas.

## Dados baseados em linhas

Os dados baseados em linhas geralmente incluem uma ou mais colunas com datas. Por exemplo, os dados do tíquete da central de serviços podem incluir colunas de data de início e data de término. Uma tabela como a mostrada na imagem a seguir, quando particionada na coluna Data de início da linha de base, seria semelhante à tabela mostrada na imagem subsequente:

![dados baseados em linhas](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu507.png)

![dados baseados em linhas](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu508.png)

Para particionar esse tipo de dados:

1. Selecione a opção **As datas são representadas em linhas**.
2. Selecione as colunas **Data de início** e **Data de término**.

O aplicativo agrupa as linhas nos períodos corretos.

## Dados baseados em colunas

Quando se está trabalhando com dados baseados em colunas, geralmente os dados incluem uma coluna para cada período em um ano fiscal ou calendário. Os títulos das colunas podem ter qualquer formato de data válido, como Jan, Jan 2016 ou P1 2016. Quando os títulos das colunas especificam apenas um ano, o ano deve estar sozinho ou em último lugar no título, por exemplo, 2016 ou Taxa 2016, mas não Taxa 2016. Uma tabela como a mostrada na imagem a seguir, quando particionada por data, se pareceria com a tabela na imagem subsequente:

![dados baseados em colunas](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu509.png)

![dados baseados em colunas](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu510.png)

Para particionar esse tipo de dados:

1. Selecione a opção **As datas são representadas em colunas**.
2. Na coluna Interpretar ano como, selecione **Ano fiscal** ou **Ano civil**.
3. No campo **New Column Prefix (Novo Prefixo de Coluna** ), digite um rótulo que você deseja adicionar à coluna label.For. Por exemplo, se as colunas na tabela original forem rotuladas como Jan, Feb, etc, e você inserir Amount (Valor) no campo **New Column Prefix (Novo Prefixo de Coluna** ), as colunas na tabela particionada por data seriam rotuladas como **Amount Jan (Valor de Janeiro** ), **Amount Feb (Valor de Fevereiro** ) etc.
4. Selecione os conjuntos de colunas que devem ser usados para particionar os dados. Se o conjunto de dados incluir dois ou mais conjuntos de colunas, você poderá particionar os dados por cada conjunto. Por exemplo, suponha que você tenha um conjunto de dados que inclua colunas mensais para custo e orçamento, conforme mostrado na imagem a seguir:

   ![dados baseados em colunas](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu306.png)
5. Você pode optar por particionar os dados por Custo, Orçamento ou ambos. Se você escolher **Custo**, o resultado será parecido com a imagem a seguir:

   ![dados baseados em colunas](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu307.png)

   Se você escolher **Budget**, o resultado será parecido com a imagem a seguir:

   ![dados baseados em colunas](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu308.png)

   E, se você escolher **Custo** e **Orçamento**, o resultado será semelhante à imagem a seguir:

   ![dados baseados em colunas](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu309.png)
