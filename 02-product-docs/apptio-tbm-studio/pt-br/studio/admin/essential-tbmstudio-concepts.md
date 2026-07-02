---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Conceitos essenciais do TBM Studio"
breadcrumb: []
source_path: "studio/admin/essential-tbmstudio-concepts.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Conceitos essenciais do TBM Studio

Aplica-se a: TBM Studio 12.0 e posterior. Em TBM Studio, você organiza seu trabalho em projetos. Em um projeto, você coleta e transforma dados em conjuntos de dados, cria modelos, adiciona objetos aos modelos, atribui conjuntos de dados aos objetos, aloca custos de um objeto para outro e resume os resultados em um ou mais relatórios. Instâncias, domínios e projetos organizam seu trabalho:

- **Instância** - Um Apptio SaaS (Software as a Service) que abriga domínios e projetos de clientes. Em uma instância, pode haver vários domínios. Em um domínio, pode haver vários projetos.
- **Domínio** - O ambiente Apptio estabelecido para uma organização específica. Foi atribuído à sua organização um domínio que contém todos os seus projetos.
- **Projeto** - A área de cálculo em um domínio Apptio no qual são criados modelos e relatórios. Um projeto contém conjuntos de dados, métricas e relatórios que são interligados e interdependentes.

O fluxo de trabalho básico para criar um projeto inclui:

- Criar tabelas a partir de dados importados.
- Crie um modelo para mostrar o fluxo de dados na organização. Os dados usados com mais frequência são os custos. Um modelo calcula o custo dos serviços oferecidos por sua organização.
- Crie métricas de modelo para calcular valores diferentes. Por exemplo: custo, orçamento, previsão.
- Crie o modelo alocando o custo de uma tabela para outra. As tabelas de origem podem ser um registro geral ou uma fatura de serviços da Web. As tabelas de destino podem ser aplicativos e unidades de negócios.
- Defina métricas calculadas com base nas métricas modeladas e nas tabelas de dados. Uma métrica calculada comum subtrai os custos reais dos custos planejados.
- Criar relatórios para apresentar os dados calculados nos modelos.

Seu ambiente Apptio contém um ou mais projetos que organizam seu trabalho de modelagem e geração de relatórios. Os projetos consistem nos seguintes elementos:

- **Tabelas de dados** - As tabelas de dados contêm os dados do projeto. Você pode fazer upload de dados de várias fontes, incluindo arquivos do Excel e arquivos simples delimitados por vírgulas, tabulações, pipes ou outros separadores. As fontes de dados comuns incluem um arquivo de contabilidade geral e uma fatura de serviços da Web. Para obter mais informações, consulte [Sobre Data Studio](../data_studio/data-transform-chapter-title-page.html "Aplica-se a: TBM Studio 12.0 e posterior").
- **Modelo de dados** - Um modelo de dados é uma representação lógica e gráfica do custo, da utilização, dos níveis de serviço ou de outros dados relevantes para seus serviços de TI. A estrutura do modelo de dados em um projeto determina o tipo de informação que pode ser exibida nos relatórios desse projeto. Para obter mais informações, consulte [Sobre Data Studio](../data_studio/data-transform-chapter-title-page.html "Aplica-se a: TBM Studio 12.0 e posterior").
- **Métricas** - As métricas são cálculos que definem o valor. Há dois tipos de métricas:
  - **Métricas modeladas** - Um modelo de dados é, por si só, uma métrica. Um modelo calcula uma única medida, como custo ou orçamento. Os modelos de dados às vezes são chamados de métricas modeladas.
  - **Métricas calculadas** - Uma métrica calculada usa uma fórmula para derivar um valor de métricas modeladas. Por exemplo, você pode criar uma métrica calculada chamada Budget\_Variance que subtrai a métrica do modelo de custo da métrica do modelo de orçamento. Para obter mais informações, consulte [Criar e gerenciar métricas](../model_studio/introduction-to-metrics.html "Aplica-se a: TBM Studio 12.0 e posterior").
- **Relatórios** - Um modelo de dados adequadamente estruturado permitirá que você crie uma variedade de relatórios úteis em uma granularidade que atenda aos seus requisitos de relatórios. Para obter mais informações, consulte [TBM Studio Sobre o Report Studio](../reports/report_studio_title_topic.html).

- **[TBM Studio Sobre o Report Studio](../../studio/reports/report_studio_title_topic.html)**
- **[Layout do relatório](../../studio/reports/report-layout.html)**  
   **Aplica-se a** : TBM Studio 12.0 e posterior
