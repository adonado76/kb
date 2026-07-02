---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Mensagens de erro do Validation Framework: Explicações e soluções alternativas"
breadcrumb: []
source_path: "studio/data_studio/validationframeworkerrors.html"
images:
  - "resources/images/studio_images/studioimages/studio_columns_add.png"
  - "resources/images/studio_images/studioimages/studio_columns_numeric.png"
  - "resources/images/studio_images/studioimages/studio_columns_pick.png"
  - "resources/images/studio_images/studioimages/studio_import_error.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Mensagens de erro do Validation Framework: Explicações e soluções alternativas

**Aplica-se a** : TBM Studio 12.0 e posterior

Este artigo descreve erros comuns de pipeline que podem ocorrer em documentos de tabela em Apptio TBM Studio. Esses erros destacam problemas de configuração que farão com que seu projeto se comporte de forma diferente da esperada. Apptio aconselha fortemente os clientes a resolver os erros.

Qual é a aparência de um erro?

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio_import_error.png)

Observação: Este artigo descreve erros comuns e não é abrangente. Além disso, novos erros são adicionados com frequência. Se você receber um erro não discutido aqui e quiser obter mais informações sobre ele, adicione um comentário abaixo e nós o investigaremos.

As informações abaixo estão classificadas por etapa do pipeline. Em cada etapa, listamos os erros, quando disponíveis, que são aplicáveis a essa etapa.

## Todas as etapas

Erros de recursão
:   *Mensagem* - "<informação> Err: Recursão detectada para <informação>" ou "Recursão ao tentar acessar a tabela"

    *Descrição* - Esse erro é como a mensagem Cycle Detected (Ciclo detectado), exceto pelo fato de que, nesse caso, a tabela é uma referência a si mesma e, portanto, essa parte da configuração não será calculada.

Ciclo detectado
:   *Mensagem* - "Ciclo detectado. Essa etapa não será calculada, pois está envolvida em uma referência circular. <table> faz referência a <table> (etapa do pipeline na outra tabela)."

    *Descrição* - O erro **Cycle Detected (Ciclo detectado** ) indica que essa etapa do pipeline está sendo totalmente ignorada. Isso ocorre porque calculá-lo resultaria em uma referência circular e, portanto, seu modelo não poderia ser calculado. Para resolver esse problema, você deve decidir qual lado da referência circular deseja manter e excluir ou alterar o outro lado da referência circular para remover a circularidade.

    ![](../../resources/images/studio_images/studioimages/studio_append_cycle%20detected.png)

    Observação: essa mensagem de erro foi introduzida em TBM Studio v12.3.4. Antes disso, outras mensagens de erro específicas da etapa ocorriam em algumas etapas, e não eram detectadas algumas circularidades que agora são encontradas.

## Mensagem de erro de origem

Conversão de cadeia dupla
:   *Mensagem* - A tabela que aciona isso normalmente apresenta um erro como o seguinte:

    "Pesquisa incompatível da coluna "< table.Column >" do tipo "<Type>" ("<varies>") para a coluna “<Column2>” do tipo "<Type>" ("<varies>")"

    *Descrição* - Esse erro significa que outra tabela está referenciando a coluna especificada com a expectativa de que ela seja do tipo Label, mas ela é uma coluna numérica ou teve valores numéricos nela.

    Para solucionar esse erro, é possível:

    - Alterar o tipo de coluna na tabela local ou na tabela remota para que as colunas correspondam; ou
    - Fazer conversão de tipo explícito.

    **Outros erros em tabelas com uma fonte de Tabela existente** - Para uma tabela que se baseia em outra tabela, os erros na outra tabela serão exibidos na etapa de origem em algumas situações. Examine a tabela de origem para obter mais informações sobre essa situação.

## Mensagem de erro da tabela existente

Erro ao obter a tabela de backup "<nome da tabela>
:   *Mensagem* - "Erro ao obter a tabela de apoio '<nome da tabela>'"

    *Descrição* - Esse erro normalmente significa que a tabela de origem foi excluída. Para resolver isso, crie uma tabela com o nome específico da tabela.

## Mensagens de erro de importação

Etiqueta de tipo incompatível
:   *Mensagem* - "Rótulo de tipo esperado, mas encontrado numérico"

    *Descrição* - Esse erro ocorrerá se o tipo de entrada especificado para a coluna for Rótulo, mas cada valor na coluna puder ser analisado como um número. Se for esperado que essa coluna tenha valores numéricos OU valores de rótulo, mas você quiser que ela seja armazenada como um rótulo, faça o seguinte:

    1. Deixe **o Type Override** definido como **Label**.
    2. Altere o **tipo de entrada** para **Any**.![](../../resources/images/studio_images/studioimages/studio_import%20error_mismatched%20type%20label.png)

