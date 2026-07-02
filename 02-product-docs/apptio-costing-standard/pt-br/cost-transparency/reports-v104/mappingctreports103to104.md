---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Mapeamento de relatórios de cálculo de custos padrão do modelo v103 para v104"
breadcrumb: []
source_path: "cost-transparency/reports-v104/mappingctreports103to104.html"
images:
  - "resources/images/ct_images/102-8842-17-189949_349-311_publiccloud.png"
  - "resources/images/ct_images/102-8842-17-189952_301-317_saas_insights.png"
  - "resources/images/ct_images/102-8842-17-189954_vendors.png"
  - "resources/images/ct_images/102-8842-17-189955_294-265_infrastructureinsights.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Mapeamento de relatórios de cálculo de custos padrão do modelo v103 para v104

Observação: Aplica-se a: Costing Standard em TBM Studio 12.3 e posterior, com o modelo v104 e posterior ([Saiba mais](ctreportcollections104-plus.html) )

A lista a seguir mapeia o movimento e a eliminação dos relatórios do modelo Costing Standard v103 para Costing Standard em execução em TBM Studio 12.3 + com o modelo v104.

Para entender a diferença entre os modelos, acesse [os relatórios Compare v104 e v103 Costing Standard](comparev103v104reports.html) .

Para obter instruções sobre a atualização para o modelo v104, acesse [Upgrade Costing Standard to v104](../user-guide/upgradectto104-8841.html "Este documento descreve as razões por trás da atualização da interface de usuário (UI) do Costing Standard e as etapas recomendadas para atualizar o conteúdo do aplicativo Apptio do modelo v103 para a versão mais recente do modelo de aplicativo.").

## Coleta de relatórios de analistas

A coleção **Analyst** ( v103 ) foi eliminada e os relatórios individuais foram transferidos:

- **Analyst - Applications** foi movido para a nova coleção de relatórios Applications como **Applications List**.
- **Analyst - Labor** foi transferido para a nova coleção de relatórios Labor como **Labor Analysis**.
- **Analista - Projetos** movidos para a nova coleção de relatórios de Projetos como **Lista de Projetos**.
- **Analyst - Vendor** foi movido para a nova coleção de relatórios Vendor como **Vendor List**.

## Coleção de relatórios do CIO Dashboards

A coleção CIO Dashboards ( v103 ) foi substituída por uma nova coleção de relatórios TBM Overview:

- **O Resumo do CIO** foi substituído pelo novo resumo **do Painel do TBM**.
- **O Resumo de Transparência de Custos** foi eliminado; as visualizações de camadas antigas foram movidas para novas coleções de relatórios.
- **Public Cloud Summarymoved** to the new Public Cloud report collection.
- **Resumo de Benchmarkingmovido** para a nova coleção de relatórios de Benchmarking.

## Coleta de relatórios de otimização de infraestrutura

Uma nova coleção de relatórios de Infraestrutura e Nuvem foi criada para v104. Ele inclui os seguintes relatórios:

- **Operações de TI - Resumo**
- **Operações de TI - TCO do servidor**
- **Operações de TI - TCO de armazenamento**

Os relatórios de **otimização de infraestrutura** ( v103 ) foram transferidos para o novo módulo Infrastructure Insights (no menu Projects):

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/102-8842-17-189955_294-265_infrastructureinsights.png)

Os seguintes relatórios de infraestrutura podem ser encontrados nesse novo módulo Infrastructure Insights (no menu **Projects** ):

- **Operações de TI - Análise de servidores**
- **Operações de TI - Análise de armazenamento**
- **Operações de TI - Análise de data centers**
- **Operações de TI - Análise da central de serviços**

Os seguintes relatórios de otimização de infraestrutura ( v103 ) foram eliminados:

- **Operações de TI - Servidores - Meta de eficiência**
- **Operações de TI - Armazenamento - Meta de eficiência**

## Coleta de relatórios do IT Finance

A coleção de relatórios do IT Finance ( v103 ) foi transferida para a nova coleção de relatórios do IT Financials:

