---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Função Lookup_From_Editable"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/lookup-from-editable.html"
images:
  - "resources/images/studio_images/lookupeditable.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Função Lookup_From_Editable

Essa função traz colunas de uma tabela editável por meio de uma pesquisa para incluí-las em tabelas de relatórios que estejam exibindo dados de uma tabela editável diferente ou dados de uma transformação/modelo.

## Onde usar

Essa função pode ser usada em:

- Conjuntos de dados
- Colunas de fórmula em tabelas editáveis

## Onde NÃO usar

Pipeline de transformação, driver de modelo ou fórmula de alocação avançada.

## Sintaxe

=Lookup\_From\_Editable(coluna\_fonte,tabela\_de\_pesquisa,coluna\_correspondente,coluna\_valor\_de\_pesquisa, [manter\_valor\_original], (substituir\_nulos], [ignorar\_maiúsculas\_minúsculas])

**Argumentos**

- *source\_column* é a coluna no conjunto de dados atual que corresponderá a uma coluna no outro conjunto de dados.
- *lookup\_table* é o nome editável de onde você precisa traduzir os dados.
- *matching\_column* é a coluna na lookup\_table que corresponde aos dados da coluna que você especificou em source\_column.
- *lookup\_value\_column* é a coluna na lookup\_table que você precisa traduzir de volta para o conjunto de dados atual.
- *leave\_original\_value* é um booleano que não atualiza o resultado se a pesquisa não for bem-sucedida
- *replace\_nulls* é um booleano que substitui o valor nulo por um valor padrão definido
- *ignore\_case* é um booleano para ignorar o caso de outros parâmetros

## Tipo de retorno

O tipo da coluna de pesquisa.

**Observações** :

- Se a função LookUp\_From\_Editable encontrar várias linhas correspondentes, ela retornará {Various} em vez de um valor nulo.
- Se estiver usando os argumentos opcionais replace\_nulls ou ignore\_case, também deverá especificar os argumentos opcionais que vêm antes deles.
- Use as chaves padrão { } para escapar de caracteres especiais ou operadores que possam aparecer nos nomes das colunas que estão sendo referenciadas. Por exemplo, {P&L Rate}.
- A inferência que vincula várias tabelas é preferível a fazer pesquisas e pode ser usada sempre que a coluna resultante não for necessária em um conjunto de dados.

## Exemplos

Essa fórmula pode ser usada para criar uma coluna de pesquisa em uma tabela editável a partir de outra tabela editável.

Observação: Essa coluna de pesquisa não adicionará dados às tabelas editáveis no backend, é apenas uma coluna visível na superfície do relatório.

![Exemplos](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/lookupeditable.png)

Exemplo de sintaxe

`=Lookup_From_Editable(Product Family ID, L1 Product Family, Product Family ID, Product
Family)`