A coluna não existe
:   *Mensagem* - "A coluna não existe"

    *Descrição* - Esse erro significa que as regras de validação de dados foram configuradas para esperar uma coluna, mas ela não existe no upload mais recente. Se você não quiser essa coluna na tabela, exclua-a da regra de validação. Caso contrário, adicione-o à sua tabela e faça o upload novamente.

    ![](../../resources/images/studio_images/studioimages/studio_validation%20framework_remove%20column.png)

Coluna incluída
:   *Mensagem* - "A coluna foi adicionada"

    *Descrição* - Isso significa que as regras de validação de dados foram configuradas para não esperar uma coluna, mas ela existe no upload mais recente. Se você quiser essa coluna na tabela, adicione-a a partir da regra de validação. Caso contrário, exclua-o em sua tabela e faça o upload da tabela novamente.

    ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio_columns_add.png)

Etiqueta de tipo desconhecido
:   *Mensagem* - "Rótulo de tipo esperado, mas encontrado desconhecido"

    *Descrição* - Esse erro ocorrerá se o tipo de entrada estiver definido como "Rótulo" e a coluna não contiver nenhum valor. Para resolver isso, adicione valores à coluna ou altere o "Incoming Type" (Tipo de entrada) para "Any" (Qualquer).

    ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio_columns_pick.png)

Tipo desconhecido
:   *Mensagem* - "Esperava-se o tipo <Numérico/Rótulo>, mas foi encontrado desconhecido"

    *Descrição* - Esse erro ocorrerá se o tipo de entrada estiver definido como Numérico ou Rótulo e a coluna não contiver nenhum valor. Para resolver isso, adicione valores à coluna ou altere o Tipo de entrada para Qualquer.

    ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio_columns_numeric.png)

Cardinalidade
:   *Mensagem* - "Cardinalidade esperada <MANY/ONE>, mas encontrada <Many/ONE)"

    *Descrição* - Esse erro ocorrerá se sua etapa **de importação** tiver sido configurada para validar a cardinalidade e a cardinalidade for alterada. Se você não quiser validar a cardinalidade, marque a caixa de seleção **Ativar validação de cardinalidade**. Caso contrário, corrija a cardinalidade em seu arquivo carregado:

    ![](../../resources/images/studio_images/studioimages/studio_validation%20framework_%20column%20does%20not%20exist.png)

## Anexar mensagens de erro

