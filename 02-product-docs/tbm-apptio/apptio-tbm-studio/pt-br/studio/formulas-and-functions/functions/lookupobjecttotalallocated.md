---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "LookupObjectTotalAllocated função"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/lookupobjecttotalallocated.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# LookupObjectTotalAllocated função

**Aplica-se a** : TBM Studio 12.0 e posterior

Encontra o valor por unidade alocado de um objeto de origem para um ou mais objetos de destino em um modelo. A função só funciona no contexto de um objeto.

Essa função se concentra no objeto de origem, não nos objetos de destino. A função extrai o valor da coluna **Assigned (Atribuído** ) na tabela **.Unassigned (Não atribuído** ).

## Onde usar

Essa função pode ser usada em:

- Métricas calculadas e relatórios com colunas de métricas
- Colunas de fórmula em tabelas de relatórios
- Texto Dinâmico
- Fórmulas de fontes de alocação

## Sintaxe

`LookupObjectTotalAllocated(metric)`

## Argumentos

*métrica*

O valor a ser recuperado. Normalmente, essa será uma métrica de modelo, como Custo.

## Tipo de retorno

Sequência

Consulte também:

- [Pesquisa de IP](iplookup.htm "(Abre em uma nova guia ou janela)")
- [Lookup e Lookup\_Wild](lookupandlookup_wild.htm "(Abre em uma nova guia ou janela)")
- [LookupEx](lookupexandlookupex_wild.htm "(Abre em uma nova guia ou janela)")
- [LookupFromPath](lookupfrompath.htm "(Abre em uma nova guia ou janela)")
- [LookupMetric](lookupmetric.htm "(Abre em uma nova guia ou janela)")
- [LookupObjectTotalValue](lookupobjecttotalvalue.htm "(Abre em uma nova guia ou janela)")
- [LookupObjectUnitAllocated](lookupobjectunitallocated.htm "(Abre em uma nova guia ou janela)")
- [LookupObjectUnitValue](lookupobjectunitvalue.htm "(Abre em uma nova guia ou janela)")
