---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Notificação de expiração do contrato"
breadcrumb:
  - "Costing Standard"
  - "Relatório detalhado"
  - "Cobrança de fornecedores"
source_path: "cost-transparency/vi_content/report-contract-expiration-notification.html"
images:
  - "resources/images/vi_images/vi/alertsicon.jpg"
  - "resources/images/vi_images/vi/contract-expiration-notification_kpis.jpg"
  - "resources/images/vi_images/vi/export.jpg"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Notificação de expiração do contrato

◆ Aplica-se a: Vendor Insights em TBM Studio 12.8 e posterior ( v107 )

Com o crescimento da TI, surge um número cada vez maior de contratos com fornecedores, despesas pré-negociadas, renovações e vencimentos de contratos. Os contratos de fornecedores exigem atenção constante para evitar a renovação automática acidental e aumentos inesperados de preços. Além disso, é difícil manter as partes interessadas informadas sobre os contratos que estão expirando para que possam tomar decisões informadas sobre renovações e negociações. O relatório Contract Expiration Notification (Notificação de vencimento do contrato) em Vendor Insights foi criado para fornecer essas informações e facilitar o gerenciamento de contratos.

**OBSERVAÇÃO** : O relatório Notificação de expiração do contrato pode ser anexado a alertas de e-mail que são gerados antes da expiração dos contratos, com base nas configurações de limite definidas pelo usuário. Para obter mais informações, consulte [Alertas para a expiração do contrato do fornecedor](alerts.html).

Este relatório foi elaborado para funções, como as listadas abaixo, que decidem se os contratos devem expirar, renegociar os termos e fornecer feedback como partes interessadas:

- Proprietários de contratos
- Gerentes de fornecedores
- Proprietários de aplicativos
- Proprietários de serviços

Casos de uso

- Quais contratos estão expirando e quando?
- Como posso saber quais contratos precisam de atenção sem ter que verificar diariamente o relatório de vencimento do contrato?
- Um contrato foi renovado ou expirou. Isso requer acompanhamento?
- Como posso garantir que todas as partes interessadas estejam cientes das alterações contratuais?
- Quais são meus contratos essenciais e quais serviços eles suportam?

**Exibir o relatório Notificação de expiração do contrato**

O relatório Notificação de expiração do contrato pode ser aberto a partir de um e-mail gerado quando um limite de expiração do contrato é atingido. Você também pode navegar até o relatório em Vendor Insights :

No menu Aplicativo, selecione  Vendor Insights .

1. Navegue até Report Collections > Contracts (Coleções de relatórios > Contratos ).
2. Na barra na parte superior da página, selecione Contract Expiration Notification (Notificação de expiração do contrato ).
3. Opcionalmente, filtre o relatório usando as opções na parte superior do relatório.
4. Para exportar ou enviar seus dados por e-mail, selecione Exportar ( ![imagem](../../../../../03-media/apptio-costing-standard/resources/images/vi_images/vi/export.jpg) ) no canto superior direito da página e selecione um formato de exportação.
5. Para criar um alerta para notificá-lo se um contrato estiver expirando, selecione Alerta ( ![imagem](../../../../../03-media/apptio-costing-standard/resources/images/vi_images/vi/alertsicon.jpg) ) no canto superior direito da página. Para saber mais, consulte [Criar alertas para contratos de fornecedores que estão expirando](alerts.html).
6. Selecione qualquer item na coluna Título do contrato da tabela para abrir o relatório Detalhes do contrato para esse contrato. Consulte [o relatório Detalhes do contrato](report-contract-detail.html).

O relatório contém os seguintes elementos:

![imagem](../../../../../03-media/apptio-costing-standard/resources/images/vi_images/vi/contract-expiration-notification_kpis.jpg)

**(1) Coleta de relatórios**

Essa coleção de relatórios fornece os detalhes de que você precisa para analisar os gastos do seu portfólio de fornecedores por tipo de fornecedor e por tempo:

- [Relatório de resumo do contrato](report-contract-summary.html)
- [Relatório de expiração do contrato (TBM Studio 12.6 e posterior)](report-contract-expiration-12-6.html)
- [Relatório de contrato para aplicativos](report-contract-applications.html)
- Notificação de vencimento do contrato (descrita neste artigo)

**(2) Cortadores**

Os seguintes filtros globais estão disponíveis nessa coleção de relatórios:

- **Vendor Manager (Gerente de** fornecedores) - Filtre por uma pessoa específica para que você possa ver o impacto dos fornecedores gerenciados por essa pessoa.
- **Nome do fornecedor normalizado** - Filtrar por um fornecedor específico.

**(3) Filtros**

Use os seguintes filtros locais para limitar os contratos exibidos na tabela Detalhes **da expiração do contrato** :

- **Renovação automática** - Filtre a coluna **Renovação automática** para contratos definidos para renovação automática (definida como **Sim** ) versus contratos que não serão renovados automaticamente (definida como **Não** ). Remova o filtro para exibir todos os contratos.
- **Criticidade do contrato** - Filtre a coluna **Criticidade do contrato** para obter contratos marcados com diferentes níveis de criticidade do contrato (como Crítico para a missão, Essencial para os negócios, Discricionário ou Estratégico). Remova o filtro para exibir todos os contratos, independentemente da criticidade.
- **Proprietário do contrato** - Filtre a coluna **Proprietário do contrato** para obter contratos por proprietário. Remova o filtro para exibir todos os contratos, independentemente do proprietário.
- **Tipo de fornecedor** - Filtre a coluna **Tipo de fornecedor** para contratos com base no tipo de fornecedor (por exemplo, se o contrato é de um fornecedor com um tipo de fornecedor preferencial ou estratégico). Remova o filtro para exibir todos os contratos, independentemente do tipo de fornecedor.

**(3) por data de expiração**

Use essa guia para visualizar os dados do contrato com base na data de término do contrato. Os contratos são classificados pela data de vencimento do contrato, listando primeiro os que vencem hoje. A tabela fornece uma visão rápida das informações mais importantes sobre os contratos, incluindo a data de término, o proprietário, os dias restantes para a expiração, os dias de notificação e o valor do contrato.

Para obter mais informações sobre um contrato específico, clique na coluna Título do contrato para abrir o [relatório Detalhes do contrato](report-contract-detail.html).

**(4) por nome do fornecedor**

Essa visualização exibe os mesmos dados da guia **Expiration Date (Data de vencimento** ), exceto pelo fato de que, ao clicar nessa guia, a coluna **Vendor Name (Nome do fornecedor)** é movida para a coluna mais à esquerda e classificada por Vendor Name (Nome do fornecedor) em ordem crescente.

**(5) Ícone de alertas**

Clique nesse ícone para abrir a página **Threshold Alerts (Alertas de limite** ), que lista todos os alertas e seus respectivos status. Nessa página, você pode clicar em qualquer alerta para abrir a página **Threshold Setting (Configuração de limite)** e editar os limites. Para obter mais informações sobre como definir alertas, consulte [Criar alertas para contratos de fornecedores que estão expirando](alerts.html).
