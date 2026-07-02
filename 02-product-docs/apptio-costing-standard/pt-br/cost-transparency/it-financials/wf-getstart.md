---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Força de trabalho Introdução"
breadcrumb:
  - "Costing Standard"
  - "Casos de uso financeiro"
  - "Força de trabalho"
source_path: "cost-transparency/it-financials/wf-getstart.html"
images:
  - "resources/images/ct_images/wf-gs.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Força de trabalho Introdução

Use os componentes Workforce & Time Tracking para carregar, alocar e analisar dados de custos de mão de obra e número de funcionários entre funcionários internos e prestadores de serviços externos. Esses componentes permitem relatórios de gastos com mão de obra, acompanhamento do número de funcionários, alocação da força de trabalho e análise da mão de obra em nível de projeto.

Dependendo do seu modelo operacional (waterfall, ágil ou híbrido), você pode instalar um ou mais componentes relacionados ao trabalho para dar suporte aos requisitos de relatórios e alocação da força de trabalho.

## Instalação de componentes

**CTF - Trabalho**

- O componente CTF-Trabalho permite relatar e analisar os custos de mão de obra e o número de funcionários, tanto para funcionários efetivos quanto para contratados. Ele permite comparar os custos reais e o número de funcionários com o planejado e o orçado.
- Acompanhe os custos de mão de obra e o número de funcionários por centro de custos, função, projeto e torre de TI
- Analisar variações no orçamento de mão de obra
- Apoiar a responsabilidade pelos custos com a força de trabalho
- Após instalar este componente, você deve carregar os dados de mão de obra e mapeá-los para a tabela **Dados Mestre de Mão de Obra** para preencher os relatórios de mão de obra relacionados a custos e orçamento

**CTF - Unidades de Trabalho**

O componente CTF-Unidades de Trabalho permite a alocação precisa da mão de obra entre projetos, aplicações e produtos em modelos operacionais em cascata, ágeis ou híbridos.

- Alocar mão de obra entre várias subtorres de recursos de TI
- Suporte modelos operacionais de TI ágeis, de projeto ou híbridos
- Relate o número exato de funcionários por aplicação, produto ou projeto

Este componente utiliza os dados mestre de mão de obra como fonte e introduz lógica e métricas de alocação adicionais, incluindo efetivo interno, efetivo externo e unidades de mão de obra.

- Revisar e ajustar alocações (Trabalho → Outras alocações de trabalho → Torres de recursos de TI)
- Aplique métricas **de pessoal interno**, **pessoal externo** e **unidades de trabalho** a alocações personalizadas
- Utilize **o ID do trabalhador** e **o fator de ponderação** para a lógica de alocação
- Consulte o diagrama abaixo para ver o modelo recomendado

**Relatórios CTF-Labor NX (Componente adicional)**

Este componente fornece relatórios NX predefinidos com base em dados de mão de obra para análise por centro de custo, função e período.

Use este componente quando:

- Você precisa de relatórios padrão sobre custos de mão de obra
- Você deseja comparar os valores reais com os orçamentos
- Você precisa de relatórios consistentes sobre mão de obra

## Fontes comuns de dados

Os dados relativos ao trabalho são normalmente obtidos a partir de sistemas de gestão de recursos humanos e da força de trabalho que mantêm informações sobre funcionários, contratados e controle de ponto. Os sistemas comuns incluem **SAP, Oracle E-Business Suite, PeopleSoft, e Workday**.

Os dados devem incluir identificadores de funcionários ou prestadores de serviços, tipo de emprego, atributos da função, alinhamento organizacional e, quando aplicável, informações sobre tempo ou atividade. Se o cliente seguir as alocações do modelo padrão, os dados de mão de obra precisarão ser mapeados para a taxonomia da Torre e Subtorre do Modelo Unificado TBM ( Apptio ) ( ATUM ) para garantir relatórios consistentes.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/wf-gs.png)

## Conjuntos de dados principais

Pode ser necessário carregar várias tabelas e mapeá-las para as tabelas principais fornecidas com os componentes. As tabelas são:

- **Dados mestre de mão de obra**
- Contém informações sobre custos de mão de obra, orçamento e número de funcionários para a força de trabalho interna e externa. Este conjunto de dados é preenchido através do upload e mapeamento de uma tabela de dados trabalhistas.
- **Outras alocações de mão de obra Dados mestre**
- Instalado com o componente Unidades de Trabalho e usado para alocar mão de obra entre Torres de Recursos de TI, Subtorres, projetos e aplicativos usando fatores de ponderação.
- **Dados mestre de controle de tempo**
- Usado pelo componente Controle de Tempo para alocar custos de mão de obra e esforço a projetos e atividades operacionais
