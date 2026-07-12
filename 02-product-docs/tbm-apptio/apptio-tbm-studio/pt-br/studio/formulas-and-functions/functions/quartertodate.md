---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "QuarterToDate função"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/quartertodate.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# QuarterToDate função

Retorna o valor acumulado de uma métrica especificada desde o início do trimestre fiscal atual até o período atual, inclusive.

O trimestre atual é o trimestre fiscal, conforme definido na caixa de diálogo **Configurar períodos de tempo**, independentemente da seleção da data atual no seletor de datas. O número de trimestres somados será 1, 2, 3 ou 4, dependendo do trimestre atual.

## Sintaxe

`QuarterToDate(metric)`

## Parâmetros

*métrica* : a coluna de métrica cujos valores serão somados desde o início do trimestre atual até o período atual. Deve se referir a uma coluna na mesma tabela. Necessário

## Comportamento

- Soma os valores da métrica especificada desde o início do trimestre fiscal atual até o período atualmente selecionado.
- A estrutura do trimestre fiscal é definida na configuração de Períodos de tempo, e não com base no seletor de datas do calendário.

## Tipo de retorno

Número

## Exemplo

O exemplo a seguir retorna a soma da métrica {Cost} desde o início do trimestre atual até o período atual.

`=QuarterToDate(Cost)`
