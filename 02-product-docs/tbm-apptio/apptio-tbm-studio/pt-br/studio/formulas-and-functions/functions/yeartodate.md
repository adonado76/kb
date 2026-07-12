---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "YearToDate função"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/yeartodate.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# YearToDate função

Retorna o valor cumulativo de uma métrica especificada desde o início do ano fiscal atual até o período atual, inclusive. Isso difere da função Annual, que sempre retorna o total do ano inteiro, independentemente do período atual.

YearToDate é diferente da função [Annual](annual.html "Retorna um valor para a métrica especificada ajustada para frente ou para trás por um número de anos, com base no tipo de calendário selecionado."), que retorna o total do ano inteiro, independentemente do período em que é visualizado.

O ano atual é o ano fiscal, conforme definido na caixa de diálogo **Configurar períodos de tempo**, independentemente da seleção da data atual no seletor de datas.

## Sintaxe

`YearToDate(metric)`

## Parâmetros

*métrica* : a coluna de métrica cujos valores serão somados desde o início do ano fiscal até o período atual. Deve se referir a uma coluna na mesma tabela. Necessário

## Comportamento

Soma os valores da métrica especificada desde o início do ano fiscal até o período atualmente selecionado. A estrutura do ano fiscal é definida na configuração de Períodos de tempo e não é afetada pelo seletor de datas.

## Tipo de retorno

Número

## Exemplo

O exemplo a seguir retorna a soma acumulada no ano da métrica {Cost}.

`=YearToDate(Cost)`
