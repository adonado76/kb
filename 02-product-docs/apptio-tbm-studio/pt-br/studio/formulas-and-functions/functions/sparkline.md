---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Função Sparkline"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/sparkline.html"
images:
  - "resources/images/studio_images/studioimages/studio/aug499.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Função Sparkline

**Aplica-se a** : TBM Studio 12.0 e posterior

A função Sparkline cria pequenos gráficos de tendências nas células das tabelas dos relatórios.

Às vezes, é útil exibir pequenos gráficos de tendências para as linhas em uma tabela. A função Sparkline é usada para essa finalidade. Um exemplo é mostrado abaixo:

![Função Sparkline](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/aug499.png)

## Onde usar

Essa função pode ser usada em:

- Colunas de fórmula em tabelas de relatórios
- Texto Dinâmico
- Métricas calculadas e relatórios com colunas de métricas

## Sintaxe

`Sparkline(past,future,column)`

## Argumentos

*passado*

O número de períodos para a tendência de retrocesso no tempo. Esse é um número positivo.

*futuro*

O número de períodos para a tendência de avanço no tempo. Esse é um número positivo.

*coluna*

A coluna de tendência.

## Tipo de retorno

Gráfico

## Exemplo

Os sparklines da Figura A acima foram criados usando essa fórmula: Sparkline( 4,4,Cost ).

Veja também: [Como adicionar sparklines a uma tabela](../../reports/tables/add-sparkline-column-to-tables.htm "(Abre em uma nova guia ou janela)").
