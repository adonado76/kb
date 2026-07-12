---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Introdução ao Mainframe"
breadcrumb:
  - "Costing Standard"
  - "Casos de uso de infraestrutura"
  - "Mainframe"
source_path: "cost-transparency/infra-use-cases/mf-gs.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Introdução ao Mainframe

Use os componentes do TCO do mainframe para carregar e gerenciar os dados de custo e consumo do mainframe necessários para relatórios abrangentes. A solução requer integração com o IBM IntelliMagic Vision para obter dados precisos de uso e conexão com seu Razão para obter informações completas sobre custos.

Instale e configure os componentes do Mainframe TCO antes de carregar seus conjuntos de dados de custo, consumo e alocação do mainframe. Após a instalação, carregue seus dados e mapeie-os para as tabelas de dados mestres apropriadas para permitir a geração de relatórios.

## Instalação de componentes

**Aplicativos CT - Mainframes**

O componente Mainframes faz parte do módulo Aplicações e Serviços de Transparência de Custos. É usado para compreender o TCO dos mainframes e alocar os custos do mainframe ao objeto Aplicativos.

**BI - Informações sobre mainframe**

O componente BI-Mainframe Insights oferece maior visibilidade sobre o custo total de propriedade (TCO) e a utilização do mainframe, incluindo uma análise detalhada dos custos unitários e do uso medido em milhões de unidades de serviço (MSUs), com desagregação entre MSUs de " GCP " e MSUs de " zIIP ".

**Observação:** este componente está disponível nos modelos **v120 e posteriores**.

**BI - Relatórios do Mainframe Insights NX (Componente adicional)**

Este componente fornece relatórios NX predefinidos com base em dados de mainframe para análise por aplicativos, uso e períodos de tempo.

Use este componente quando:

- Você precisa de relatórios padrão de mainframe
- Você deseja analisar as tendências de uso e custo
- Você precisa de relatórios consistentes do mainframe

## Componentes pré-requisitos

- CTF - Fonte de custos
- CTF - Torres de TI
- Aplicativos CT - Aplicações

## Fontes comuns de dados

Os dados de TCO do mainframe geralmente vêm de várias fontes em todo o ambiente do mainframe e sistemas empresariais. As fontes de dados comuns incluem:

- **IBM IntelliMagic Visão:** Principal fonte de dados sobre a utilização do mainframe, incluindo MSU de GCP, MSU de zIIP, armazenamento alocado, armazenamento utilizado, consumo de carga de trabalho e métricas de uso de aplicativos.
- Outras soluções de desempenho ou telemetria para mainframe, como zPCA,, etc
- **Contabilidade geral:** fonte dos custos reais com hardware, software, instalações e despesas de depreciação do mainframe, categorizados por centro de custos e conta.
- **Sistemas de RH:** Custos de mão de obra e número de funcionários para operações de mainframe, desenvolvimento e equipe de suporte.
- **Sistemas de gerenciamento de fornecedores:** Custos com licenças de software para mainframe, contratos de manutenção e serviços externos.
- **Sistemas de gerenciamento de ativos:** inventário de hardware de mainframe, configurações e informações sobre o ciclo de vida dos ativos.
- **Portfólio de aplicativos:** nomes dos aplicativos, proprietários e associações de unidades de negócios para alocação de custos.

## Conjuntos de dados principais

A solução Mainframe TCO requer que várias tabelas de dados mestres sejam preenchidas com dados de custo e consumo do mainframe. Carregue os dados nessas tabelas e certifique-se de que todos os campos obrigatórios estejam mapeados corretamente.

**Dados mestres do mainframe:** GCP (consumo de MSU), zIIP (consumo de MSU), armazenamento alocado, armazenamento utilizado, categoria de carga de trabalho, tipo de carga de trabalho, linha de produtos, nome do produto e nome do aplicativo, obtidos em IBM IntelliMagic Vision.

Para obter mais informações sobre a configuração e instalação do TCO do mainframe, clique [aqui](../reports/mainframe-config-guide.html)
