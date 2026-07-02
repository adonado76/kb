---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Função de dias"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/days.html"
images:
  - "resources/images/studio_images/studioimages/studio/stu126.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Função de dias

Converte uma data especificada em um valor numérico que representa o número de dias desde 1º de janeiro de 1970.

Converte uma data especificada em um valor decimal, que pode ser usado em fórmulas. O valor decimal é o número de dias desde 1º de janeiro de 1970.

## Sintaxe

`Days(date_expression [, from_format])`

## Parâmetros

*expressão de data*

Uma expressão que é avaliada como uma data a ser convertida em um valor numérico. A expressão deve representar apenas uma data e não pode incluir um componente de tempo. Observação: esse parâmetro aceita uma expressão, o que significa que você pode fornecer um valor literal, uma referência de coluna ou o resultado de outra função. Necessário

## Comportamento

- Converte a data fornecida para o número de dias desde 1º de janeiro de 1970.
- Se from\_format for especificado, a função o utilizará para analisar a cadeia de datas de entrada.
- Se a expressão date\_expression incluir um componente de tempo, ele deverá ser ignorado ou truncado.

## Tipo de retorno

Número

## Exemplo

O exemplo a seguir calcula a duração do projeto em dias e a multiplica pelo custo diário do projeto.

`=(Days(ProjectEnd)-Days(ProjectStart))*ProjectCostPerDay`

Observação: Somente valores de data (sem hora) são suportados. Se from\_format for omitido e a expressão date\_expression for uma cadeia de caracteres, o sistema tentará analisar com base nas configurações padrão de localidade.

## Conversão de dias em um carimbo de data/hora do UNIX

Um registro de data e hora do UNIX é o número de segundos decorridos desde 1º de janeiro de 1970. Esse número pode ser útil se você quiser fazer cálculos com datas. Você pode converter o resultado da função Days em um carimbo de data/hora do UNIX usando a seguinte fórmula:

`=Days(date_expression)*24*60*60`

Isso pega o resultado da função Days e o multiplica pelo número de segundos em um dia: 24 horas x 60 minutos x 60 segundos.

Por exemplo, você poderia converter as datas mostradas na tabela abaixo:

![imagem](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu126.png)

A fórmula para a coluna Days Function é: =Days(Date)

A fórmula da coluna Carimbo de data/hora do UNIX é: =(Days Function)\*24\*60\*60

Consulte também:

- [CurrentDate](currentdate.html "Retorna a data de início do período de tempo selecionado no momento, se o tempo estiver ativado. Caso contrário, retorna o Eon 2000.")
- [Horas](hours.html "Converte um valor de data no número de horas desde 1º de janeiro de 1970, como um valor numérico.")
- [Minutos](minutes.html "Converte um valor de data no número de minutos desde 1º de janeiro de 1970, como um valor numérico.")
- [Meses](months.html "Converte uma data especificada em um valor decimal que representa o número de períodos desde 1º de janeiro de 1970. Útil para cálculos baseados em tempo, como determinação de durações ou custos proporcionais.")
