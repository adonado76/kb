---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "DateFormat função"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/dateformat.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# DateFormat função

Converte uma expressão de data em um formato de data especificado.

## Sintaxe

```
DateFormat(date_expression, format_string [, time_zone [, from_format]])
```

## Parâmetros

- *date\_expression* : O valor da data a ser formatado. Pode ser uma data ou uma cadeia de caracteres. Observação: esse parâmetro aceita uma expressão, o que significa que você pode fornecer um valor literal, uma referência de coluna ou o resultado de outra função. Necessário
- *format\_string* : Especifica o formato desejado da cadeia de caracteres de saída. Usa padrões de formatação de data padrão (por exemplo, 'aaaa-MM-dd'). Consulte a seção Referência de padrão abaixo para obter uma lista completa das letras de padrão disponíveis. Observação: esse parâmetro aceita uma expressão, o que significa que você pode fornecer um valor literal, uma referência de coluna ou o resultado de outra função. Necessário
- *time\_zone* : Especifica o fuso horário para exibir a data e a hora. Para incluir o fuso horário na saída, a format\_string deve incluir um 'z'. Opcional (padrão: GMT)
- *from\_format* : Especifica o formato atual da expressão date\_expression se ela for uma cadeia de caracteres. Usado para analisar corretamente a data antes da formatação. Usa as mesmas letras de padrão que format\_string - consulte a seção Referência de padrão abaixo. Observação: esse parâmetro aceita uma expressão, o que significa que você pode fornecer um valor literal, uma referência de coluna ou o resultado de outra função. Opcional (padrão: análise padrão dependente da localidade)

## Exemplos

Os exemplos a seguir pressupõem uma data de 12 de outubro de 2014 10:24:52 AM.

- Formata a data atual como "ano-mês-dia". `DateFormat(CurrentDate(),
  "yyyy-MM-dd")`
- Analisa o registro de data e hora ISO de entrada, muda para o horário do Pacífico e formata como 'Apr 29, 2025'.

  ```
  DateFormat("2025-04-29T08:00:00", "MMM dd, yyyy", "PST", "yyyy-MM-dd'T'HH:mm:ss")
  ```

Observação: Ao usar time\_zone, a format\_string deve incluir 'z' para mostrar de fato o fuso horário no resultado. Se from\_format for omitido e date\_expression for uma string, a análise poderá falhar se o formato não corresponder às suposições padrão do sistema.

## **Referência de padrão de data e hora**

Os formatos de data e hora são definidos usando cadeias de padrões. Nessas cadeias de caracteres, as letras sem aspas de 'A'-'Z' e 'a'-'z' servem como símbolos de padrão que representam partes da data ou da hora. Para incluir texto literal, você pode usar aspas simples ('); duas aspas simples consecutivas ('') representam uma aspa simples literal. Quaisquer outros caracteres são tratados como literais - eles são inseridos na saída formatada ou correspondem exatamente à análise. A tabela a seguir mostra as letras de padrão que podem ser usadas em format\_string e from\_format:

| Elemento de formato | Formato | Descrição | Exemplo |
| --- | --- | --- | --- |
| M | MMMMMMMMMMM | Mês | M: 6MM: 06MMM: JunMMMMM: Junho |
| D | DDDDDD | Dia do ano. O número de Ds determina o número de dígitos exibidos | D: 7 (7 de janeiro)DD: 07 (7 de janeiro)DDD: 007 (7 de janeiro) |
| d | ddd | Dia do mês (1 a 31) | d: 2dd: 02 |
| w | www | A semana do ano (1 a 52) | w: 9ww: 09 |
| W | W | Semana do mês em que a data ocorre (1 a 5) | 1 |
| E | E | Dia da semana | Seg |
| E | EEEE | Dia da semana (longo) | Segunda-feira |
| F | F | Dia da semana no mês (o número de vezes que o dia da semana ocorreu durante o mês) | 2 |
| y | aaaaah | Ano | 14yyyy: e 2014 |
| H | HHH | Hora em horário militar (0-23) | H: 4, 14HH: 04, 14 |
| h | hhh | Hora em am/pm (1-12) | h: 2hh: 02 |
| m | mmm | Minuto (0-59) | m: 3, 30mm: 03, 30 |
| s | sss | Segundo em minutos (0-59) | s: 3, 30ss: 03, 30 |
| S | SSSSSS | Milissegundo | S: 7SS: 07SSS: 007 |
| a |  | Exibir AM ou PM, conforme apropriado | MANHÃ |
| z | z | Fuso horário geral (formato curto) | GMT |
| z | zzzz | Fuso horário geral (formato longo) | Tempo Médio de Greenwich |
| Z | Z | RFC822 fuso horário (deslocamento do GMT) | 8 (para o horário do Pacífico) |
| p | ppp | Descrição do período curto | Tipos de calendário de período: P1Gregorian tipo de calendário: Mar |
| p | pppp | Descrição de longo prazo | Tipos de calendário de período: Período 1Gregorian tipo de calendário: Março |
| f | ffff | Período do ano fiscal | FY2014 |

## Tipo de retorno

Sequência
