---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Introdução à nuvem pública"
breadcrumb:
  - "Costing Standard"
  - "Casos de uso financeiro"
  - "Nuvem pública"
source_path: "cost-transparency/it-financials/pc-getstart.html"
images:
  - "resources/images/ct_images/pc-itfin.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Introdução à nuvem pública

## Nuvem pública integrada Introdução

Use o componente **Public Cloud Integrated (CTF-Cloud)** para carregar, alocar e analisar os gastos com nuvem pública como parte do modelo Costing Standard. Este componente permite a geração de relatórios sobre os custos de IaaS e PaaS na nuvem pública e oferece suporte à análise completa do TCO da nuvem, combinando os dados de faturamento do provedor de nuvem com os custos de TI baseados no razão geral.

Instale e configure este componente antes de analisar os relatórios da nuvem. Após a instalação do componente, os dados de faturamento da nuvem são inseridos automaticamente e mapeados para as tabelas de dados mestres necessárias para dar suporte à alocação, geração de relatórios e análise em torres de recursos de TI, aplicativos e serviços.

**Instalação de componentes**

O componente CTF-Cloud fornece os dados e a lógica fundamentais necessários para relatórios e análises de nuvem pública. Ele oferece os seguintes recursos:

- Permite que relatórios e KPIs acompanhem e gerenciem os gastos com nuvem pública entre provedores, serviços e torres de recursos de TI.
- Utiliza dados detalhados de faturamento em nuvem para mapear serviços em nuvem para subtorres de recursos de TI e alocar custos do razão geral em um nível mais granular.

Esse componente é usado quando as organizações desejam ter visibilidade dos custos do provedor de nuvem e dos custos não relacionados ao provedor**,** como mão de obra, software e serviços de TI compartilhados, necessários para operar ambientes de nuvem.

**Relatórios de TCO da Nuvem Pública NX (Componente adicional)**

Este componente oferece relatórios NX predefinidos com base em dados de custos da nuvem pública para análise por serviço, conta e período.

Use este componente quando:

- Você precisa de relatórios padrão de custos de nuvem
- Você deseja comparar os valores reais com os orçamentos
- Você precisa de relatórios consistentes sobre os custos da nuvem

**Pré-requisitos**

Antes de usar o componente CTF-Cloud, certifique-se de que os seguintes componentes estejam instalados e configurados:

- CTF - Fonte de custos
- CTF - Fornecedor

Esses componentes fornecem o contexto financeiro e de fornecedores necessário para arcar integralmente com os custos da nuvem.

**Fontes de dados na nuvem**

Os dados relativos aos custos da nuvem pública são obtidos a partir de Cloudability e introduzidos em Apptio através do ApptioData Management (ADM)**.** Os dados são atualizados periodicamente e carregados em tabelas de faturamento mensal específicas da nuvem, incluindo:

- AWS: `cldy_monthly_aws`
- Azure: `cldy_monthly_azure`
- GCP: `cldy_monthly_gcp`

Para obter orientações adicionais sobre como configurar o ADM ( Apptio ) Data Management, consulte a documentação disponível [aqui](https://www.ibm.com/docs/en/apptio-platform/adm/saas?topic=creation-entity-cloudability "(Abre em uma nova guia ou janela)")

**Conjuntos de dados**

**CLDY Transform Master Data** - Os dados de faturamento das tabelas mensais da nuvem são então mapeados para o CLDY Transform Master Data, que normaliza os serviços específicos do provedor.

**Dados mestres do provedor de serviços em nuvem** - Os dados transformados são subsequentemente mapeados para os dados mestres do provedor de serviços em nuvem, permitindo uma classificação consistente entre os provedores e o alinhamento com o Modelo Unificado TBM ( Apptio ) ( ATUM ).

Para obter orientações detalhadas, consulte a documentação disponível aqui.

## Nuvem pública para relatórios financeiros de TI

Os relatórios sobre a nuvem pública para finanças de TI fornecem às equipes financeiras de TI uma visão consolidada e focada nas finanças dos gastos com nuvem pública nos principais provedores de nuvem, como AWS e Azure. Esses relatórios foram elaborados para destacar os fatores financeiros que influenciam os custos da nuvem, incluindo serviços que contribuem para o aumento dos gastos, a eficácia do modelo de compra, o comportamento da taxa unitária e as tendências de consumo. Com detalhamentos integrados, os relatórios permitem uma análise mais profunda das variações de custos por fornecedor, serviço, conta e fatores comerciais ou técnicos subjacentes, apoiando uma governança financeira mais forte e uma tomada de decisão informada.

Este relatório foi elaborado para ser utilizado pelas seguintes funções:

- Finanças de TI
- Controladores financeiros

**Informações fornecidas:**

- Identifique os serviços e provedores de nuvem que mais geram custos para concentrar os esforços de controle e otimização de custos.
- Avalie a eficácia dos modelos de compra de nuvem em relação aos melhores benchmarks da categoria para descobrir oportunidades de economia.
- Monitore as taxas unitárias e as tendências de consumo para detectar anomalias nos preços, melhorias na eficiência ou aumentos nos custos decorrentes do uso.
- Use a análise detalhada para vincular custos a contas específicas, serviços comerciais e aplicativos para fins de prestação de contas, análise de causa raiz e decisões orçamentárias informadas.

Para obter mais detalhes sobre como usar a Nuvem Pública para relatórios de finanças de TI, clique [aqui.](https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=reports-public-cloud-tcooverview "(Abre em uma nova guia ou janela)")

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/pc-itfin.png)

