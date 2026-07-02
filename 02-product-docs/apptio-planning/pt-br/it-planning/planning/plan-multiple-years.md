---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Planeje para vários anos"
breadcrumb: []
source_path: "it-planning/planning/plan-multiple-years.html"
images:
  - "resources/planning_images/itp_multi-year-line-items.png"
  - "resources/planning_images/itp_time-period-adjuster.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Planeje para vários anos

Use os recursos de planejamento plurianual para planejar e acompanhar as finanças de TI em um horizonte de tempo contínuo e plurianual. Você pode dar suporte a planos de longo prazo e previsões contínuas para além dos limites do ano fiscal.

Apptio Planning os aplicativos suportam planos de até seis anos. Um plano que abrange vários anos ajuda você a fazer o seguinte:

- Compreender melhor o impacto financeiro dos recursos trabalhistas, contratos e ativos projetados para vários anos (consulte [Gerenciar ativos](manage-assets.html) ).
- Previsão com até 12 meses (ou quatro trimestres completos) de dados reais para apoiar previsões contínuas (consulte [Planejamento e previsão orçamentária](budget-planning-forecasting.html) ).

## Sobre o ajustador de período de tempo

Use o ajustador de período de tempo para escopo de dados resumidos. A aparência é a seguinte:

![imagem](../../../../../03-media/apptio-planning/resources/planning_images/itp_time-period-adjuster.png)

Veja como funciona o ajustador de período de tempo:

- O período de tempo com escopo atual é indicado pela região sombreada em azul. Para ajustar o período de tempo, clique e arraste as alças esquerda e direita.
- Os valores de KPI na exibição Resumo têm como escopo o período de tempo definido usando o ajustador de período de tempo.
- O gráfico de barras empilhadas para um plano que abrange vários anos inclui as seguintes opções adicionais de visualização: linha de tendência real e capacidade de agregar dados usando diferentes períodos de tempo (como uma previsão contínua de quatro trimestres).

## Recursos de vários anos em tabelas

Ao trabalhar em tabelas de itens de linha, é possível ajustar a parte visível de um plano que abrange vários anos. Consulte [Personalizar, salvar e compartilhar layouts de tabela.](customize-save-share.html)

- Ajuste os dados em escala de tempo para mostrar ou ocultar meses, trimestres ou exercícios fiscais específicos.
- Mostrar ou ocultar colunas específicas do ano fiscal.
- Os dados em escala de tempo no exemplo a seguir são definidos para mostrar (1) os meses do trimestre atual e o total trimestral, (2) os trimestres restantes do ano atual e (3) os totais do ano fiscal dos anos anteriores.

![imagem](../../../../../03-media/apptio-planning/resources/planning_images/itp_multi-year-line-items.png)

É possível salvar os ajustes da tabela de itens de linha em um layout de tabela personalizado. Além disso, os proprietários e administradores de processos orçamentários podem tornar um layout personalizado o layout padrão para outros usuários. Consulte [Criar e compartilhar layouts de tabela personalizados](customize-save-share.html).

Os valores de planejamento de recursos gerados para mão de obra, contratos e ativos (consulte [Planejamento de mão de obra](labor-planning.html "Use os recursos de planejamento de mão de obra para incorporar custos baseados em recursos ao seu processo geral de planejamento orçamentário. Os custos de mão de obra são sempre um componente importante, possivelmente o maior componente, de seus orçamentos de TI. Agora, você pode discriminar os custos baseados em recursos por dimensões específicas de mão de obra, como tipo, local e função, usando regras de cálculo de custos de mão de obra consistentes e gerenciadas centralmente.")) podem se estender por toda a duração de um plano que abrange vários anos. Consulte [Planejamento trabalhista.](labor-planning.html "Use os recursos de planejamento de mão de obra para incorporar custos baseados em recursos ao seu processo geral de planejamento orçamentário. Os custos de mão de obra são sempre um componente importante, possivelmente o maior componente, de seus orçamentos de TI. Agora, você pode discriminar os custos baseados em recursos por dimensões específicas de mão de obra, como tipo, local e função, usando regras de cálculo de custos de mão de obra consistentes e gerenciadas centralmente.") O planejamento de recursos pode incluir o seguinte:

- Os custos de mão de obra atuais ou planejados sem data de término ou com uma data de término além do plano plurianual se estenderão por todo o plano (consulte [Criar um plano de mão de obra](create-labor-plan.html) ).
- Ajustes de remuneração trabalhista que se aplicam desde a Data de Vigência do Ajuste até a duração do plano (consulte [Plano para ajustes de remuneração trabalhista](plan-labor-compensation.html "Os proprietários do processo orçamentário ou os usuários com permissões de proprietário de um objeto de custo podem contabilizar os ajustes planejados nas taxas de remuneração de mão de obra. Isso pode ser feito para mão de obra atual ou planejada. Você pode especificar uma alteração percentual na remuneração base por recurso de mão de obra e a data em que a alteração entrará em vigor.") ). Os ajustes de remuneração trabalhista são recorrentes anualmente. Por exemplo, um aumento de 3% em vigor a partir de 1º de abril do ano corrente resultaria em um aumento de 3% em relação ao ano anterior.

Os valores de KPI em tabelas de itens de linha têm escopo apenas para o ano fiscal atual e são rotulados de acordo. Os KPIs de item de linha não se ajustam com base em quais períodos fiscais são visíveis ou não.

Ao importar ou exportar dados financeiros, os aplicativos Apptio Planning suportam até 72 períodos de tempo. Cada período de tempo é rotulado de P1 a P12, ou P1 FYnnnn, em que P1 representa o primeiro período do ano fiscal e nnnn representa o ano fiscal de quatro dígitos. Consulte [Inserir ou importar dados de itens de linha](enter-import-line.html "Depois que um plano ou previsão orçamentária é aberto, os responsáveis pelo orçamento recebem uma notificação por e-mail e podem começar a inserir dados de itens de linha e enviar planos. Os proprietários de departamentos, proprietários de serviços e proprietários de projetos podem inserir ou importar seus dados de itens de linha e enviar seus planos.") e [Exportar e preencher tabelas ou layouts de itens de linha](export-populate-line.html).

Ao comparar duas versões ou planos, as colunas de comparação ficam adjacentes às colunas de total. Consulte [Comparar versões ou planos](compare-versions-plans.html). Os cabeçalhos verdes indicam comparações de versões, enquanto os roxos indicam comparações de planos.

DICAS:

- Ao criar um novo plano, especifique um plano de 1 ou 6 anos (consulte [Criar um plano ou previsão orçamentária](create-budget-plan.html) ).
- Ao criar um novo plano plurianual usando um plano de um ano, os dados do primeiro ano do plano original são copiados para os dados do primeiro ano do novo plano, mesmo que os períodos fiscais do plano original e do novo plano sejam diferentes.
- Ao publicar um plano plurianual em Costing Standard, os aplicativos Apptio Planning publicarão 72 meses de dados em uma única ação de publicação (consulte [Integrar com transparência de custos](integrate-ct.html "Se a sua organização executa o Apptio Costing Standard e um aplicativo Apptio Planning, é possível integrá-los para compartilhar dados.") ).
