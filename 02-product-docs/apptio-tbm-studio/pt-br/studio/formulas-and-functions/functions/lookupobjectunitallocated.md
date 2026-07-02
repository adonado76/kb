---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "LookupObjectUnitAllocated função"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/lookupobjectunitallocated.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# LookupObjectUnitAllocated função

**Aplica-se a** : TBM Studio 12.0 e posterior

Procura o valor alocado entre dois objetos para uma métrica específica em uma base de unidade por unidade.

## Onde usar

Essa função pode ser usada em:

- Relatórios com colunas de métricas modeladas
- Colunas de fórmula em tabelas de relatórios
- Texto Dinâmico

## Sintaxe

```
=LookupObjectUnitAllocated(sourceObject,destObject,metric,
columnInLocalTable,columnInSourceObjectTable)
```

## Argumentos

*sourceObject*

O objeto que fornece o valor.

*destObject*

O objeto que recebe o valor.

*métrica*

O nome da métrica a ser pesquisada.

*columnInLocalTable*

O nome da coluna na tabela de destino que identifica as unidades.

*columnInSourceObjectTable*

A coluna na tabela de origem que identifica as unidades.

## Tipo de retorno

Sequência

**Observações** :

O aplicativo Apptio Billing usa essa função em conjunto com a função LookupObjectUnitValue para determinar a quantidade total de um serviço que está sendo consumido em um modelo de estilo de preço.

Se você estiver usando essa função com!NEWCOLUMN ao editar um caminho de dados, você geralmente precisará especificar a palavra-chave [ canSum ] no!NEWCOLUMN porque não pode ser recalculado com parâmetros de agrupamento diferentes.

## Exemplo

O exemplo de caminho de dados a seguir determina o custo alocado do objeto Support para o objeto Services. O valor é retirado das unidades na coluna Support.ID e alocado para as unidades na coluna Services.ID.

```
!NEWCOLUMN[alloc=LookupObjectUnitAllocated
(Support,Services,Cost,ID,ID)][canSum]
```

Consulte também:

- [Pesquisa de IP](iplookup.htm "(Abre em uma nova guia ou janela)")
- [Lookup e Lookup\_Wild](lookupandlookup_wild.htm "(Abre em uma nova guia ou janela)")
- [LookupEx](lookupexandlookupex_wild.htm "(Abre em uma nova guia ou janela)")
- [LookupFromPath](lookupfrompath.htm "(Abre em uma nova guia ou janela)")
- [LookupMetric](lookupmetric.htm "(Abre em uma nova guia ou janela)")
- [LookupObjectTotalValue](lookupobjecttotalvalue.htm "(Abre em uma nova guia ou janela)")
- [LookupObjectTotalAllocated](lookupobjecttotalallocated.htm "(Abre em uma nova guia ou janela)")
- [LookupObjectUnitValue](lookupobjectunitvalue.htm "(Abre em uma nova guia ou janela)")