## Nuvem pública para finanças de TI Introdução

A nuvem pública para finanças de TI permite que as organizações analisem e controlem os gastos com a nuvem pública usando um modelo centrado nas finanças, focado nos custos do provedor, no uso e na economia unitária. A solução se integra diretamente aos dados d Cloudability, oferecendo relatórios padronizados e independentes de provedores para o AWS, Azure, GCP e OCI, sem a necessidade de alocação de custos não relacionados a provedores. Ele foi projetado para implantação rápida e é ideal para equipes financeiras de TI que buscam visibilidade rápida dos gastos com nuvem, tendências e oportunidades de otimização.

**Instalação de componentes**

**Custo total de propriedade da nuvem pública**

Este componente suporta integração com os seguintes provedores de nuvem:

- Amazon Web Services (AWS)
- Microsoft Azure
- Google Cloud Platform (GCP)
- Oracle Infraestrutura em nuvem (OCI)

Observação: este componente está disponível nos modelos **v120 e posteriores**.

Após instalar o componente, prossiga com o carregamento e o mapeamento dos conjuntos de dados necessários nas tabelas de dados mestres para permitir a geração de relatórios.

**Fontes comuns de dados**

A nuvem pública para finanças de TI depende do Cloudability como fonte principal de dados sobre custos e uso da nuvem:

- **Apptio Data Management (ADM)**

  Fornece conjuntos de dados mensais sobre gastos e uso da nuvem, como `cldy_monthly_aws` e `cldy_monthly_azure`, que formam a base para relatórios de custos e consumo.

  Para obter orientações adicionais sobre como configurar o ADM ( Apptio ) Data Management, consulte a documentação disponível [aqui](https://www.ibm.com/docs/en/apptio-platform/adm/saas?topic=creation-entity-cloudability "(Abre em uma nova guia ou janela)")
- **Cloudability Relatórios de instâncias reservadas (RI) por meio de serviços REST**

  Dados sobre horas reservadas e utilização, utilizados para calcular a eficácia das Instâncias Reservadas e dos Planos de Economia nos sites AWS, Azure e GCP.

**Conjuntos de dados principais**

Para habilitar a geração de relatórios, os **cinco conjuntos de dados de entrada** a seguir devem ser criados e mapeados usando dados de origin Cloudability es (por exemplo, `cldy_monthly_aws` `cldy_monthly_azure`):

- **Mapeamento de contas → Mapeamento de nomes de contas**

  Alinha nomes de contas na nuvem extraídos de conjuntos de dados do Cloudability.
- **Entrada de referência da BU → Referência da unidade de negócios**

  Normaliza regiões ou identificadores organizacionais em unidades de negócios padronizadas.
- **Entrada do Mapeamento da Torre das Nuvens → Mapeamento da Torre das Nuvens**

  Mapeia as famílias de uso da nuvem para nomes normalizados da Cloud Tower para garantir a consistência dos relatórios.
- **Entrada CC → Lista de centros de custo**

  Mapeia centros de custo e categorias; quaisquer valores não mapeados aparecem como *Não atribuídos*.
- **Entrada RI → Horas reservadas**

  Permite o cálculo das métricas de utilização de Instâncias Reservadas e Planos de Economia em todos os provedores compatíveis.
- Mapeie os conjuntos de dados acima para **os dados mestres do IT Finance Cloud** usando a coluna *“Fonte de dados”* para referenciar o nome do conjunto de dados “ Cloudability ” (por exemplo, `cldy_monthly_aws`).

Para obter orientações detalhadas sobre a configuração, consulte a documentação de apoio [aqui.](https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=reports-public-cloud-tcoconfiguration "(Abre em uma nova guia ou janela)")
