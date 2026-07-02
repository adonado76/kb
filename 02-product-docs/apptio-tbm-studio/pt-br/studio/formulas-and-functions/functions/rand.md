---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Função Rand"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/rand.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Função Rand

Gera um número decimal aleatório entre 0.0 (inclusive) e 1.0 (exclusive).

## Sintaxe

```
Rand()
```

## Parâmetros

Nenhum

## Comportamento

Cada vez que a função é avaliada, ela produz um novo número pseudo-aleatório. Retorna um número de ponto flutuante maior ou igual a 0.0 e menor que 1.0.

## Tipo de retorno

Número

## Exemplo

`Rand()`

Alguns valores de retorno possíveis incluem:

- 0.354
- 0.515
- 0.034

`Rand() * 100`: Gera uma porcentagem aleatória entre 0 e 100.

Nota:

Como essa função retorna um resultado diferente a cada vez que é recalculada, os resultados podem variar entre as avaliações.
