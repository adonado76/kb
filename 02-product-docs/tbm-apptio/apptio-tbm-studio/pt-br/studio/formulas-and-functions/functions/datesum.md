---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "DateSum função"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/datesum.html"
images:
  - "resources/images/studio_images/datesum-1.png"
  - "resources/images/studio_images/datesum-2.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# DateSum função

Soma os valores em todas as colunas cujos nomes estão em conformidade com os formatos de data reconhecidos, ignorando as colunas que não são de data.

A função DateSum é útil se você tiver tabelas com colunas que contenham dados numéricos em colunas de data, bem como em outras colunas. A função soma apenas as colunas com cabeçalhos de data.

## Sintaxe

`DateSum()`

## Comportamento

- Examina as colunas da tabela atual.
- Identifica colunas cujos nomes correspondem aos formatos de data padrão do aplicativo (como "Jan 2025", "02/2025", etc.).
- Soma os valores numéricos em todas as colunas de data identificadas.
- Ignora colunas que não correspondem a um formato de data.

## Parâmetros

Não há argumentos para essa função.

## Tipo de retorno

Número

## Exemplo

Soma todas as colunas cujos cabeçalhos são datas, ignorando as colunas que não são de datas.

A tabela abaixo mostra um exemplo simples da função DateSum. A função adiciona a 2nd,3rd e a 5ª coluna, que são colunas com data como cabeçalho, mas ignora a 1st,4th e a 5ª coluna. E a diferença entre Datesum e Total sum pode ser vista no exemplo abaixo

![exemplo de soma de datas](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/datesum-1.png)

Exemplo de captura de tela com sintaxe

![exemplo de dame sum](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/datesum-2.png)

Observação: essa função é útil para tabelas que combinam colunas regulares com colunas que representam períodos de tempo. Os formatos de data reconhecidos são determinados pela localidade e pela configuração do aplicativo. Essa função não recebe nenhum argumento.
