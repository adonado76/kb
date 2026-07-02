---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "product"
title: "Usando a carteira de compromissos para entender o desempenho histórico"
breadcrumb:
  - "Cloudability Premium"
  - "Otimizar"
  - "Guia para a gestão de compromissos"
source_path: "product/using_commitment_portfolio_to_understand_historical_performance.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Usando a carteira de compromissos para entender o desempenho histórico

## **Finalidade**

O objetivo deste documento é fornecer uma visão geral de como usar o Portfólio de Compromissos. Em um nível resumido, você usa o Portfólio de Compromissos para entender o desempenho de seus compromissos existentes ao longo do tempo, onde existe risco no futuro e para fornecer um ponto de partida para iniciar a conversa sobre onde as oportunidades permanecem. Quando totalmente utilizada, essa página combina insights táticos com interpretação estratégica, permitindo que os profissionais do FinOps passem rapidamente de sinais (KPIs) para ações (alertas, relatórios, recomendações).

## **Como acessar e usar**

A página Portfólio de compromisso está localizada na seção Otimizar no menu de navegação à esquerda e é organizada por fornecedor. Cada guia compartilha uma estrutura comum para que você possa comparar as nuvens sem trocar de modelo mental. A barra de ferramentas do cabeçalho permite que você crie uma visualização de portfólio focada

**Tipo de compromisso**

Essa seleção é organizada por fornecedor ( AWS ), por serviço ( EC2 ) e por tipo de compromisso ( EC2 Instâncias reservadas). Observe que a página de serviço intermediário não é necessária quando há um único tipo de compromisso que cobre o serviço.

- **Todos os níveis** (página de destino baseada no fornecedor): Mostra todos os serviços/tipos suportados para o fornecedor selecionado.
- **Nível de serviço** : Mostra todos os tipos de compromisso compatíveis com o serviço selecionado.
- **Nível de tipo** : Mostrou todos os tipos de compromisso para os vários tipos.

**Conta**

O seletor de contas controla o uso das contas que você está analisando e puxa automaticamente todos os compromissos que afetaram esse uso, mesmo que esses compromissos tenham sido comprados em outro lugar. Por exemplo, se o compromisso da conta A cobrir o uso da conta B, selecionar somente a conta B ainda refletirá o impacto do compromisso de A sobre o uso de B. Como prática recomendada, escolha contas que se alinhem às configurações de compartilhamento do console do fornecedor para que a análise reflita como os compromissos são realmente compartilhados. O seletor representa a natureza hierárquica de suas contas e é de seleção múltipla.

- A seleção de uma ou mais contas de pagador (Gerenciamento, Assinatura, Faturamento) seleciona todas as contas vinculadas abaixo dela.
- A seleção de conta(s) vinculada(s) específica(s) (Membro, Assinatura, Projeto) mostra um estado de seleção parcial na conta do pagador.

Você pode restringir a conta faturada usando filtros de tabela. Para ver as hierarquias de provedores e os escopos de compartilhamento, consulte [Estrutura da conta por fornecedor](commitments_vendor_account_structure.html).

**Base de custo**

A escolha de preços de lista ou ajustados permite que os usuários entendam suas recomendações a partir de preços de lista ou negociados sob demanda e de compromisso. Os KPIs e as tabelas refletem a base que você selecionou. Observe que as páginas de compromisso do Azure talvez ainda não apresentem uma alternância. Quando presentes, os valores refletem o Custom quando aplicável. Para obter mais informações, consulte [Como os fatores de preços personalizados são considerados nos compromissos](custom_pricing_factors_across_commitments.html)

**Período de análise**

Essa seleção orienta todos os KPIs e metadados da tabela na página. O padrão é o mês passado e as horas estão em UTC. Nossa sugestão é evitar a geração de relatórios sobre as 24 horas mais recentes para permitir que os dados concluam o processamento em nosso pipeline. Para obter mais informações, consulte [Data Freshness](data_freshness.html).

## **Interpretação dos KPIs do portfólio**

- A economia líquida e o custo restante do compromisso são KPIs em dólares com escopo para o período de análise.
- Taxa de economia, utilização e cobertura são KPIs de taxa com escopo para o período de análise.
- Taxa de economia do portfólio (PSR) = economia líquida do compromisso ÷ gastos compromissáveis (de acordo com a base selecionada). A PSR isola o efeito dos descontos de compromisso dos preços negociados sob demanda, tornando-a uma métrica de portfólio mais limpa do que a Taxa de Economia Efetiva (ESR) quando as taxas negociadas estão em jogo. Quando a Base de custo = Lista, a PSR é igual à ESR, pois todos os valores são em termos de taxa de lista e não há economia devido às taxas negociadas. Para obter mais informações, consulte [Indicadores-chave de desempenho do compromisso](commitments_key_performance_indicators.html).
- A utilização é ponderada pelo impacto/tamanho relativo dos compromissos na tabela.
- Os modais de detalhes do KPI estão disponíveis para Economia líquida e Cobertura. Esses modais fornecem informações adicionais para ajudar a entender como o KPI é calculado. Para obter mais informações, consulte [Poupança líquida](net_savings_modal.html) de compromisso e [Modais de cobertura](coverage_modal.html).

