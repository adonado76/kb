---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Função de minutos"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/minutes.html"
images:
  - "resources/images/studio_images/studioimages/studio/aug120.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Função de minutos

Converte um valor de data no número de minutos desde 1º de janeiro de 1970, como um valor numérico.

## Sintaxe

`Minutes(date_expression, date_format)`

## Parâmetros

- *date\_expression* : A data a ser convertida. O formato deve ser um formato de data compatível. Observação: esse parâmetro aceita uma expressão, o que significa que você pode fornecer um valor literal, uma referência de coluna ou o resultado de outra função. Necessário
- *date\_format* : O formato da cadeia de caracteres de data. Necessário somente se a expressão date\_expression não estiver em um formato padrão suportado. OptionalAn expressão que avalia uma data a ser convertida em um valor duplo. O formato é MM/DD/AAAA HH:MM ou qualquer outro formato de data padrão suportado pelo aplicativo.

## Comportamento

- Recebe uma entrada de data e a converte em um valor numérico que representa os minutos desde a época (1º de janeiro de 1970).
- Se nenhum date\_format for fornecido, o aplicativo presumirá que a entrada está em um formato padrão compatível.
- O resultado é útil para calcular diferenças de tempo, durações ou realizar aritmética baseada em tempo.

## Tipo de retorno

Número

## Exemplo

Suponha que você queira calcular a duração das chamadas de suporte. Você tem um conjunto de dados com duas colunas: SupportTicket\_Start e SupportTicket\_End. Os dados nas colunas estão no formato MMDDYYYY HH:MM. Você define uma terceira coluna na tabela para calcular a duração de cada chamada. A fórmula para a terceira coluna é:

`=(Minutes({SupportTicket_End}))-(Minutes({SupportTicket_Start}))`

O resultado é mostrado abaixo:

![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/aug120.png)

Nota:

- Se a data de entrada estiver em um formato não padrão, use o parâmetro date\_format para especificar o formato correto.
- Consulte a função DateFormat para conhecer as regras de formatação.
- Os formatos de data comuns incluem MM/DD/AAAA, AAAA-MM-DD e MM/DD/AAAA HH:MM.
