---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Criar e gerenciar métricas"
breadcrumb: []
source_path: "studio/model_studio/introduction-to-metrics.html"
images:
  - "resources/images/studio_images/studioimages/modelreport_dialog.png"
  - "resources/images/studio_images/studioimages/modelreport_edit_button.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Criar e gerenciar métricas

**Aplica-se a** : TBM Studio 12.0 e posterior

As métricas são cálculos que definem medidas para relatórios. As métricas definidas para cada projeto estão disponíveis para todos os relatórios do projeto em todos os períodos de tempo. As métricas estão listadas na seção **Métricas** do **Project Explorer**. Para definir uma nova métrica, abra o menu **New (Novo** ) na guia **Home (Página inicial** ) e clique em **Metric (Métrica** ).

## Tipos de métricas

Há dois tipos de métricas:

- **Métricas modeladas**. Um modelo é, por si só, uma métrica. Um modelo calcula um valor numérico, como custo, quantidade ou orçamento. Um modelo pode ter várias métricas. Os modelos também são chamados de métricas modeladas.
- **Métricas calculadas**. Uma métrica calculada usa uma fórmula para derivar um valor numérico. Por exemplo, você poderia criar uma métrica calculada chamada **Budget\_Variance** definida como a métrica modelada pelo orçamento menos a métrica modelada pelo custo.

Os valores calculados pelas métricas geralmente são exibidos em relatórios por meio de gráficos. As métricas, uma vez definidas, ficam disponíveis para todos os relatórios em um projeto e em todos os períodos de tempo.

Há várias diferenças importantes entre as métricas modeladas e calculadas:

- Ao agrupar, as métricas do modelo somam números. As métricas calculadas são recalculadas.
- As métricas calculadas podem ser calculadas ao longo do tempo. As métricas modeladas não podem.

A seguir, há várias diretrizes que podem ajudá-lo a determinar o tipo de métrica a ser criada:

- Se você tiver um atributo que se aplicará a várias áreas diferentes, crie uma métrica **modelada**. Um ótimo exemplo é o Custo, que é a métrica de modelo padrão no aplicativo. Um modelo de custo pode ser usado para analisar o custo de muitas áreas em diferentes níveis de sua organização.
- Se você quiser alocar um valor numérico de um elemento da organização para outro, crie uma métrica **modelada**. Por exemplo, se você quiser alocar o custo dos servidores aos aplicativos, é melhor fazer isso com uma métrica modelada.
- Se você tiver um atributo que será usado para apenas um cálculo, crie uma métrica **calculada**. Um exemplo pode ser o número de servidores ou o número de tíquetes de problemas.

## Criar uma métrica

Para criar uma métrica:

1. Na guia Página **inicial**, no grupo **Documento**, clique em **Novo** e, em seguida, clique em **Métrica**.
2. Digite um nome para a métrica e clique em **OK**.
3. Preencha os campos no painel **Propriedades**. Consulte as seguintes descrições detalhadas em nível de campo em **Propriedades de métrica**.
4. Clique em **Salvar**.

## Excluir uma métrica

Para excluir uma métrica:

1. No **Project Explorer,** clique em **Metrics**.
2. Clique na métrica que deseja excluir.
3. Verifique a métrica, caso ainda não tenha sido verificada.
4. Na guia Página **inicial**, no grupo **Documento**, clique em **Excluir** e, em seguida, clique em **Salvar**.
5. Verifique a métrica.

## Selecionar métricas para melhorar o desempenho

Você pode usar o botão **Editar métricas** no Tier Editor para especificar quais métricas deseja aplicar a um relatório de modelo. As métricas selecionadas são salvas no check-in, o que acelera os cálculos nos ambientes de preparação e produção. A seleção de menos métricas resulta em cálculos mais rápidos.

Para selecionar (editar) as métricas do modelo para um novo relatório:

1. Em TBM Studio, clique em **New > Model Report**.
2. Clique em **Edit Metrics (Editar métricas** ) para abrir a caixa de diálogo **Model Report (Relatório de modelo** ).

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/modelreport_edit_button.png)
3. (Opcional) Clique em **None (Nenhum** ) para limpar a lista de verificação.
4. Selecione as métricas que deseja aplicar ao seu novo relatório de modelo.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/modelreport_dialog.png)
5. (Opcional) Adicione uma **descrição**.
6. Clique em **OK**.
7. Clique em **Exibir > Mostrar documento**. Observe que as opções disponíveis no seletor **Selecionar uma métrica** agora estão limitadas às métricas selecionadas na caixa de diálogo **Relatório de modelo**.

Para limitar as métricas calculadas para um relatório de modelo existente:

1. Abra o relatório e clique em **Exibir > Mostrar documento > Editar métricas**.
2. Selecione apenas as métricas que deseja aplicar ao relatório e clique em **OK**.

## Propriedades métricas

As propriedades da métrica controlam o comportamento de uma métrica no projeto. Usando as propriedades da métrica, você pode selecionar o nome da métrica, o tipo, o formato e se a métrica aparece nas tabelas de unidades. As propriedades métricas são descritas abaixo. As propriedades que se aplicam somente às métricas calculadas são marcadas com um asterisco (\*).

- **Visualização padrão** - Se a métrica for exibida em um relatório como um link, clicar no link exibirá o relatório inserido nesse campo.
- **Tipo de modelo** - Ao criar uma métrica, selecione o tipo de modelo.
  - **Model** - Cria um novo modelo no modelador.
  - **Calculado** - Exibe o campo **Cálculo do valor**, no qual você insere uma fórmula ou função para definir como a métrica é derivada. Depois que a métrica é criada, esse campo se torna somente leitura.
