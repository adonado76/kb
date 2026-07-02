---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "CT Apps - componente Service Desk"
breadcrumb: []
source_path: "cost-transparency/configuration/servicedesk.html"
images:
  - "resources/images/ct_images/6868_1.png"
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# CT Apps - componente Service Desk

O componente Service Desk é um componente de pré-requisito que é usado pelo componente Service Desk Insights. O componente Service Desk não fornece novos relatórios, mas é usado para criar métricas que são expostas no componente Service Desk Insights.

Aplica-se a: Costing Standard em TBM Studio 12.0 e posterior

Ícone do componente

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6868_1.png)

## Tabelas de suporte

Quando você instala o componente CT Apps - Service Desk, é criado um novo grupo de Service Desk com duas tabelas: Tickets (tabela modelo), Tickets Master Data.

## Dados principais

Para obter uma descrição dos campos na tabela de dados mestre, consulte as informações na página do componente CT Apps - Service Desk no produto. Para exibir a página:

1. Clique na guia **Project (Projeto** ) na faixa de opções.
2. Clique em **Components (Componentes** ).
3. Clique no componente **CT Apps - Service Desk**.

## Fazer upload dos dados

Faça o upload dos dados de sua central de serviços. Os campos obrigatórios e recomendados estão listados abaixo. Todos os campos podem ser mapeados para a tabela de dados mestre de tíquetes.

- ID do aplicativo (recomendado)
- Atribuído a (recomendado)
- Categoria (obrigatório)
- Horário de fechamento (obrigatório)
- Fechado (recomendado)
- Descrição (recomendado)
- Duração (recomendada)
- Impacto (recomendado)
- Localização (recomendado)
- Horário de funcionamento (obrigatório)
- Prioridade (obrigatório)
- Peso da prioridade (obrigatório)
- Relatado por (recomendado)
- Serviço (recomendado)
- Gravidade (recomendado)
- Status (obrigatório)
- ID do ingresso (obrigatório)
- Tipo (obrigatório)
- Ponderação (obrigatório)

## Mapear os dados

Depois de fazer o upload dos dados da central de serviços, mapeie a tabela para a tabela de dados mestre da central de serviços.

Depois que você mapear os dados, deverá haver um valor alocado das Torres de recursos de TI para os tíquetes no modelo de custo.

## Informações relacionadas

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentários sobre a Central de Ajuda](productfeedback@apptio.com "(Abre em uma nova guia ou janela)")
