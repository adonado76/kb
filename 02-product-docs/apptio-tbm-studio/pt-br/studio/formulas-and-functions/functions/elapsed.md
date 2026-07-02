---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Função decorrida"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/elapsed.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Função decorrida

Calcula o tempo decorrido entre duas datas em segundos, contabilizando opcionalmente os períodos excluídos e oferecendo suporte à saída formatada.

## Sintaxe

`Elapsed(startDate, endDate [, "format" [, exclusionTable [, startCol,
endCol]]])`

## Parâmetros

- **startDate** : Uma expressão que avalia a data e a hora de início. Deve estar em um formato de data e hora reconhecido (por exemplo, 'MM/DD/AAAA HH:MM'). Observação: esse parâmetro aceita uma expressão, o que significa que você pode fornecer um valor literal, uma referência de coluna ou o resultado de outra função. Necessário
- **endDate** : Uma expressão que é avaliada como a data e a hora de término. Deve estar em um formato de data e hora reconhecido. Observação: esse parâmetro aceita uma expressão, o que significa que você pode fornecer um valor literal, uma referência de coluna ou o resultado de outra função. Necessário
- **formato** : Opcional. Se a cadeia de caracteres "format" for fornecida, a função retornará o tempo decorrido dividido em Anos, Dias, Horas, Minutos e Segundos em vez do total de segundos. Deve ser exatamente "format" (diferencia maiúsculas de minúsculas). Opcional (padrão: retorna o total de segundos decorridos)
- **exclusionTable** : Opcional. Uma referência de tabela que lista os períodos de tempo a serem excluídos do cálculo do tempo decorrido. Opcional (padrão: nenhuma exclusão aplicada)
- **startCol** : opcional. O nome da coluna na tabela de exclusão que representa o início do período excluído. O padrão é "De". Opcional (padrão: coluna "From")
- **endCol** : opcional. O nome da coluna na tabela de exclusão que representa o fim do período excluído. O padrão é "To". Opcional (padrão: coluna "To")

## Comportamento

- Calcula a diferença entre startDate e endDate em segundos.
- Se 'format' for fornecido como um literal de cadeia de caracteres, retorna a saída dividida em Years, Days, Hours, Minutes e Seconds.
- Oferece suporte à exclusão de períodos de tempo usando uma tabela de exclusão e colunas especificadas.
- Se não forem fornecidos startCol e endCol, o padrão será as colunas "From" e "To" na tabela de exclusão.

## Tipo de retorno

Número

## Tabela de exclusões

Para calcular períodos de tempo que excluem horas não trabalhadas, feriados, etc, a função se baseia em uma tabela de exclusões definida como um conjunto de dados em seu projeto Apptio. Um exemplo de tabela de exclusões é mostrado abaixo. A coluna Description é ignorada pela função.

| De | Para | Descrição |
| --- | --- | --- |
| 00:00 Sábado | 00:00 Segunda-feira | Exclui finais de semana |
| 16:00 | 08:00 | O horário de trabalho padrão é das 8:00 A.M. às 4:00 P.M. |
| 1/1/2009 00:00 | 1/2/2009 00:00 | Dia de Ano Novo |
| 18/01/2009 00:00 | 19/01/2009 00:00 | Dia do MLK |
| 15/02/2009 00:00 | 16/02/2009 00:00 | Dia do Presidente |
| 4/6/2009 00:00 | 5/6/2009 00:00 | 4 de julho |
| 25/12/2009 00:00 | 26/12/2009 00:00 | Natal |

## Exemplos

- `Elapsed("04/23/2010 08:00", "04/23/2010 10:00")`

  Retorna o número de segundos entre 8:00 AM e 10:00 AM em 23 de abril de 2010.
- `Elapsed(DateSubmitted, DateFirstResponse)`

  Calcula o tempo decorrido entre a data de envio e a data da primeira resposta.
- `Elapsed("04/23/2010 18:00", "04/26/2010 11:00", Exclusions, From,
  To)`

  Calcula o tempo decorrido excluindo os períodos definidos na tabela "Exclusões".
- `Elapsed("04/23/2010 18:00", "04/26/2010 11:00", "format")`

  Retorna o tempo decorrido formatado como Anos, Dias, Horas, Minutos e Segundos.
- `Elapsed("04/23/2010 18:00", "04/26/2010 11:00", "format", Exclusions, From,
  To)`

  Retorna o tempo decorrido formatado, excluindo os períodos definidos na tabela "Exclusões".

Nota:

- Todos os valores de data e hora devem ser fornecidos em formatos reconhecidos.
- O argumento 'format' deve ser inserido exatamente como a string "format".
- Ao especificar uma tabela de exclusão, as colunas inicial e final podem ser personalizadas opcionalmente.
- Se a tabela de exclusão for usada, mas não forem especificados startCol e endCol, "From" e "To" serão assumidos.
