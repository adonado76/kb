---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "pt-br"
doc_type: "it-benchmarking"
title: "Benchmarking interativo - Métricas de benchmark de infraestrutura"
breadcrumb: []
source_path: "it-benchmarking/benchmarking-guides/infrastructure-metrics.html"
images:
  - "resources/images/it_benchmarking_images/double_image_adjusters_fig4.jpg"
  - "resources/images/it_benchmarking_images/influence_of_industry_adjuster_fig7.jpg"
  - "resources/images/it_benchmarking_images/influence_of_region_adjuster_fig8.jpg"
  - "resources/images/it_benchmarking_images/influence_of_scal_adjuster_fig9.jpg"
  - "resources/images/it_benchmarking_images/mainframe_mips_unit_cost_fig3.jpg"
  - "resources/images/it_benchmarking_images/scale_region_industry_influencers_fig2.jpg"
  - "resources/images/it_benchmarking_images/server_unit_as_box_plot_fig1.jpg"
  - "resources/images/it_benchmarking_images/single_point_comparison_fig6.jpg"
  - "resources/images/it_benchmarking_images/unit_cost_by_cost_pool_fig5.jpg"
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Benchmarking interativo - Métricas de benchmark de infraestrutura

♦ Aplica-se a: Benchmarking interativo

Este artigo descreve a metodologia do Interactive Benchmarking conforme ela se aplica aos Benchmarks de infraestrutura e recomenda como aproveitar os recursos do Interactive Benchmarking. O foco deste artigo é explicar como a metodologia atual difere da metodologia usada no Benchmarking v1.

**Experiência**

Antes do Interactive Benchmarking, as duas principais solicitações dos clientes do Apptio eram

- Detalhes adicionais sobre os dados de referência, como tamanho da amostra, quartil superior e mediana, em vez de um único ponto de dados
- Uma melhor compreensão dos drivers de dados de benchmark

Com base nesse feedback, o site Apptio trabalhou com os fornecedores de benchmark para melhorar a fidelidade dos dados de benchmark. Com o lançamento do Apptio Interactive Benchmarking, as seguintes alterações foram incorporadas:

- Dados de referência na forma de uma distribuição, com tamanho de amostra, mostrados por quartis, usando uma representação estatística padrão de gráfico de caixa.
- Principais influenciadores identificados para cada tipo de métrica. Por exemplo, as métricas de Indústria e Infraestrutura têm suas próprias características e, portanto, seus próprios influenciadores exclusivos.
- Fidelidade de escala aprimorada usando uma função de potência para métricas de infraestrutura.

Além disso, o Interactive Benchmarking oferece três níveis de métricas com os seguintes níveis de granularidade:

- **Benchmarks do setor** - As métricas de benchmark do setor fornecem cinco métricas de alto nível para as finanças da organização, como "Gastos de TI como % da receita da organização", que o ajudam a comparar o desempenho geral e a eficiência da TI com seus pares.
- **Benchmarks de TI OpEx** - As métricas de benchmark de TI OpEx fornecem uma orientação de alto nível sobre as características de sua organização OpEx.
- **Benchmarks de infraestrutura** - As métricas de benchmark de infraestrutura incluem métricas de benchmark de pares no nível mais granular, o que permite comparar seus custos unitários de subtorre e eficiências de FTE com os de seus pares.

