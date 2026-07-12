---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "LookupEx função"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/lookupexandlookupex_wild.html"
images:
  - "resources/images/studio_images/studioimages/studio/aug160.png"
  - "resources/images/studio_images/studioimages/studio/aug161.png"
  - "resources/images/studio_images/studioimages/studio/aug162.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# LookupEx função

Realiza uma pesquisa em tabelas e retorna todos os valores correspondentes, criando novas linhas para cada correspondência. Essa função permite um relacionamento de um para muitos ao unir cada linha correspondente da tabela de pesquisa à tabela transformada.

## Sintaxe

```
LookupEx(source_column, lookup_table, matching_column, lookup_value_column, leave_original_value, replace_nulls, ignore_case)
```

## Parâmetros

- *source\_column* : A coluna no conjunto de dados atual cujos valores são usados para encontrar correspondências na tabela de pesquisa. Observação: esse parâmetro aceita uma expressão, o que significa que você pode fornecer um valor literal, uma referência de coluna ou o resultado de outra função. Necessário
- *lookup\_table* : O nome da tabela que contém os valores a serem retornados. Deve se referir a uma tabela existente no conjunto de dados. Necessário
- *matching\_column* : A coluna na lookup\_table na qual procurar uma correspondência com os valores de source\_column. Necessário
- *lookup\_value\_column* : A coluna na lookup\_table que fornece os valores de retorno para as linhas correspondentes. Necessário
- *leave\_original\_value* : Se verdadeiro, retorna o valor original da coluna source\_column quando nenhuma correspondência é encontrada; caso contrário, retorna NULL. O padrão é false. Opcional (padrão: false)
- *replace\_nulls* : Se verdadeiro, substitui valores NULL ou vazios na coluna source\_column fazendo a correspondência com NULLs na coluna matching\_column. O padrão é false. Opcional (padrão: false)
- *ignore\_case* : Se verdadeiro, executa a correspondência sem distinção de maiúsculas e minúsculas entre source\_column e matching\_column. O padrão é false. Opcional (padrão: false)

## Comportamento

- Executa uma pesquisa de um para muitos e adiciona uma nova linha para cada correspondência adicional encontrada na tabela de pesquisa.
- Se não houver correspondências, a linha original será preservada com um valor NULL na coluna de pesquisa.
- Se houver várias correspondências, a linha original será duplicada para cada correspondência, e cada cópia receberá um dos valores correspondentes.
- Os parâmetros opcionais devem ser usados em sequência se forem especificados parâmetros posteriores.

## Tipo de retorno

Tipo da coluna especificada em lookup\_value\_column

## Exemplos

`LookupEx(Cost Center Category, Cost Category Resources, Cost Center Category,
Resources)`

Na tabela BU Cost Centers, adiciona uma nova coluna chamada Resources que recupera todos os valores correspondentes da tabela Cost Category Resources com base na Cost Center Category. Se vários recursos corresponderem a uma única categoria, serão criadas várias linhas. Se nenhuma correspondência for encontrada, a linha original permanecerá com um valor NULL na coluna Resources.

**Tabela de centros de custo da BU (antes):**

| Unidade de negócios | Local | Gerenciador | Categoria do centro de custo |
| --- | --- | --- | --- |
| Pesquisa | Dallas | Smith | Nível 1 |
| Desenvolvimento | Nova Iorque | Jones | Nível 1 |
| Produção | Seattle | Wilson | Nível 2 |
| Marketing | Londres | Marrom | Nível 3 |
| Vendas | Viena | Deider | Nível 3 |

**Tabela de recursos da categoria de custo:**

| Categoria do centro de custo | Recursos |
| --- | --- |
| Nível 1 | Aplicativos |
| Nível 1 | Hardware |
| Nível 1 | Rede |
| Nível 2 | Hardware |
| Nível 2 | Rede |
| Nível 3 | Rede |

**Tabela de centros de custo da BU (após aplicar LookupEx ):**

| Unidade de negócios | Local | Gerenciador | Categoria do centro de custo | Recursos |
| --- | --- | --- | --- | --- |
| Desenvolvimento | Nova Iorque | Jones | Nível 1 | Rede |
| Desenvolvimento | Nova Iorque | Jones | Nível 1 | Aplicativos |
| Desenvolvimento | Nova Iorque | Jones | Nível 1 | Hardware |
| Marketing | Londres | Marrom | Nível 3 | Rede |
| Produção | Seattle | Wilson | Nível 2 | Rede |
| Produção | Seattle | Wilson | Nível 2 | Hardware |
| Pesquisa | Dallas | Smith | Nível 1 | Rede |
| Pesquisa | Dallas | Smith | Nível 1 | Aplicativos |
| Pesquisa | Dallas | Smith | Nível 1 | Hardware |
| Vendas | Viena | Deider | Nível 3 | Rede |

Suponha que você tenha a seguinte tabela de centros de custo da BU:

![pesquisa de imagens](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/aug160.png)

Você deseja fazer a correspondência entre cada categoria de centro de custo e os recursos atribuídos a essa categoria. Para fazer a correspondência, você criou a seguinte tabela Recursos de categoria de custo que lista os recursos para cada categoria:

![pesquisa de imagens](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/aug161.png)

Você adiciona uma nova coluna à tabela BU Cost Centers chamada Resources que usa a função LookupEx. Abaixo está a sintaxe da função e a função como ela apareceria na coluna Recursos.

```
LookupEx(source_column,lookup_table,matching_column,replacement_column
)
```

```
=LookupEx(Cost Center Category,Cost Category
            Resources,Cost Center
      Category,Resources)
```

O resultado é mostrado na imagem a seguir. Observe que o aplicativo adicionou linhas à tabela para cada correspondência encontrada. Por exemplo, há três linhas para a unidade de negócios **Desenvolvimento**, representando os três recursos: Rede, Aplicativos e Hardware.

![pesquisa de imagens](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/aug162.png)

Nota:

- Use essa função com cautela em conjuntos de dados grandes, pois ela pode resultar em grandes expansões de linha.
- Apenas uma instância dessa função deve ser usada por tabela para evitar resultados incorretos.
- Essa função não é compatível com a barra de fórmulas da faixa de opções ou com a visualização da guia Dados.
- Não use chaves { } para escapar dos nomes das colunas nessa função.
