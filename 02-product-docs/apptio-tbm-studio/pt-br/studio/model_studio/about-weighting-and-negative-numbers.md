---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Sobre ponderação e números negativos"
breadcrumb: []
source_path: "studio/model_studio/about-weighting-and-negative-numbers.html"
images:
  - "resources/images/studio_images/studioimages/studio_allocation_destination.png"
  - "resources/images/studio_images/studioimages/studio_cost-metric_gl-with-credits.png"
  - "resources/images/studio_images/studioimages/studio_data-issue_cost-pool-weight.png"
  - "resources/images/studio_images/studioimages/studio_diagram_cost_line_item_to_vendors.jpg"
  - "resources/images/studio_images/studioimages/studio_diagram_cost_source_and_allocations.jpg"
  - "resources/images/studio_images/studioimages/studio_diagram_credits_and_debits.jpg"
  - "resources/images/studio_images/studioimages/studio_diagram_net_positive_weighting.jpg"
  - "resources/images/studio_images/studioimages/studio_diagram_net_positive_weighting_with_extremes.jpg"
  - "resources/images/studio_images/studioimages/studio_diagram_target_object.jpg"
  - "resources/images/studio_images/studioimages/studio_disagram_first_gl_line_item.jpg"
  - "resources/images/studio_images/studioimages/studio_formulas_cost_per_weight.jpg"
  - "resources/images/studio_images/studioimages/studio_gl-with-credits_destination.png"
  - "resources/images/studio_images/studioimages/studio_gl_with_credits_cost_center.jpg"
  - "resources/images/studio_images/studioimages/studio_gl_with_credits_delimited_data_import_options.jpg"
  - "resources/images/studio_images/studioimages/studio_gl_with_credits_new_object_identifier.jpg"
  - "resources/images/studio_images/studioimages/studio_gl_with_credits_source_record.jpg"
  - "resources/images/studio_images/studioimages/studio_gl_with_credits_target_object.jpg"
  - "resources/images/studio_images/studioimages/studio_steps_table.png"
  - "resources/images/studio_images/studioimages/studio_weighted_value_examples.jpg"
  - "resources/images/studio_images/studioimages/studio_weighting_gl_with_credits.jpg"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Sobre ponderação e números negativos

aplica-se a: TBM Studio 11.8.3.1 e posterior; TBM Studio 12.0 e posterior. O objetivo de uma ponderação é alocar o número de origem onde a **soma** é a mesma no destino.

A ponderação por números negativos pode resultar em resultados inesperados. Em Apptio TBM Studio, versão 12, Apptio define os padrões para não alocar quando ponderações negativas estiverem em uso. Os motivos para definir esse padrão são descritos neste artigo, juntamente com exemplos de cenários em que pode ser legítimo ponderar por valores negativos, os riscos inerentes à ativação desse recurso e maneiras de lidar com essas alocações com segurança.

## Por que a ponderação negativa não está ativada por padrão

Quando é criada uma alocação que tenta ponderar por um conjunto de valores, que inclui números negativos, podem ocorrer vários problemas. Discutimos alguns dos problemas comuns aqui e enfatizamos a importância de compreender os riscos.

Para sua referência, a planilha usada para dar suporte a esses exemplos está anexada no final deste artigo, na seção **ANEXOS**.

## Exemplo

Primeiro, para acentuar como as coisas podem dar errado de uma forma altamente visual, suponha que você tenha uma alocação que pondera por números positivos e negativos, mas em que um dos valores de ponderação é pequeno em relação aos outros. Nesse exemplo, US$ 100 são alocados em três linhas na meta, mas com uma ponderação positiva grande, uma negativa grande e uma positiva pequena. Observe os resultados extremos nas linhas de recebimento da tabela a seguir.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio_diagram_net_positive_weighting_with_extremes.jpg)

Como a divisão por zero é uma impossibilidade lógica, o Standard for Floating-Point Arithmetic (Padrão para Aritmética de Ponto Flutuante) define limites para a representação de zeros, que são efetivamente números positivos ou negativos minúsculos. Apptio como qualquer outro software, adere a esse princípio e, portanto, o pequeno número positivo neste exemplo está presente mesmo quando a interface do usuário do Apptio pode mostrar um valor 0. Assim, com as ponderações negativas ativadas, é possível ver uma explosão repentina de valores nos objetos downstream que estão sendo alocados.

## Exemplos mais comuns

Nas tabelas de ponderação a seguir, vemos três exemplos: um exemplo líquido positivo, um exemplo líquido zero e um exemplo líquido negativo. Em cada exemplo, observe que os valores na meta, embora somados ao valor original, criam a inflação ou a deflação do valor nas linhas individuais da meta.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio_weighted_value_examples.jpg)

## Um exemplo insidioso

