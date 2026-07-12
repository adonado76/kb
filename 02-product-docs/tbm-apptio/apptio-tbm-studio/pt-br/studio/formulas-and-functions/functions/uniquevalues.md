---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "UniqueValues função"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/uniquevalues.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# UniqueValues função

Retorna uma lista de valores exclusivos em uma coluna.

## Onde usar

Essa função pode ser usada em:

- Conjuntos de dados
- Colunas de fórmula em tabelas de relatórios
- Texto Dinâmico
- Qualquer lugar onde você possa adicionar uma cláusula de filtragem de condição.

Observação: Essa função não pode ser colocada em uma coluna na mesma tabela que é referenciada na função. Se você tentar fazer isso, receberá uma mensagem de erro.

## Sintaxe

`UniqueValues(table:column1,true)`

`UniqueValues(table:column1[column2=columnA],true)`

## Argumentos

*tabela:coluna*

A tabela e a coluna a serem examinadas quanto a valores distintos. A *tabela* não pode ser igual à tabela atual.

*table:column[ column2=columnA ]*

Se um critério de correspondência entre colchetes [] for adicionado após a especificação table:column, os valores de retorno serão limitados a valores que correspondam entre duas tabelas.

*column2* é uma coluna na *tabela* externa

*columnA* é uma coluna na tabela atual

*verdadeiro*

Se esse parâmetro for incluído, os valores em branco e nulos serão excluídos da lista.

Por exemplo, suponha que você tenha os seguintes dados:

| **Coronel A** | **Coronel B** |
| --- | --- |
| F1 | A |
| F2 | B |
| F3 |  |

Se você especificar =UniqueValues(ColB ), obterá: "null", "A", "B".

Se você especificar =UniqueValues(ColB,true ), obterá: "A", "B".

## Tipo de retorno

Lista separada por vírgulas de valores exclusivos na coluna designada.

## Exemplo

Suponha que você tenha a tabela abaixo:

| Servidor | Local |
| --- | --- |
| EXCH006 | Seattle |
| EXCH010 | Boston |
| NET207 | Boston |
| STOR124 | Seattle |
| STOR250 | Boston |
| STOR350 | Denver |

A função a seguir, se executada na tabela Servidores acima, retorna três valores: Seattle, Boston, Denver.

`=UniqueValues(Servers:Location)`

Outra aplicação dessa função é retornar uma lista de endereços de e-mail concatenados de uma coluna em uma tabela para usar com a API SendMail Apptio Script.
