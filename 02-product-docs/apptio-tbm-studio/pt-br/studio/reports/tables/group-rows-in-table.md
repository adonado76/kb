---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Agrupar as linhas em uma tabela"
breadcrumb: []
source_path: "studio/reports/tables/group-rows-in-table.html"
images:
  - "resources/images/studio_images/studioimages/reports/rep161.png"
  - "resources/images/studio_images/studioimages/reports/rep162.png"
  - "resources/images/studio_images/studioimages/studio/stu615.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Agrupar as linhas em uma tabela

**Aplica-se a** : TBM Studio 12.0 e posterior

Talvez você queira consolidar os dados em uma tabela, agrupando-os pelos valores da primeira coluna. Para consolidar os dados, use o recurso Group (Grupo). As tabelas são agrupadas automaticamente por pelo menos um campo na área **Linhas** do painel **Configuração de componentes**.

Você pode agrupar as linhas em uma tabela clicando em **Group (Grupo** ) na guia **Data (Dados)**. As imagens a seguir mostram uma tabela antes e depois do agrupamento. As colunas com dois ou mais valores diferentes exibirão três pontos verticais. Uma coluna **Count** é adicionada à tabela e exibe o número de unidades no grupo.

Um exemplo é a coluna **SubService** na imagem a seguir.

![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep162.png)

![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu615.png)

Se houver campos vazios na coluna **Group By**, será exibida uma linha na parte inferior da tabela com os seguintes valores:

| Nesta coluna: | Esse valor é exibido: |
| --- | --- |
| Coluna Group By | Em branco |
| .Contagem | Número de linhas em branco |
| Colunas numéricas | Soma de todas as linhas com espaços em branco na coluna Group By |

Para agrupar uma tabela:

1. Selecione a tabela e clique no ícone **Group (Grupo** ) na guia **Data (Dados)**.
2. A caixa de diálogo **Group** é exibida como mostra a imagem a seguir:

   ![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep161.png)
3. Selecione as colunas que serão usadas para agrupar a tabela. Na imagem anterior, **Data Center** e **Service** foram selecionados.
4. Depois de fazer suas seleções, clique em **Group (Grupo** ). O aplicativo agrupa a tabela.
