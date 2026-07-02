---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Função de pesquisa"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/lookup.html"
images:
  - "resources/images/studio_images/studioimages/studio/aug036.png"
  - "resources/images/studio_images/studioimages/studio/aug037.png"
  - "resources/images/studio_images/studioimages/studio/aug039.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Função de pesquisa

Procura um valor em uma tabela de pesquisa com base em uma correspondência entre uma coluna na tabela atual e uma coluna na tabela de pesquisa e retorna o valor correspondente de uma coluna de substituição.

Encontra o valor em uma coluna de origem especificada na tabela atual e em uma coluna especificada de uma tabela de pesquisa. Lookup e Lookup\_Wild retornam o valor na coluna de substituição especificada correspondente da tabela de pesquisa. Se dois ou mais valores forem encontrados na tabela de pesquisa, o valor {Various} será retornado. A única diferença entre as duas funções é que Lookup\_Wild suporta expressões regulares na coluna de correspondência e Lookup não.

Para aumentar a contagem de linhas criando uma nova linha para cada valor de retorno em vez de {Various}, use [LookupEx](lookupexandlookupex_wild.html "Realiza uma pesquisa em tabelas e retorna todos os valores correspondentes, criando novas linhas para cada correspondência. Essa função permite um relacionamento um-para-muitos unindo todas as linhas correspondentes da tabela de pesquisa na tabela transformada.").

Se estiver usando a pesquisa para trazer um valor numérico e quiser que os valores sejam somados em vez de retornar vários, use a sintaxe de [pesquisa de dados](../data-lookup.html).

## Sintaxe

```
Lookup(source_column, lookup_table, matching_column, replacement_column, leave_original_value, replace_nulls, ignore_case, default_value)
```

## Parâmetros

- *source\_column* : A coluna na tabela atual usada para encontrar correspondências. Oferece suporte a várias colunas unidas com & ou &&. Necessário
- *lookup\_table* : O nome da tabela de pesquisa que contém os valores de correspondência e substituição. Deve ser uma constante. Necessário
- *matching\_column* : A coluna na tabela de pesquisa a ser comparada com a coluna de origem. Oferece suporte a expressões regulares somente em Lookup\_Wild. Necessário
- *replacement\_column* : A coluna na tabela de pesquisa da qual será retornado o valor. Prefixo com "=" para selecionar dinamicamente uma coluna usando a tabela de origem. Necessário
- *leave\_original\_value* : Retorna o valor original da fonte se nenhuma correspondência for encontrada. Se falso, retorna em branco. Opcional (padrão: False)
- *replace\_nulls* : Determina o comportamento quando o valor de origem é nulo. Se for verdadeiro, tentará corresponder a um valor nulo na coluna de pesquisa. Opcional (padrão: False)
- *ignore\_case* : Se verdadeiro, executa uma correspondência sem distinção entre maiúsculas e minúsculas. Se for falso, a correspondência diferencia maiúsculas de minúsculas. Opcional (padrão: False)
- *default\_value* : Valor padrão opcional a ser retornado quando nenhuma correspondência for encontrada e leave\_original\_value for false. Opcional

## Comportamento

- Encontra uma correspondência entre a coluna de origem e a coluna correspondente na tabela de pesquisa.
- Retorna o valor da coluna de substituição para a última correspondência encontrada.
- Se várias linhas corresponderem, retorna ' {Various} '.
- Oferece suporte a sinalizadores booleanos opcionais para personalização do comportamento: leave\_original\_value, replace\_nulls e ignore\_case.
- Só funciona com colunas do tipo rótulo nas colunas de origem e de correspondência (não há suporte para tipos numéricos).

## Tipo de retorno

Corresponde ao tipo de dados da coluna de substituição

## Exemplos

`Lookup({Product ID}, ProductTable, ProductCode, Description)`: Retorna a descrição do site ProductTable que corresponde à ID do produto da linha atual.

`Lookup(ProductType, LookupTable, Type, Label, true)`: Retorna o rótulo da correspondência ProductType;. Se nenhuma correspondência for encontrada, retorna o ProductType original.

`Lookup(Region & SubRegion, GeographyTable, Region & SubRegion, Code, false,
false, true)`: Executa uma pesquisa sem distinção entre maiúsculas e minúsculas usando duas colunas combinadas.

Suponha que você tenha a seguinte tabela chamada Data Centers, que lista os data centers e sua localização:

![imagem de pesquisa](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/aug036.png)

Com base na localização, você deseja preencher a coluna Fuso horário. Você tem a seguinte tabela chamada Time Zone, que pode fornecer o deslocamento GMT.

![imagem de pesquisa](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/aug037.png)

Insira o seguinte no campo Substituição de valor para a coluna Localização na tabela Data Centers:

```
=Lookup(Location,Time Zone,City,Time
      Zone)
```

O resultado é:

![imagem de pesquisa](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/aug039.png)

Nota:

- Se estiver usando replace\_nulls ou ignore\_case, você também deverá incluir todos os parâmetros opcionais anteriores.
- Quando nenhuma correspondência é encontrada e leave\_original\_value é falso, a função retorna em branco, a menos que um default\_value seja especificado.
- Use Lookup\_Wild se você precisar de correspondência de padrões por meio de expressões regulares na coluna de correspondência.
- Se forem encontradas várias linhas correspondentes, Lookup retornará ' {Various} '. Se isso não for aceitável, use LookupEx em vez disso.