- **IT Finance - O resumo** foi substituído pelo novo [relatório Financial Review ( v104](../reports-v107/itfmf-ct_financialreview107.html) ).
- **IT Finance - Outliers** foi substituído pelo novo [relatório de e-mail Financial Variance Review ( v104](itfmf-ct_financialvariancereviewemail104.html) ).
- **IT Finance - Cost Pools** não foi alterado, mas agora é intitulado [Cost Pool Analysis report ( v104](itfmf-ct_costpoolanalysis104.html) ).
- **IT Finance - Labor** foi substituído pelo relatório **Labor Review** na nova coleção de relatórios Resources.
- **IT Finance - O ativo fixo** foi transferido para a nova coleção de relatórios de recursos.
- **IT Finance - Os fornecedores** foram transferidos para a nova coleção de relatórios de fornecedores e divididos em vários relatórios.
- **Finanças de TI - Resumo da fatura do provedor de serviços de nuvem** foi eliminado.
- **Finanças de TI - A integração ITPF** foi eliminada e os seguintes relatórios foram alterados:
  - **ITP - Orçamento de mão de obra** e **ITP - Previsão de mão de obra** foram consolidados e movidos para a nova coleção de relatórios Recursos.
  - **ITP - Asset Budget** e **ITP - Asset Forecast** foram consolidados e movidos para a nova coleção de relatórios Resources.
  - **ITP - Orçamento de contrato** e **ITP - Previsão de contrato** foram consolidados e movidos para a nova coleção de relatórios de Fornecedores.

## Coleta de relatórios de gerenciamento de TI

A coleção de relatórios de gerenciamento de TI ( v103 ) foi reorganizada nas seguintes novas coleções de relatórios para v104:

- **IT Management - Summary** foi substituído pelo [relatório Financial Review ( v104](../reports-v107/itfmf-ct_financialreview107.html) ) na nova coleção de relatórios IT Financials.
- **IT Management - Financials** foi substituído pelo relatório IT Financial Review na nova coleção de relatórios IT Financials.
- **Gerenciamento de TI - Projetos** movidos para a nova coleção de relatórios de Projetos e divididos em vários relatórios.
- **Gerenciamento de TI - As Torres de TI** foram movidas para a nova coleção de relatórios de Recursos.
- **Gerenciamento de TI - Public Cloud** foi transferido para um novo módulo Public Cloud fora do Costing Standard.
- **O Portfólio de aplicativos** foi movido para a nova coleção de relatórios Aplicativos e dividido em vários relatórios.
- **Gerenciamento de TI - Os serviços** foram movidos para a nova coleção de relatórios de serviços e divididos em vários relatórios.
- **Gerenciamento de TI - As unidades de negócios** foram movidas para a nova coleção de relatórios de unidades de negócios e divididas em vários relatórios.

## Coleta de relatórios de benchmarking

A coleção de relatórios de Benchmarking foi muito pouco alterada para v104, exceto pelo seguinte:

- **O Resumo de Benchmark** foi movido da coleção de relatórios CIO Dashboards para a nova coleção de relatórios de Benchmarking.
- Os relatórios foram atualizados de acordo com o site ATUM v.2.
- O relatório de **comunicações** foi eliminado.

## Coleta de relatórios móveis

Toda a coleção de relatórios do Mobile foi eliminada, incluindo os seguintes relatórios:

- **iPad Painel de controle do CIO - Finanças**
- **iPad Painel de controle do CIO - Trabalho**
- **iPad Painel de controle do CIO - Projetos**
- E assim por diante

## Public Cloud

A coleção de relatórios Public Cloud foi transferida para o novo módulo Public Cloud (disponível no menu Projetos).

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/102-8842-17-189949_349-311_publiccloud.png)

## SaaS Insights (novo)

Foi adicionado um novo módulo SaaS Insights (disponível no menu Projects), que fornece análises de custo e licenciamento sobre os seguintes aplicativos:

- Office 365
- Salesforce
- Service Now
- Dia útil![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/102-8842-17-189952_301-317_saas_insights.png)

## Visão do fornecedor

O Vendor Insight deixou de ser um módulo separado (no menu Projects) e passou a fazer parte do site Costing Standard como uma nova coleção de relatórios Vendors.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/102-8842-17-189954_vendors.png)

## Veja também

[Compare os relatórios v104 e v103 Costing Standard](comparev103v104reports.html)
