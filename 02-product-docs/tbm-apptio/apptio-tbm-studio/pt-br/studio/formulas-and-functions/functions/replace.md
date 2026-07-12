---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Substituir função"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/replace.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Substituir função

Substitui valores em uma tabela com base em mapeamentos de uma tabela de pesquisa separada. A função faz a correspondência em colunas-chave e atribui novos valores de colunas especificadas na tabela de substituição. Todos os valores são tratados como cadeias de caracteres.

A função Replace é usada para substituir valores em uma coluna em uma tabela de transformação por valores de uma tabela de pesquisa e substituição. A função é inserida no campo **Value Override (Substituição de valor** ) para uma coluna em uma tabela de transformação. Os valores de substituição são inseridos em uma tabela search\_and\_replace (conjunto de dados). As entradas na tabela search\_and\_replace são executadas sequencialmente, do topo da tabela para a base. As substituições baseadas nas primeiras linhas da tabela podem ser substituídas por substituições nas últimas linhas. Todos os valores são tratados como cadeias de caracteres.

## Sintaxe

`=Replace((transform_table_column1,transform_table_column2,...),search_and_replace_table,(match_column1,match_column2,...),(new_column1,new_column2,...),replace_table_column)`

## Argumentos

*transform\_table\_column1, 2,...*

Os nomes das colunas na tabela que serão usadas para identificar exclusivamente cada linha na tabela. As colunas com valores que serão substituídos também devem ser incluídas.

*tabela search\_and\_replace*

O nome da tabela que fornecerá os valores de substituição.

*match\_column1, 2,...*

As colunas da tabela search\_and\_replace\_table que correspondem às colunas da tabela de transformação. Elas podem ter nomes diferentes, mas para cada coluna na tabela de transformação, deve haver uma coluna correspondente na tabela de pesquisa e substituição.

*new\_column1, 2,...*

Os nomes das colunas na tabela search\_and\_replace que serão usadas para fornecer os novos valores.

*substituir\_coluna\_da\_tabela*

A coluna na tabela search\_and\_replace que fornecerá o novo valor.

## Exemplo

Suponha que você tenha a seguinte tabela de transformação:

| Departamento | Local | ID |
| --- | --- | --- |
| Vendas | Seattle | 001 |
| Marketing | Seattle | 002 |
| Pesquisa | Chicago | 003 |
| Desenvolvimento | Chicago | 004 |
| Distribuição | Denver | 005 |

Você deseja alterar os IDs adicionando um Ds na frente de cada ID. Para garantir um identificador exclusivo, você cria uma nova tabela (conjunto de dados) chamada **Tabela de pesquisa e substituição** (exemplo a seguir):

| Departamento | ID | Novo\_Dept | Nova\_ID |
| --- | --- | --- | --- |
| Vendas | 001 | Vendas | D001 |
| Marketing | 002 | Marketing | D002 |
| Pesquisa | 003 | Pesquisa | D003 |
| Desenvolvimento | 004 | Desenvolvimento | D004 |
| Distribuição | 005 | Distribuição | D005 |

Abra a tabela de transformação no aplicativo e digite o seguinte no campo **Value Override** da coluna ID:

```
=Replace((Dept,ID),Search_and_Replace_Table,(Dept,ID),(New_Dept,
New_ID),New_ID)
```
