---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "CapFirstLetter função"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/capfirstletter.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# CapFirstLetter função

Coloca a primeira letra de cada palavra no argumento da cadeia de caracteres em maiúscula e deixa todas as outras letras em minúsculas.

## Sintaxe

`CapFirstLetter(text)`

## Parâmetros

*texto* : Um valor de cadeia de caracteres ou uma expressão que é avaliada como uma cadeia de caracteres. Isso pode incluir texto estático, referências a colunas ou outras fórmulas que produzem strings. Opcional

## Comportamento

- Cada palavra na string de entrada terá seu primeiro caractere convertido em maiúsculas.
- Todos os outros caracteres de cada palavra serão convertidos em letras minúsculas.
- Normalmente, as palavras são separadas por espaços ou pontuação.

## Tipo de retorno

Sequência

## Exemplo

- `CapFirstLetter("hello world")`: Retorna "Hello World"
- `CapFirstLetter(User Name)`: Coloca a primeira letra de cada palavra no campo UserName em maiúscula.
- `CapFirstLetter("tHiS is a tEsT")`: Retorna "This Is A Test" (Este é um teste).

Observação: útil para formatar nomes, títulos ou outros campos de texto para que sigam as convenções de capitalização adequadas. Se a entrada já seguir a capitalização desejada, o resultado permanecerá inalterado.
