---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Serviços Introdução"
breadcrumb:
  - "Costing Standard"
  - "Casos de uso da solução"
  - "Serviços"
source_path: "cost-transparency/solution-uc/services-gs.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Serviços Introdução

Use o componente Serviços para consolidar e analisar os custos de tecnologia por serviço. O componente CT Apps - Serviços fornece a estrutura de dados e os objetos de modelo necessários para relatórios e análises de custos de serviços.

Instale e configure o componente Serviços e, em seguida, carregue os dados do serviço, incluindo definições de serviço, propriedade do serviço, métricas de consumo e categorização do serviço. Após a instalação do componente, mapeie seus dados para as tabelas apropriadas.

## Instalação de componentes

O componente CT Apps – Serviços oferece visibilidade dos gastos de TI com serviços, permitindo que as organizações compreendam os custos totais dos serviços, acompanhem as mudanças mensais nos gastos e avaliem o desempenho em relação ao planejado. Ele consolida os custos subjacentes de tecnologia, aplicativos, mão de obra e fornecedores em uma visão de nível de serviço, oferecendo suporte à transparência consistente dos custos de serviço e à análise do portfólio.

## Componente instalado

**Aplicativos de TC – Serviços**

O componente CT Apps – Serviços instala as estruturas de dados, conjuntos de dados, métricas e relatórios fundamentais necessários para analisar os custos, as tendências e o desempenho orçamentário dos serviços de negócios em toda a empresa.

**Aplicativos de tomografia computadorizada – Relatórios de serviços NX (componente adicional)**

Este componente fornece relatórios NX predefinidos com base em dados de serviços para análise por serviço, categoria e período.

Use este componente quando:

- Você precisa de relatórios de serviços padrão
- Você deseja analisar as tendências de custos e uso
- Você precisa de relatórios consistentes sobre os serviços

## Pré-requisitos

Você deve instalar os seguintes componentes antes de instalar o componente Serviços:

• CTF - Fonte de custos

• Torres CTF-IT

• Aplicativos CT - Aplicativos

## Fontes comuns de dados

Os dados dos serviços empresariais provêm normalmente de catálogos de serviços, sistemas CMDB, ferramentas de gestão de portfólio de aplicações e plataformas de gestão de serviços. Os dados que você usar determinarão o nível de detalhes disponíveis para análise de custos de serviços e acompanhamento de consumo.

As fontes de dados comuns incluem:

- **Plataformas de gerenciamento de serviços:** definições de serviços, dados do catálogo de serviços e métricas de consumo ( ServiceNow, BMC Remedy, Cherwell).
- **Banco de dados de gerenciamento de configuração (CMDB):** relações entre serviços e aplicativos e mapeamento de dependências de serviços.
- **Gerenciamento de portfólio de aplicativos:** propriedade do serviço, estágio do ciclo de vida do serviço e mapeamentos de aplicativos para serviços ( ServiceNow APM, LeanIX ).
- **Sistemas de gestão de negócios de TI:** dados de custos de serviços, volumes de consumo de serviços e métricas de nível de serviço.
- **Catálogos de serviços:** Definições de serviços publicados, descrições de serviços e categorização de serviços.

## Conjuntos de dados

Você precisará fazer o upload dos dados do serviço e mapeá-los para a tabela Todos os serviços comerciais. Embora não exista uma tabela de dados mestre separada para o componente CT Apps - Serviços, a tabela Todos os serviços comerciais tem uma função semelhante e contém todas as definições e atributos dos serviços.

**Todos os serviços empresariais**

Esta tabela define todos os serviços comerciais em seu portfólio de serviços. Contém identificação do serviço, categorização, propriedade, métricas de consumo e configuração de alocação. Todos os dados de serviço devem ser mapeados para esta tabela.
