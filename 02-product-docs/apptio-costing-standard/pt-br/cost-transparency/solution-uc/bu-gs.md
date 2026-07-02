---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Unidade de Negócios Introdução"
breadcrumb:
  - "Costing Standard"
  - "Casos de uso da solução"
  - "Unidade de negócios"
source_path: "cost-transparency/solution-uc/bu-gs.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Unidade de Negócios Introdução

O componente Unidades de Negócio permite que as organizações compreendam como os custos de tecnologia são consumidos nas unidades de negócio, consolidando os custos de serviços e aplicações em uma única visão alinhada com os negócios. Ele oferece visibilidade completa do custo total dos aplicativos e serviços consumidos por cada unidade de negócios, promovendo transparência, responsabilidade e tomada de decisões informadas.

## Instalação de componentes

**CT – Unidades de Negócios**

O componente CT-Unidades de Negócio instala as estruturas de alocação necessárias para transferir os custos de aplicações e serviços para as unidades de negócio. Ele introduz mecanismos de alocação direta e indireta que garantem uma visão completa e justificável do consumo das unidades de negócios.

Use este componente quando desejar analisar os gastos totais com tecnologia por unidade de negócios, compreender os fatores que influenciam os custos e apoiar iniciativas de showback ou chargeback.

## **Pré-requisitos**

Você deve instalar os seguintes componentes antes de instalar o componente Alocações da Unidade de Negócios:

- CTF - Fonte de custos
- CTF - Torres de Recursos de TI
- Aplicativos CT - Aplicações
- Aplicativos CT - Serviços

**Fontes comuns de dados**

Os dados da unidade de negócios geralmente provêm de sistemas de hierarquia organizacional, sistemas de RH, plataformas de gerenciamento de serviços e aplicativos de planejamento de negócios. Os dados que você usa determinarão o nível de detalhes disponíveis e os métodos de alocação que você pode suportar.

As fontes de dados comuns incluem:

- **Sistemas de RH:** Dados sobre o número de funcionários e prestadores de serviços para alocações indiretas (Workday, SAP SuccessFactors, Oracle HCM).
- **Plataformas de gerenciamento de serviços:** dados de consumo de serviços e mapeamentos de unidades de negócios ( ServiceNow, BMC Remedy).
- **Sistemas de planejamento empresarial:** estrutura, programas e projetos da unidade de negócios (Anaplan, Adaptive Insights).
- **Gerenciamento do portfólio de aplicativos:** relações entre aplicativos e unidades de negócios e métricas de consumo.
- **Hierarquia organizacional:** estrutura da unidade de negócios, propriedade e relações hierárquicas a partir dos organogramas da empresa.

**Conjuntos de dados mestres**

Pode ser necessário carregar várias tabelas e mapeá-las para as tabelas de dados mestres fornecidas com o componente. As duas principais tabelas de dados mestre são:

- **Dados mestre de alocação da unidade de negócios**
  - Esta tabela define as unidades de negócios da sua organização e contém atributos utilizados para a alocação de custos indiretos. Inclui informações sobre a hierarquia organizacional, dados sobre o número de funcionários para cálculos de proporções de alocação e detalhes sobre a propriedade das unidades de negócios.
  - **Alocações de serviços Dados mestre diretos**
  - Esta tabela define a relação de consumo direto entre serviços comerciais e unidades comerciais. Ele contém as quantidades de consumo que determinam a alocação de custos diretos, juntamente com identificadores de serviços e unidades de negócios para mapeamento.

**Fluxo de alocação**

Depois de mapear os dados, os custos devem fluir pelo modelo da seguinte forma:

- **Serviços empresariais → Alocações de serviços diretas**
- **Serviços empresariais → Alocações de serviços indiretas**
- **Alocações de serviços diretas → Alocação por unidade de negócios:** Custos diretos alocados às unidades de negócios com base nas quantidades consumidas
- **Alocações de serviços indiretos → Alocação por unidade de negócios:** custos indiretos alocados às unidades de negócios com base nas proporções do número de funcionários
- **Projetos → Alocação da unidade de negócios:** Custos do projeto alocados diretamente às unidades de negócios associadas

**Alocações diretas vs. indiretas**

Em Apptio, os custos são alocados como **diretos** ou **indiretos** para garantir uma atribuição de custos precisa e justificável. **As alocações diretas** são baseadas no consumo e atribuem custos como mão de obra, software ou equipamentos diretamente a um produto, serviço, departamento ou projeto específico. Esses custos podem ser claramente atribuídos a um objeto de custo e, normalmente, representam a maior parte dos gastos controláveis. **As alocações indiretas** representam custos compartilhados ou indiretos necessários para o funcionamento da organização, tais como instalações, serviços públicos, equipamentos para usuários finais e infraestrutura geral, e são distribuídas utilizando índices de alocação definidos, como o número total de funcionários ou o número de funcionários por departamento.

No modelo de custos “ Apptio ”, as alocações diretas e indiretas são calculadas na parte superior do modelo utilizando quatro objetos principais: **Serviços Empresariais**, **Alocações de Serviços Diretas**, **Alocações de Serviços Indiretas** e **Alocação de Unidades Empresariais**. Os custos dos serviços comerciais fluem para **as alocações diretas de serviços** com base em mapeamentos explícitos de nível de serviço, enquanto os custos compartilhados fluem para **as alocações indiretas de serviços** com base na lógica de alocação configurada. Essa estrutura garante uma separação clara entre os custos diretos relacionados ao consumo e os custos indiretos compartilhados, permitindo transparência, consistência e relatórios precisos em todos os serviços, aplicativos e unidades de negócios.
