---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Aplicativos Introdução"
breadcrumb:
  - "Costing Standard"
  - "Casos de uso da solução"
  - "Aplicativos"
source_path: "cost-transparency/solution-uc/app-gs.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Aplicativos Introdução

O componente Aplicações faz parte do módulo Aplicações e Serviços de Transparência de Custos. Permite que as organizações aloquem custos relacionados à infraestrutura e aos aplicativos para calcular o custo total de propriedade (TCO) preciso dos aplicativos. Este componente instala as estruturas de dados, métricas e relatórios necessários para analisar os custos das aplicações em termos de mão de obra, infraestrutura, projetos e serviços de suporte.

## Instalação de componentes

**Aplicativos CT – Aplicativos**

O componente Aplicações instala novos conjuntos de dados, métricas e relatórios, o que ajuda a alocar custos relacionados à infraestrutura e às aplicações para determinar o TCO das aplicações da empresa.

**Aplicativos CT - Relatórios NX (Componente adicional)**

Este componente fornece relatórios NX predefinidos com base nos dados do aplicativo para análise entre aplicativos, portfólios e períodos de tempo.

Use este componente quando:

- Você precisa de relatórios padrão do aplicativo
- Você deseja analisar as tendências de custos e uso
- Você precisa de relatórios consistentes sobre as aplicações

## Pré-requisitos

Você deve instalar os seguintes componentes antes de instalar o componente Aplicativos:

- CTF - Fonte de custos
- CTF - Torres de TI

**Fontes comuns de dados**

Os dados relativos aos custos e atributos das aplicações são normalmente obtidos a partir de sistemas de contabilidade geral, inventários de aplicações ou plataformas CMDB, ferramentas de gestão de projetos e portfólios e sistemas de gestão de serviços de TI. Os custos relacionados à infraestrutura são provenientes de fontes de dados de computação, armazenamento, central de atendimento e projetos já configuradas no modelo de custos.

## Conjuntos de dados

Quando você instala o componente CT Apps – Aplicativos, um novo grupo Aplicativos é criado com as seguintes tabelas:

- Aplicações (tabela modelo)
- Aplicativos Dados Mestres

Após carregar os dados da aplicação, mapeie o conjunto de dados para a tabela Dados Mestre das Aplicações. Após mapear os dados, deve haver um valor alocado das Torres de Recursos de TI, Servidores, Tickets e Projetos para Aplicações no modelo de Custos.
