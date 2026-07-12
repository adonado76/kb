---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Computação Introdução"
breadcrumb:
  - "Costing Standard"
  - "Casos de uso de infraestrutura"
  - "Informática"
source_path: "cost-transparency/infra-use-cases/compute-gs.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Computação Introdução

## Introdução - Visão geral dos custos de computação

Use os componentes de gerenciamento de computação para carregar e gerenciar o inventário do servidor, a utilização, o custo e os dados do ciclo de vida necessários para a transparência dos custos de computação e a análise do TCO no nível do aplicativo. Essa capacidade estabelece o modelo de dados fundamental para analisar os custos de computação em ambientes físicos, virtuais, de nuvem privada e de nuvem pública, além de oferecer suporte a relatórios de custos de infraestrutura e aplicativos downstream.

**Instalação de componentes**

CT Apps– Servidores – O componente CT Apps– Servidores fornece as estruturas de dados, métricas e alocações essenciais necessárias para modelar os custos da infraestrutura de servidores e associá-los às aplicações. Esse componente é um pré-requisito para relatórios avançados do Server Insights e permite a alocação de custos de infraestrutura de computação para aplicativos, a fim de dar suporte à análise de TCO.

**Pré-requisitos:**

• Fonte de custo

• Torres de TI

**Fontes comuns de dados**

Os dados computacionais são normalmente obtidos a partir de uma combinação de infraestrutura e sistemas empresariais. As fontes comuns incluem ferramentas de monitoramento de servidor para métricas de CPU, memória e utilização; plataformas de virtualização, como VMware ou Hyper-V, para relações entre máquinas virtuais e hosts; sistemas de gerenciamento de ativos para inventário, configuração e detalhes do ciclo de vida do servidor; CMDBs para relações entre servidor e aplicativo e classificação do ambiente; ferramentas de gerenciamento de serviços para dados de incidentes e suporte; e sistemas de contabilidade geral para custos relacionados a hardware, software, mão de obra e suporte de computação.

**Conjuntos de dados**

A solução de gerenciamento de computação requer que vários conjuntos de dados principais sejam preenchidos e mapeados corretamente. Isso inclui dados mestres do servidor para todos os servidores físicos e virtuais, dados mestres do servidor físico para hosts físicos e hipervisores e dados mestres do hipervisor para servidores que hospedam cargas de trabalho virtuais. Os dados do servidor são normalmente obtidos a partir de uma única extração de inventário e transformados em conjuntos de dados separados para garantir a modelagem precisa de servidores físicos, servidores virtuais e hipervisores, permitindo a alocação correta de custos e a análise de utilização.

## Introdução - Insights e otimização de computação

O Compute Insights & Optimization oferece visibilidade detalhada dos custos, da capacidade, da utilização e da eficiência dos servidores em ambientes de infraestrutura híbrida. Esse recurso é construído sobre o **componente** básico CT Apps-Servers e o amplia por meio **do BI-Server Insights**, parte do módulo Infrastructure Insights. Juntos, esses componentes permitem análises operacionais e financeiras avançadas de ambientes de servidores físicos e virtuais, auxiliando na otimização, padronização e decisões relacionadas ao ciclo de vida.

**Instalação de componentes**

**BI - Server Insights** - O Compute Insights & Optimization é ativado através do **componente** BI - Server Insights. Este componente oferece uma análise aprimorada da infraestrutura do servidor, incluindo tendências de custo unitário, eficiência de utilização e desempenho operacional em ambientes locais e na nuvem.

**Pré-requisito**

Os seguintes componentes devem ser instalados antes de instalar o Server Insights:

• CTF - Fonte de custos

• Torres CTF-IT

• Aplicativos CT – Servidores

**Fontes comuns de dados**

Os dados de computação e infraestrutura são normalmente obtidos a partir do inventário de servidores e sistemas de monitoramento, plataformas de virtualização, como VMware vCenter, sistemas de gerenciamento de data centers e ativos, e dados de faturamento de nuvem pública de provedores como AWS, Azure e Google Cloud, quando aplicável. As métricas de utilização incluem o uso médio e máximo da CPU e da memória, juntamente com os dados de utilização do armazenamento, quando disponíveis.

**Conjuntos de dados principais**

O recurso Server Insights depende de conjuntos de dados preenchidos por meio do componente CT Apps – Servers, incluindo servidor físico, servidor lógico (VM) e dados mestres do hipervisor, combinados com dados de custo do Cost Source e mapeamentos de torre do IT Towers. Esses conjuntos de dados permitem a modelagem detalhada dos custos, da utilização e da alocação do servidor para aplicativos e serviços para análise de otimização.