A tabela de ponderação a seguir é outro exemplo positivo líquido, mas sutil e, portanto, pode passar despercebido. Nesse exemplo, o valor líquido das linhas de destino não é muito diferente do que em um conjunto maior de alocações em que não poderia ser perdido. Nesse caso, os valores nos objetos downstream podem ser sutilmente distorcidos de forma a gerar números imprecisos.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio_diagram_net_positive_weighting.jpg)

## Situações que podem exigir ponderações negativas

Cenários de débito/crédito
:   Uma situação comum é quando há débitos e créditos em um livro-razão ou fatura. Por exemplo, a fatura de um fornecedor pode incluir tanto créditos quanto débitos em uma conta, como nas faturas de serviços de nuvem. Quando isso ocorrer, talvez você queira ponderar por números negativos (créditos).

Re-classificação de horas de trabalho
:   Outra situação em que as ponderações negativas são apropriadas é a reclassificação das horas de trabalho. Por exemplo, em um mês, alguém envia horas para o Projeto A e, mais tarde, percebe que pretendia enviar horas para o Projeto B. Assim, no próximo mês, eles "creditam" horas ao Projeto A enviando um número negativo.

## Opções para ponderações negativas

Use ponderações negativas seletivamente com uma fórmula
:   A fórmula a seguir pode ser usada como parte de uma alocação com fórmula avançada para habilitar seletivamente ponderações negativas. Observe que isso não evita a possibilidade de problemas como os descritos anteriormente neste artigo, apenas limita sua exposição a eles. O uso de uma fórmula é preferível a permitir alocações negativas para todo o ambiente, pois reduz o risco de ocorrência de resultados inesperados quando não prevemos a necessidade de ponderações negativas.

    ```
    =SOURCE *
            ({Table.Weighting}/~{Table.Weighting})
    ```

    Onde o seguinte se aplica ao conjunto de linhas que estão associadas por meio de um relacionamento de dados ( v12 ) ou chave ( r11 ).

    - **SOURCE** é o valor de origem que está sendo alocado por meio da relação.
    - **~** é o operador de rollup que soma os valores na coluna de ponderação para a relação dada.
    - O **Table.Column** (ou métrica) deve ser sempre idêntico no numerador e no denominador da fórmula. Caso contrário, você não estará criando uma relação válida.

O principal valor do uso dessa fórmula é permitir que você ative seletivamente ponderações negativas para uma alocação específica. Isso ajuda a protegê-lo dos riscos descritos no início deste artigo.

## Segregação de valores de origem negativos e ponderação por valores absolutos

Outra estratégia para lidar com valores negativos é segregá-los na fonte e usar o valor absoluto para ponderar. No exemplo a seguir de uma fatura com créditos, o total (incluindo os créditos) é instalado no Razão como um único item de linha com a soma de US$ 100. Em seguida, ele é alocado ao objeto Vendors (para dar suporte a relatórios prontos para uso), ponderado pelos valores da fatura. Como a fatura inclui créditos, obtemos números incorretos na meta.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio_diagram_cost_line_item_to_vendors.jpg)

Se, em vez disso, segregarmos os créditos no Razão/fonte de custos e garantirmos que o relacionamento/chave de dados preserve a segregação, poderemos usar o valor absoluto da fatura, incluindo os créditos:

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio_disagram_first_gl_line_item.jpg)

Isso resulta em números precisos no alvo.

## Exemplo 1: um problema de dados

Nesta seção, apresentamos um cenário simples do mundo real em que uma ponderação negativa impede uma alocação. Esse também é um exemplo de uma situação em que a ponderação negativa não foi intencional. Nesse caso, uma fórmula baseada em dados que fluíam para o sistema deu errado e criou alguns valores negativos de forma não intencional.

Aqui, vemos uma alocação da fonte de custos para o Ledger de ativos fixos que não está funcionando, e o usuário está ciente disso.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio_diagram_cost_source_and_allocations.jpg)

Quando a alocação é examinada mais de perto, o problema não é óbvio.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio_allocation_destination.png)

No entanto, quando classificamos o Cost Pool Weight em ordem crescente, vemos dois pequenos valores negativos:

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio_data-issue_cost-pool-weight.png)

Observação: Como nem sempre é óbvio, é recomendável verificar as colunas de ponderação classificando-as em ordem crescente se você encontrar uma alocação que pareça estar configurada corretamente.

Nesse caso, o peso do pool de custos foi obtido por meio de uma fórmula (mostrada abaixo). A combinação de positivos e negativos era proveniente de duas fontes de dados anexadas diferentes como parte da automação da alocação. No entanto, uma combinação de positivos e negativos não foi prevista e, portanto, o problema só apareceu quando os uploads incluíram valores de depreciação negativos. Nesse caso, a solução foi corrigir os dados.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio_formulas_cost_per_weight.jpg)

