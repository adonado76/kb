---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Função de trimestre"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/quarter.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Função de trimestre

Retorna o valor total de uma métrica especificada na mesma tabela para um trimestre especificado, somando os valores de todo o trimestre. Se nenhum trimestre for especificado, a função será avaliada para o trimestre atual. Essa função retorna o total de todo o trimestre, independentemente do mês em que ele é visualizado.

## Sintaxe

`Quarter(metric[,delta[,type]])`

## Parâmetros

- *métrica* : Uma métrica na mesma tabela. A função retorna a soma dessa métrica para todo o trimestre.
- *delta* : O número de trimestres a serem deslocados em relação ao trimestre atual. Use números negativos para olhar para trás (por exemplo, -2 para dois trimestres atrás). O padrão é 0 (trimestre atual). Opcional (padrão: 0)
- *type (tipo* ): Especifica se o trimestre é baseado no ano fiscal (`FY`) ou no ano civil (`CY`). O padrão é `FY`. Deve ser fornecido como um literal de cadeia de caracteres. Opcional (padrão: "FY")

## Comportamento

- Calcula o valor total da métrica especificada para o trimestre inteiro.
- Suporta os tipos de trimestre fiscal e de calendário, dependendo da configuração do conjunto de dados.
- O padrão é o trimestre fiscal atual se nenhum delta ou tipo for fornecido.
- Sempre retorna o valor do trimestre inteiro, independentemente do mês a partir do qual a função é avaliada.

## Tipo de retorno

Número

## Exemplo

O exemplo a seguir retorna o total de {cost} para o trimestre fiscal atual:

`=Quarter(Cost)`

O exemplo a seguir retorna o total de {cost} para o próximo trimestre fiscal:

`=Quarter(Cost,1)`

Retorna o total {Cost} de dois trimestres anteriores.

`Quarter(Cost, -2, "CY")`

Observação: Use o tipo FY para calendários fiscais (incluindo os tipos de 4-4-5 ou 13 períodos) e CY para estruturas de calendário gregoriano. Se não houver dados para o trimestre especificado, a função retornará 0 ou nulo, dependendo da integridade dos dados.
