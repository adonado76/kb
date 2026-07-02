---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Gerenciamento de entidades"
breadcrumb: []
source_path: "it-planning/planning/adm/custom-dimension-entitiy-metric.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Gerenciamento de entidades

Em Planning , os clientes podem criar até 13 dimensões personalizadas para definir os conjuntos de categorias de dados que ampliam e aprimoram seu planejamento e análise financeiros.

Para saber mais sobre dimensões personalizadas, consulte [Dados de referência personalizados](../manage-custom-reference.htm "(Abre em uma nova guia ou janela)").

Para que o ADM (Automated Data Management ) atualize automaticamente as alterações nas dimensões personalizadas para Planning, é necessário atualizar a tabela de mapeamento de entidades no ADM sobre a dimensão personalizada recém-criada para que o usuário possa adicionar o nome do conjunto de dados em TBM Studio de onde os dados de origem estão vindo.

A adição/exclusão de dimensões personalizadas no Mapeamento de entidades é totalmente automatizada.

Quando uma nova dimensão personalizada for adicionada em Planning, o Automated Data Management > **Entity Mapping** será atualizado automaticamente com a nova entrada na tabela Entity.

1. [Criar…](../manage-custom-reference.htm "(Abre em uma nova guia ou janela)")

   ![imagem](../../../resources/images/it%20planning_images/create-custom-dim_949x656.png)
2. Navegue até Automated Data Management > Entity Mapping (Mapeamento de entidades). A dimensão "Pedido de compra" está automaticamente disponível no mapeamento de entidades do ADM.

   ![imagem](../../../resources/images/it%20planning_images/ent-mapp.png)

Quando uma dimensão personalizada é excluída em Planning, o mapeamento da entidade correspondente no Data Management automatizado também será excluído se não houver outro aplicativo que assine a dimensão excluída. Caso haja uma assinatura ativa diferente de Planning presente para a entidade que está sendo excluída, somente a assinatura Planning para essa dimensão será removida.

**Tópico principal:** [Conectar-se a Apptio Costing](../../../it-planning/planning/adm/adm_capabilities.html)
