---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Aplicativos CT - Componente de armazenamento"
breadcrumb: []
source_path: "cost-transparency/configuration/storage.html"
images:
  - "resources/images/ct_images/6849_1.png"
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Aplicativos CT - Componente de armazenamento

O componente Storage é um componente de pré-requisito fundamental que é usado pelo componente Storage Insights. O componente Storage não fornece novos relatórios, mas é usado para criar métricas que são expostas no componente Storage Insights.

Ícone do componente:

![Aplicativos do CT - Armazenamento](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6849_1.png)

## Tabelas de suporte

Quando você instala o componente CT Apps - Storage, dois novos grupos são criados com duas tabelas cada:

- Armazenamento
- Armazenamento (tabela de modelos)
- Dados mestre de armazenamento
- Dispositivo de Armazenamento
- Dispositivos de armazenamento (tabela de modelos)
- Dispositivos de armazenamento Dados mestre

A tabela Storage Devices Master Data (Dados mestre de dispositivos de armazenamento) inclui informações sobre os dispositivos de armazenamento físico.

A tabela Storage Master Data inclui os LUNs (números de unidades lógicas) associados aos dispositivos de armazenamento físico.

## Dados principais

Para obter uma descrição dos campos na tabela de dados mestre, consulte as informações na página do componente CT Storage no produto. Para exibir a página:

1. Clique na guia **Project (Projeto** ) na faixa de opções.
2. Clique em **Components (Componentes** ).
3. Clique no componente **CT Apps - Armazenamento**.

## Fazer upload dos dados

Faça o upload dos dados de seu data center. Os campos obrigatórios e recomendados estão listados abaixo. Todos os campos podem ser mapeados para a tabela Storage Master Data (Dados mestre de armazenamento) ou para a tabela Storage Devices Master Data (Dados mestre de dispositivos de armazenamento).

- Unidades reais (obrigatório)
- Unidades orçadas (recomendado)
- Data da compra (recomendada)
- Ambiente (obrigatório)
- Localização (obrigatório)
- Plataforma (obrigatório)
- Objetivo (obrigatório)
- ID do servidor (obrigatório)
- Sourcing (obrigatório)
- ID do dispositivo de armazenamento (obrigatório)
- Nível (obrigatório)
- Espaço total (obrigatório)
- Tipo (obrigatório)

## Mapear os dados

Depois de fazer o upload dos dados de armazenamento, mapeie a tabela para a tabela Storage Devices Master Data (Dados mestre de dispositivos de armazenamento).

## Informações relacionadas

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentários sobre a Central de Ajuda](productfeedback@apptio.com "(Abre em uma nova guia ou janela)")
