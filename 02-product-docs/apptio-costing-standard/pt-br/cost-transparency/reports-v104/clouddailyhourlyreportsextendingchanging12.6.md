---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Relatórios diários/horários na nuvem - Extensão ou alteração ( 12.6 e posterior)"
breadcrumb: []
source_path: "cost-transparency/reports-v104/clouddailyhourlyreportsextendingchanging12.6.html"
images:
  - "resources/images/ct_images/clouddailyhourlyreportsextendingchanging12.6_1.png"
  - "resources/images/ct_images/clouddailyhourlyreportsextendingchanging12.6_2.png"
  - "resources/images/ct_images/clouddailyhourlyreportsextendingchanging12.6_3.png"
  - "resources/images/ct_images/clouddailyhourlyreportsextendingchanging12.6_4.png"
  - "resources/images/ct_images/clouddailyhourlyreportsextendingchanging12.6_5.png"
  - "resources/images/ct_images/clouddailyhourlyreportsextendingchanging12.6_6.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Relatórios diários/horários na nuvem - Extensão ou alteração ( 12.6 e posterior)

- Aplica-se a: Cloud em Costing Standard e Cloud Business Management em TBM Studio 12.6 e posterior

Para obter informações sobre os relatórios diários/horários em TBM Studio 12.5.x e anteriores, consulte [Relatórios diários/horários na nuvem - Extensão ou alteração ( 12.5 e anteriores)](clouddailyhourlyreportsextendingchanging12.6.html)

## Visão geral

Os relatórios diários/horários são criados em um formato de dados que permite armazenamento e consultas rápidas e eficientes em conjuntos de dados de volume muito alto, como contas de nuvem muito granulares, como o Relatório de custo e uso (CUR) do AWS. Como resultado, a extensão do esquema dos conjuntos de dados envolvidos e a modificação dos relatórios criados com base nesses conjuntos de dados exigem alguma configuração.

Os dados diários/hora são armazenados em um formato diferente, separadamente de outros dados do site Apptio. O objeto sobre o qual os relatórios são criados chama-se dbr\_daily, que pode ser encontrado na seção de tabelas do site TBM Studio, mas, devido ao volume extremamente alto de dados e ao novo formato de dados, algumas ações não podem ser executadas:

- Você não poderá ver os dados em TBM Studio.
- Não é possível adicionar itens ao pipeline de transformação (com a exceção explicada na seção "Adição de atributos novos e personalizados", abaixo).
- Não é possível adicionar transformações ao conjunto de dados.

## Ampliação do esquema diário/hora

Para usar atributos prontos para uso (a maneira mais rápida de ver os dados específicos de sua organização):

1. Mapeie as colunas das contas do provedor, como Contas ou Tags, para o CBM pronto para uso attributes.For. Por exemplo, se você tiver um usuário de tag chamado Proprietário, mapeie essa tag para o atributo Proprietário do sistema existente.
2. Para obter mais informações, consulte [Mapeamento de nuvem](../configuration/cloudmapping.html "O recurso de mapeamento da nuvem (também conhecido como mapeamento de tags) oferece a capacidade de mapear metadados da nuvem (como tags e contas) para atributos em Apptio, como unidade de negócios, aplicativo etc. O mapeamento dos dados da nuvem permitirá que você veja não apenas quais serviços de nuvem são consumidos, mas também que marque os dados de faturamento da nuvem com informações que o ajudem a entender os gastos e a propriedade da nuvem.").

Adicionar atributos personalizados à etapa do pipeline do Cloud Mapping
:   A primeira etapa é estender a lista de Colunas de destino que aparecem na etapa do pipeline do Cloud Mapping para AWS e Azure. A lista padrão de Destination Columns é mostrada abaixo.

    ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/clouddailyhourlyreportsextendingchanging12.6_1.png)

    1. Em TBM Studio, navegue até Tag Mapping Reference Data (Dados de referência de mapeamento de tags).

       ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/clouddailyhourlyreportsextendingchanging12.6_2.png)
    2. Exporte a tabela para um arquivo.csv e adicione linhas com os novos campos que deseja adicionar ao esquema.
    3. Verifique a tabela e carregue o arquivo.csv que foi atualizado na etapa anterior.
    4. Verifique suas alterações.
    5. Vá para a etapa do pipeline de mapeamento da nuvem em AWS Cost and Usage Report Raw ou Azure EA Bill Raw. Seus novos campos aparecerão no menu suspenso Destination Column (Coluna de destino).
    6. Crie regras de mapeamento para essas novas colunas na etapa do pipeline do Cloud Mapping.

    Observação: as alterações no Cloud Mapping precisam ser verificadas e promovidas para produção antes que esses mapeamentos entrem em vigor nos dados diários/horários.

