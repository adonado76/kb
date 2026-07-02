---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Opções de filtragem"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Report Studio"
  - "Componentes do relatório: Tabelas"
source_path: "studio/new-uc/reference/report-studio-reference/filtering-options.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Opções de filtragem

É possível filtrar as tabelas para exibir apenas as linhas que atendam a critérios específicos. Os filtros são configurados na área Filtros do painel Configuração do Componente.

**Adicionar filtros**

1. Arraste um campo do Explorador de Projetos para a área de Filtros.
2. Clique com o botão direito do mouse no filtro e selecione “Editar filtro”.
3. Selecione valores ou configure os critérios de filtragem.

**Operadores de filtro**

|  |  |  |
| --- | --- | --- |
| **Operador** | **Descrição** | **Exemplo** |
| Igual | Correspondência exata. | O tipo de despesa é igual a " OpEx " |
| Diferente | Exclui as linhas correspondentes. | O tipo de despesa não é igual a " CapEx " |
| Contém | O valor inclui o texto especificado. | A conta contém 2111 |
| Não contém | O valor exclui o texto especificado. | Descrição: Não contém texto de teste |
| Começa com | O valor começa com o texto especificado. | A conta começa com ACCT |
| Termina com | O valor termina com o texto especificado. | Descrição: Termina com serviços |
| Está em | O valor corresponde a qualquer um da lista separada por vírgulas. | A conta está nos anos 2111, 2112 e 2113 |
| Não está em | O valor não corresponde a nenhum da lista. | O tipo não está em teste, demonstração |
| É nulo | O valor está vazio. | A categoria está nula |
| Não é nulo | O valor não está vazio. | A categoria não é nula |
| > (Maior que) | Valor numérico maior do que o especificado (apenas numérico). | Custo > 10.000 |
| < (Menor que) | Valor numérico inferior ao especificado (apenas numérico). | ETP < 5 |

**Recurso de pesquisa automática**

Ative os campos de pesquisa abaixo do cabeçalho de cada coluna para permitir a filtragem por parte do usuário.

**Para ativar a Pesquisa automática:**

1. Clique com o botão direito do mouse na tabela e selecione Propriedades.
2. Na guia Dados, ative a opção Pesquisa automática.
3. Clique em OK. Os campos de pesquisa aparecem abaixo dos cabeçalhos das colunas.

**Tópico principal:** [Componentes do relatório: Tabelas](../../../../studio/new-uc/reference/report-studio-reference/report-component-table.html)
