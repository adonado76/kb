---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Excluir uma coluna numérica de uma tendência"
breadcrumb: []
source_path: "studio/data_studio/exclude-numeric-column-from-trend.html"
images:
  - "resources/images/studio_images/studioimages/studio_data_ungroup_sui.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Excluir uma coluna numérica de uma tendência

◆ Aplica-se a: TBM Studio 11.0 e posterior, TBM Studio 12.0 e posterior

Às vezes, ao criar um relatório ad-hoc, você deseja criar tendências para alguns números e excluir outros. Este artigo descreve como excluir uma ou mais colunas da tendência.

Este artigo contém capturas de tela do TBM Studio R12, mas os mesmos princípios se aplicam ao TBM Studio v.11.

Digamos que você comece com um relatório que tenha uma tendência dos custos dos três meses anteriores por Pool de custos:

![](../../resources/images/studio_images/studioimages/studio_cost%20pool_exclude%20numeric%20column_sui.png)

Se você simplesmente adicionar Budget, obterá o seguinte:

![](../../resources/images/studio_images/studioimages/studio_exclude%20numeric%20column_budget_sui.png)

No entanto, neste exemplo, nosso número de orçamento é o mesmo todos os meses e, portanto, queremos exibi-lo apenas uma vez e não que ele apareça sob a tendência. Então, em vez disso, fazemos o seguinte:

1. Remover temporariamente os valores de tempo das **Colunas**.
2. Insira uma coluna de fórmula e defina-a como igual à métrica Orçamento:

   ![](../../resources/images/studio_images/studioimages/studio_exclude%20numeric%20column_create%20new_sui.png)
3. Arraste a coluna **Budget** da seção **Values (Valores** ) para a seção **Rows (Linhas** ).
4. Clique com o botão direito do mouse na coluna Budget e selecione Ungroup (Desagrupar).

   Se você esquecer de desagrupar a coluna ao adicionar a tendência temporal novamente, a tabela terá zeros nessa coluna.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio_data_ungroup_sui.png)
5. Adicione a tendência de volta às colunas:

   ![](../../resources/images/studio_images/studioimages/studio_data_excluding%20numeric%20column_sui.png)