Adicionar atributos personalizados ao objeto dbr\_daily
:   Agora que você pode mapear atributos da fatura para as novas colunas de destino, também precisará garantir que essas novas colunas possam ser expostas no Report Editor. Isso é feito adicionando suas novas colunas ao esquema do objeto dbr\_daily.

    1. Em TBM Studio, acesse o objeto dbr\_daily e adicione uma nova coluna à etapa da fórmula, certificando-se de que o nome da coluna corresponda ao nome que você adicionou aos dados de referência do mapeamento de tags.

       ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/clouddailyhourlyreportsextendingchanging12.6_3.png)
    2. Salve as alterações. A nova coluna já está disponível para relatórios.

Modificar os componentes do relatório (pivôs, slicers, gráficos e tabelas)
:   Você pode modificar os componentes de relatórios diários/horários existentes como faz em relatórios normais, com algumas restrições e nuances específicas.

    Para adicionar um atributo não numérico a um pivô, gráfico ou outro componente:

    1. Selecione o componente em questão.
    2. Navegue até a perspectiva Diária/Horária.
    3. Localize o atributo que deseja adicionar ao componente e arraste-o para o campo apropriado. Neste exemplo, Environment foi adicionado ao Pivot no relatório Daily Transparency.

       ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/clouddailyhourlyreportsextendingchanging12.6_4.png)
    4. Salvar o relatório

    Observação: devido à natureza granular da série temporal dos campos numéricos nos relatórios diários/horários, são necessárias as etapas a seguir. Para serem usados em relatórios, os campos numéricos já devem existir na perspectiva Daily/Hourly ou no objeto dbr\_daily.

    Para adicionar ou modificar campos numéricos em um gráfico ou tabela:

    1. Localize o campo numérico que deseja usar. Este exemplo usa o Usage Qty no objeto dbr\_daily.

       ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/clouddailyhourlyreportsextendingchanging12.6_5.png)
    2. Arraste o campo numérico para a coluna **Values (Valores** ).

       ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/clouddailyhourlyreportsextendingchanging12.6_6.png)
    3. Remova todos os campos numéricos desnecessários da coluna Values (Valores) e atualize a formatação do gráfico conforme necessário.
    4. Certifique-se de que a coluna de granularidade de tempo adequada esteja em place.In. Em muitos casos, os componentes do relatório precisarão saber qual granularidade de tempo deve ser exibida. Por exemplo, um gráfico de colunas pode ser configurado para mostrar o custo diário ou por hora. As colunas Granularity\_DD e Granularity\_HH são usadas para esse controle de granularidade. Em geral, use Granularity\_HH apenas em gráficos que você deseja incluir detalhes por hora. Para todos os outros, inclua Granularity\_DD no campo **Axis** (onde os dias são um atributo a ser exibido) ou no campo **Filter** (onde os dias não são um atributo a ser exibido).
    5. Salve suas alterações.
    6. O custo agora é substituído pela quantidade de uso no gráfico de custo diário da fatura. Repita as etapas de 1 a 5 para os seguintes campos numéricos.
       - objeto dbr\_daily
         - **Custo** - o custo associado ao serviço de nuvem consumido. (Esse é atualmente o custo não combinado no Relatório Detalhado de Faturamento)
         - **Taxa** - A taxa unitária do serviço de nuvem consumido. Esse campo é calculado pela divisão do custo pela quantidade de uso. Observe que, devido ao grande número de tarifas unitárias na fatura da nuvem, esse campo apresentará resultados incomuns quando um gráfico ou tabela não for filtrado para uma única tarifa unitária.
         - Qtd**. de uso** - A quantidade de unidades consumidas para o serviço de nuvem. Por exemplo, para os serviços de computação EC2, esse campo incluirá o número de horas de instância consumidas.
       - Perspectiva diária/hora
         - **Cloud Invoice Cost MTD** - O custo total do mês que está sendo analisado.
         - **Cloud Invoice Cost Today (Custo da fatura na nuvem hoje** ) - O custo total do último dia inteiro. Atualmente, os relatórios diários/horários não informam sobre dias parciais.
         - **Cloud Invoice Cost Yesterday (Custo da fatura na nuvem ontem** ) - O custo total do dia anterior ao último dia completo.
         - **Previsão de fatura na nuvem do mês atual** - A despesa projetada no final do mês para o mês que está sendo analisado. Isso é calculado por meio de uma projeção linear dos custos incorridos no mês até a data. Para meses anteriores, esse valor será igual aos custos reais incorridos naquele mês.
         - **Custo diário da fatura na nuvem** - Equivale ao campo Custo em dbr\_daily.
         - **Prev Month Invoice Cost (Custo da fatura do mês** anterior) - O custo total do mês anterior.
         - **Prev Month Invoice Cost MTD** - O custo total do mês anterior até o mesmo dia em que é medido para o mês atual.
    7. Salve suas alterações.
