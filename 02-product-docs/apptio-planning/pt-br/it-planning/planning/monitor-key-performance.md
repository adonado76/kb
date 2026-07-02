---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Monitorar os principais indicadores de desempenho no Dashboard"
breadcrumb: []
source_path: "it-planning/planning/monitor-key-performance.html"
images:
  - "resources/planning_images/itp_annual-vendor-spend.png"
  - "resources/planning_images/itp_executive-dashboard_elements.png"
  - "resources/planning_images/itp_it-spend-trend_chart.png"
  - "resources/planning_images/itp_it-spend-variance.png"
  - "resources/planning_images/itp_it-trend-spend_department-name.png"
  - "resources/planning_images/itp_uncommitted-spend.png"
  - "resources/planning_images/itp_uncommitted-spend_donut-detail.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Monitorar os principais indicadores de desempenho no Dashboard

O Dashboard oferece uma visão rápida, porém abrangente, dos principais indicadores de desempenho do plano. Especificamente, o Dashboard mostra o desempenho real em relação ao orçamento e a previsão atual em relação ao orçamento do ano e do acumulado do ano. Essa visão consolidada resume os principais elementos e o estado atual do planejamento.

Observação: O Dashboard deve estar visível na interface. Consulte [Editar o perfil da empresa](edit-company-profile.html "O Company Profile permite que os usuários Admin e Budget Process Owner definam as configurações de todo o aplicativo que personalizam a exibição, ativam ou desativam recursos e definem o comportamento do fluxo de trabalho em Apptio Planning."). Uma vez feito isso, o Dashboard poderá ser acessado por todos os usuários. O conteúdo do Dashboard é limitado. No entanto, ele se baseia nas permissões de função do usuário.

O conteúdo do Dashboard é preenchido por um plano selecionado. As comparações, quando disponíveis, são feitas em relação ao plano selecionado Compare To:.

## Abra o Dashboard

1. Nos menus do plano no canto superior direito, selecione um plano, um tipo de objeto de custo e um objeto de custo ou grupo de objetos de custo.

   [Saiba mais sobre a navegação no Planejamento](navigate-apptio-planning.html)
2. Navegue até Planning > Dashboard.

## Elementos do painel

Indicadores-chave de desempenho (KPIs) - Os três KPIs a seguir aparecem na parte superior do Dashboard. Somente os valores do tipo de transação direta estão incluídos. A variação é calculada em relação a uma meta, se definida. Consulte [Definir metas financeiras](set-financial-targets.html). Os KPIs incluem o seguinte:

- OpEx Total para o ano do plano
- CapEx Total para o ano do plano
- Número médio de funcionários no ano do plano

![imagem](../../../../../03-media/apptio-planning/resources/planning_images/itp_executive-dashboard_elements.png)

IT Spend Trend (Tendência de gastos de TI) - Faz um gráfico do plano selecionado e dos dados reais disponíveis para o ano atual em relação ao plano selecionado Comparar com. Use o filtro rápido para alternar entre os valores All (Todos), OpEx, e CapEx.

![imagem](../../../../../03-media/apptio-planning/resources/planning_images/itp_it-spend-trend_chart.png)

DICA : Clique em uma barra para ver os detalhes do item de linha. Os KPIs podem ser mostrados por meses, trimestres e anos, e podem ser baixados.

IT Spend Variance (Desvio de despesas de TI ) - Gráficos dos fatores de desvio descobertos pelos proprietários de centros de custo e identificados como parte da análise de desvio. O resumo por fator de variação é feito em cascata do orçamento original para o real. É possível fazer drill down usando o controle de árvore, semelhante a outros gráficos de planejamento. Use o botão Download para exportar um arquivo.csv com todas as informações do motorista de variação capturadas, incluindo entradas de texto de forma livre.

![imagem](../../../../../03-media/apptio-planning/resources/planning_images/itp_it-spend-variance.png)

Annual Labor Plan (Plano anual de mão de obra) - Faz um gráfico do número de funcionários identificados no plano selecionado em relação a uma linha de tendência do plano Compare com:. Você pode agrupar ou dinamizar os dados por várias dimensões, como Centro de custo > Código ou Departamento > Código.

Dica: você pode clicar em uma barra para ver os detalhes do item de linha e fazer o download dos dados.

![imagem](../../../../../03-media/apptio-planning/resources/planning_images/itp_it-trend-spend_department-name.png)

Despesas não comprometidas - apresenta gráficos de possíveis economias de custos em períodos futuros por categoria de despesas em gráficos de rosca. O cálculo é baseado na data de entrada padrão Commit After:

- Para um plano de previsão, a data de entrada é o primeiro dia do mês de início da previsão, se esse dia estiver no primeiro ano do plano. Caso contrário, ele é tratado como um plano orçamentário.
- Para um plano orçamentário, a data de hoje se for o primeiro ano do plano. Caso contrário, o primeiro dia do primeiro ano do plano.

![imagem](../../../../../03-media/apptio-planning/resources/planning_images/itp_uncommitted-spend.png)

Os cálculos para cada valor do gráfico de rosca são os seguintes: os valores da Data de início de cada item da lista a seguir são encontrados na guia correspondente da página Despesas.

Por exemplo, a Data de início do item de mão de obra é encontrada na visualização Despesas, guia Mão de obra. Se a Experiência de planejamento de trabalho simplificado estiver ativada no Perfil da empresa, os valores poderão ser encontrados na página Despesas, guia Atividades. Consulte [Editar o perfil da empresa](edit-company-profile.html "O Company Profile permite que os usuários Admin e Budget Process Owner definam as configurações de todo o aplicativo que personalizam a exibição, ativam ou desativam recursos e definem o comportamento do fluxo de trabalho em Apptio Planning.").

- Despesas de mão de obra não comprometidas - Soma dos itens financeiros em que a data de início do item de mão de obra é maior ou igual à data de entrada.
- Despesas de contratos não comprometidos - Soma dos itens financeiros em que a Data de início do item de linha do contrato é maior ou igual à data de entrada. Observe que o tratamento sofisticado de extensões de contrato está atualmente excluído e os contratos que são estendidos após a data final listada são considerados comprometidos.
- Despesas de ativos não comprometidos - Soma das partidas individuais financeiras em que a data de compra da partida individual do ativo é maior ou igual à data de entrada.

Clique em um valor de fatia de rosca para exibir uma tabela detalhada de itens de linha associada a esse valor. Esses detalhes permitem que você identifique oportunidades específicas de economia de custos dentro do seu plano.

![imagem](../../../../../03-media/apptio-planning/resources/planning_images/itp_uncommitted-spend_donut-detail.png)

Despesas anuais do fornecedor - apresenta gráficos das despesas planejadas do fornecedor (onde o valor do fornecedor não é nulo), comparando o plano selecionado com o plano Comparar com:. O grupo selecionado por é exibido em cascata no gráfico em cascata, de comparado a selecionado.

![imagem](../../../../../03-media/apptio-planning/resources/planning_images/itp_annual-vendor-spend.png)
