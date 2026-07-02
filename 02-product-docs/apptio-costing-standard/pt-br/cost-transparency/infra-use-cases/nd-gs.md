---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Dispositivos de rede Introdução"
breadcrumb:
  - "Costing Standard"
  - "Casos de uso de infraestrutura"
  - "Dispositivos de rede"
source_path: "cost-transparency/infra-use-cases/nd-gs.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Dispositivos de rede Introdução

Use os componentes da Visão Geral dos Custos dos Dispositivos de Rede para carregar, modelar e alocar os custos da infraestrutura de rede em toda a empresa. Esse recurso permite que as organizações aloquem os custos de LAN, WAN, voz e outros dispositivos de rede dos data centers e escritórios aos consumidores desses serviços, proporcionando transparência sobre como os custos de rede são incorridos e consumidos em toda a TI e nos negócios.

**Instalação de componentes**

Aplicativos CT – Dispositivos de rede

O componente Dispositivos de rede instala um novo objeto, oferecendo suporte a conjuntos de dados e estratégias de alocação recomendadas para distribuir os custos de infraestrutura de rede. Esses custos são alocados aos seguintes consumidores típicos:

Mainframe

Equipamentos de rede que suportam mainframes em centros de dados empresariais.

Servidores físicos

Equipamentos de rede que suportam a infraestrutura de servidores em centros de dados empresariais.

Dispositivo de Armazenamento

Equipamentos de rede que suportam plataformas de armazenamento em centros de dados empresariais.

Dispositivos do usuário final

Equipamentos de rede que suportam conectividade com e sem fio para PCs, laptops e dispositivos móveis em escritórios.

**Pré-requisitos**

Você deve instalar os seguintes componentes antes de instalar o componente Dispositivos de Rede:

CTF - Fonte de custos

CTF - Torres de TI

**Fontes comuns de dados**

Os dados dos dispositivos de rede são normalmente obtidos a partir de sistemas financeiros, como o livro razão geral para informações sobre custos e orçamentos, combinados com ferramentas de gerenciamento e monitoramento de rede (por exemplo, SolarWinds, Cisco DNA Center, ferramentas baseadas em SNMP), plataformas CMDB e sistemas de gerenciamento de ativos. Juntas, essas fontes fornecem visibilidade do inventário, dos custos, da utilização e das relações da rede necessárias para uma alocação e relatórios precisos dos custos da rede.

**Conjuntos de dados**

O principal conjunto de dados necessário é o Dados Mestres dos Dispositivos de Rede, que captura atributos dos dispositivos, como localização, tipo, finalidade, origem e infraestrutura suportada. Este conjunto de dados é preenchido com dados extraídos dos sistemas de gerenciamento de rede, monitoramento, CMDB e financeiros, e é usado para alocar custos de rede a servidores físicos, dispositivos de armazenamento, dispositivos de usuários finais e mainframes dentro do modelo de custos.
