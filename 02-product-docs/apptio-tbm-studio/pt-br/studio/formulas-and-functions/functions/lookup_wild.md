---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Função Lookup_Wild"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/lookup_wild.html"
images:
  - "resources/images/studio_images/studioimages/studio/aug036.png"
  - "resources/images/studio_images/studioimages/studio/aug037.png"
  - "resources/images/studio_images/studioimages/studio/aug039.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Função Lookup_Wild

Procura um valor em uma tabela de pesquisa usando a correspondência de padrões (expressões regulares) na coluna de correspondência e retorna o valor correspondente de uma coluna de substituição.

## Sintaxe

```
Lookup_Wild(source_column, lookup_table, matching_column, replacement_column, leave_original_value, replace_nulls, ignore_case, default_value)
```

`Lookup_Wild(source_column,lookup_table,matching_column,replacement_column[,leave_original_value][,replace_nulls][,ignore_case])`

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

`Lookup_Wild(ProductCode, ProductTable, CodePattern, Description)`: Retorna a Descrição em que ProductCode corresponde a uma expressão regular na coluna CodePattern.

`Lookup_Wild(Name, PatternsTable, RegexPattern, Category, false, true,
true)`: Executa uma pesquisa baseada em padrão de substituição nula e sem distinção entre maiúsculas e minúsculas para "Name".

Suponha que você tenha a seguinte tabela chamada Data Centers, que lista os data centers e sua localização:

![função de consulta](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/aug036.png)

Com base na localização, você deseja preencher a coluna Fuso horário. Você tem a seguinte tabela chamada Time Zone, que pode fornecer o deslocamento GMT.

![função de consulta](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/aug037.png)

Insira o seguinte no campo Substituição de valor para a coluna Localização na tabela Data Centers:

```
=Lookup(Location,Time Zone,City,Time
      Zone)
```

O resultado é:

![função de consulta](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/aug039.png)

- Se estiver usando replace\_nulls ou ignore\_case, você também deverá incluir todos os parâmetros opcionais anteriores.
- Quando nenhuma correspondência é encontrada e leave\_original\_value é falso, a função retorna em branco, a menos que um default\_value seja especificado.
- Oferece suporte à correspondência de padrões usando expressões regulares na coluna matching\_column.
- Se forem encontradas várias linhas correspondentes, Lookup\_Wild retornará ' {Various} '. Se isso não for aceitável, use LookupEx em vez disso.
- A vinculação de inferência é preferível a Lookup\_Wild quando possível, especialmente se o resultado não precisar persistir no conjunto de dados.
