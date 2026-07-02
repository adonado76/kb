---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "LookupContains função"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/lookupcontains.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# LookupContains função

**Aplica-se a** : TBM Studio 12.0 e posterior

Executa uma pesquisa de correspondência parcial em várias colunas. O principal uso é a limpeza de dados usando pesquisas um-para-muitos (fonte única, colunas de destino múltiplas) e pesquisas muitos-para-um (fonte múltipla, colunas de destino únicas).

Para uma discussão sobre essa função, consulte o blog [R12 Quick Guide: Lookup Contains](https://community.apptio.com/people/dmahan@apptio.com/blog/2017/02/04/r12-quick-guide-lookupcontains "(Abre em uma nova guia ou janela)"), de Douglas Mahan.

## Onde usar

Essa função pode ser usada em:

- Conjuntos de dados
- Colunas de fórmula em tabelas de relatórios (embora isso não seja recomendado devido a problemas de desempenho)
- Texto Dinâmico

## Sintaxe

Pesquisas de um para muitos:

`LookupContains(sourceColumn,TargetTable,[targetCol1,TargetCol2,...TargetColN],TargetValueColumnName,caseSensitivity={true/false},outputVariousOnMultipleMatches={true/false}))`

A função retornará o valor do TargetTable:TargetValueColumnName para a linha quando as seguintes condições forem verdadeiras:

1. A linha tem uma correspondência: o valor de pelo menos uma das colunas de destino está "contido" no valor da coluna de origem nessa linha (a distinção entre maiúsculas e minúsculas é determinada pelo último sinalizador opcional).
2. A linha tem o número máximo de correspondências possíveis.
3. A linha é exclusiva (existe apenas uma linha com o número máximo de colunas correspondentes).

Se apenas as duas primeiras condições forem verdadeiras e outputVariousOnMultipleMatches for verdadeiro, a função retornará " {Various} "; caso contrário, a função retornará null.

Pesquisas de muitos para um:

`LookupContains([sourceColumn1,..sourceColumnN],TargetTable,targetCol,TargetValueColumnName,caseSensitivity={true/false},outputVariousOnMultipleMatches={true/false})`

A função retornará o valor do TargetTable:TargetValueColumnName para a linha quando as seguintes condições forem verdadeiras:

1. A linha tem uma correspondência: o valor de pelo menos uma das colunas de origem está "contido" no valor da coluna de destino (a distinção entre maiúsculas e minúsculas é determinada pelo último sinalizador opcional).
2. A linha tem o número máximo de correspondências possíveis.
3. A linha é exclusiva (existe apenas uma linha com o número máximo de colunas correspondentes).

Se apenas as duas primeiras condições forem verdadeiras e outputVariousOnMultipleMatches for verdadeiro, a função retornará " {Various} "; caso contrário, a função retornará null.

Pesquisas individuais:

`LookupContains(sourceColumn,TargetTable,targetCol,TargetValueColumnName,caseSensitivity={true/false},outputVariousOnMultipleMatches={true/false},oneToOneBidirectional={true/false},oneToOneSourceToTarget={true/false})`

Análogo aos casos acima, com um sinalizador opcional para especificar se a correspondência exige contenção em ambas as direções ( oneToOneBidirectional ) ou se a correspondência exige contenção somente da origem para o destino ( oneToOneSourceToTarget ).

## Argumentos

sourceColumn

A coluna na tabela atual que contém o valor a ser pesquisado. Esse valor pode ser o nome de uma coluna do tipo rótulo. A pesquisa não é compatível com valores numéricos na coluna de origem.

TargetTable

O nome da tabela que contém os valores de retorno. Deve ser uma constante e não pode fazer referência a outras colunas ou fórmulas.

targetCol

A(s) coluna(s) da tabela de destino em que se deve procurar uma correspondência.

TargetValueColumnName

A coluna na tabela de destino que fornece o valor de retorno.

Se você colocar um sinal de igual (=) na frente do nome da coluna, a função verificará o valor da coluna na tabela de origem. O valor encontrado será usado como o nome da coluna a ser usada na tabela de destino. Isso permite que a coluna de substituição seja dinâmica em uma base por linha.

caseSensitivity={true/false}

O valor pode ser verdadeiro ou falso.

outputVariousOnMultipleMatches={true/false}

true: se houver mais de uma correspondência, a função retornará " {Various}."

false: Se houver mais de uma correspondência, a função retornará null. [Isso está correto ou ele retorna a primeira ou a última correspondência?]

oneToOneBidirectional={true/false}

verdadeiro: a partida requer contenção em ambas as direções.

falso: A correspondência exige contenção em apenas uma direção.

oneToOneSourceToTarget={true/false}

true: a correspondência exige a contenção de uma única origem para um único destino.

false (falso): A correspondência pode ter contenção de mais de uma origem para mais de um destino.

## Tipo de retorno

O tipo da coluna de pesquisa.

Consulte também:

- [Pesquisa de IP](iplookup.htm "(Abre em uma nova guia ou janela)")
- [LookupEx](lookupexandlookupex_wild.htm "(Abre em uma nova guia ou janela)")
- [LookupFromPath](lookupfrompath.htm "(Abre em uma nova guia ou janela)")
- [LookupMetric](lookupmetric.htm "(Abre em uma nova guia ou janela)")
- [LookupObjectTotalAllocated](lookupobjecttotalallocated.htm "(Abre em uma nova guia ou janela)")
- [LookupObjectTotalValue](lookupobjecttotalvalue.htm "(Abre em uma nova guia ou janela)")
- [LookupObjectUnitAllocated](lookupobjectunitallocated.htm "(Abre em uma nova guia ou janela)")
- [LookupObjectUnitValue](lookupobjectunitvalue.htm "(Abre em uma nova guia ou janela)")
