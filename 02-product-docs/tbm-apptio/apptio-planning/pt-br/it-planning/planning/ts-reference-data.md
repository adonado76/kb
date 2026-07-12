---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Solucionar problemas de erros de exclusão de dados de referência"
breadcrumb:
  - "Planning"
  - "Solução de problemas e perguntas frequentes"
source_path: "it-planning/planning/ts-reference-data.html"
images:
  - "resources/images/it_planning_images/publish_dialog.jpg"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Solucionar problemas de erros de exclusão de dados de referência

## Sobre esta tarefa

As tarefas abaixo só podem ser realizadas por usuários atribuídos às funções Admin ou Budget Process Owner.

Se você excluir um atributo e tentar publicar uma dimensão nos dados de referência, poderá receber o seguinte erro:![ícone de engrenagem](../../../../../03-media/apptio-planning/resources/images/it_planning_images/publish_dialog.jpg)

## Procedimento

Muitas dimensões incorporadas têm dependências em outras dimensões. Para obter mais informações, consulte [Dependências de atributos e dimensões de dados de referência](manage-reference-data.html).

Por exemplo, uma dimensão de Departamento pode conter um Centro de Custo. A remoção dessa dimensão do centro de custo resultaria em um erro. Para evitar esse erro, você deve primeiro remover a dimensão relacionada antes de poder remover a dimensão original.

1. Exportar as tabelas de dados de referência afetadas. Para obter mais informações, consulte [Download e preenchimento de tabelas ou modelos de dados de referência](manage-reference-data.html).
2. Edite o modelo conforme necessário para remover os dados afetados.
3. Importar e publicar a tabela de dados de referência atualizada. Para obter mais informações, consulte [Importar e publicar dados de referência](manage-reference-data.html).

Observação: Se continuar a ter problemas, você pode excluir o conteúdo das duas dimensões e reimportá-las.