- **Ignorar para filtragem interna\*** - Quando marcada, as métricas calculadas são excluídas na avaliação para filtrar as linhas que têm todos os zeros. Essa avaliação ocorre mesmo que as métricas estejam ocultas. As linhas com zeros em todas as colunas podem ser incluídas desmarcando a opção.
- **Pode somar\*** - Se for válido somar os valores desse cálculo em vez de recomputar a fórmula ao calcular, marque a caixa.
- **Incluir em modelos virtuais\*** - Se você quiser que a métrica seja incluída em modelos filtrados e recursivos, marque a caixa.
- **Metric Type (Tipo de** métrica) - Se os valores de métrica forem monetários de uma fonte totalmente custeada, como um razão geral, selecione **Costing (Custeio** ). Se você selecionar **Cálculo de custos**, também deverá definir o formato da tabela como **Moeda**.
  - Se a métrica estiver associada a um modelo de preço x quantidade, selecione **Pricing (Preço)**.
  - Se os valores métricos estiverem em qualquer outro formato, selecione **Numérico**.
- **Oculto** - Oculta a métrica nas tabelas de unidades de objetos do modelo.
- **Cálculo do valor\*** - Insira uma fórmula que defina o valor da métrica calculada (consulte [Fórmulas e funções](../formulas-and-functions/introduction-to-formulas-and-functions.html "Aplica-se a: TBM Studio 12.0 e posterior") ).
  - Para se referir a uma coluna em uma tabela, use o formato **table.column name**.
  - Para fazer referência a uma coluna em uma tabela em outro projeto, use o formato **project!table:column name**.
  - Para recuperar a soma de todos os valores em uma coluna da tabela, use o formato **table:column name**.
  - Para recuperar a soma dos valores em uma coluna em que uma segunda coluna é igual a um valor específico, use o formato **table:column[ column2= "value"]**.
  - Para recuperar a soma dos valores em uma coluna em que uma segunda coluna é igual ao valor do valor table.column da linha atual, use o formato **table:column[ column2=table.column name]**.
  - Você pode se referir à métrica atual usando **$\_** em vez de ter que digitar o nome completo da métrica. Isso é útil se você quiser usar a mesma fórmula em várias métricas. Você pode copiar e colar a fórmula sem precisar substituir o nome da métrica todas as vezes.
- **Formato da tabela** - Especifica o formato do valor da métrica quando exibido nas tabelas do relatório. Você pode especificar formatos em HTML ou usar a função [NumberFormat](../formulas-and-functions/functions/numberformat.html "Formata um valor numérico em um rótulo (string) usando padrões personalizados para números positivos e negativos, durações ou formatação de tamanho de dados. Essa função foi projetada para uso em colunas do tipo Label.") função.
  - Para exibir valores como dólares em modelos, digite: =Currency($\_).
  - Para especificar formatos usando uma caixa de diálogo em vez de código, clique no ícone **Table Format (Formato de tabela)** ![](../../resources/images/studio_images/studioimages/table+format%20icon.png).
  - Se você selecionar Advanced (Avançado), deverá inserir uma fórmula manualmente, da mesma forma que faz no campo **Table Format (Formato da tabela** ) do painel **Properties (Propriedades** ). Se você selecionar outro formato, a caixa de diálogo exibirá as opções de formatação apropriadas. Para os formatos Número e Moeda, você pode optar por incluir separadores de "milhares" (vírgula, ponto, etc.) selecionando a opção **Usar separador de agrupamento**.
- **Modelos aplicáveis** - Esse campo é usado somente pelo grupo Apptio Applications e está relacionado ao **templates.apptio.com** projeto. NÃO edite esse campo.
- **Comportamento de tempo** - Especifica a operação quando a métrica é visualizada em um período de tempo agregado, como um trimestre.
  - **Soma** - Calcula cada período separadamente e, em seguida, soma os períodos.
  - **Média** - Calcula cada período separadamente, soma os períodos e, em seguida, divide o resultado pelo número de períodos.
  - **Recalcular** - Calcula os valores agregados em todas as colunas referenciadas pela métrica calculada e, em seguida, executa novamente a fórmula da métrica.
- **Chart Format (Formato de gráfico** ) - Insira um padrão a ser usado na formatação de números no eixo do gráfico. A sintaxe é a mesma dos padrões e padrões negativos usados pela função **NumberFormat** mas sem o nome da função ou aspas. Por exemplo, para que os números sejam exibidos em um formato como $ 5.000.000, você digitaria **$#,###**. Não é possível usar uma fórmula neste campo.
  - Se você quiser formatar os números como moeda, de modo que o símbolo de moeda reflita a localidade selecionada para o projeto, coloque no início da declaração de formato o símbolo Unicode de moeda universal (¤). A maneira mais fácil de fazer isso é copiar o símbolo da frase anterior e colá-lo no campo.
  - Para obter mais informações sobre a formatação de números, consulte a função.
- **Prefixo do gráfico** - Um prefixo a ser adicionado à métrica quando exibida em gráficos. Por exemplo, um sinal $.
- **Sufixo de gráfico** - Um sufixo a ser adicionado à métrica quando exibida em gráficos.
- **Intervalo de tempo\*** - **Nenhum**, **trimestral** ou **anual**. Se você definir essa opção como **Quarterly (Trimestral** ) ou **Yearly (Anual)**, a métrica será extraída do primeiro período no intervalo de tempo em vez de ser calculada. Por exemplo, se você selecionar **Yearly (Anual** ), a métrica voltará e procurará os valores de janeiro em vez de recalcular com base no período de tempo atual.
