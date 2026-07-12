---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Revisão financeira ( OpEx ) relatório ( v107 )"
breadcrumb: []
source_path: "cost-transparency/reports-v107/itfmf-ct_financialreview107.html"
images:
  - "resources/images/ct_images/itfmf-ct_images/itfmf-ct_financialreview_opex.png"
  - "resources/images/ct_images/itfmf-ct_images/itfmf-ct_financialreview_spendanalysis.png"
  - "resources/images/ct_images/itfmf-ct_images/itfmf-ct_financialreview_transactiondetail.png"
  - "resources/images/ct_images/itfmf-ct_images/itfmf-ct_financialreview_variancedetail.png"
  - "resources/images/ct_images/itfmf-ct_images/itfmf-ct_financialreview_viewby.png"
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Revisão financeira ( OpEx ) relatório ( v107 )

Aplica-se a: Planejamento e Costing Standard em TBM Studio 12.3 e posteriores, com o modelo v107 e posteriores

## Casos de uso

- Em nível executivo, acompanhe os gastos de TI por CIO -1 por proprietário do centro de custos e custo
- Analisar os detalhes da transação para entender os fatores do plano de variação
- Identificar variações significativas de gastos em relação ao planejado

O relatório **Financial Review** fornece uma visão executiva da variação geral do orçamento OpEx e das despesas OpEx de sua organização. O relatório detalha o custo de TI por pool de custos e proprietário para que você possa determinar quais proprietários de TI são responsáveis pelos maiores gastos com TI. Vários gráficos no relatório também o ajudam a determinar se as variações são reais ou causadas por categorização incorreta.

Use este relatório para criar um resumo executivo que explique as despesas de TI OpEx e para realizar as revisões financeiras periódicas que são essenciais para o gerenciamento eficaz das despesas de TI. Os dados desse relatório incluem itens de linha do razão geral para que você possa ajustar os planos para acomodar a variação.

Este relatório foi elaborado para ser usado pelas seguintes funções:

- CIO -1 (Escritório da TBM)
- Proprietários de centros de custo
- Analistas financeiros de TI

## Exibir o relatório

1. Faça login em Apptio e navegue até **Planning > Costing Standard**.
2. Na página **inicial**, clique em **IT Financials**.

   O relatório **Revisão financeira** é aberto.

1. Faça login em Apptio e navegue até **Costing Standard**.
2. Na página **inicial**, clique em **IT Financials**.

   O relatório **Revisão financeira** é aberto.

O relatório contém os seguintes elementos.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/itfmf-ct_images/itfmf-ct_financialreview_opex.png)

(1) Coleta de relatórios
:   Esta coleção de relatórios fornece os detalhes financeiros de TI de que você precisa para analisar as variações de gastos e a precisão das previsões:

    - Revisão financeira (aberta por padrão) (descrita neste artigo)
    - [Revisão financeira - relatório CapEx ( v107 )](itfmf-ct_financialreviewcapexv107.html)
    - [Relatório de análise financeira ( v104 e posterior)](../reports-v104/itfmf-ct_financialanalysis104.html)
    - [Relatório de análise do pool de custos ( v104 e posterior)](../reports-v104/itfmf-ct_costpoolanalysis104.html)

(2) Cortadores
:   Use as segmentações locais e globais para refinar os dados em seu relatório. Os fatiadores nesse relatório permitem que você veja seus dados de custo por região, grupo de contas e responsabilidade organizacional, incluindo centro de custo, proprietário do centro de custo e proprietário (por exemplo, CIO -1)).

    As seguintes funções podem usar as segmentações neste relatório para obter uma visualização mais personalizada:

    Controlador financeiro ou CIO de TI
    :   Sem definir quaisquer segmentações, você pode ver a visão geral das despesas em todos os centros de custos da organização. É possível detalhar os pools de custos, os proprietários de centros de custos e as contas individuais.

    Proprietário do centro de custo ou CIO -1
    :   Defina as segmentações do **centro de custo** ou **do proprietário do centro de custo** para filtrar suas áreas de responsabilidade.

    Analista financeiro
    :   Defina o fatiador **do centro de custos** para as áreas às quais você dá suporte ou defina um grupo de contas específico para permitir uma análise detalhada e interorganizacional das despesas por categoria.

(3) KPIs
:   Os KPIs fornecem uma visão de alto nível de seus gastos em OpEx :

    **OpEx YTD** e **OpEx Orçamento**
    :   Esses dois KPIs mostram seu orçamento geral de OpEx em comparação com o gasto de OpEx no mês atual. A porcentagem de variação é mostrada à direita.

    **OpEx YTD** e **OpEx Orçamento YTD**
    :   Esses dois KPIs mostram suas despesas em OpEx em comparação com o orçamento YTD. A porcentagem de variação é mostrada à direita.

    **OpEx anual** e **orçamento anual OpEx**
    :   Esses dois KPIs mostram seu gasto anual em OpEx em comparação com o orçamento do ano fiscal. A porcentagem de variação é mostrada à direita.

    **% OpEx Variável YTD** e **% OpEx Fixo YTD**
    :   Esses KPIs o ajudam a determinar a agilidade de seus gastos com TI, observando a proporção de despesas fixas e variáveis para o ano fiscal.

