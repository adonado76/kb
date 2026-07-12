---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "GetTimeOffset função"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/gettimeoffset.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# GetTimeOffset função

**Aplica-se a** : TBM Studio v12.1 e posterior.

Use a função GetTimeOffset para determinar a defasagem do período atual em relação ao mês, trimestre, semestre ou ano inteiro atual. Por exemplo, se for abril de 2017 e você definir a função para determinar o deslocamento do final do trimestre (junho de 2017), ela retornará um valor de 2.

## Onde usar

Essa função pode ser usada em:

- Conjuntos de dados (somente campos do tipo rótulo)
- Métricas calculadas e relatórios com colunas de métricas
- Colunas de fórmula em tabelas de relatórios
- Texto Dinâmico

## Sintaxe

`=GetTimeOffset("granularity","start/end","span",[period])`

## Argumentos

*granularidade*

Especifica o bloco de tempo usado para expressar o deslocamento.

Valores: mês, trimestre, metade, ano

O valor deve ser igual ou menor que o valor inserido para o argumento "span".

*início/fim*

Especifica a partir de quando o deslocamento deve ser calculado.

Valores: start, end, calendarStart, calendarEnd

Se o segundo argumento for "start" ou "end", os argumentos de granularidade e abrangência serão baseados em "ano fiscal", não em "ano civil" Se o segundo argumento for "calendarStart,", o cálculo será feito a partir do primeiro mês do ano civil atual (sempre janeiro). Se o segundo argumento for "calendarEnd",, o cálculo será feito a partir do último mês do calendário do ano (sempre dezembro). O padrão usará o formato especificado pela localidade.

*span*

Especifica o bloco de tempo dentro do qual o deslocamento é calculado.

Valores: mês, trimestre, metade, ano, todo o tempo

Alltime refere-se ao período de tempo abrangido pelas datas de início e término do projeto. As datas são definidas na caixa de diálogo **Configurações de tempo do projeto** e refletidas no seletor de datas.

*período*

Esse é um argumento opcional. Ele fornece uma data alternativa à data atual padrão usada no cálculo. A data deve ser especificada no seguinte formato: Jan:FY2016. Ele suporta apenas períodos fiscais.

## Possíveis saídas em um calendário de 12 períodos

- GetTimeOffset(Month,Start/End,Quarter ) dá 0, 1 ou 2.
- GetTimeOffset(Month,Start/End,Half ) dá 0, 1, 2, 3, 4 ou 5.
- GetTimeOffset(Month,Start/End,Year ) fornece de 0 a 11.

## Possíveis saídas em um calendário de 13 períodos

- GetTimeOffset(Month,Start/End,Quarter ) dá 0, 1, 2 ou 3.
- GetTimeOffset(Month,Start/End,Half ) dá 0, 1, 2, 3, 4, 5 ou 6.
- GetTimeOffset(Month,Start/End,Year ) fornece de 0 a 12.

## Possíveis saídas em qualquer calendário

- GetTimeOffset(Month,CalendarStart/CalendarEnd,Quarter ) dá 0, 1 ou 2.
- GetTimeOffset(Month,CalendarStart/CalendarEnd,Half ) dá 0, 1, 2, 3, 4 ou 5.
- GetTimeOffset(Month,CalendarStart/CalendarEnd,Year ) fornece de 0 a 11.

## Exemplos

- GetTimeOffset("Quarter","End","Year" )=0 em qualquer mês do último trimestre do ano, 1 no penúltimo trimestre.
- GetTimeOffset("Month","End","Quarter" )=0 no último mês do trimestre, 1 no penúltimo mês.