## **Painel de resumo e detalhes por tipo**

Abaixo do cabeçalho está a tabela. Cada linha resume um compromisso. As colunas se adaptam ao tipo de compromisso selecionado. Clique em Details (Detalhes) em qualquer linha para abrir o painel de detalhes (gaveta direita). Mostramos as seguintes informações:

- Todos os metadados disponíveis para o compromisso.
- KPIs com escopo para esse compromisso (as mesmas definições dos KPIs de cabeçalho).
- Visualizações de tendências para economia líquida diária e utilização para o período de análise selecionado. Incluímos um botão de alternância vitalício para ajustar o gráfico a toda a vida do compromisso, independentemente do período de análise atual.

**Operações e filtros de tabela**

- **Classificar** : Clique em um cabeçalho de coluna para classificar de forma decrescente, clique novamente para classificar de forma crescente e uma terceira vez para redefinir.
- **Mostrar/ocultar colunas** : Use o controle de colunas para escolher quais campos serão exibidos.
- **Paginação** : Os controles de paginação padrão aparecem abaixo da tabela.
- **Exportar** : O botão “Exportar” gera um arquivo do tipo “ CSV ” no formato WYSIWYG (o que você vê é o que você obtém) para o escopo atual e as colunas visíveis.

**Adicionar filtro e filtragem em linha**

- Use adicionar filtro (abaixo da barra de ferramentas do cabeçalho) para filtrar por qualquer campo suportado.
- As células com hiperlink estão disponíveis para filtragem. A seleção de uma célula vinculada filtrará a tabela por esse atributo e adicionará um chip à barra de filtros.

**Alertas e visualizações**

- **Alertas** : O botão de alertas no canto superior direito abre [os Alertas de compromisso](setting_commitment_alerts.html) para configurar os e-mails de Expiração e Limite de utilização.
- **Suporte a visualizações** : O portfólio suporta visualizações com escopo de conta e fornecedor. Outros mapeamentos de negócios não são suportados aqui porque as métricas por compromisso não podem ser computadas de forma confiável em remapeamentos arbitrários.

**Tabelas agrupadas versus não agrupadas do GCP**

Para o “ GCP ”, o Portfolio oferece suporte a duas perspectivas complementares, determinadas pela forma como o “ GCP ” relata os compromissos (créditos sem IDs de compromisso por uso e CUDs de recursos multidimensionais). Nas exportações, a ID da reserva normalmente não é definida.

- **Visão agrupada:** Agrega compromissos no escopo aplicável (por exemplo, conta de cobrança/região para GCE CUDs). Nessa visualização, o aplicativo pode mostrar métricas de desempenho por grupo.
- **Visualização não agrupada:** Espelha AWS / Azure com uma linha por compromisso. Algumas métricas de desempenho por item são omitidas quando os dados subjacentes não têm granularidade por compromisso. O painel de detalhes agrupados lista os CUDs que compõem o grupo.

## **Usar esta página para implementar as práticas recomendadas**

- **Horizonte de tempo** : Tendência por mês/trimestre para sinais em nível de portfólio; use semana/dia para confirmar a sazonalidade.
- **Disciplina de base** : Manter a fonte de preços e a base de reconhecimento consistentes em todas as comparações. Para obter mais informações, consulte [Cloudability Abordagem de custo do compromisso](commitment_approach_to_cost.html) e [como os fatores de preço negociado são considerados nos compromissos](custom_pricing_factors_across_commitments.html)
- **Showback/Chargeback** : Use os filtros do portfólio e os links [de cobertura](coverage_modal.html) para separar o que foi coberto do que não foi coberto por equipe/aplicativo para fins de responsabilidade.
- **Prontidão para renovação** : Compare a economia líquida e a utilização dos itens que estão prestes a expirar; decida renovar, trocar (se aplicável) ou simplesmente deixá-los expirar.
- **Controle de desperdício** : O vermelho persistente na [economia líquida](net_savings_modal.html) geralmente indica desalinhamento do escopo, excesso de compras ou sazonalidade - ajuste o prazo, o escopo ou a combinação de categorias.

## **Principais pontos**

- O portfólio é sua visão única dos compromissos assumidos e do desempenho histórico.
- Leia primeiro os KPIs agregados e, em seguida, use o painel de detalhes e os modais ( [Cobertura](coverage_modal.html) / [Economia Líquida](net_savings_modal.html) ) para entender os fatores determinantes.
- Use filtros, alternâncias agrupadas/não agrupadas e o contexto do fornecedor para passar do sinal à ação.
- Use [Alertas](setting_commitment_alerts.html) e [Recomendações para](using_commitment_recommendations_to_analyze_savings_opportunities.html) operacionalizar as descobertas.
- Trate o portfólio como seu sistema de registro; analise-o semanalmente para verificar as tendências e mensalmente para planejar a renovação.

**Tópico dos pais:** [Guia para gerenciamento de compromissos](../product/guide_to_commitment_management.html)
