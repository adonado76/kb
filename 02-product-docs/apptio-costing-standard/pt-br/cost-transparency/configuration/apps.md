---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "CT Apps - Componente de aplicativos"
breadcrumb: []
source_path: "cost-transparency/configuration/apps.html"
images:
  - "resources/images/ct_images/6859_1.png"
  - "resources/images/ct_images/6859_2.png"
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# CT Apps - Componente de aplicativos

O componente Applications é um componente de pré-requisito fundamental usado pelo componente Applications Insights. O componente Applications fornece novos relatórios e também cria métricas que são expostas no componente Application Insights.

Aplica-se a: Costing Standard em TBM Studio 12.0 e posterior

Ícone do componente:

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6859_1.png)

## Tabelas de suporte

Quando você instala o componente CT Apps - Aplicativos, um novo grupo Aplicativos é criado com três tabelas: Aplicativos (tabela modelo), Dados mestre de aplicativos, Lista de referência de aplicativos.

A tabela Lista de referência de aplicativos inclui uma lista de famílias de aplicativos (por exemplo, g.: Business Apps, Collaboration, Database, etc.) e as várias funções de aplicativos associadas a cada família de aplicativos. Você não deve modificar essa tabela.

## Dados principais

Para obter uma descrição dos campos na tabela de dados mestre, consulte as informações na página do componente Aplicativos CT - Aplicativos no produto. Para exibir a página:

1. Clique na guia **Project (Projeto** ) na faixa de opções.
2. Clique em **Components (Componentes** ).
3. Clique no componente **CT Apps - Aplicativos**.

## Fazer upload dos dados

Faça o upload dos dados de seu aplicativo. Os campos obrigatórios e recomendados estão listados abaixo. Todos os campos podem ser mapeados para a tabela de dados mestre de aplicativos.

- Unidades reais (obrigatório)
- Proprietário de empresa de aplicativos (recomendado)
- Contagem de aplicativos (recomendado)
- Família do aplicativo (obrigatório)
- Função do aplicativo (recomendado)
- ID do aplicativo (obrigatório)
- Data de entrada em serviço do aplicativo (recomendada)
- Objetivo de investimento do aplicativo (obrigatório)
- Proprietário de TI de aplicativos (recomendado)
- Ciclo de vida do aplicativo (recomendado)
- Nome do aplicativo (obrigatório)
- Data de aposentadoria do aplicativo (recomendado)
- Tipo de aplicativo (recomendado)
- Categoria de usuário do aplicativo (recomendado)
- Crítica para os negócios (recomendado)

## Mapear os dados

Depois de fazer o upload dos dados do aplicativo, mapeie a tabela para a tabela de dados mestre de aplicativos.

Depois que você mapear os dados, deverá haver um valor alocado de Torres de recursos de TI, Servidores, Tickets e Projetos para Aplicativos no modelo de custos.

## Atribuir armazenamento a aplicativos

Lembre-se de que os LUNs de armazenamento foram mapeados para aplicativos quando você configurou o armazenamento. Para alocar o armazenamento para aplicativos, siga as etapas abaixo.

1. Clique em Storage no grupo Storage.
2. Confira o documento Storage.
3. Clique em **Add Allocation (Adicionar alocação** ) e defina a alocação usando as seguintes configurações:

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6859_2.png)

## Informações relacionadas

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentários sobre a Central de Ajuda](productfeedback@apptio.com "(Abre em uma nova guia ou janela)")
