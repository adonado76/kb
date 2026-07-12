---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Ver itens atualizados"
breadcrumb:
  - "Planning"
  - "Fluxos de trabalho e colaboração"
source_path: "it-planning/planning/view-upd-li.html"
images:
  - "resources/images/it_planning_images/vuli.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Ver itens atualizados

O recurso **Exibir itens atualizados** permite identificar rapidamente o que mudou em um plano desde o último **envio** ou **instantâneo**. Quando ativado, o sistema filtra a tabela para exibir apenas os itens de linha que foram adicionados, atualizados ou excluídos, tornando as revisões e aprovações mais rápidas e precisas.

Esta visualização está disponível na página **Despesas**. Quando um departamento do grupo ou vários departamentos são selecionados, a visualização atualizada compara **o instantâneo mais recente** de cada departamento folha com **o instantâneo anterior** e exibe as diferenças.

**Principais benefícios:**

- Isole rapidamente as alterações de grandes conjuntos de dados
- Melhore a precisão da revisão concentrando-se apenas nos itens modificados
- Acelere a colaboração e as aprovações destacando o que precisa de atenção
- Forneça transparência sobre quem fez as alterações e quando

## Como ela funciona

1. Ative a opção **Exibir atualizações** na página Despesas.
2. A tabela é atualizada imediatamente para mostrar apenas os itens que foram alterados desde o último instantâneo.
3. Cada linha exibida inclui uma coluna **Ação** que descreve o tipo de atualização, juntamente com as colunas **Modificado por** e **Última atualização** para mostrar quem fez a alteração e quando.

   |  |  |
   | --- | --- |
   | **Ação** | **Descrição** |
   | **Novo** | Um novo item foi adicionado. |
   | **Atualizado** | Um item de linha existente foi modificado. |
   | **Excluído** | Um item foi removido. |

![imagem dos itens atualizados](../../../../../03-media/apptio-planning/resources/images/it_planning_images/vuli.png)

**Notas adicionais:**

- **Os itens importados** são marcados como **Novos** e exibem a data e hora e o nome de usuário da importação.
- **Os dados financeiros gerados** (Mão de obra, Atividade de mão de obra, Contratos, Ativos) são marcados como **Atualizados** e refletem as últimas atualizações feitas nos seus dados de origem.
- As alterações aplicadas através de **Atualizar dados de referência** ou **Atualizar dados reais** não aparecem no modo Exibir atualizações.
- Os planos criados a partir de uma linha de base mantêm os valores **da última atualização** da linha de base para esses itens.