## **Exemplo 2: Use a fórmula de ponderação em uma alocação para representar créditos**

Às vezes, uma empresa tem entradas no razão geral que contêm créditos de faturas que deseja mostrar nos relatórios. O local em que eles desejam exibir os créditos pode variar, mas, neste exemplo, mostramos os créditos em um objeto de destino ao qual a fonte do razão geral é alocada. Os dados brutos são de três centros de custo: CC1, CC2, e CC3. CC1 tem apenas débitos, mas CC2 e CC3 têm uma combinação de débitos e créditos.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio_gl_with_credits_source_record.jpg)

O livro-razão com a tabela Créditos tem um driver baseado na coluna Valor e o identificador de objeto da tabela é Centro de custo. Isso resulta em valores líquidos para CC1, CC2 e CC3 de US$ 900, US$ 0 e US$ 400, respectivamente.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio_gl_with_credits_cost_center.jpg)

Nenhum dólar está sendo alocado:

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio_cost-metric_gl-with-credits.png)

Neste exemplo, os dados brutos de nosso objeto de destino são idênticos aos de nossa origem e usam o UID como identificador de objeto. Isso não é incomum em cenários reais em que uma empresa tem itens de linha do razão geral (GL) que sabe que somam os valores de uma fatura ou anexa os detalhes da fatura ao GL, substituindo os itens de linha originais do GL. Aplicamos a fórmula de ponderação. CC1 e CC3 recebem os valores esperados, mas como CC2 foi zero líquido em GL com Créditos, não recebemos nada nessas linhas:

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio_gl-with-credits_destination.png)

A fórmula funcionou: as ponderações negativas foram ativadas e, quando os números não chegaram a zero, obtivemos os resultados esperados. No entanto, no caso em que um débito e um crédito somavam zero na origem, o sistema não alocava. Portanto, não obtivemos nenhum valor no alvo.

No próximo exemplo, abordamos tanto a ponderação negativa quanto o zero líquido na fonte.

## Exemplo 3: Usando a segregação de positivos e negativos em uma alocação para representar créditos

Neste exemplo, nosso objetivo é o mesmo que no exemplo anterior. Estamos usando os mesmos dados brutos para o GL. No entanto, em vez de usar a fórmula de ponderação, separamos os valores negativos e positivos na origem e no destino para que possamos usar o valor absoluto da coluna Value para ponderar e, assim, obter exatamente o que queremos no destino. Além disso, os dados de apoio do nosso objeto de destino não incluem a granularidade da origem, portanto, devem ser modificados para suportar a exibição de créditos e segregar negativos e positivos.

Mais uma vez, os dados brutos são para três centros de custo: CC1, CC2, e CC3. CC1 tem apenas débitos, mas CC2 e CC3 têm uma combinação de débitos e créditos.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio_gl_with_credits_delimited_data_import_options.jpg)

Como em nosso último exemplo, o identificador de objeto da tabela era Centro de custo, e o relacionamento de dados é baseado no Centro de custo. Portanto, queremos adicionar granularidade onde existem negativos. Poderíamos usar a coluna UID nos dados brutos, mas isso aumentaria desnecessariamente a granularidade do nosso modelo. Isso pode ter impactos negativos sobre o desempenho em um grande projeto. Portanto, em vez disso, adicionamos uma coluna de fórmula chamada CC Credits and Debits (Créditos e débitos CC), conforme mostrado abaixo. Também adicionamos uma coluna de fórmula chamada CC Negatives.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio_weighting_gl_with_credits.jpg)

Modificamos o identificador de objeto para usar a nova coluna de fórmula:

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio_gl_with_credits_new_object_identifier.jpg)

Em seguida, examinamos nossa tabela de destino:

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio_steps_table.png)

Para manter os valores negativos e positivos segregados e obter os números corretos no alvo, precisamos adicionar granularidade a essa tabela. Para fazer isso, adicionamos as seguintes colunas de fórmula:

- CC Negatives - Soma os CC Negatives no objeto de origem com base no centro de custo no destino.
- Type Helper - Se CC Negatives indicar que há créditos em um centro de custos, o valor será Debit,Credit. Caso contrário, é débito.
- Type - Divide as linhas com base no valor do Type Helper.
- CC Credits and Debits (Créditos e débitos CC) - Mescla os dados do centro de custo e do tipo para formar o novo identificador de objeto e a coluna de relacionamento de dados.
- Peso - Soma os valores na fonte com base em Créditos e Débitos CC e obtém o valor absoluto.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio_diagram_target_object.jpg)

Em seguida, configuramos o identificador de objeto:

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio_diagram_credits_and_debits.jpg)

Por fim, configuramos a alocação:

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio_gl_with_credits_target_object.jpg)

Isso nos permite exibir os créditos com precisão nos relatórios com base no objeto de destino com o menor aumento possível na granularidade do nosso modelo.
