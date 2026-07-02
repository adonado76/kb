---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Resumo do contrato"
breadcrumb:
  - "Costing Standard"
  - "Relatório detalhado"
  - "Cobrança de fornecedores"
source_path: "cost-transparency/vi_content/report-contract-summary.html"
images:
  - "resources/images/vi_images/vi/alertsicon.jpg"
  - "resources/images/vi_images/vi/export.jpg"
  - "resources/images/vi_images/vi/vi_contract_summary_11.jpg"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Resumo do contrato

◆ Aplica-se a: Vendor Insights no TBM Studio 12.8 e posterior ( v107 )

Use o relatório **Resumo do contrato** para visualizar os gastos com contratos dos dez principais fornecedores e os detalhes dos contratos ao longo do tempo. Este relatório permite que você:

- Analise proativamente os contratos antes do vencimento e das renovações
- Analisar os termos comerciais do contrato
- Analisar o desempenho do SLA

Este relatório foi elaborado para:

- CIO e liderança sênior de TI
- Proprietários de aplicativos
- Proprietários de serviços
- Gerentes de Finanças de TI
- Gerentes de fornecedores

**Exibir o relatório Resumo do contrato**

No menu Aplicativo, selecione Vendor Insights .

1. Navegue até Coleções de relatórios > Contratos.
2. Na barra na parte superior da página, selecione Resumo do contrato.
3. Para exportar ou enviar seus dados por e-mail, selecione Exportar ( ![img](../../../../../03-media/apptio-costing-standard/resources/images/vi_images/vi/export.jpg) ) no canto superior direito da página e selecione um formato de exportação.
4. Para criar um alerta para notificá-lo quando um contrato estiver expirando, selecione Alerta ( ![img](../../../../../03-media/apptio-costing-standard/resources/images/vi_images/vi/alertsicon.jpg) ) no canto superior direito da página. Para saber mais, consulte [Criar alertas para contratos de fornecedores que estão prestes a expirar](alerts.html).

![img](../../../../../03-media/apptio-costing-standard/resources/images/vi_images/vi/vi_contract_summary_11.jpg)

**(1) Coleta de relatórios**

Esta coleção de relatórios fornece os detalhes necessários para analisar os gastos planejados e reais do contrato com o fornecedor e o progresso em direção ao cumprimento de quaisquer gastos mínimos contratuais:

- Resumo do contrato (descrito neste artigo)
- [Expiração do contrato](report-contract-expiration-12-6.html)
- [Contrato para Aplicações](report-contract-applications.html)
- [Notificação de expiração do contrato](report-contract-expiration-notification.html)

**(2) KPIs**

Os KPIs fornecem uma visão geral dos gastos e vencimentos dos seus contratos:

- **Gastos com contratos até à data** - Este KPI mostra o total de gastos com contratos acumulados no ano e os gastos mensais com contratos no período atual. Os gastos até à data são a soma de todas as contas a pagar associadas a contratos desde o início do ano fiscal até ao período atual.
- **Contratos ativos** - Este KPI mostra o número total de contratos ativos no período atual e o número total de contratos.
- **Contratos com vencimento em menos de 90 dias** - Este KPI mostra o número de contratos com vencimento em menos de 90 dias e menos de 180 dias.
- **Despesa mínima comprometida para contratos com vencimento em menos de 90 dias** - Este KPI mostra a despesa mínima comprometida para contratos com vencimento em menos de 90 dias e menos de 180 dias.

**(3) Gastos contratuais dos 10 principais fornecedores**

Use esta seção para identificar os 10 principais fornecedores com os maiores gastos contratuais no período atual e a tendência desses gastos no acumulado do ano.

Para obter detalhes adicionais sobre um fornecedor específico, clique no gráfico para abrir o [relatório Detalhes do fornecedor](report-vendor-detail.html).

**(4) Detalhes do contrato por fornecedor**