(4) **OpEx Variação orçamentária**
:   Selecione uma métrica (pool de custos, grupo de contas, proprietário, proprietário do centro de custos ou ID do centro de custos) na lista **Exibir por** para preencher os gráficos **Top Over Budget YTD** e **Top Under Budget YTD** com os itens com a maior variação de orçamento em relação ao planejado no acumulado do ano. Essas informações o ajudarão a priorizar onde procurar oportunidades de redução.

    ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/itfmf-ct_images/itfmf-ct_financialreview_viewby.png)

    Clique em uma barra em um dos gráficos para abrir uma caixa de diálogo **Detalhe de variação** que mostra as despesas, o orçamento, a variação e a porcentagem de variação do OpEx para a métrica selecionada. Use as opções na parte superior da página para selecionar um período de tempo.

    ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/itfmf-ct_images/itfmf-ct_financialreview_variancedetail.png)

    Clique em um código de conta na coluna da esquerda para ver os detalhes da transação da sua fonte financeira de registro (como o razão geral).

    ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/itfmf-ct_images/itfmf-ct_financialreview_transactiondetail.png)

    A tabela **Detalhes** permite que você veja um resumo do orçamento, da variação e da porcentagem de variação do OpEx para todos os itens na métrica selecionada com base nos períodos de tempo selecionados acima da tabela.

    Perguntas respondidas:

    - Onde estão as variações significativas entre as despesas e o planejamento?
    - Quais centros de custos estão gerando variação de despesas em relação ao planejado e quem é responsável por esses centros de custos?
    - A variação é real ou causada pela categorização incorreta de uma despesa?
    - Para onde vai a maior parte de nossos gastos com TI? Por pool de custos? Por proprietário de TI (por exemplo, CIO -1))? Por proprietário do centro de custo?
    - Há mudanças significativas nas despesas de um período para outro?
    - Quais itens de linha de despesas contribuem para o custo de uma função de TI?

(5) **OpEx Variação da previsão**
:   Selecione uma métrica (pool de custos, grupo de contas, proprietário, proprietário do centro de custos ou ID do centro de custos) na lista **Exibir por** para preencher os gráficos **Top Over Forecast YTD** e **Top Under Forecast YTD** com os itens com a maior variação de previsão em relação ao planejado YTD.

    Clique em uma barra em um dos gráficos para abrir uma caixa de diálogo **Detalhe de variação** que mostra as despesas, a previsão, a variação da previsão e a porcentagem de variação do OpEx para a métrica selecionada. Use as opções na parte superior da página para selecionar um período de tempo.

    Clique em um código de conta na coluna da esquerda para ver os detalhes da transação da sua fonte financeira de registro (como o seu GL).

    A tabela **Detalhes** permite que você veja um resumo da previsão OpEx, da variação da previsão e da porcentagem da variação da previsão para todos os itens na métrica selecionada com base nos períodos de tempo selecionados acima da tabela.

    Perguntas respondidas:

    - Para onde vai a maior parte de nossos gastos com TI? Por pool de custos? Por proprietário de TI (por exemplo, CIO-1 )? Por proprietário do centro de custo?
    - Onde observamos mudanças significativas nas despesas de um período para outro?
    - Quais são os itens de linha de despesas que contribuem para o custo de uma função de TI?

(6) Análise de despesas
:   Selecione uma métrica (pool de custos, grupo de contas, proprietário, proprietário do centro de custos ou ID do centro de custos) na lista **View by** para preencher os gráficos **OpEx Spend YTD** e **OpEx Trend** com os itens com a maior variação de gastos em relação ao planejado YTD e a tendência de gastos nos seis meses anteriores.

    ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/itfmf-ct_images/itfmf-ct_financialreview_spendanalysis.png)

    Clique em uma barra no gráfico para abrir uma caixa de diálogo **Detalhe da variação** que mostra as despesas mensais, trimestrais e anuais OpEx para a métrica selecionada. Use as opções na parte superior da página para selecionar um período de tempo.

    Clique em um código de conta na coluna da esquerda para ver os detalhes da transação da sua fonte financeira de registro (como o seu GL).

(7) **Perspectivas para o ano fiscal**
:   Use a guia **FY Outlook** para visualizar o orçamento OpEx, a previsão e a variação de gastos para o ano fiscal.

    Clique em qualquer item da coluna da esquerda para ver os detalhes da transação da fonte financeira de registro (como o GL).

(8) Ícone de e-mail
:   O ícone de e-mail é visível apenas para analistas financeiros com permissões de administrador. Clique no ícone para abrir o relatório de e-mail **Finance Variance Review**. Consulte o [relatório de e-mail Finance Variance Review](../reports-v104/itfmf-ct_financialvariancereviewemail104.html).

## Informações relacionadas

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentários sobre a Central de Ajuda](productfeedback@apptio.com "(Abre em uma nova guia ou janela)")
