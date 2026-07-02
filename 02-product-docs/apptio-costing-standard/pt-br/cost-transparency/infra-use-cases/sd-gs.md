---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Guia de introdução ao Service Desk"
breadcrumb:
  - "Costing Standard"
  - "Casos de uso de infraestrutura"
  - "Central de atendimento"
source_path: "cost-transparency/infra-use-cases/sd-gs.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Guia de introdução ao Service Desk

## Introdução - Visão geral dos custos do Service Desk

A funcionalidade Visão geral dos custos do Service Desk permite que as organizações compreendam e distribuam os custos do help desk e do suporte entre aplicativos, serviços e unidades de negócios com base no volume de tickets, prioridade, impacto e esforço. Ao associar os dados de atividade do service desk aos dados de custos financeiros, este componente proporciona transparência quanto ao custo real da prestação de suporte e ajuda as organizações a gerenciar a eficiência, a demanda e os fatores de custo do service desk de forma mais eficaz.

Este componente é um pré-requisito para relatórios operacionais e analíticos mais detalhados disponíveis através do Service Desk Insights.

**Instalação de componentes**

Aplicativos CT – Central de Atendimento

O componente CT Apps – Service Desk fornece a estrutura de dados fundamental necessária para a alocação de custos do service desk. Ele captura atividades de tratamento de incidentes e solicitações, incluindo volumes de tickets, prioridades, níveis de impacto e tempo gasto na resolução de problemas.

**Pré-requisito**

Você deve instalar os seguintes componentes antes de instalar o componente Service Desk:

- CTF – Fonte de Custos
- CTF – Trabalho
- CTF – Torres de TI

**Fontes comuns de dados**

Os dados relativos aos custos e atividades do serviço de assistência são normalmente obtidos a partir de uma combinação de sistemas financeiros e plataformas de gestão de serviços de TI. Os dados de custo e orçamento geralmente vêm do livro razão, enquanto o volume de tickets, a gravidade, a prioridade e o esforço de resolução são obtidos do ITSM e das ferramentas de suporte. O nível de detalhes disponível depende dos dados capturados nesses sistemas e mapeados para os dados mestres do service desk.

**Conjuntos de dados**

Para ativar os relatórios de visão geral dos custos do Service Desk, carregue os dados de entrada do Service Desk e mapeie-os para as tabelas de dados mestres fornecidas com o componente.

Os dados mestre dos tickets contêm a lista completa dos tickets do service desk, incluindo impacto, prioridade, aplicativos ou serviços associados, detalhes do responsável e tempo gasto na resolução dos problemas.

Ao instalar o componente CT Apps – Service Desk, é criado um grupo de tabelas Service Desk com uma tabela modelo Tickets e uma tabela Tickets Master Data. Após o mapeamento dos dados, os custos do service desk são alocados das Torres de Recursos de TI para os tickets dentro do modelo de custos, permitindo uma atribuição e um relatório precisos dos custos de suporte.

## Introdução – Informações e otimização do Service Desk

O Service Desk Insights & Optimization baseia-se no modelo de custos fundamental do Service Desk para fornecer uma análise operacional e financeira mais aprofundada do desempenho do service desk. Esse recurso oferece visibilidade sobre os volumes, custos e eficiência dos tickets do service desk em diferentes locais, prioridades e categorias, permitindo que as organizações passem do rastreamento básico de custos para a otimização de serviços baseada em dados

Essa capacidade é desenvolvida com base no componente **CT Apps – Service Desk.**

**Instalação de componentes**

**BI – Informações sobre o Service Desk**

O Service Desk Insights é fornecido através do componente **BI – Service Desk Insights**.

**Pré-requisito**

Antes de instalar o componente Service Desk Insights, certifique-se de que os seguintes componentes pré-requisitos estejam instalados e configurados na ordem correta:

- CTF - Fonte de custos
- CTF - Torres de TI
- Aplicativos CT - Central de Atendimento
