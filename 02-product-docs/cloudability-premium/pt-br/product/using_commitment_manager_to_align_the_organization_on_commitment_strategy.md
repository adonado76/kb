---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "product"
title: "Utilizando a Visão Geral do Gerenciador de Compromissos para alinhar a organização à estratégia de compromissos"
breadcrumb:
  - "Cloudability Premium"
  - "Otimizar"
  - "Guia para a gestão de compromissos"
source_path: "product/using_commitment_manager_to_align_the_organization_on_commitment_strategy.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Utilizando a Visão Geral do Gerenciador de Compromissos para alinhar a organização à estratégia de compromissos

## Propósito

A página de visão geral serve como base de orientação para os compromissos do Cloudability. Ele reúne a situação atual (desempenho histórico) e as oportunidades futuras (recomendações modeladas) em uma visão única que abrange todos os serviços e fornecedores. A partir desta página inicial, as equipes podem começar a se alinhar em torno de uma visão abrangente do impacto atual que a otimização da taxa de conversão tem sobre seu portfólio e onde podem estar as oportunidades imediatas. O gráfico personalizado e os KPIs padronizados orientam diretamente os usuários antes de aprofundarem-se no Portfólio ou nas Recomendações. Este documento fornecerá instruções sobre como usar esta página.

Observação: Estamos trabalhando para que esta página ofereça relatórios que abranjam diferentes fornecedores e serviços. Por enquanto, devido a questões de desempenho e à falta de compatibilidade de recursos, pretendemos, em primeiro lugar, oferecer suporte ao " AWS " em uma única conta de pagador.

## Acesso e configuração básica

A página "Gerenciador de Compromissos" está localizada na seção "Otimizar" do menu de navegação à esquerda, abaixo do Painel de Otimização, e difere das páginas de portfólio e recomendações.

**Tipo de serviço**

Para começar, o seletor de tipo de serviço é um menu suspenso com seleção múltipla usado para escolher qual uso do serviço você deseja analisar. Quando um serviço é selecionado, apenas o *uso comprometível* é analisado e exibido no gráfico. Esta é uma página de visão geral; portanto, uma análise mais aprofundada do seu portfólio ou das oportunidades em cada tipo de compromisso deve ser feita nas páginas do portfólio e de recomendações. É importante destacar que as páginas agregadas no nível do fornecedor e do serviço garantem que as recomendações apresentadas sejam mutuamente exclusivas entre si.

Para obter mais informações sobre esse comportamento, consulte a seção *“Tipo de recomendação”* abaixo.

**Conta**

O seletor de contas determina quais contas o nosso modelo irá analisar. O seletor reflete a estrutura hierárquica das suas contas e permite a seleção múltipla. Ao selecionar uma ou mais contas de pagador (Administração, Assinatura, Faturamento), o botão seleciona/desmarca todas as contas vinculadas abaixo dele. Ao selecionar uma ou mais contas vinculadas específicas (Membro, Assinatura, Projeto), o botão em questão seleciona/desmarca a conta, exibindo um estado de seleção parcial na conta do pagador. Em geral, é recomendável escolher uma opção de conta que corresponda às suas preferências de compartilhamento configuradas no console do fornecedor.

Para obter mais informações sobre a terminologia das contas, consulte “[Estrutura das contas por fornecedor](commitments_vendor_account_structure.html) ”.

**Base de custo**

A página de resumo não oferece a opção de selecionar sua base de custo; no entanto, se a opção “Ajustado” estiver configurada, o gráfico será apresentado em termos de “Ajustado”.

Para obter mais informações, consulte “[Como os preços negociados influenciam os compromissos](custom_pricing_factors_across_commitments.html) ”.

**Período de análise**

A seleção do período de análise na página de visão geral difere das páginas de recomendações de carteira, pois o usuário seleciona um intervalo em meses. É importante ressaltar que os usuários podem fazer suas escolhas com antecedência. Por padrão, o período de análise abrange um mês anterior e três meses futuros em relação à data de hoje. Se o mês atual for considerado parte da projeção ou “previsão”, uma vez que nem todos os dias do mês foram concluídos, a seleção do período de análise permite tanto a escolha de um intervalo de meses quanto de um único mês. Para entender como os KPIs funcionam em relação ao período de análise selecionado, consulte as opções de KPI na seção a seguir.

**Tipo de recomendação**

Esta seção permite que o relatório inclua ou exclua a recomendação para o serviço selecionado. “Ótimo” refere-se ao tipo de recomendação ideal. Para obter mais informações sobre o tipo de recomendação ideal, consulte [Tipo de recomendação](using_commitment_recommendations_to_analyze_savings_opportunities.html). No caso de despesas com serviços que possam ser cobertas por vários tipos de compromisso, considere que a recomendação aplicada corresponde ao tipo de compromisso baseado em despesas. A título de exemplo. Para o serviço de computação do AWS, a recomendação apresentada nesta página se refere aos planos de economia de computação.

