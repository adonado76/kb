---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Adicionar uma coluna baseada em calendário a uma tabela"
breadcrumb: []
source_path: "studio/reports/tables/add-calendar-based-column.html"
images:
  - "resources/images/studio_images/studioimages/reports/rep203.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Adicionar uma coluna baseada em calendário a uma tabela

**Aplica-se a** : TBM Studio 12.0 e posterior

As tabelas geralmente incluem dados numéricos, como unidades e custo. Elas são exibidas para o mês/período selecionado no momento. Se quiser ver os valores de um período de tempo maior que um mês ou período, você pode adicionar uma variedade de colunas baseadas em calendário. Adicione itens de calendário usando os itens de menu sob o ícone **Dates** na guia **Formulas (Fórmulas** ). Vários exemplos de colunas baseadas em calendário são mostrados na imagem a seguir. Quando você adiciona uma coluna baseada em calendário, o nome padrão da coluna é a abreviação mais o nome da coluna selecionada.

![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep203.png)

## Adicionar uma coluna baseada em calendário

1. Selecione uma coluna de valor na tabela que servirá de base para a coluna de calendário.
2. Clique na guia **Fórmulas**.
3. Abra o menu **Dates (Datas** ) e selecione a coluna **Calendar (Calendário** ).

## Tipos de colunas

Os tipos de colunas são descritos a seguir.

- **Valor anualizado (ANN)** - Calcula o valor mensal médio até a data para uma métrica e, em seguida, multiplica esse valor por 12 para projetar o valor anual total para o ano fiscal. Essa função é útil para projetar valores reais, como custo e unidades.
- **Ano fiscal (FY)** - Soma o valor de uma métrica especificada na mesma tabela para todo o ano fiscal. Se nenhum ano for especificado, a função será avaliada para o ano atual. Essa função retorna o total do ano inteiro, independentemente do período selecionado.
- **Trimestre fiscal (FQ)** - Soma o valor de uma métrica especificada na mesma tabela para todo o trimestre fiscal. Se nenhum trimestre for especificado, a função será avaliada para o trimestre atual. Essa função retorna o total do trimestre inteiro, independentemente do período selecionado no momento.
- **Year to Date (YTD)** - Soma os valores até o mês selecionado, inclusive, no ano atual.
- **Trimestre até a data (QTD)** - Soma os valores até o mês selecionado, inclusive, no trimestre atual.
- **Último ano fiscal (LFY)** - Mostra o valor do ano anterior. É útil para comparar mudanças de valores ano a ano.
- **Último trimestre fiscal (LFQ)** - Soma os valores do trimestre fiscal anterior.
- **Últimos 12 meses (LTM)** - Mostra o valor dos últimos 12 meses (não incluindo o mês atualmente selecionado) sem levar em conta os calendários fiscais.
- **Último mês (LM)** - Mostra o valor do mês anterior.
- **Este período do ano passado (LY)** - Mostra o valor do mesmo período do ano passado. Útil para comparar mudanças de valor ano a ano.
- **Sparkline Trend** - Mostra os valores dos últimos seis meses em uma pequena linha de tendência.
