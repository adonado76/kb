---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "PeriodsInHalf função"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/periodsinhalf.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# PeriodsInHalf função

**Aplica-se a** : TBM Studio e posterior

Retorna o número de períodos na primeira ou segunda metade do ano.

## Onde usar

Essa função pode ser usada em:

- Conjuntos de dados
- Colunas de fórmula em tabelas de relatórios
- Texto Dinâmico

## Sintaxe

`PeriodsInHalf(half)`

## Argumentos

*Metade*

O número do tempo, 1 ou 2 para o primeiro ou o segundo tempo.

## Tipo de retorno

Sequência

## Exemplo

Considerando um projeto de 13 períodos e um período definido como P10 FY2013, a função a seguir retorna os resultados mostrados abaixo.

| Função | Voltar |
| --- | --- |
| PeriodsInHalf(1) | 6 |
| PeriodsInHalf(2) | 7 |
