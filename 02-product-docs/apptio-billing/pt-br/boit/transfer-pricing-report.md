---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Relatório de preços de transferência"
breadcrumb: []
source_path: "boit/transfer-pricing-report.html"
images:
  - "resources/images/boit_images/boit_transfer-pricing-report_kpis.jpg"
  - "resources/images/boit_images/boit_transfer-pricing-report_model.jpg"
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Relatório de preços de transferência

aplica-se a: Billing Standard em TBM Studio 12.6 e posterior

Para obter informações detalhadas sobre o preço de transferência, consulte [Configurar preço de transferência](configure-transfer-price.html).

O componente Preço de transferência adiciona dois novos objetos ao modelo:

- O objeto **Preço de transferência entre empresas** oferece um local para modelar seus débitos e créditos, ou fornece a capacidade de aplicar uma proporção para ajustar o preço de um serviço. O objeto inclui todos os dados do cadastro de todos os serviços comerciais e adiciona as seguintes colunas:
  - Entidade jurídica fornecedora
  - Localização do provedor
  - Entidade jurídica consumidora
  - Localização do consumidor
  - Taxa de transferência
  - Taxa de transferência ajustada
- O objeto **Legal Entities and Cross Charging** é uma duplicata do objeto Business Unit e do conjunto de dados mestre, acima do objeto Business Unit para cobranças e unidades de negócios nos conjuntos de dados Business Services e Business Units. Esse objeto permite redistribuir as taxas de serviço para níveis inferiores da hierarquia da unidade de negócios depois que a taxa inicial for incorrida.   
   Um exemplo de entidade jurídica pode ser uma unidade de negócios, uma unidade funcional ou um centro de custos.

![img](../../../../03-media/apptio-billing/resources/images/boit_images/boit_transfer-pricing-report_model.jpg)

As cobranças podem ser alocadas diretamente no objeto BU Allocation ou podem passar pelo objeto Transfer Pricing antes de serem cobradas. Se houver serviços que não possam ser transferidos por preço, você poderá usar uma combinação desses dois caminhos.

O fluxo geral do preço de transferência é:

1. Um provedor de serviços de TI define uma estratégia de preço de transferência.
2. Essa cobrança é alocada no objeto de preço de transferência, onde é ajustada em uma taxa fixa ou em uma proporção, dependendo da estratégia.
3. O custo é cobrado de volta da unidade de negócios.
4. Quando a primeira cobrança ocorrer, a empresa poderá usar o objeto Entidade legal e Cobrança cruzada para localizar essa cobrança em diferentes departamentos da mesma unidade de negócios.

**OBSERVAÇÃO** : Um filtro na alocação de Serviços de Negócios para Preço de Transferência entre Empresas é baseado na Taxa de Transferência (se a Taxa de Transferência = 0, os valores fluirão para a Alocação de BU, se a Taxa de Transferência não = 0, os valores fluirão através do Preço de Transferência entre Empresas).

Exemplos

**Caso de uso 1** - O Big Bank tem seis entidades jurídicas, ou unidades de negócios:

- Banco de Investimentos do Reino Unido LLC
- Banco de Investimentos da França LLC
- Banco de Investimentos Alemanha
- Banco Comercial do Reino Unido
- Banco Comercial França
- Banco Comercial de Luxemburgo

Embora essas seis unidades de negócios funcionem separadamente na organização do Big Bank, uma única organização de TI do Big Bank dá suporte a todas as seis. Nessa situação, a TI atua como um provedor de serviços interno (ou fornecedor externo) para prestar serviços de tecnologia a cada unidade de negócios e cobrar pelos serviços prestados.

**Caso de uso 2:** Outras organizações podem se dividir em "centros de excelência" ou centros regionais de TI que prestam um serviço focado aos outros centros da organização. Suponha que uma organização tenha os seguintes centros de TI:

- Gerenciamento de rede - Reino Unido
- Computação de médio porte - Irlanda
- Comunicação e colaboração - França

Cada centro cobra dos outros centros por seus serviços específicos. Um preço de transferência é aplicado a cada cobrança e, geralmente, é único para cada cobrança centro a centro. Nesse caso, a taxa de transferência tem um valor "de-para" que é diferente para cada país e serviço, de modo que a organização possa cobrar e alocar com precisão os custos entre as diferentes unidades de negócios, essencialmente permitindo que cada centro de custo faça a cobrança cruzada de outro. Além disso, alguns encargos talvez precisem ser redistribuídos para níveis inferiores da hierarquia da unidade de negócios.

**Exibir o relatório de preços de transferência**

1. No menu **Aplicativo**, clique em**Billing Standard** (consulte[Billing Standard menu](getting_started/boit-menu.html) ).
2. No menu **Coleção de relatórios**, clique em **Provedor de serviços de TI**.
3. Na barra na parte superior da página, clique em **Inter Company Transfer and Cross-Charging (Transferência entre empresas e cobrança cruzada** ).

O relatório contém os seguintes elementos:  
 ![img](../../../../03-media/apptio-billing/resources/images/boit_images/boit_transfer-pricing-report_kpis.jpg)

**(1) Coleção de relatórios -** A coleção de relatórios contém os seguintes relatórios:

- Resumo do provedor de serviços de TI
- Análise de recuperação
- Análise da taxa unitária
- Recuperação de aplicativos
- Recuperação na nuvem
- Recuperação de projetos
- Preços de transferência entre empresas e cobrança cruzada (descritos neste documento)

**(2) KPIs -** Os KPIs fornecem uma visão de alto nível de seus gastos com desenvolvimento e outras métricas.

- **Cobrança** - A cobrança principal de um determinado serviço.
- **Cobrança modificada do provedor** - O valor da cobrança após a aplicação da estratégia de preço de transferência.
- **Potencial** de economia - O custo do serviço com a estratégia de preços que introduz a maior redução de custos.
- **YTD Provider Modified Charge (Cobrança modificada do provedor Y** TD) - O valor da cobrança ajustada YTD.

**(3) Cobranças e cobranças modificadas por provedor -** Esta seção ajuda a entender a taxa de transferência para uma determinada combinação provedor-consumidor, bem como a cobrança resultante que está sendo faturada e a contagem de unidades faturáveis. Perguntas respondidas:

- Quais são minhas taxas de transferência e as cobranças resultantes?
- Qual é a porcentagem de serviços com cobrança cruzada?
- Qual é a tendência dos serviços com cobrança cruzada ao longo do tempo?
- Qual é a distribuição das cobranças por destino?

**(4) Detalhes da cobrança -** Essa tabela fornece uma visão do relacionamento de cada transação entre a entidade jurídica fornecedora e a entidade jurídica consumidora, e o impacto financeiro de cada transação. Essas informações o ajudam a entender e antecipar o lucro geral, a perda e a carga tributária de sua estratégia de preço de transferência. Perguntas respondidas:

- Qual é o impacto de nossa estratégia de preço de transferência?
- Qual é o impacto da cobrança cruzada entre pessoas jurídicas?
- Qual é a origem e o destino de minhas cobranças, por unidade de negócios?
