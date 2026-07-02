---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Função de anualização"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/annualize.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Função de anualização

**Aplica-se a** : TBM Studio 12.0 e posterior

A função Annualize calcula o valor médio do período até a data para uma métrica e, em seguida, multiplica esse valor pelo número de períodos para projetar o valor anual total para o ano fiscal. Essa função é usada com mais frequência para projetar valores reais, como custo e unidades, em vez de valores de planejamento e previsão. Os últimos valores geralmente são entregues para o ano inteiro de uma só vez.

A função Annualize é diferente da [função Annual](annual.htm "(Abre em uma nova guia ou janela)"). A função Annual retorna o valor de uma métrica especificada na mesma tabela para um ano fiscal ou calendário especificado, somando os valores do ano inteiro.

## Onde usar

Essa função pode ser usada em:

- Métricas calculadas e relatórios com colunas de métricas
- Colunas de fórmula em tabelas de relatórios
- Texto Dinâmico

## Sintaxe

`Annualize(metric)`

## Argumentos

*métrica*

Uma métrica no projeto. A função retorna o valor anual total projetado da métrica para o ano fiscal com base no valor da métrica até o período atual.

## Tipo de retorno

Número

## Exemplo

Suponha que seu ano fiscal vai de julho a junho. Estamos em janeiro e você deseja projetar os custos para o restante do ano fiscal. Os custos totais até o momento são de US$ 2.400.000. Você deve inserir a seguinte função:

`=Annualize(Cost)`

A função executa os seguintes cálculos:

uS$ 2.400.00/6 períodos \* 12 períodos= US$ 48.000.000

uS$ 2.400.00/6 períodos \* 13 períodos= US$ 52.000.000

Consulte também:

- [Anual](annual.htm "(Abre em uma nova guia ou janela)")
- [PreviousMonth](previousmonth.htm "(Abre em uma nova guia ou janela)")
- [PreviousYear](previousyear.htm "(Abre em uma nova guia ou janela)")
- [TimePeriod](timeperiod.htm "(Abre em uma nova guia ou janela)")
- [YearToDate](yeartodate.htm "(Abre em uma nova guia ou janela)")
