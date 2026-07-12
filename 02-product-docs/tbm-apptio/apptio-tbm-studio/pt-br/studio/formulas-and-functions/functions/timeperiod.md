---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "TimePeriod função"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/timeperiod.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# TimePeriod função

Retorna o valor de uma métrica especificada no início de um período (por exemplo, mês, trimestre, ano) que é um número especificado de períodos antes ou depois do período atual. A unidade de tempo é determinada pela visualização selecionada ou por um sufixo de granularidade explícito.

## Sintaxe

`TimePeriod(metric, offset)`

## Parâmetros

- **métrica** : a coluna métrica da qual recuperar valores para uma unidade de tempo anterior ou futura. Deve se referir a uma coluna na mesma tabela. Necessário
- **desvio** : Um desvio numérico combinado com um sufixo de unidade de tempo opcional (por exemplo, “m”, “q”, “h”, “y”) indicando quantos períodos devem ser deslocados. Os valores negativos se deslocam para trás; os valores positivos se deslocam para frente. Se nenhum sufixo for fornecido, o padrão da unidade é meses. Necessário

## Comportamento

- Retorna o valor da métrica no início do período resolvido no deslocamento especificado.
- A unidade de tempo é determinada pelo sufixo ('m' para mês, 'q' para trimestre, 'h' para semestre, 'y' para ano) ou, se omitido, o padrão é mês.

## Exemplos

- `TimePeriod(Sales, -6)`: Retorna o valor de um {Sales} e no início do período há 6 meses. A unidade é mensal por padrão.
- `TimePeriod(Sales, -3q)`: Retorna o valor de um {Sales} e no início do período de três trimestres atrás.
- `TimePeriod(Sales, -1y)`: Retorna o valor de um {Sales} o no início do período há um ano.

Observação: Os sufixos de granularidade válidos incluem "m" (mês), "q" (trimestre), "h" (semestre) e "y" (ano).

## Tipo de retorno

Número
