---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Editar propriedades de linha"
breadcrumb: []
source_path: "studio/reports/edit-row-properties.html"
images:
  - "resources/images/studio_images/cf-findall.png"
  - "resources/images/studio_images/cf-replaceallerror.png"
  - "resources/images/studio_images/checkbox-del-row.png"
  - "resources/images/studio_images/editable-table-options.png"
  - "resources/images/studio_images/fr-menu.png"
  - "resources/images/studio_images/fr-popup.png"
  - "resources/images/studio_images/fr-uneditablecolumn.png"
  - "resources/images/studio_images/search-datasets.png"
  - "resources/images/studio_images/show-changes-history.jpg"
  - "resources/images/studio_images/show-changes-row.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Editar propriedades de linha

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/editable-table-options.png)

## Pesquisar conjuntos de dados

Mantenha o cursor sobre o valor/célula para o qual você deseja pesquisar os conjuntos de dados. Clique com o botão direito do mouse e selecione Search datasets for <value> para ver os resultados da pesquisa em uma janela pop-up.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/search-datasets.png)

## Filtrar por valor

Mantenha o cursor sobre a célula/para a qual você deseja filtrar a tabela. Clique com o botão direito do mouse e selecione Filter by Value (Filtrar por valor) para ver os resultados filtrados por esse valor de célula.

## Localizar e substituir

**Aplica-se a** 12.10.10 e posterior

Esse recurso é aplicável somente a algumas colunas do componente Tabela editável e [Relatórios com tabela editável](tables/et-report-find-replace.htm "(Abre em uma nova guia ou janela)"). Você pode localizar ou substituir colunas provenientes de outra tabela de origem se a caixa de seleção **Permitir edição em colunas incluídas** estiver marcada na configuração do ET.

Para localizar e substituir um valor na tabela, faça o seguinte:

1. Clique com o botão direito do mouse na coluna da tabela editável

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/fr-menu.png)
2. Escolha a opção **Localizar e Substituir**. A seguinte janela pop-up é exibida

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/fr-popup.png)
3. Digite o valor (sensível a maiúsculas e minúsculas) a ser pesquisado e selecione o botão **Find All (Localizar tudo** ). A contagem de resultados de correspondência exata será exibida.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/cf-findall.png)
4. Digite o valor a ser substituído e selecione o botão **Replace All (Substituir tudo** ). Se houver algum erro no valor de substituição, será exibida uma mensagem de erro apropriada. Veja abaixo um exemplo

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/cf-replaceallerror.png)
5. A opção Localizar e Substituir será desativada para [colunas não editáveis](tables/edit-properties-tables.htm "(Abre em uma nova guia ou janela)").

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/fr-uneditablecolumn.png)

**Exceções**

- O recurso de localização não é compatível com a pesquisa booleana
- A pesquisa é aplicável somente a uma única coluna de cada vez, e não em toda a tabela ou em várias colunas juntas.
- A pesquisa não se aplica a colunas desativadas, como fórmula, total, outras e pk.

## Incluir Linha

Clique no botão **Add Row (Adicionar linha** ) na parte inferior da tabela. Uma nova linha é adicionada à parte inferior da tabela, na cor laranja.

## Linha duplicada

Para saber mais, consulte [Adicionar linha duplicada.](tables/add-duplicate-row.htm "(Abre em uma nova guia ou janela)")

## Excluir linha

Clique com o botão direito do mouse na tabela editável e clique em **Delete Row (Excluir linha** ).

Se a **coluna Adicionar caixa de seleção** estiver ativada nas [propriedades avançadas](tables/set-table-properties.htm "(Abre em uma nova guia ou janela)"), selecione a caixa de seleção para uma única ou várias linhas, clique com o botão direito do mouse e selecione **Excluir linha**.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/checkbox-del-row.png)

## Mostrar alterações para esta linha

**12.11.1 e posteriores** : Essa opção mostrará as alterações da linha selecionada.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/show-changes-row.png)

## Mostrar mudanças

**12.11.0 e antes** : Essa opção mostrou as alterações na linha selecionada.

**12.11.1 e posteriores** : Selecione essa opção para exibir todas as alterações em toda a tabela

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/show-changes-history.jpg)
