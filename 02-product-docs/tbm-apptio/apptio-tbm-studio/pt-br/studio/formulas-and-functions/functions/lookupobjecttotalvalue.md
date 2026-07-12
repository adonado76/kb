---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "LookupObjectTotalValue função"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/lookupobjecttotalvalue.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# LookupObjectTotalValue função

**Aplica-se a** : TBM Studio 12.0 e posterior

Encontra o valor total de um objeto. Se o parâmetro métrico não for usado, a função usará o modelo atual. Se o parâmetro driver for fornecido, ele procurará o valor total do driver especificado.

## Onde usar

Essa função pode ser usada em:

- Métricas calculadas e relatórios com colunas de métricas
- Métricas de modelo
- Colunas de fórmula em tabelas de relatórios
- Texto Dinâmico
- Fórmulas de fontes de alocação

## Sintaxe

*LookupObjectTotalValue(object [,métrico [, motorista]])*

## Argumentos

*objeto*

O nome do objeto de destino. O objeto não deve estar acima do nível atual na hierarquia do modelo em que a função está sendo usada.

*métrica*

Se especificado, retorna o valor da métrica conforme ela se aplica ao objeto.

Se não for especificado, retorna o valor do objeto no modelo atual.

*motorista*

Se especificado, retorna o valor do driver. O driver deve ser um driver associado ao objeto.

## Tipo de retorno

Sequência

## Exemplos

Suponha que você tenha o modelo de custo mostrado na imagem a seguir. O objeto C tem dois drivers: Objeto A e Objeto B.

![Exemplos](../../../resources/images/studio_images/studioimages/visio%20diagrams/lookupobjecttotalvalue.png)

Você deseja poder usar o valor do Objeto A em outra parte do modelo. Você usaria a seguinte função:

```
=LookupObjectTotalValue(Object
      A,Cost)
```

A função retornaria o valor $7M.

Agora, suponha que você queira encontrar o valor do objeto C que é contribuído pelo driver do objeto A. Você usaria a seguinte função:

```
=LookupObjectTotalValue(Object C,Cost,Object
      A)
```

Na função, Object A é o nome do driver proveniente do Object A.

Consulte também:

- [Pesquisa de IP](iplookup.htm "(Abre em uma nova guia ou janela)")
- [Lookup e Lookup\_Wild](lookupandlookup_wild.htm "(Abre em uma nova guia ou janela)")
- [LookupEx](lookupexandlookupex_wild.htm "(Abre em uma nova guia ou janela)")
- [LookupFromPath](lookupfrompath.htm "(Abre em uma nova guia ou janela)")
- [LookupMetric](lookupmetric.htm "(Abre em uma nova guia ou janela)")
- [LookupObjectTotalAllocated](lookupobjecttotalallocated.htm "(Abre em uma nova guia ou janela)")
- [LookupObjectUnitAllocated](lookupobjectunitallocated.htm "(Abre em uma nova guia ou janela)")
- [LookupObjectUnitValue](lookupobjectunitvalue.htm "(Abre em uma nova guia ou janela)")
