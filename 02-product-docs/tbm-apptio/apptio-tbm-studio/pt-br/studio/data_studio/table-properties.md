---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Editar propriedades da tabela"
breadcrumb: []
source_path: "studio/data_studio/table-properties.html"
images:
  - "resources/images/studio_images/edit-generated-table.png"
  - "resources/images/studio_images/revert-generated.png"
  - "resources/images/studio_images/truncate-general.png"
  - "resources/images/studio_images/truncate-generated.png"
  - "resources/images/studio_images/truncated-empty.png"
  - "resources/images/studio_images/warning-truncate.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Editar propriedades da tabela

## Filtrar por valor

Mantenha o cursor sobre a célula/para a qual você deseja filtrar a tabela. Clique com o botão direito do mouse e selecione Filter by Value (Filtrar por valor) para ver os resultados filtrados por esse valor de célula.

## Adicionar uma linha a uma tabela

Clique no botão **Add Row (Adicionar linha** ) na parte inferior da tabela. Uma nova linha é adicionada à parte inferior da tabela, na cor laranja.

## Truncar

**Aplica-se a** : 12.11.4 e posterior

O botão **Truncar** é exibido para as tabelas editáveis Geral e Enriquecida. No entanto, a função Truncate funciona apenas para tabelas geradas.

1. Abra uma tabela editável enriquecida. O botão **Truncar** aparece no canto inferior direito da página.

   ![Truncar](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/truncate-generated.png)
2. Altere o valor ' Q1 ' e 'Engagement nas células destacadas acima, salve a tabela e, em seguida, selecione **Truncate**. Uma mensagem de aviso pop-up é exibida conforme mostrado.

   ![mensagem de aviso](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/edit-generated-table.png)
3. Selecione **Ok**. O valor original de Q1 e Engagement é revertido conforme mostrado.

   ![O engajamento é revertido](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/revert-generated.png)
4. Agora, abra uma tabela geral editável.

   ![tabela geral editável](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/truncate-general.png)
5. Selecione **Truncar**. A mensagem pop-up é exibida.

   ![Truncar mensagem pop-up](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/warning-truncate.png)
6. Selecione o botão **Ok**. Todas as linhas são excluídas da tabela.

   ![Linhas excluídas](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/truncated-empty.png)
7. Verifique a tabela editável. O truncamento é permanente somente após a verificação na tabela editável. As linhas são excluídas do MySQL DB, e essa alteração também não aparecerá em **Mostrar alterações**.

Observação: Se uma tabela editável estiver vinculada a um relatório, as linhas truncadas serão excluídas mesmo nesse relatório.

**Reverter alterações**

Se você quiser reverter a ação de truncamento, isso deve ser feito antes de fazer o check-in da tabela. Depois de truncar e fazer o check-in da tabela, não é possível reverter a ação de truncar.
