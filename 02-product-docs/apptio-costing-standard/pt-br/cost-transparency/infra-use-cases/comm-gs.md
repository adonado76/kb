---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Comunicações Introdução"
breadcrumb:
  - "Costing Standard"
  - "Casos de uso de infraestrutura"
  - "Comunicações"
source_path: "cost-transparency/infra-use-cases/comm-gs.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Comunicações Introdução

O componente Comunicações permite que as organizações aloquem os custos de infraestrutura de comunicação, como circuitos, serviços de voz e tarifas baseadas no uso, aos consumidores apropriados. Ele oferece suporte à alocação transparente e justificável dos gastos com comunicação para aplicativos, serviços e unidades de negócios, ajudando a estabelecer o custo total de propriedade (TCO) preciso de aplicativos e serviços.

## Instalação de componentes

**Aplicativos CT – Comunicações**

O componente Comunicações instala um novo objeto Comunicações, suportando conjuntos de dados e lógica de alocação usados para distribuir os custos de comunicação aos serviços consumidores. Ele oferece suporte à alocação de custos de comunicação para servidores que dão suporte a centros de dados, dispositivos de usuários finais que dão suporte à conectividade do escritório e da força de trabalho e serviços comerciais específicos, como call centers ou quiosques de varejo.

Você deve instalar os seguintes componentes antes de instalar o componente Comunicações:

CTF – Fonte de Custos

CTF – Torres de TI

## Fontes comuns de dados

Os dados relativos aos custos e à utilização das comunicações são normalmente obtidos a partir do livro-razão e dos sistemas de despesas de telecomunicações ou de rede. O nível de detalhes disponível depende dos dados de origem fornecidos e determina como os custos são mapeados para os dados mestre de comunicações para alocação e relatórios.

## Conjuntos de dados

Quando o componente CT Apps – Comunicações é instalado, um grupo Comunicações é criado com as seguintes tabelas:

Comunicações (tabela modelo)

Dados mestres de comunicações

Após carregar os dados de comunicação, mapeie-os para a tabela Dados Mestres de Comunicações. Uma vez mapeados, os custos fluem das Torres de Recursos de TI para as Comunicações e das Comunicações para os Servidores e Serviços Comerciais dentro do modelo de custos.
