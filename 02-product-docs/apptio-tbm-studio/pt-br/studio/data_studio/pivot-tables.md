---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Dados dinâmicos"
breadcrumb: []
source_path: "studio/data_studio/pivot-tables.html"
images:
  - "resources/images/studio_images/studioimages/studio/stu204.png"
  - "resources/images/studio_images/studioimages/studio/stu205.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Dados dinâmicos

**Aplica-se a** : TBM Studio 12.0 e posterior

Os dados de itens de linha, como um registro geral, informações sobre tíquetes de problemas ou utilização da CPU, podem ser resumidos com o recurso **Pivot**. Por exemplo, talvez você queira resumir os dados por data center, aplicativo ou tipo de servidor.

Para ilustrar o poder da dinamização de dados, suponha que você tenha uma tabela de problemas como a seguinte:

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu204.png)

Você gostaria de totalizar os minutos dos tíquetes de problemas por aplicativo e por local, em que os aplicativos são as linhas da tabela, os locais são as colunas e as células exibem o total de minutos. Quando você dinamiza a tabela, o aplicativo cria uma tabela que se parece com a seguinte:

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu205.png)

## Pivotar uma tabela

1. Dê uma olhada na tabela.
2. Adicione uma etapa **Pivot** ao pipeline de transformação.
3. Complete o seguinte:
   - **Linha dinâmica** : Selecione a coluna na tabela que será usada para os valores na primeira coluna da tabela dinâmica. No exemplo acima, a coluna **Aplicativo** foi selecionada.
   - **Coluna dinâmica** : Selecione a coluna na tabela que será usada para os cabeçalhos de coluna nas colunas seguintes à primeira coluna. No exemplo acima, a coluna **Geography** foi selecionada.
   - **Valor pivô** : Selecione a coluna cujos valores serão somados e exibidos nas células da tabela dinâmica. No exemplo acima, a coluna **Duration** (não visível) foi selecionada.
4. Para executar o pivô, clique em **OK**.

## Criar vários pivôs

Se você tiver dados que se beneficiariam de vários pivôs, poderá criar uma nova tabela de dados para cada pivô. Para criar uma nova tabela, clique com o botão direito do mouse na etapa **de saída** no pipeline de transformação e clique em **Criar nova tabela a partir desta etapa**.
