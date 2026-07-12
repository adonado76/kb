---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Função de horas"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/hours.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Função de horas

Converte um valor de data no número de horas desde 1º de janeiro de 1970, como um valor numérico.

## Sintaxe

`Hours(date_expression, date_format)`

## Argumentos

- *date\_expression* : A data a ser convertida. O formato deve ser um formato de data compatível. Observação: esse parâmetro aceita uma expressão, o que significa que você pode fornecer um valor literal, uma referência de coluna ou o resultado de outra função. Obrigatório.
- *date\_format* : O formato da cadeia de caracteres de data. Necessário somente se a expressão date\_expression não estiver em um formato padrão suportado. Opcional

## Tipo de retorno

Número

## Exemplo

Suponha que você tenha a seguinte tabela:

| Fonte de ingressos | Data de envio |
| --- | --- |
| Pré-vendas | 2/2/2010 17:38 |
| CS | 10/03/2010 9:41 |
| Produtos | 9/3/2010 13:14 |

Você cria uma terceira coluna chamada Hours usando a seguinte função:

`=Hours(Date Submitted)`

O resultado é a tabela a seguir:

| Fonte de ingressos | Data de envio | Horas |
| --- | --- | --- |
| Pré-vendas | 2/2/2010 17:38 | 351425.633 |
| CS | 10/03/2010 9:41 | 352281.683 |
| Produtos | 9/3/2010 13:14 | 352261.233 |

`Hours("2/2/2010 17:38")`

Retorna o número de horas desde 1º de janeiro de 1970 para a data e a hora fornecidas.

Observação: se a data de entrada estiver em um formato não padrão, use o parâmetro date\_format para especificar o formato correto. Consulte a função DateFormat para conhecer as regras de formatação.

## Comportamento

- Recebe uma entrada de data e a converte em um valor numérico que representa as horas desde a época (1º de janeiro de 1970).
- Se nenhum date\_format for fornecido, o aplicativo presumirá que a entrada está em um formato padrão compatível.
- O resultado é útil para realizar aritmética ou comparações com outros valores baseados em tempo.
