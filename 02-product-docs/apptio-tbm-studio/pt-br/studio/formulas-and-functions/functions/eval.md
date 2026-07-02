---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Função de avaliação"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/eval.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Função de avaliação

**Aplica-se a** : TBM Studio 12.0 e posterior

Pega uma cadeia de caracteres que se parece com uma expressão e a avalia como se fosse uma expressão.

## Onde usar

Essa função pode ser usada em:

- Colunas de fórmula em tabelas de relatórios
- Texto dinâmico

## Onde NÃO usar:

- Transformações - use a função [DynamicColumn](dynamic-column.htm "(Abre em uma nova guia ou janela)") em vez disso.

## Sintaxe

`Eval(string)`

## Argumentos

*sequência*

Uma cadeia de caracteres que se parece com uma expressão.

## Exemplo

O exemplo a seguir retorna 12.

`Eval("=24/2")`

Para maximizar as melhorias de desempenho de cálculo do novo recurso "cálculos de precisão", a funcionalidade da função Eval() é substituída por DynamicColumn( ) ou outras alterações de código. Os clientes que ainda têm Eval() na configuração do projeto podem fazer as alterações necessárias usando o documento [de código de substituição OOTB Eval()](../updated-eval-formulas.htm "(Abre em uma nova guia ou janela)"), que contém informações de todos os relatórios e alterações de métricas.

Observação: Se você tiver modificado os relatórios OOTB, o Eval() não será removido dos relatórios em modelos anteriores (por exemplo, v104, v105, v106. v107 ). Veja também, [DynamicColumn](dynamic-column.htm "(Abre em uma nova guia ou janela)")
