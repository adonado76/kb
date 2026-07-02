---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Função de linha"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/row.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Função de linha

Retorna o índice da linha atual na tabela, começando com zero para a primeira linha.

## Sintaxe

```
Row()
```

## Parâmetros

Nenhum

## Comportamento

Avalia o índice baseado em zero da linha atual na tabela. A primeira linha é numerada como 0, a segunda como 1 e assim por diante.

## Tipo de retorno

Número

**Comentários**

Essa função pode fazer referência apenas à tabela atual, não a tabelas externas.

Observe que **não** é recomendável usar a função Row como parte de uma fórmula que gera uma coluna de chave primária em uma tabela. Se você carregar novos dados na tabela, as linhas e, portanto, as chaves primárias, poderão mudar e resultar em alocações imprecisas com base na chave.

## Exemplo

`=Row()`: Retorna 0 para a primeira linha, 1 para a segunda linha e assim por diante.
