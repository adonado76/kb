---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Pesquisa de dados"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/data-lookup.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Pesquisa de dados

A pesquisa de dados é um recurso que permite que uma célula faça referência a um valor de uma ou mais células. Dependendo da localização das células, há duas variantes de pesquisa de dados:

- [Pesquisa de dados internos](#Datalookup__Internaldatalookup)

Pesquisa de dados que faz referência a um valor na mesma tabela.

- [Pesquisa de dados externos](#Datalookup__Externaldatalookup)

Pesquisa de dados que faz referência a um valor em outra tabela, mas no mesmo projeto.

## Pesquisa de dados internos

A pesquisa interna de dados permite que uma célula faça referência a um valor de uma ou mais células na mesma linha.

Sintaxe de pesquisa de dados internos

`=column`

A fórmula retorna os valores de todas as células que estão na mesma linha e na **coluna**, em que **coluna** é qualquer nome de coluna na mesma tabela.

## Exemplos

Criamos uma nova coluna chamada **Space Usage Percent** e atribuímos a seguinte fórmula:

`=(Used Space/Total Space)*100`

Cada célula da nova coluna **Percentual de uso de espaço** :

1. Faz referência às células das colunas **Espaço usado** e **Espaço total** na mesma linha.
2. Faz o cálculo da fórmula.
3. Atribui o valor final à célula que contém a fórmula.

Observação: Não é possível fazer referência a uma célula em uma linha diferente na mesma tabela. Por exemplo, não é possível atribuir a fórmula =B1 à célula A2 em uma planilha do Excel ou pesquisar uma célula em uma linha diferente com base em critérios ou ordem de pesquisa.

## Pesquisa de dados externos

A pesquisa de dados externos permite que uma célula faça referência a um valor de uma ou mais células em uma coluna de outra tabela.

[Leia sobre considerações de caso de uso e desempenho](#Datalookup__Use)

[Leia sobre métodos alternativos de pesquisa de dados externos](#Datalookup__Alternat)

Sintaxe de pesquisa de dados externos

```
={table}:{column1}

or

={table}:{column1}[selector]
```

A fórmula retorna o valor de todas as células em **column1** na **tabela**. Você também pode adicionar **[selector]** para acrescentar critérios adicionais que as células devem atender.

- **{table}** - nome de outra tabela que contém as células que queremos referenciar.
- **{column1}** - qualquer nome de coluna na **tabela**.
- **[seletor]** - critérios adicionais das células.
  - No seletor, você pode usar operadores relacionais, por exemplo, **=**, **!=**, **IN**, **NOT IN**, **>** e **<.**
  - O seletor pode fazer referência a uma ou mais colunas na **tabela** e na tabela em que essa fórmula está definida.

Observação: Haverá apenas um valor retornado, mesmo que várias células atendam aos critérios do seletor. Se a coluna for numérica, será retornado o valor somado de todas as células correspondentes. Se a coluna for não numérica e houver mais de uma correspondência, será retornado ":" ou " {Various} ".

## Exemplos

`=GL:Cost[ID="95847"]`

Retorna a soma de todas as células na coluna **Custo** da tabela **GL**, em que o valor **de ID** nessas células é igual a **95847**.

`=GL:Cost[ID="95847"]*PercentColumn`

Retorna a soma de todas as células na coluna **Custo** da tabela **GL**, em que o valor na coluna **ID** dessa tabela é igual a **95847**.

Em seguida, usa uma pesquisa de dados interna para multiplicar o valor retornado pelo valor da célula na coluna **PercentColumn** coluna. O **PercentColumn** deve estar na mesma linha que essa fórmula.

Essa fórmula usa uma pesquisa de dados externa e uma pesquisa de dados interna.

`=GL:Cost[Type=Expense Type]`

Retorna a soma de todas as células na coluna **Custo** da tabela **GL**, em que o valor na coluna **Tipo** e nas mesmas linhas é igual ao valor da coluna **Tipo de despesa** na célula em que essa fórmula está definida.

Ao usar esses nomes de coluna:

- O lado esquerdo de cada comparação procura uma coluna com esse nome na tabela de destino.
- O lado direito procura uma coluna na tabela, onde a fórmula é definida.

Neste exemplo, **GL**.

Essa fórmula usa uma pesquisa de dados interna dentro de uma pesquisa de dados externa.

`=GL:Cost[Type="ServerType"]`

Retorna a soma de todas as células na coluna **Custo** da tabela **GL**, em que o valor na coluna **Tipo** dessa tabela é igual ao rótulo: **ServerType**.

`=Labor:Amount[Equipment IN ("server","router","desktop") ]`

Retorna a soma de todas as células na coluna **Amount** da tabela **Labor**, em que o valor na coluna **Equipment** dessa tabela é igual a **servidor**, **roteador** ou **desktop**.

`=Labor:Amount[Equipment NOT IN ("server","router","desktop")]`

Retorna a soma de todas as células na coluna **Amount (Valor)** da tabela **Labor (Trabalho** ), em que o valor na coluna **Equipment (Equipamento** ) dessa tabela não é igual a **servidor**, **roteador** ou **desktop**.

`=Storage:Amount[Amount>Threshold]`

Retorna a soma de todas as células na coluna **Amount** (Valor) da tabela **Storage (Armazenamento** ), em que o valor na coluna **Amount (Valor)** dessa tabela é maior que o valor na célula da coluna **Threshold (Limite** ) na mesma linha (na tabela em que a fórmula está definida, não na tabela **Storage** ).

## Considerações sobre casos de uso e desempenho

Como a pesquisa de dados externos executa o equivalente a um SumIf na tabela de destino (encontrando todas as células que atendem aos critérios e, em seguida, somando-as), é uma operação potencialmente cara que pode ter um impacto negativo no desempenho.

Sempre que possível, use a função de pesquisa que suporta o caso de uso necessário. A função de pesquisa retorna apenas a primeira correspondência encontrada, o que reduz o impacto no desempenho. A pesquisa de dados externos encontra todas as linhas que correspondem aos critérios do seletor.

Se houver necessidade de executar os mesmos critérios do seletor de pesquisa de dados externos na mesma tabela mais de uma vez, sugerimos criar uma nova coluna na tabela que seja equivalente aos critérios do seletor (e que inclua potencialmente um SumIf,, se necessário) e, em seguida, usá-la como a coluna que é pesquisada em várias funções de pesquisa em outras tabelas. Dessa forma, a operação mais cara de encontrar as linhas correspondentes é feita apenas uma vez, e a operação menos cara de consultar as colunas nas tabelas é feita várias vezes.

## Métodos alternativos de pesquisa de dados externos

Há outras maneiras de procurar dados em outras tabelas, cada uma delas adequada a diferentes casos de uso, e cada uma delas tem diferentes considerações a serem levadas em conta.

- [Consulta](functions/lookupandlookup_wild.htm "(Abre em uma nova guia ou janela)")
- [LookupEx](functions/lookupexandlookupex_wild.htm "(Abre em uma nova guia ou janela)")
- [TableMatch](functions/tablematch.htm "(Abre em uma nova guia ou janela)")
- [Etapa de união](../data%20studio/join-data.htm "(Abre em uma nova guia ou janela)") no pipeline de transformação
