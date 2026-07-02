---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Função Use_Map_Table"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/usemaptable.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Função Use_Map_Table

**Aplica-se a** : TBM Studio 12.0 e posterior

Use essa função para criar alocações entre dois objetos usando uma fórmula inserida manualmente.

Observação: o suporte a essa função foi descontinuado na versão 12 do site TBM Studio . Embora essa função ainda esteja disponível, não há suporte para aproveitá-la para novas alocações líquidas. Se estiver trabalhando com um projeto que foi atualizado da versão 11 (que usa essa função), consulte a [Tarefa a seguir em v12](#UseMapTablefunction__TasksforStudio12) abaixo, que descreve a prática recomendada v12 para obter as mesmas alocações. A Apportion incentiva os clientes que fazem upgrade para TBM Studio v12 a mudar para esse novo método. Informações adicionais sobre essa função são fornecidas abaixo para fins históricos.

## Onde usar

Ao definir uma alocação entre dois objetos em um modelo, selecione **Advanced** como a opção de alocação. O aplicativo exibe a caixa de diálogo **Editar fórmula**, na qual você pode inserir a função. A vantagem de usar a função Use\_Map\_Table é que ela não depende do mecanismo de inferência para vincular os identificadores de unidade dos dois objetos. Os identificadores no objeto de origem podem ser mapeados para identificadores no objeto de destino.

## Sintaxe

`Use_Map_Table(table:weight_column[,source_column,target_column][,format)]`

ou

`Use_Map_Table(table:weight_column[,format)]`

## Argumentos

*tabela*

Faz referência a uma tabela de mapeamento.

*coluna\_peso*

A coluna na tabela que contém os números de ponderação.

*coluna\_fonte*

A coluna na tabela que contém o ID da unidade do objeto de origem.

*coluna\_alvo*

A coluna na tabela que contém a ID da unidade do objeto de destino.

*formato*

Ao usar a primeira instrução de sintaxe (table:weight), isso pode ser "ratio", "percent" ou "fraction\_percent", sendo que o padrão é "fraction\_percent"

Ao usar a segunda instrução de sintaxe (table:weight), ela pode ser "percent" ou "fraction\_percent", sendo que o padrão é "fraction\_percent"

## Tipo de retorno

O tipo das colunas na tabela de correspondência.

## Comentários

Para a primeira sintaxe, se o Objeto A estiver transferindo valores para o Objeto B, a tabela de mapeamento deverá incluir os seguintes tipos de colunas:

| A | B | coluna\_peso |
| --- | --- | --- |
| Valores da coluna do identificador de A | Valores da coluna do identificador de B | Porcentagem numérica (por exemplo: 0.2 = 20%, 1.0 = 100%) |

## Tarefas para o Studio 12

Se o seu projeto foi atualizado da versão 11 para a versão 12 do TBM Studio , todas as alocações que usam use\_map\_table funcionarão após a atualização. No entanto, se você editar a alocação, deverá alterá-la para que funcione na versão 12. Para fazer isso, você converterá a use\_map\_table em um objeto modelado. Em seguida, você alocará do objeto de origem original para o novo objeto de mapeamento e, depois, do novo objeto de mapeamento para o objeto de destino original.

Em TBM Studio versão 12, siga estas etapas:

1. Adicione uma etapa de modelagem à tabela de mapeamento originalmente usada na função use\_map\_table.
2. Alocar do objeto de origem original para a tabela de mapeamento recém-modelada.
   - Nessa alocação, certifique-se de especificar um relacionamento de dados usando o identificador do objeto de origem e a coluna source\_column da tabela de mapeamento.
   - Atualize essa alocação para ponderar adequadamente pela coluna weight\_column da tabela de mapeamento. A forma de fazer isso dependerá do formato de sua função use\_map\_table.
     - Se o formato use\_map\_table for **ratio**, use **a ponderação** como regra de distribuição e especifique a **coluna source\_column** na tabela de mapeamento.
     - Se o formato use\_map\_table for porcentagem, crie uma alocação avançada com a fórmula:

       ```
       =SOURCE*Mapping
                               Table.weight_column/100
       ```
     - Se o formato de use\_map\_table for fraction\_percent, crie uma alocação avançada com a fórmula:`=SOURCE*Mapping Table.weight_column`

       **Exemplo: Alocação da fonte para a tabela de mapeamento**

       ![](../../../resources/images/studio_images/studioimages/studio_mapping%20table_distributing.png)
3. Alocar da tabela de mapeamento recém-modelada para o objeto de destino original.
   - Nessa alocação, certifique-se de especificar um relacionamento de dados usando o identificador do objeto de origem e a coluna source\_column da tabela de mapeamento.
   - Normalmente, a ponderação dessa alocação não importa, pois cada linha na tabela de mapeamento é alocada para uma linha no objeto receptor.

## Resumo

O resultado final desse método é o mesmo da função original use\_map\_table, segue as práticas recomendadas da versão 12 do site TBM Studio e permite que as otimizações do mecanismo de modelagem do site Apptio tenham seu efeito total.
