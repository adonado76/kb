---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Expiração do contrato"
breadcrumb:
  - "Costing Standard"
  - "Relatório detalhado"
  - "Cobrança de fornecedores"
source_path: "cost-transparency/vi_content/report-contract-expiration-12-6.html"
images:
  - "resources/images/vi_images/vi/alertsicon.jpg"
  - "resources/images/vi_images/vi/contract-expiration-report-12-6_main.jpg"
  - "resources/images/vi_images/vi/export.jpg"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Expiração do contrato

◆ Aplica-se a: Vendor Insights no TBM Studio 12.8 e posterior ( v107 )

Use o relatório de vencimento de contratos para analisar proativamente os contratos antes do vencimento e das renovações. Este relatório foi elaborado para:

- Gerentes de fornecedores
- Proprietários de serviços
- Proprietários de aplicativos
- Gerentes de Finanças de TI
- CIO e liderança sênior de TI

**Exibir o relatório de vencimento do contrato**

No menu Aplicativo, selecione Vendor Insights .

1. Navegue até Coleções de relatórios > Contratos.
2. Na barra na parte superior da página, selecione Expiração do contrato.
3. Opcionalmente, filtre o relatório usando as opções na parte superior do relatório.
4. Para exportar ou enviar seus dados por e-mail, selecione Exportar ( ![imagem](../../../../../03-media/apptio-costing-standard/resources/images/vi_images/vi/export.jpg) ) no canto superior direito da página e selecione um formato de exportação.
5. Para criar um alerta para notificá-lo quando um contrato estiver expirando, selecione Alerta ( ![imagem](../../../../../03-media/apptio-costing-standard/resources/images/vi_images/vi/alertsicon.jpg) ) no canto superior direito da página. Para saber mais, consulte [Criar alertas para contratos de fornecedores que estão expirando](alerts.html).
6. Selecione qualquer item na coluna Título do contrato da tabela no componente Relatório de detalhes de vencimento do contrato para abrir o relatório Detalhes do contrato para esse contrato. Para saber mais, consulte [o relatório Detalhes do contrato](report-contract-detail.html).

O relatório contém os seguintes elementos:

![imagem](../../../../../03-media/apptio-costing-standard/resources/images/vi_images/vi/contract-expiration-report-12-6_main.jpg)

**(1) Coleta de relatórios**

Esta coleção de relatórios fornece os detalhes necessários para analisar os gastos do seu portfólio de fornecedores por tipo de fornecedor e período:

- [Relatório resumido do contrato](report-contract-summary.html)
- Relatório de expiração de contrato (descrito neste artigo)
- [Relatório de contratos para aplicações](report-contract-applications.html)
- [Relatório de notificação de expiração do contrato](report-contract-expiration-notification.html)

**(2) Fatiadores**

Os seguintes filtros globais estão disponíveis nesta coleção de relatórios:

- **Gerente de fornecedores** - Filtre por uma pessoa específica para ver o impacto dos fornecedores gerenciados por essa pessoa.
- **Nome do fornecedor normalizado** - Filtrar por um fornecedor específico.

**(3) KPIs**

Os KPIs fornecem uma visão geral dos gastos com fornecedores e do vencimento dos contratos:

- **Valor com vencimento em 30 dias** - Este KPI mostra o gasto total para o período atual e o número de fornecedores com gastos no período atual. O gasto é a soma de todas as contas a pagar no período atual.
- **Valor com vencimento entre 31 e 60 dias** - Este KPI mostra o gasto total com fornecedores no acumulado do ano e a diferença no gasto acumulado entre o ano anterior e o atual.
- **Valor com vencimento entre 61 e 90 dias** - Este KPI mostra o número de contratos com vencimento em menos de 90 dias e em menos de 180 dias.
- **Valor com vencimento entre 91 e 180 dias** - Este KPI mostra o gasto mínimo comprometido para contratos com vencimento em menos de 90 dias e em menos de 180 dias.

**(4) Tendência de vencimento dos contratos**

Use esta seção para entender quantos contratos estão expirando nos próximos meses ou trimestres (gráfico de linhas) e o valor dos contratos afetados (gráfico de barras). Esta seção ajuda você a visualizar o impacto das expirações de contratos futuras e o esforço que pode ser necessário para planejar as renovações de contratos.

- Clique na guia **1 ano (mensal)** para ver o valor do contrato e o número de contratos com fornecedores que expiram nos próximos 12 meses, em incrementos mensais. Visualize o valor total mensal dos contratos que expiram passando o cursor sobre o gráfico de barras.
- Clique na guia **3 anos (trimestral)** para ver o valor do contrato e o número de contratos de fornecedores com vencimento previsto nos próximos três anos, em incrementos trimestrais.

**(5) Detalhes sobre o vencimento do contrato**

Utilize esta seção para visualizar os detalhes dos contratos que estão expirando por período. Você pode ver o contrato com maior valor gasto durante um período selecionado classificando a coluna **Valor do contrato**.

Use as guias para visualizar diferentes períodos. Definir um filtro permite restringir os resultados conforme necessário. Para obter detalhes adicionais sobre um contrato específico, clique na coluna **Título do** contrato para abrir o [relatório Detalhes do contrato](report-contract-detail.html).

O valor **de Dias de notificação** será destacado em vermelho quando um contrato estiver vencido, para que você possa notificar o fornecedor para atualizar o contrato.

A partir da versão 12.7, uma coluna para **Suprimir Alerta** foi adicionada à tabela Detalhes. **Sim** significa que os alertas são suprimidos para o contrato.

Perguntas respondidas

- Quais contratos estão expirando e quando?
- Quais contratos estão prestes a ser renovados e quando?
- Quais são os meus contratos críticos e os serviços que eles oferecem?
