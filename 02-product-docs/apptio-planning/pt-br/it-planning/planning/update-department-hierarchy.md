---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Atualizar a hierarquia de departamentos"
breadcrumb: []
source_path: "it-planning/planning/update-department-hierarchy.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Atualizar a hierarquia de departamentos

## Sobre esta tarefa

As tarefas abaixo só podem ser realizadas por usuários atribuídos às funções Admin ou Budget Process Owner. Para obter mais informações sobre funções, consulte Permissões e funções do Frontdoor.

As dimensões são as categorias de dados essenciais nos itens de linha do orçamento. Muitas dimensões incorporadas têm dependências em outras dimensões. Para obter mais informações, consulte [Dependências de atributos e dimensões de dados de referência](manage-reference-data.html#dimensiondepend). Você pode importar dados de referência de dimensões de um arquivo `.csv` ou de Costing Standard e exportar modelos de dados de referência de dimensões e dados de tabela. Para obter mais informações, consulte [Gerenciar dimensões](manage-reference-data.html).

As seguintes dimensões estão vinculadas à dimensão Departamento:

- Permissões de objeto de custo
- Centro de custos
- Taxa de câmbio planejada

## Procedimento

Se você planeja atualizar ou reorganizar a hierarquia de departamentos, é necessário:

1. Atualize os dados de referência do centro de custo e do departamento. Para obter mais informações, consulte [Gerenciar dados de referência de dimensões financeiras](manage-financial-dimensions.html) ).
2. Atualize os dados de referência das permissões do objeto de custo. Para obter mais informações, consulte [Gerenciar dados de referência de permissões de objetos de custo](manage-cost-object.html) ).
3. Se o suporte para várias moedas estiver ativado, você deverá atualizar os dados de referência da taxa de moeda do plano. Para obter mais informações, consulte [Gerenciar tabelas de taxas de conversão de várias moedas (dados de referência](manage-multi-currency.html) ).
4. Navegue até seu plano e clique em Update Reference Data (Atualizar dados de referência ). Para obter mais informações, consulte [Forçar um plano para usar dados de referência atualizados](force-plan-use.html) ).