## Configuração e interpretação dos KPIs

**Opções de KPI - Tipo**

Esta seleção é utilizada para configurar os KPIs. A opção “Padrão”, que é a predefinida, apresenta dois valores por KPI, indicando o período mais antigo e o mais recente selecionados. Dessa forma, o padrão permite comparar os KPIs em dois momentos diferentes. O "Total" calcula simplesmente o KPI para todo o período de análise selecionado. Média: apresenta a média do período de análise selecionado para a granularidade do KPI escolhida.

**Opções de KPI - Granularidade**

Esta seleção define a granularidade do KPI como semanal ou mensal. Em conjunto com o tipo de KPI, o usuário tem a flexibilidade de analisar o desempenho real e previsto ao longo do tempo.

**Opções de KPI - Comparação**

Essa seleção adicionará um KPI de comparação quando for selecionado o tipo de KPI “padrão” ou “média”. Use o botão ao lado para configurar o KPI de comparação de modo a permitir métodos de comparação de variação absoluta e percentual.

**Mais opções - Nível de detalhamento dos custos**

Atualmente, oferecemos suporte apenas à granularidade diária no gráfico. Portanto, cada barra no gráfico representa o custo de um dia

**Mais opções - Tipo de custo**

Oferecemos suporte ao custo real e ao equivalente sob demanda (ODE). Quando a opção “custo real” é selecionada (opção padrão), todos os valores no gráfico são apresentados em termos do custo pago ou previsto para ser pago. Quando a ODE é selecionada, todos os valores são expressos em termos da ODE; portanto, a recomendação e o custo do compromisso existente são convertidos para os termos da ODE. Observe que, quando o tipo de custo “ODE” é selecionado, o gráfico de barras corresponde ao da utilização do ODE, pois todos os custos apresentados são em termos de “on-demand”.

Aqui estão alguns exemplos de como configurar o KPI para um caso de uso específico.

**Exemplo 1**

Caso de uso: "Hoje é 1º de julho de 2026. Gostaria de saber como meu portfólio evoluiu — se valorizou ou desvalorizou — ao longo do primeiro semestre do ano."

Configuração: Selecione “Todos os serviços” e um pagador específico; selecione o período de análise de janeiro de 2026 a junho de 2026; selecione “Desativado” como tipo de recomendação; selecione “Padrão” como tipo de opções de KPI, “Mês” como granularidade e ative a comparação.

Interpretação: O KPI marcado com a anotação amarela corresponde ao mês de janeiro. O KPI em roxo corresponde ao mês de junho. O KPI de comparação para cada KPI individual representará a variação percentual entre janeiro e junho. Essa configuração pode ser usada para qualquer combinação de vários meses; portanto, permite comparar dois meses/semanas no passado, dois meses/semanas no futuro ou o passado com o futuro. Na interface do usuário, o passado é explicitamente denominado “real”, enquanto o futuro é explicitamente denominado “previsão”.

**Exemplo 2**

Caso de uso: "Hoje é 1º de julho de 2026. Gostaria de saber qual seria minha economia líquida e minha cobertura ao longo de todo o ano, caso não faça nenhuma compra no futuro."

Configuração: Selecione “Todos os serviços” e um pagador específico, selecione o período de análise de janeiro de 2026 a dezembro de 2026, selecione “Desativado” como tipo de recomendação e selecione “Total” como tipo de opções de KPI.

Interpretação: A partir de agora, haverá um único valor por KPI\*. Os KPIs passarão a representar os valores de todo o período selecionado.

\*O custo restante também está incluído no KPI de custos.

**Exemplo 3**

Caso de uso: "Hoje é 15 de julho de 2026. Gostaria de saber o valor das oportunidades de compromisso imediato para o próximo mês." "Gostaria de ver isso em comparação com o mês anterior."

Configuração: Selecione “Todos os serviços” e um pagador específico; selecione o período de análise de junho de 2026 a agosto de 2026; selecione o tipo de recomendação como “ótimo”; selecione o tipo de opções de KPI como “padrão”, a granularidade como “mês” e ative a comparação.

Interpretação: O KPI marcado com a anotação em amarelo corresponde ao desempenho real observado em junho. O KPI em roxo corresponde ao desempenho previsto, excluindo a recomendação ideal para agosto. O KPI comparativo para cada KPI individual representará a variação percentual entre junho e agosto.

**Tópico dos pais:** [Guia para gerenciamento de compromissos](../product/guide_to_commitment_management.html)
