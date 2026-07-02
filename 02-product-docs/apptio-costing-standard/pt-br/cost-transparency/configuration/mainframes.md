---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Componente CT Apps - Mainframes"
breadcrumb: []
source_path: "cost-transparency/configuration/mainframes.html"
images:
  - "resources/images/ct_images/6863_1.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Componente CT Apps - Mainframes

componente Mainframes faz parte do módulo Costing Standard Applications and Services. Ele é usado para entender o TCO dos mainframes e para alocar os custos do mainframe ao objeto Aplicativos.

Aplica-se a: Costing Standard em TBM Studio 12.0 e posterior

Ícone do componente:

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6863_1.png)

## Requisitos

Você deve instalar os seguintes componentes do aplicativo Costing Standard Foundation antes de instalar o componente Mainframes:

- Fonte de custos
- Torres de TI

## Tabelas de suporte

Quando você instala o componente CT Apps - Mainframes, um novo grupo de Dispositivos do usuário final é criado com seis tabelas:

- LPARs de mainframe (tabela de modelos)
- Mainframe LPARs Dados mestre
- Armazenamento em mainframe (tabela de modelos)
- Dados mestre de armazenamento do mainframe
- Mainframes (tabela de modelos)
- Mainframes Dados mestre

## Dados principais

Para obter uma descrição dos campos nas tabelas de dados mestre, consulte as informações na página do componente CT Apps - Mainframes no produto. Para exibir a página:

1. Clique na guia **Project (Projeto** ) na faixa de opções.
2. Clique em **Components (Componentes** ).
3. Clique no componente **CT Apps - Mainframes**.

## Fazer upload dos dados

Faça o upload dos dados de seus mainframes. Os campos obrigatórios e recomendados estão listados abaixo por tabela mestre.

Mainframe LPARs Dados mestre

- ID do aplicativo (obrigatório)
- Nome do aplicativo (obrigatório)
- LPAR (obrigatório) (LPAR: partição lógica)
- Mainframe (obrigatório)
- Identificador de objeto (obrigatório)

Dados mestre de armazenamento do mainframe

- ID do aplicativo (obrigatório)
- Nome do aplicativo (obrigatório)
- Identificador de objeto (obrigatório)
- ID do armazenamento (obrigatório)

Mainframes Dados mestre

- Unidades reais (obrigatório)
- Capacidade da CPU (recomendado)
- MIPS garantido (recomendado)
- Localização (recomendado)

## Mapear os dados

Depois de fazer o upload dos dados do mainframe, mapeie a tabela para as tabelas de dados mestre.

Depois de mapear os dados, deve haver um valor alocado conforme descrito abaixo.

- LPARs de mainframe - dos mainframes aos LPARS de mainframe e dos LPARS de mainframe aos aplicativos.
- Armazenamento do mainframe - das torres de recursos de TI ao armazenamento do mainframe e do armazenamento do mainframe aos aplicativos.
- Mainframes - De torres de recursos de TI e data centers a mainframes, e de mainframes a LPARS de mainframes.