Utilize esta seção para visualizar os detalhes do contrato por **fornecedor**. Use o gráfico de barras para ver os fornecedores com os maiores gastos contratuais. Utilize a tabela para visualizar os detalhes desses contratos classificados pelo contrato com o maior gasto no topo.

Clique nas guias para visualizar os gastos com contratos para o período atual, trimestre atual, acumulado no ano e contratos sem gastos. Os filtros para nome normalizado do fornecedor, função e proprietário do contrato permitem restringir os resultados conforme necessário.

Para obter detalhes adicionais sobre um contrato específico, clique no gráfico ou clique na coluna **Título do** contrato na tabela para abrir o [relatório Detalhes do contrato](report-contract-detail.html).

**(5) Contratos por hierarquia**

Use esta seção para visualizar os detalhes do contrato por **contrato principal**. Use o gráfico de barras para ver os contratos principais com os maiores gastos contratuais. Utilize a tabela para visualizar os detalhes desses contratos classificados pelo contrato com o maior gasto no topo.

Clique nas guias para visualizar os gastos com contratos para o período atual, trimestre atual e acumulado no ano. Os filtros para nome normalizado do fornecedor, contrato principal e proprietário do contrato permitem restringir os resultados conforme necessário.

Para obter detalhes adicionais sobre um contrato específico, clique no gráfico ou clique na coluna **Título do** contrato na tabela para abrir o [relatório Detalhes do contrato](report-contract-detail.html).

**(6) Plano contratual**

Use esta seção para visualizar os detalhes dos gastos orçados do contrato. Use o gráfico de barras para ver o fornecedor com o maior gasto do orçamento do contrato. Utilize a tabela para visualizar os detalhes desses contratos classificados pelo contrato com o maior gasto no topo.

Clique nas guias para visualizar o plano contratual original da ITP e o plano contratual mais recente. Os filtros para proprietário do centro de custos, nome do centro de custos, fornecedor, tipo de contrato e localização permitem restringir os resultados conforme necessário.

Use as opções acima da tabela para adicionar detalhes específicos à sua análise, incluindo proprietário do centro de custos, nome do centro de custos e localização.

Esta seção só aparecerá com a [integração](../../it-planning/planning/integrate-ct.html "Se a sua organização utiliza tanto o padrão de custos Apptio quanto o aplicativo de planejamento Apptio, é possível integrá-los para compartilhar dados.") do ITP para Vendor Insights extrair o orçamento do ITP.

**(7) Contrato ARC RRC**

Use esta seção para visualizar uma visão geral dos contratos ARC RRC. Use o gráfico de barras para ver o valor máximo do contrato de referência para contratos ARC RRC. Utilize a tabela para visualizar os detalhes desses contratos ARC RRC por fornecedor, ordenados pelo contrato com o custo base mais alto no topo.

Clique no botão **Contrato ARC RRC** para navegar até o relatório **Resumo ARC RRC**. Os filtros para a unidade de recurso e o fornecedor permitem restringir os resultados conforme necessário.

Use as opções acima da tabela para adicionar detalhes específicos à sua análise, incluindo unidades reais, variação entre a fatura e as unidades reais, descrição da unidade de recurso, torre de recursos de TI e subtorre de recursos de TI.

Para obter detalhes adicionais sobre um contrato específico, clique na coluna **Título do** contrato na tabela para abrir o [relatório Detalhes do contrato](report-contract-detail.html).

**Veja o resumo do ARC RRC**

Para saber como visualizar o Resumo ARC RRC, consulte [o relatório Resumo ARC RRC](report-arcrrc-summary.html).

Perguntas respondidas

Use as informações deste relatório para responder às seguintes perguntas:

- Corro o risco de gastar demais ou de menos?
- Estamos cumprindo nosso gasto mínimo contratado?
- Como posso verificar se os serviços estão sendo prestados conforme o esperado?
- Quais são os detalhes de cada contrato (datas de renovação e vencimento, mínimos contratuais, alterações nas taxas, etc.)?
