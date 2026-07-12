---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Função de modificação"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/mod.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Função de modificação

Divide um número por outro e retorna o restante, preservando o sinal do dividendo (primeiro número).

## Sintaxe

`Mod(number, divisor)`

## Parâmetros

*número* : O número a ser dividido. Esse é o dividendo na operação de módulo. Observação: esse parâmetro aceita uma expressão, o que significa que você pode fornecer um valor literal, uma referência de coluna ou o resultado de outra função. Necessário

*divisor* : O número pelo qual o dividendo é dividido. Observação: esse parâmetro aceita uma expressão, o que significa que você pode fornecer um valor literal, uma referência de coluna ou o resultado de outra função. Necessário

## Comportamento

- Retorna o restante da divisão do primeiro número pelo segundo.
- O sinal do resultado sempre corresponde ao sinal do dividendo (o primeiro número), independentemente do sinal do divisor.
- Suporta valores decimais tanto no dividendo quanto no divisor.

## Tipo de retorno

Número

## Exemplos

O sinal do resultado sempre corresponde ao sinal do primeiro número, não ao sinal do divisor.

| Função | Resultado |
| --- | --- |
| =Mod(5,3) | 2 - 5 dividido por 3 é 1 com um resto de 2. |
| =Mod(4,2) | 0 - 4 dividido igualmente por 2. |
| =Mod(7,-3) | 1 - o sinal do resultado segue o dividendo (7). |
| =Mod(-7,3) | -1 - o sinal do resultado segue o dividendo (-7) |
| =Mod(-7,-3) | -1 - ambos os números são negativos; o resultado mantém o sinal de -7. |
| =Mod(7, 2.25 ) | 0.25 - 7 dividido por 2.25 é 3 com um resto de 0.25. |

Observação: Mod é frequentemente usado para percorrer valores, identificar números pares ou ímpares ou segmentar dados. O resultado de Mod tem o mesmo sinal que o primeiro argumento (o dividendo).
