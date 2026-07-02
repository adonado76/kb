---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "RowCount função"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/rowcount.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# RowCount função

Retorna uma contagem do número total de linhas em uma tabela especificada. Se nenhuma tabela for especificada, ele retornará o número de linhas no contexto da tabela atual.

## Sintaxe

`RowCount([table])`

## Parâmetros

*table* : O nome da tabela a partir da qual as linhas serão contadas. Se omitido, conta as linhas no contexto da tabela atual. Você não pode especificar explicitamente o nome da tabela atual. Opcional (padrão: tabela atual)

## Comportamento

- Conta todas as linhas da tabela especificada.
- Se nenhuma tabela for fornecida, o padrão será o contexto da tabela atual.
- O nome da tabela atual não pode ser usado explicitamente como um argumento.

## Tipo de retorno

Número

## Exemplo

No exemplo a seguir, se a tabela Servers tiver 180 linhas, a função retornará 180.: `=RowCount(Servers)`

`RowCount()`: Retorna o número de linhas no contexto da tabela atual.
