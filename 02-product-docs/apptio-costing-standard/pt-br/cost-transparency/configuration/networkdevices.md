---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Componente CT Apps - Dispositivos de rede"
breadcrumb: []
source_path: "cost-transparency/configuration/networkdevices.html"
images:
  - "resources/images/ct_images/6846_1.png"
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Componente CT Apps - Dispositivos de rede

O componente Network Devices (Dispositivos de rede) faz parte do módulo Costing Standard Applications and Services (Aplicativos e serviços). É usado para alocar os custos de infraestrutura de dispositivos de rede, incluindo LAN, WAN, voz e outros equipamentos de rede usados no data center e nos escritórios para os consumidores dos dispositivos de rede.

Aplica-se a: Costing Standard em TBM Studio 12.0 e posterior

Ícone do componente:

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6846_1.png)

## Introdução

O componente Dispositivos de rede instala um novo objeto, conjuntos de dados e estratégias de alocação recomendadas para distribuir os custos do Dispositivo de rede para os seguintes serviços típicos:

- Mainframe - para equipamentos de rede que suportam os mainframes nos data centers corporativos
- Servidores físicos - para equipamentos de rede que suportam servidores nos data centers corporativos
- Dispositivos de armazenamento - para equipamentos de rede que suportam o armazenamento nos data centers corporativos
- Dispositivos do usuário final - para equipamentos de rede que suportam conexões físicas e sem fio com PCs, laptops e dispositivos móveis nos escritórios

## Tabelas de suporte

Quando você instala o componente CT Apps - Dispositivos de rede, um novo grupo de Dispositivos de rede é criado com duas tabelas: Dispositivos de rede (tabela de modelo), Dados mestre de dispositivos de rede.

## Dados principais

Para obter uma descrição dos campos na tabela de dados mestre, consulte as informações na página do componente Aplicativos CT - Dispositivos de rede no produto. Para exibir a página:

1. Clique na guia **Project (Projeto** ) na faixa de opções.
2. Clique em **Components (Componentes** ).
3. Clique no componente **CT Apps - Dispositivos de rede**.

## Fazer upload dos dados

Faça o upload dos dados de seus dispositivos de rede. Os campos obrigatórios e recomendados estão listados abaixo. Todos os campos podem ser mapeados para a tabela de dados mestre de dispositivos de rede.

- Contagem de dispositivos (obrigatório)
- Tipo de dispositivo (obrigatório)
- Localização (recomendado)
- Tipo de local (obrigatório)
- Dispositivos de rede/Dispositivos de armazenamento (obrigatório)
- Identificador de objeto (obrigatório)
- ID do serviço (recomendado)
- Nome do serviço (recomendado)

## Mapear os dados

Depois de fazer o upload dos dados dos dispositivos de rede, mapeie a tabela para a tabela de dados mestre dos dispositivos de rede.

Depois de mapear os dados, deve haver um valor alocado das torres de recursos de TI e dos data centers para os dispositivos de rede e dos dispositivos de rede para o servidor físico, os dispositivos de armazenamento, os dispositivos do usuário final e os mainframes no modelo de custo.

## Informações relacionadas

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentários sobre a Central de Ajuda](productfeedback@apptio.com "(Abre em uma nova guia ou janela)")
