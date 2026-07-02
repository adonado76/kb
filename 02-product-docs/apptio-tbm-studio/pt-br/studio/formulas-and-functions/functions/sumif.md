---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "SumIf função"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/sumif.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# SumIf função

Retorna a soma dos valores em uma coluna, incluindo apenas as linhas que correspondem aos critérios especificados. Útil para calcular totais agrupados com base na lógica condicional.

## Sintaxe

`SumIf(key_column, criteria, sum_range)`

## Parâmetros

*key\_column* : A coluna usada para atribuir valores para a soma. Ele agrupa os dados e determina como os resultados são estruturados. Necessário

*critérios* : O valor ou a coluna usada para filtrar as linhas para a soma. Determina quais linhas do intervalo sum\_range serão incluídas. Observação: esse parâmetro aceita uma expressão, o que significa que você pode fornecer um valor literal, uma referência de coluna ou o resultado de outra função. Necessário

*sum\_range* : A coluna que contém os valores a serem somados. Observação: esse parâmetro aceita uma expressão, o que significa que você pode fornecer um valor literal, uma referência de coluna ou o resultado de outra função. Necessário

## Tipo de retorno

Número

**Observações** :

Ao usar a função SumIf em uma transformação filtrada, ela incluirá valores filtrados em sua soma. A solução alternativa é filtrar sua tabela, criar uma transformação a partir dela e, em seguida, criar a função SumIf na nova tabela.

## Exemplos

SumIf(Region, Region, Weight): Soma os valores de Weight de cada região e os exibe em uma terceira coluna.

Suponha que você tenha a seguinte tabela:

| Região | Peso |
| --- | --- |
| Américas | 22 |
| Américas | 20 |
| Europa | 30 |
| Américas | 40 |
| Austrália | 50 |
| Austrália | 60 |

Você deseja somar os valores de cada uma das regiões e exibi-los em uma terceira coluna, conforme mostrado abaixo:

Para isso, você deve adicionar a coluna Sum (Soma) à transformação da tabela e inserir a seguinte equação no campo Value (Valor):

SumIf(Region, Região, peso)

Inserir "Region" como argumento de critério informa ao aplicativo para avaliar todas as entradas na coluna Region.

| Região | Peso | Soma |
| --- | --- | --- |
| Américas | 22 | 70 |
| Américas | 20 | 70 |
| Europa | 30 | 30 |
| Américas | 40 | 70 |
| Austrália | 50 | 110 |
| Austrália | 60 | 110 |

`SumIf(Region, "Americas", Weight)`

Adiciona apenas os valores para as Américas.

Agora, suponha que você queira adicionar apenas os valores das Américas. Você usaria a seguinte equação:

SumIf(Region, “Américas”, Peso)

Resultado:

| Região | Peso | Soma |
| --- | --- | --- |
| Américas | 22 | 70 |
| Américas | 20 | 70 |
| Europa | 30 | 70 |
| Américas | 40 | 70 |
| Austrália | 50 | 70 |
| Austrália | 60 | 70 |