Vários tipos de valores
:   *Mensagem* - Exemplo de mensagem completa: "Entrega: Vários tipos de valores para a coluna Entrega: [LABEL in Business Services Transform], [UNKNOWN in All Business Services]"

    *Descrição* - Sua etapa Append está mapeando colunas de um tipo diferente.

    Como corrigir isso:

    Certifique-se de que todos os conjuntos de dados tenham um tipo definido na coluna e que esse tipo seja idêntico em todos os conjuntos de dados. O tipo pode ser definido em uma etapa **de importação** ou na etapa de **fórmulas**. Para tabelas editáveis, você pode adicionar uma etapa **de Fórmulas**, adicionar as colunas editáveis a ela e definir um tipo para elas.

    Se não for possível tornar o tipo idêntico, na etapa *Anexar*, você poderá converter o tipo entre **Numérico** e **Rótulo** usando as fórmulas a seguir:

    - Para converter um valor numérico em um rótulo: = NumberFormat(column,”#,###” )
    - Para converter um rótulo em um número: =Value(column)

## Outros erros

*Mensagem* - Varia.

*Descrição* - Verifique o erro na seção "Etapa da fórmula" deste documento. Como você pode digitar uma fórmula arbitrária em uma etapa **Append**, isso pode gerar os mesmos erros que em uma etapa **Formulas**.

## Mensagens de erro do grupo

Coluna ausente
:   *Mensagem* - "Não é possível encontrar a coluna 'coluna'"

    *Descrição* - Você receberá esse erro se a operação de agrupamento estiver configurada para agrupar em uma coluna que não existe mais. Para resolver isso, atualize a etapa de agrupamento para agrupar em uma coluna existente.

Coluna não especificada
:   *Mensagem* - "Nenhuma coluna especificada"

    *Descrição* - Você precisa especificar uma coluna para agrupar na etapa Group (Grupo). Você pode ignorar esse erro com segurança.

## Ocultar e renomear a mensagem de erro

Não é possível encontrar a coluna
:   *Mensagem* - "Não é possível encontrar a coluna"

    *Descrição* - A etapa de ocultar e renomear está fazendo referência a uma coluna que não existe.

    Para resolver isso:

    - remover a referência a essa coluna do hide e renomear
    - ou adicioná-lo a uma etapa anterior do pipeline

      ![](../../resources/images/studio_images/studioimages/studio_hide%20and%20rename_column%20to%20replace.png)

## Mensagens de erro de fórmula

Não é possível encontrar a coluna
:   *Mensagem* - "Não é possível encontrar a coluna chamada '<coluna>' na tabela '<tabela>'"

    *Descrição* - A fórmula está fazendo referência ao nome da coluna especificada na tabela especificada. No entanto, a coluna não existe nessa tabela.

    Para resolver isso, ou:

    - adicionar a coluna a essa tabela
    - ou corrija sua fórmula para não fazer referência a uma coluna inexistente.

Não é possível encontrar a coluna
:   *Mensagem* - "Não é possível encontrar a coluna chamada '<coluna>'"

    *Descrição* - A fórmula está fazendo referência ao nome da coluna especificada na tabela atual. No entanto, a coluna não existe.

    Para resolver isso, ou:

    - adicionar a coluna a essa tabela em uma etapa anterior do pipeline
    - ou corrija sua fórmula para não fazer referência a uma coluna inexistente

Não é possível encontrar a coluna
:   *Mensagem* - "Não é possível encontrar a coluna chamada '<coluna>' na etapa anterior da tabela '<tabela>'"

    *Descrição* - A fórmula está fazendo referência ao nome da coluna especificada na tabela atual. No entanto, a coluna não existe. Esse erro será apresentado por fórmulas que só podem aproveitar colunas da etapa anterior (não da etapa atual de Fórmulas).

    Para resolver isso, ou:

    - adicionar a coluna a essa tabela em uma etapa anterior do pipeline
    - ou corrija sua fórmula para não fazer referência a uma coluna inexistente

Pesquisa incompatível
:   *Mensagem* - "Pesquisa incompatível da coluna '< table.Column >' do tipo '<Type>' ('<varies>') para a coluna ' <Column2> ' do tipo '<Type>' ('<varies>')"

    *Descrição* - As duas colunas também:

    1. Ter tipos diferentes. Nesse caso, também:
       1. Altere o tipo de uma das colunas para que elas correspondam
       2. Ou converta explicitamente o tipo:
          - Para converter um valor numérico em um rótulo: = NumberFormat(column,”#,###” )
          - Para converter um rótulo em um número: =Value(column)
    2. Valores inseridos em uma coluna que não mapeiam o tipo da coluna. Nesse caso:
       - Se o erro indicar <LABEL> ("long"), isso significa que a coluna especificada é do tipo Label, mas contém valores numéricos. Se você receber esse erro, volte à tabela referenciada e corrija explicitamente os valores nessa coluna para garantir que eles tenham o tipo correto.
       - Se o erro indicar <Numeric> ( “BoxedStringOffset” ), isso significa que a coluna especificada é do tipo Numeric, mas contém valores Label. Se você receber esse erro, volte à tabela referenciada e corrija explicitamente os valores nessa coluna para garantir que eles tenham o tipo correto.

Não é possível encontrar a tabela
:   *Mensagem* - "Não é possível encontrar a tabela"

    *Descrição* - Isso significa que a fórmula faz referência a uma tabela que não existe. Esse erro também poderá ser observado se a tabela de destino for um objeto de modelo atualizado a partir de TBM Studio v11, pois não há uma etapa **de tabela**. Para resolver isso, atualize a fórmula para fazer referência a uma tabela que tenha uma etapa Table.

Formato de número
:   *Mensagem* - "Não é possível formatar NaN de {}: <a string>"

    *Descrição* - Esse erro será chamado pela função Numberformat quando for passado um valor do tipo Label. Se você passar um rótulo para a função de formato de número, ela tentará convertê-lo em um número usando o formato de número padrão. Se ele puder ser processado, você não receberá nenhuma mensagem de erro. Se não puder ser processado, você receberá este erro.

    Para resolver isso, atualize sua configuração para chamar a função NumberFormat somente em colunas do tipo Numeric, que contêm apenas valores numéricos.

    **Erros envolvendo colunas que usam instruções IF** - Em muitos casos, as instruções IF tentam avaliar a condicional e os dois resultados possíveis em paralelo, para melhorar o desempenho do cliente. Como resultado, se uma fórmula gerar um erro para a ramificação true ou false, o erro será exibido mesmo que essa ramificação não seja usada para nenhuma linha que possa acionar o erro.

## Mensagem de erro da partição de data

**Não é possível encontrar a coluna**

*Mensagem* - "<Nome da coluna>: Não é possível encontrar a coluna"

*Descrição* - Esse erro normalmente indica que a etapa Partição de data foi configurada para usar uma coluna de tempo que, desde então, foi excluída da tabela. Para resolver isso, adicione essa coluna de volta à tabela de apoio.

## Mensagem de erro de desdobramento

A coluna não existe
:   *Mensagem* - "<Nome da coluna>: A coluna não existe"

    *Descrição* - A etapa Unpivot faz referência a uma coluna que não existe. Remova-o da configuração Unpivot ou adicione a coluna de volta à tabela.

## Mensagens de erro de etapa do modelo

Atribuição ao objeto
:   *Mensagem* - "A fórmula de alocação para o objeto <objectName>:USE\_MAP\_TABLE não pode ser usada com filtros do objeto <objeto>"

    *Descrição* - Há duas situações em que você pode receber esse erro:

    1. Você está usando uma regra de Valor ponderado e o Relacionamento de dados é um Relacionamento automático com a opção Muitos para muitos ativada. Há também um filtro especificado na etapa From (De). O recurso legado de alocação automática de muitos para muitos não oferece suporte a filtros na etapa De. Esse recurso existe para compatibilidade com versões anteriores para clientes do TBM Studio v11 e se comporta da mesma forma que no R11 e anteriores. Para eliminar esse erro, faça o seguinte:
       - Remova o filtro da etapa **De**. Isso não alterará seus números, pois o filtro está sendo ignorado no momento.
       - Ou, em vez disso, desative o relacionamento automático e use chaves explícitas.

         Observação: Isso mudará seus números, pois o filtro agora será usado.
    2. Você está usando uma fórmula de alocação avançada que aproveita a função USE\_MAP\_TABLE. Há também um filtro especificado na etapa From (De). A função USE\_MAP\_TABLE herdada não é compatível com filtros na etapa From step.To. Para eliminar esse erro, remova o filtro da etapa 'From'. Isso não alterará seus números, pois o filtro está sendo ignorado no momento. Se quiser que o filtro seja aplicado, filtre a tabela que está passando para a função USE\_MAP\_TABLE em seu pipeline de transformação.

Ligações de colunas não encontradas
:   *Mensagem* - "Não foram encontrados vínculos de colunas de <table> para <table> < table.column > foi agrupado e não pode ser usado para transferir valores. < table.column > foi agrupado e não pode ser usado para transferir valores. (A detecção automática de Muitos->Muitos está desativada)."

    *Descrição* - Se esse erro ocorrer, essa etapa de modelagem tem uma alocação para outra tabela listada que está usando o recurso de alocação automática legado. Para resolver isso, passe a usar chaves explícitas em seu relacionamento de dados de alocações.

    **O que isso significa:**

    No objeto de origem, a coluna de identificador do objeto de destino é nula ou variada (conforme trazido pela etapa Join), e no objeto de destino, a coluna de identificador do objeto de origem é nula ou variada (conforme trazido pela etapa Join). As alocações automáticas legadas dependem de uma delas ser não-vária e não-nula para alocações que não sejam automáticas de muitos para muitos. Recomenda-se desativar as alocações automáticas de chaves legadas para resolver esse problema.

    Observação: a alocação individual que está causando esse problema pode não estar sinalizada como quebrada.

Chaves vinculadas não encontradas
:   *Mensagem* - "Não foi possível encontrar chaves vinculadas de <Tabela de origem> para <Tabela de destino>"

    *Descrição* - Esse erro ocorrerá se o objeto de origem não existir:

    - A partir da etapa **anterior** do pipeline, não é possível computar sua tabela. Esse erro também pode ocorrer algumas vezes se a tabela não contiver nenhuma linha.
    - As colunas de alocação foram especificadas diretamente, e uma delas não existe na respectiva tabela;
    - A alocação está usando as alocações "Automáticas" que existem para compatibilidade retroativa com R11, e a tabela de destino não contém a coluna de identificador da tabela de origem.

    Para resolver isso, adicione a coluna ausente ou atualize o relacionamento de dados para usar as colunas existentes.

Chave de modelo não encontrada
:   *Mensagem* - "Não foi possível encontrar a chave de modelo necessária na tabela totalmente vinculada: <table>.<Column>"

    *Descrição* - Esse erro ocorrerá se a etapa Modelo estiver configurada para usar uma coluna de identificador e a coluna de identificador configurada não existir. Para resolver isso, adicione novamente a coluna nomeada ou escolha um identificador diferente.
