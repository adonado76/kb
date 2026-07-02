---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "PeriodsInQuarter função"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/periodsinquarter.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# PeriodsInQuarter função

**Aplica-se a** : TBM Studio e posterior

Retorna o número de períodos no primeiro, segundo, terceiro ou quarto trimestre.

## Onde usar

Essa função pode ser usada em:

- Conjuntos de dados
- Colunas de fórmula em tabelas de relatórios
- Texto Dinâmico

## Sintaxe

`PeriodsInQuarter(quarter)`

## Argumentos

*trimestre*

O número do trimestre, 1, 2, 3 ou 4.

## Tipo de retorno

Sequência

## Exemplo

Dado um projeto de 13 períodos com o terceiro trimestre tendo quatro períodos e o seletor de calendário definido como P10 FY2013, a função a seguir retorna os resultados mostrados abaixo:

| Função | Voltar |
| --- | --- |
| PeriodsInQuarter(1) | 3 |
| PeriodsInQuarter(2) | 3 |
| PeriodsInQuarter(3) | 4 |
| PeriodsInQuarter(4) | 3 |
