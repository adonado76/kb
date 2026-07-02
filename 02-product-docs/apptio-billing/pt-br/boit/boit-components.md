---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Componentes do padrão de faturamento"
breadcrumb: []
source_path: "boit/boit-components.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Componentes do padrão de faturamento

Os componentes do site Billing Standard estão descritos abaixo. Billing Standard - O Foundation é o único componente necessário e instala a maioria dos conjuntos de dados, modelos e dimensões.

- **Billing Standard - Fundação** (obrigatório) - O componente Fundação é necessário para Billing Standard . Ele fornece relatórios baseados em cobranças, incluindo uma fatura que pode ser enviada aos usuários. Todos os modelos e tabelas necessários também são instalados com o componente Foundation.
- **Billing Standard - Aplicativos** (opcional) - O componente Aplicativo adiciona novos relatórios focados em relatórios de aplicativos. O componente adiciona dois novos relatórios:
  - O relatório **Cobranças de aplicativos** fornece à unidade de negócios e ao gerente de relacionamento comercial uma visão das cobranças de aplicativos e das licenças (unidades) utilizadas.
  - O relatório de **recuperação de aplicativos** oferece à TI uma visão dos dados de recuperação acima ou abaixo do esperado por aplicativo, em que os encargos do aplicativo são comparados ao custo de TI do aplicativo.
- **Billing Standard - Nuvem** (opcional) - O componente Nuvem adiciona novos relatórios focados em relatórios IaaS na nuvem. O componente adiciona dois novos relatórios e exercícios:
  - O relatório de **cobranças na nuvem** pode ser usado pela unidade de negócios e pelo gerente de relacionamento comercial para entender as cobranças de serviços na nuvem. Ele inclui uma lista detalhada dos serviços em nuvem usados pela unidade de negócios.
  - O relatório **Cloud Recovery** fornece dados de recuperação acima/abaixo por serviço. As cobranças pelo serviço são comparadas ao custo da prestação do serviço.
- **Billing Standard - Variação de Custo** (opcional) - O componente Variação de Custo permite a comparação de cobranças com o custo real de prestação dos serviços. O componente Cost Variance inclui muitos relatórios que só podem ser visualizados pela equipe com funções de Service Owners ou Business Relationship Manager.
- **Billing Standard - Variação do plano** (opcional) - O componente Variação do plano adiciona a capacidade de comparar cobranças ao orçamento e comparar custos a um orçamento. O componente habilita novos relatórios para análise de variação de orçamento e previsão e expõe comparações com o orçamento e a previsão nos relatórios existentes.
- **Billing Standard - Preço** (opcional) - O componente Preço permite expor um preço aos usuários finais. Os preços são definidos na Biblioteca de serviços. Qualquer ajuste ou combinação de preços aplicados a um serviço pode fazer com que o preço efetivo seja diferente do preço indicado na Biblioteca de serviços.
- **Billing Standard - Projetos** (opcional) - O componente Projetos adiciona novos relatórios focados em relatórios de Projetos. O componente adiciona dois novos relatórios com exercícios de apoio:
  - O relatório de **cobranças do projeto** pode ser usado pela unidade de negócios e pelo gerente de relacionamento comercial para ver as cobranças do projeto e os serviços de suporte que a unidade de negócios utilizou.
  - O relatório de **recuperação de projeto** fornece dados de recuperação acima/abaixo de TI por projeto, variação de orçamento e status.
- **Billing Standard - Servidores** (opcional) - O componente **Servidores** fornece ao Provedor de Serviços de TI e ao Consumidor Empresarial uma visão sobre a composição dos serviços oferecidos e consumidos. Billing Standard - Os servidores podem ser configurados para acomodar uma visão baseada em aplicativo e serviço dos custos e consumo do servidor.
- **Billing Standard - Unidades** (opcional) - O componente **Unidades** adiciona unidades em todos os relatórios existentes e calcula um preço efetivo dividindo a cobrança pelas unidades faturáveis. Um tipo de unidade pode ser definido por oferta de serviço. Quando a variação de custo também está instalada, as taxas unitárias podem ser comparadas.

**Instalar os componentes do site Billing Standard**

Billing Standard não são instalados automaticamente quando você cria um projeto Billing Standard . Você deve instalar cada componente separadamente. Somente o componente Billing Standard - Foundation é necessário.

Para instalar os componentes:

1. No TBM Studio, clique na guia **Project (Projeto** ).
2. Clique em **Components (Componentes** ).
3. Clique no componente **Billing Standard Foundation**.
4. Clique em **Install (Instalar** ).
5. Repita as etapas acima para cada um dos componentes opcionais do site Billing Standard que você deseja instalar.
