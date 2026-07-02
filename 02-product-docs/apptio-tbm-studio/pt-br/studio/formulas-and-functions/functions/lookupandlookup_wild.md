---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Funções Lookup e Lookup_Wild"
breadcrumb: []
source_path: "studio/formulas-and-functions/functions/lookupandlookup_wild.html"
images:
  - "resources/images/studio_images/studioimages/studio/aug036.png"
  - "resources/images/studio_images/studioimages/studio/aug037.png"
  - "resources/images/studio_images/studioimages/studio/aug039.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Funções Lookup e Lookup_Wild

**Aplica-se a** : TBM Studio 12.0 e posterior

Encontra o valor em uma coluna de origem especificada na tabela atual e em uma coluna especificada de uma tabela de pesquisa. Lookup e Lookup\_Wild retornam o valor na coluna de substituição especificada correspondente da tabela de pesquisa. Se dois ou mais valores forem encontrados na tabela de pesquisa, o valor {Various} será retornado. A única diferença entre as duas funções é que Lookup\_Wild suporta expressões regulares na coluna de correspondência e Lookup não.

Para aumentar a contagem de linhas criando uma nova linha para cada valor de retorno em vez de {Various}, use [LookupEx](lookupexandlookupex_wild.htm "(Abre em uma nova guia ou janela)").

Se estiver usando a pesquisa para trazer um valor numérico e quiser que os valores sejam somados em vez de retornar vários, use a sintaxe de [pesquisa de dados](../data-lookup.htm "(Abre em uma nova guia ou janela)").

## Onde usar

Essa função pode ser usada em:

- Conjuntos de dados
- Colunas de fórmula em tabelas de relatórios (embora isso não seja recomendado). Em vez disso, use inferência)
- Mapeador de dados
- Texto dinâmico

## Substitui

Há novas versões das funções Lookup e Lookup\_Wild que substituem as versões antigas. Se houver versões antigas que você tenha usado, o aplicativo as renomeará para Lookup\_Old e Lookup\_Wild\_Old. NÃO EDITE ESSAS VERSÕES ANTIGAS. Se você precisar fazer alterações nessas funções, exclua-as e insira novas funções Lookup e Lookup\_Wild.

## Sintaxe

`Lookup(source_column,lookup_table,matching_column,replacement_column[,leave_original_value][,replace_nulls][,ignore_case])`

`Lookup_Wild(source_column,lookup_table,matching_column,replacement_column[,leave_original_value][,replace_nulls][,ignore_case])`

## Argumentos

*coluna\_fonte*

A coluna na tabela atual que contém o valor a ser pesquisado. Esse valor pode ser o nome de uma coluna do tipo rótulo. A pesquisa não é compatível com valores numéricos na coluna de origem. Você pode incluir duas ou mais colunas de origem correspondentes usando o operador "&" (executa ambos os testes) ou "&&" (executa o segundo teste somente se o primeiro for verdadeiro). Você deve incluir o mesmo número de colunas no parâmetro matching\_column.

**AVISO**

A coluna não pode ser do tipo "Numérico".

*tabela de pesquisa*

O nome da tabela que contém os valores de retorno. Deve ser uma constante e não pode fazer referência a outras colunas ou fórmulas.

*coluna\_correspondente*

A coluna na *lookup\_table* na qual se deve procurar uma correspondência. Se estiver usando Lookup\_Wild, você poderá inserir expressões regulares na coluna. Para obter informações sobre expressões regulares, pesquise na Web.

Você pode incluir duas ou mais colunas correspondentes usando o operador "&" (executa ambos os testes) ou "&&" (executa o segundo teste somente se o primeiro for verdadeiro).

**AVISO**

A coluna não pode ser do tipo "Numérico".

*replacement\_column*

A coluna na lookup\_table que fornece o valor de retorno.

Se você colocar um sinal de igual (=) na frente do nome da coluna, a função verificará o valor da coluna na tabela de origem. O valor encontrado será usado como o nome da coluna a ser usada na lookup\_table. Isso permite que a coluna de substituição seja dinâmica em uma base por linha.

*leave\_original\_value*

Um valor booleano (verdadeiro ou falso) que controla o valor que é retornado se o valor pesquisado não for encontrado. Se leave\_original\_value = true, a pesquisa retornará o valor procurado; se false, a pesquisa retornará uma célula em branco. Se esse argumento não for especificado, o padrão será false.

*replace\_nulls*

Um valor booleano (verdadeiro ou falso) que controla o valor que é retornado quando o valor pesquisado está vazio ou é nulo. Se você digitar true, ele procurará um valor na replacement\_column cujo valor correspondente na matching\_column seja nulo. Se você inserir false, um valor NULL na coluna source\_column permanecerá nulo. Se a coluna matching\_column não contiver NULL ou um valor vazio, o valor de retorno será NULL. O padrão desse valor é false.

*ignore\_case*

Um valor booleano (true ou false) que controla se a pesquisa ignora maiúsculas e minúsculas ao comparar valores da coluna\_de\_origem com a coluna\_correspondente. Se ignore\_case = true, a pesquisa ignora maiúsculas e minúsculas; se false, a pesquisa diferencia maiúsculas e minúsculas. Se esse argumento não for especificado, o padrão será false. A operação de pesquisa será mais rápida quando ignore\_case for falso, portanto, altere isso somente quando necessário.

## Tipo de retorno

O tipo da coluna de pesquisa.

**Observações** :

- Se a função LookUp encontrar várias linhas correspondentes, ela retornará {Various} em vez de um valor nulo.
- Se estiver usando os argumentos opcionais *replace\_nulls* ou *ignore\_case*, também deverá especificar os argumentos opcionais que vêm antes deles.
- Use as chaves padrão { } para escapar de caracteres especiais ou operadores que possam aparecer nos nomes das colunas que estão sendo referenciadas. Por exemplo, {P&L Rate}.
- A inferência que vincula várias tabelas é preferível a fazer pesquisas e pode ser usada sempre que a coluna resultante não for necessária em um conjunto de dados.

## Exemplo de pesquisa

Suponha que você tenha a seguinte tabela chamada Data Centers, que lista os data centers e sua localização:

![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/aug036.png)

Com base na localização, você deseja preencher a coluna Fuso horário. Você tem a seguinte tabela chamada Time Zone, que pode fornecer o deslocamento GMT.

![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/aug037.png)

Insira o seguinte no campo Substituição de valor para a coluna Localização na tabela Data Centers:

```
=Lookup(Location,Time Zone,City,Time
      Zone)
```

O resultado é:

![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/aug039.png)

Consulte também:

- [IPLookup](iplookup.htm "(Abre em uma nova guia ou janela)")
- [LookupEx](lookupexandlookupex_wild.htm "(Abre em uma nova guia ou janela)")
- [LookupFromPath](lookupfrompath.htm "(Abre em uma nova guia ou janela)")
- [LookupMetric](lookupmetric.htm "(Abre em uma nova guia ou janela)")
- [LookupObjectTotalAllocated](lookupobjecttotalallocated.htm "(Abre em uma nova guia ou janela)")
- [LookupObjectTotalValue](lookupobjecttotalvalue.htm "(Abre em uma nova guia ou janela)")
- [LookupObjectUnitAllocated](lookupobjectunitallocated.htm "(Abre em uma nova guia ou janela)")
- [LookupObjectUnitValue](lookupobjectunitvalue.htm "(Abre em uma nova guia ou janela)")
