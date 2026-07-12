---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Filtrar dados"
breadcrumb: []
source_path: "studio/data_studio/filter-data-set.html"
images:
  - "resources/images/studio_images/studioimages/icons/delete_icon.png"
  - "resources/images/studio_images/studioimages/icons/paren.png"
  - "resources/images/studio_images/studioimages/studio/stu500.png"
  - "resources/images/studio_images/studioimages/studio/stu659.png"
  - "resources/images/studio_images/studioimages/studio_filter_compute.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Filtrar dados

**Aplica-se a** : Apptio TBM Studio R12.0 e posterior

Para filtrar dados, adicione um filtro às etapas de transformação. Você pode inserir uma ou mais expressões de filtro e combiná-las usando a lógica AND e OR. Além disso, você pode aninhar expressões de filtro usando parênteses. Você pode aplicar filtros aos seguintes itens:

- Conjuntos de dados no pipeline de transformação
- Objeto modelo
- Alocações

Dica: Como prática recomendada, se você usar OR/AND, certifique-se de usar parênteses para agrupar argumentos relacionados.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu500.png)

## filtrar linhas

Para adicionar uma expressão de filtro:

1. Adicione uma etapa de filtro ao pipeline de transformação.
2. Construa a primeira expressão de filtro:
   - No menu suspenso da etapa de filtro, selecione a coluna a ser filtrada.
   - No campo suspenso no centro, selecione um operador (**Equals**, **Not Equals**, etc.).

     Observação: alguns operadores de filtro de linha funcionam somente com determinados tipos de dados. Consulte [Operadores e tipos de dados com filtros](#Filterdata__Operatorsanddatatypeswithfilters).
   - No campo à direita, digite um valor de filtro (exemplo: Compute).

     ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio_filter_compute.png)

Se desejar, adicione mais expressões de filtro.

Para adicionar uma expressão de filtro simples (usando OR ou AND, não ambos), conclua estas etapas:

1. Clique em **Add condition (Adicionar condição** ), logo abaixo da expressão de filtro anterior. Uma nova linha de expressão é adicionada abaixo da anterior, juntamente com uma lista de seletores booleanos (para AND e OR).
2. Selecione AND ou OR.
3. Digite valores para coluna, operador e filtro para a nova expressão e clique em **Save (Salvar)**.

O filtro é aplicado.

![](../../resources/images/studio_images/studioimages/studio_filter%20data_row.png)

Para adicionar uma expressão de filtro complexa (usando OR e AND), conclua estas etapas:

1. Clique no ícone **Plus-Parenthesis**![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/icons/paren.png) à direita. ![](../../resources/images/studio_images/studioimages/studio_filter_add%20row.png)
2. Selecionar o ícone de parênteses recua uma expressão em relação aos outros argumentos.

   ![](../../resources/images/studio_images/studioimages/studio_filter_add%20condition.png)

   Dica: Como prática recomendada, ao usar OR/AND, certifique-se de usar parênteses para agrupar argumentos relacionados. Isso ajuda a garantir que as expectativas do usuário sejam refletidas corretamente na configuração do filtro. O uso de ambos os argumentos OR/AND sem parênteses pode fazer com que o sistema não filtre os registros de acordo com as expectativas do usuário.
3. Clique em **Adicionar condição**. Uma nova linha de expressão recuada é adicionada abaixo da linha anterior, o que significa que ela também está entre parênteses, juntamente com uma lista de seletores booleanos (para AND e OR).
4. Selecione AND ou OR.
5. Digite valores para coluna, operador e filtro para a nova expressão e clique em **Save (Salvar)**.

Mais opções ao adicionar expressões:

- Para adicionar uma linha de expressão sem subaninhamento, clique em **Adicionar condição** à esquerda. Selecione um operador booleano e, em seguida, complete a linha de expressão como antes.
- Para adicionar uma linha de expressão com outra camada de subaninhamento, clique no ícone **Mais-Parêntese** ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/icons/paren.png) à direita. Selecione um operador booleano e, em seguida, complete a linha de expressão como antes. Os usuários podem ver quando uma expressão está entre parênteses porque a expressão é recuada para mostrar como os parênteses estão agrupando expressões.![](../../resources/images/studio_images/studioimages/studio_filter_it%20resource%20tower.png)
- Para excluir uma linha, clique no ícone **Excluir** ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/icons/delete_icon.png) à direita dos critérios.

## Copiar/colar filtros

Use os ícones **Copiar/Colar** para copiar ou colar um conjunto de filtros de uma tabela para outra.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu659.png)

## Operadores e tipos de dados com filtros

Alguns operadores de filtro de linha funcionam apenas com determinados tipos de dados. Por exemplo, **Less Than** funciona com colunas que contêm apenas dados numéricos, enquanto **Equals** funciona com colunas que contêm qualquer tipo de dados. A tabela a seguir descreve os tipos de dados que funcionam com cada operador de filtro de linha. O grupo superior de operadores na tabela oferece funcionalidade semelhante à dos curingas. Os filtros não suportam símbolos tradicionais de curinga, como \*.

|  |  |
| --- | --- |
| Operador de filtro de linha | Tipo de dados da coluna |
| ContainsDoes Não ContainEnds WithDoes Não termina WithStarts WithDoes Não começa com | Sequência |
| Menos ThanLess Maior ou igual ToGreater ThanGreater Maior ou igual a | Numérico |
| EqualsNot EqualsIs NullIs Não NullIs InIs Não em | Todos os tipos |
| Intersect CurrentUserColumnIntersects Tabela:Coluna | Sequência |

## Está dentro e não está dentro das operadoras

O operador **Is In** verifica se um valor em uma coluna também existe em **uma ou mais** colunas da tabela. O operador **Is Not In** verifica se um valor em uma coluna não existe em **uma ou mais** colunas. Diferentemente dos outros operadores, **Is In** e **Is Not In** podem aceitar várias entradas no campo certo. Cada entrada deve ser separada por uma vírgula.

![](../../resources/images/studio_images/studioimages/studio_filter_is%20in.png)

Para que o filtro seja aplicado a uma linha, a expressão do filtro deve ser verdadeira para todas as colunas listadas.
