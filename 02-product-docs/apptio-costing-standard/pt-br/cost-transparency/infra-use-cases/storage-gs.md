---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Armazenamento Introdução"
breadcrumb:
  - "Costing Standard"
  - "Casos de uso de infraestrutura"
  - "Armazenamento"
source_path: "cost-transparency/infra-use-cases/storage-gs.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Armazenamento Introdução

## Introdução – Visão geral dos custos de armazenamento

A solução Visão geral dos custos de armazenamento permite que as organizações estabeleçam transparência de custos básica para a infraestrutura de armazenamento, alocando custos de armazenamento a aplicativos e serviços para compreender o verdadeiro custo total de propriedade do armazenamento. Ele fornece visibilidade dos gastos com armazenamento em ambientes locais e na nuvem e serve como pré-requisito para análises e otimização avançadas de armazenamento disponíveis por meio do Storage Insights.

**Instalação de componentes**

**CT Apps- Armazenamento** - A solução Visão geral dos custos de armazenamento é ativada através da instalação do **componente CT Apps-** Armazenamento. Este componente instala as estruturas de dados principais, métricas e relatórios de armazenamento básicos necessários para a análise do custo total de propriedade (TCO) do armazenamento e a alocação de custos de aplicativos.

**Pré-requisito**

Antes de instalar o componente CT Apps-Storage, os seguintes componentes já devem estar instalados:

- CTF - Fonte de custos
- CTF - Torres de TI

**Fontes comuns de dados**

Os dados relativos aos custos de armazenamento e ao inventário provêm normalmente de uma combinação de sistemas financeiros e de infraestrutura. As fontes comuns incluem sistemas de gerenciamento de ativos para dispositivos de armazenamento e inventário de LUN, plataformas de gerenciamento de armazenamento para informações de capacidade e camadas, bancos de dados de gerenciamento de configuração para relações de aplicativos e o livro razão para custos relacionados a hardware, software, mão de obra e suporte de armazenamento.

**Conjuntos de dados**

Para ativar os relatórios de custos de armazenamento, os dados devem ser carregados e mapeados para os conjuntos de dados principais de armazenamento instalados com o componente CT Apps-Storage. Esses conjuntos de dados incluem dados mestres de dispositivos de armazenamento contendo atributos físicos de armazenamento e dados mestres de armazenamento que capturam unidades lógicas, capacidade, camadas, fontes e informações sobre o ambiente. Depois de preenchidos, esses conjuntos de dados fornecem suporte para relatórios básicos de TCO de armazenamento e insights de armazenamento downstream.

## Introdução – Storage Insights e otimização

Storage Insights A otimização amplia a visibilidade dos custos básicos de armazenamento com análises mais aprofundadas sobre operações, capacidade e utilização. Permite que as organizações analisem a eficiência dos custos de armazenamento, os padrões de utilização e a integridade do ciclo de vida em ambientes locais, na nuvem e híbridos. Esse recurso oferece suporte a análises operacionais, iniciativas de otimização e planejamento de atualização tecnológica, combinando dados financeiros, de capacidade e de utilização em uma única visão analítica.

**Instalação de componentes**

BI- Storage Insights

Este componente fornece uma análise aprimorada da infraestrutura de armazenamento, incluindo visibilidade dos custos unitários, utilização e eficiência.

**Pré-requisito**

É necessário instalar os seguintes componentes antes da ativação:

- CTF - Fonte de custos
- CTF - Torres de TI
- Aplicativos de TC - Armazenamento

**Fontes comuns de dados**

Storage Insights A otimização depende de dados de várias infraestruturas e sistemas empresariais para fornecer uma visão completa dos custos e da utilização do armazenamento, incluindo:

- Dados da infraestrutura de armazenamento local, incluindo dispositivos de armazenamento e unidades lógicas (LUNs)
- Sistemas de inventário de centros de dados e infraestruturas
- VMware vCenter para ambientes de nuvem privada, coletados por meio de conectores Apptio Datalink (Classic), quando aplicável
- Dados de faturamento da nuvem pública de AWS, Azure ou Google Cloud, coletados por meio de conectores ApptioDatalink (Classic), quando aplicável
- Dados de utilização do armazenamento capturando capacidade bruta, alocada e utilizada
- Métricas operacionais, incluindo indicadores de utilização média e máxima

**Conjuntos de dados**

Storage Insights A otimização requer que os seguintes conjuntos de dados sejam preenchidos e mapeados corretamente:

- Dados mestre de armazenamento – Unidades lógicas de armazenamento (LUNs), capacidade, alocação, camada e atributos do ambiente
- Dados mestre dos dispositivos de armazenamento – Inventário físico dos dispositivos de armazenamento, tipo, modelo, fornecedor, localização e detalhes do ciclo de vida