A Interactive Benchmarking fornece dados de distribuição com ajustadores para todos os três níveis de métricas. O principal fator de influência das métricas do setor é o setor, com influenciadores secundários como região e receita. As métricas de infraestrutura, por outro lado, são significativamente afetadas pelas economias de escala. A região e o setor têm uma influência secundária. Para obter mais informações sobre essas métricas, consulte a [Base de Conhecimento de Benchmarking](https://community.apptio.com/community/apptio/product-central/it-benchmarking "(Abre em uma nova guia ou janela)").

**Comparação**

As principais diferenças entre as métricas de infraestrutura no Benchmarking v1 (2016) e as métricas de infraestrutura no Benchmarking interativo são:

- **Distribuição baseada em gráficos de caixa** - No Benchmarking interativo, os custos unitários de subtorres e as métricas de eficiência FTE são apresentados como dados de distribuição completa, na forma de gráficos de caixa que mostram dados de benchmark medianos, do quartil superior, do quartil inferior e do quartil médio, com informações sobre o tamanho da amostra e o provedor de dados de benchmark (Figura 1). Em contraste, o Benchmarking v1 apresenta benchmarks de infraestrutura como dados de ponto único, sem visibilidade da distribuição da amostra.

  ![img](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/server_unit_as_box_plot_fig1.jpg)

  Figura 1: Dados de referência de custo unitário do servidor como um gráfico de caixa
- Ajustes **adicionais** - Ajustes de escala, região e setor estão disponíveis no Interactive Benchmarking.
  - Os ajustadores de escala permitem que você analise a influência da economia de escala no custo unitário e nos números de referência de eficiência FTE.
  - Os ajustadores de região e setor permitem que você escolha a região apropriada e os grupos de pares do setor para entender seu impacto e comparar seus números de eficiência de custo unitário e FTE.

    Somente um desses ajustadores pode ser selecionado de cada vez (Figura 2).

  Por outro lado, o Benchmarking v1 pré-aplicou ajustadores de escala, região e setor e os apresentou como uma única métrica de benchmark. A extensão real de seu impacto não foi exposta no produto.

  ![img](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/scale_region_industry_influencers_fig2.jpg)

  Figura 2: Ajustes de escala, região e setor para benchmarks de infraestrutura
- **Maior fidelidade do ajustador** de escala - No Benchmarking interativo, os ajustadores de escala são calculados usando uma função de potência para melhorar a fidelidade e a precisão. A fidelidade aprimorada de escala para o custo unitário do Mainframe MIPS é mostrada na Figura 3, em laranja. Benchmarking v1, mostrado em azul, tem uma função de passo de baixa fidelidade.

  ![img](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/mainframe_mips_unit_cost_fig3.jpg)

  Figura 3: Ajustador de escala

**Uso de recursos de Benchmarking interativo**

Esta seção descreve como usar o Benchmarking interativo, que enfatiza a comparação dos dados reais com toda a distribuição usando o gráfico de caixa. Os ajustadores que influenciam os custos são escala, região e setor (Figura 4).

![img](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/double_image_adjusters_fig4.jpg)

Figura 4: Ajustes de escala, região e setor à esquerda, gráfico de caixa à direita

**Comparar os custos reais com os dados de referência**

Depois de preencher os campos Volume de entrada e **Custo anual total**, você pode avaliar como seus custos unitários reais se comparam à distribuição usando o gráfico de caixa. Compare seus dados reais com a mediana e veja se eles se enquadram na faixa interquartil ou se são discrepantes. Em seguida, compare seus dados reais por divisão de direcionador de custo e com os números de referência correspondentes, conforme mostrado abaixo. Isso chama a atenção para qualquer diferença significativa nas características de custo.

![img](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/unit_cost_by_cost_pool_fig5.jpg)

Figura 5: Custo unitário por drivers do pool de custos

**Comparação de ponto único**

Para uma comparação de ponto único, recomendamos usar a mediana como base. A tabela na parte inferior da página (Figura 6) mostra a diferença entre seus valores reais e a mediana. Embora a redução das comparações a um único ponto ofereça uma maneira fácil de rastrear os pontos de dados, ela desvia a visão de uma distribuição de pares.

![img](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/single_point_comparison_fig6.jpg)

Figura 6: Comparação de ponto único do custo unitário com a mediana de referência

**Impacto dos influenciadores nas métricas**

Para entender o impacto da escala, da região e do setor, clique nos gráficos à esquerda para ver sua influência no gráfico de caixa.

A Figura 7 e a Figura 8 mostram o setor e a região, respectivamente. Para ver o impacto do setor ou da região na métrica de referência, clique em um dos grupos de setores ou regiões.

![img](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/influence_of_industry_adjuster_fig7.jpg)

Figura 7: Influência do ajustador do setor nos dados de referência de custo unitário

![img](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/influence_of_region_adjuster_fig8.jpg)

Figura 8: Influência do ajustador regional nos dados de referência de custo unitário

**Impacto das economias de escala**

O gráfico de escala na Figura 9 mostra as economias de escala. Em volumes menores, os custos unitários de referência têm alta variação. À medida que os números de volume aumentam, os custos unitários de referência diminuem e se estabilizam após atingir um determinado limite. Isso indica que, devido às economias de escala, os custos unitários são significativamente mais altos em volumes baixos. Clique em um gráfico de influenciador de escala para ver o impacto da escala em um contexto de gráfico de caixa.

![img](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/influence_of_scal_adjuster_fig9.jpg)

*Figura 9: Influência do ajustador de escala nos dados de referência de custo unitário*

**Conclusão**

O Benchmarking interativo tem recursos aprimorados que fornecem dados de benchmark mais ricos e precisos. Para saber mais sobre dados de benchmark ou funcionalidades do Interactive Benchmarking, acesse a [Base de Conhecimento de Benchmarking](https://community.apptio.com/community/apptio/product-central/it-benchmarking "(Abre em uma nova guia ou janela)").
