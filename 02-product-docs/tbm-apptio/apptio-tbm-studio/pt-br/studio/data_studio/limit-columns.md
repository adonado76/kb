---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Limite_Colunas"
breadcrumb: []
source_path: "studio/data_studio/limit-columns.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Limite_Colunas

Determina as colunas exibidas em uma tabela. Você pode limitar as colunas usando a **faixa de opções**.

## Sintaxe

`!LIMIT_COLUMNS[{columns to include}][{columns to
add}][{columns to exclude}][options]`

## Argumentos

Colunas a serem incluídas
:   Uma lista de colunas separada por vírgulas a ser incluída na tabela. Esse é o único argumento obrigatório, mas pode estar vazio. Se estiver vazio, todas as colunas da tabela serão incluídas.

    Você pode usar o texto dinâmico para fazer referência a uma coluna em uma tabela que seja uma lista de colunas separada por vírgulas. Por exemplo:!Limit\_Columns[<%=ABC Aggregation.Columns %>] inseriria a lista de colunas em uma coluna chamada Columns em uma tabela chamada ABC Aggregation.

Colunas a serem adicionadas
:   Uma lista de colunas separada por vírgulas para adicionar à tabela. As colunas devem vir do conjunto de dados usado para gerar a tabela.

Colunas a serem excluídas
:   Uma lista separada por vírgulas de colunas a serem excluídas da tabela.

## Opções

As seguintes opções estão disponíveis:

| Opção | Descrição |
| --- | --- |
| máximo:# | Define o número máximo de colunas que serão exibidas. |
| onlyModeledMetrics | Se a tabela que está sendo limitada tiver colunas métricas, exclua-as da tabela. Mostrar apenas colunas de métricas modeladas. |
| includePrimaryKey | Sempre inclua a coluna Chave primária, independentemente das outras configurações. |
| showIrrelevant | Substitui o filtro de coluna relevante. |

## Exemplo

Suponha que você tenha a seguinte tabela.

![](../../resources/images/it%20planning_images/limit-columns.png)

O caminho de dados da tabela é:

```
docs.org:ABC Company/
Reports/
.DateGoesHere/
CostModels/
Default/
.TableTransform:Applications/
.Summary/
!LIMIT[0,2147483647]/
!LIMIT_COLUMNS[]/
```

Você deseja mostrar apenas as colunas Aplicativo, Nível de serviço e Nível de suporte. Você edita o!LIMIT\_COLUMNS para que se pareça com o seguinte:

`!LIMIT_COLUMNS[{Application},{Service Level},{Support Tier}]/`

## Fita

Para limitar as colunas exibidas usando a **faixa de opções** :

1. Selecione a tabela a ser editada.
2. Selecione o ícone **Propriedades** na guia **Autoria** da **Faixa de Opções**.
3. Na guia **Data (Dados** ) da caixa de diálogo **Properties (Propriedades** ), use os campos **Include (Incluir** ) ou **Exclude (Excluir** ) para selecionar as colunas exibidas.

**Tópico pai:** [Tabelas editáveis: Acomodando a entrada do usuário](../../studio/data_studio/editabletables.html "Aplica-se a: TBM Studio 12.6 e posterior")
