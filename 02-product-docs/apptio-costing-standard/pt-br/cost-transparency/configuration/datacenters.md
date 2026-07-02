---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Componente CT Apps - Centros de dados"
breadcrumb: []
source_path: "cost-transparency/configuration/datacenters.html"
images:
  - "resources/images/ct_images/6833_1.png"
  - "resources/images/ct_images/6833_2.png"
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Componente CT Apps - Centros de dados

O componente Data Centers é um componente de pré-requisito fundamental que é usado pelo componente Data Centers Optimization. O componente Data Centers não fornece relatórios. Ele fornece métricas que são expostas nos relatórios do componente Otimização do data center.

Aplica-se a: Costing Standard em TBM Studio 12.0 e posterior

Ícone do componente:

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6833_1.png)

## Tabelas de suporte

Quando você instala o componente CT Apps - Data Centers, um novo grupo de Data Centers é criado com duas tabelas: Data Centers (tabela de modelo), Data Centers Master Data.

## Dados principais

Para obter uma descrição dos campos na tabela de dados mestre, consulte as informações na página do componente CT Data Centers no produto. Para exibir a página:

1. Clique na guia **Project (Projeto** ) na faixa de opções.
2. Clique em **Components (Componentes** ).
3. Clique no componente **CT Apps - Data Centers**.

## Fazer upload dos dados

Faça o upload dos dados de seu data center. Os campos obrigatórios e recomendados estão listados abaixo. Todos os campos podem ser mapeados para a tabela Data Centers Master Data.

- Nível de certificação (obrigatório)
- ID do data center (obrigatório)
- Capacidade de energia do data center (necessário)
- Uso de energia do data center (obrigatório)
- Capacidade de RU do data center (necessário)
- Uso de RU do data center (obrigatório)
- Metragem quadrada do data center (obrigatório)
- Localização (obrigatório)
- Gerente (recomendado)
- Nome (obrigatório)
- Objetivo (obrigatório)
- Região (recomendado)
- Provedor de serviços (recomendado)
- Nível (obrigatório)

## Mapear os dados

1. Após fazer o upload dos dados de armazenamento, mapeie a tabela para a tabela Storage Devices Master Data (Dados mestre de dispositivos de armazenamento) e a tabela Storage Master Data (Dados mestre de armazenamento).
2. No diagrama do modelo, se você seguir a alocação do Physical Server clicando na seta para a direita no objeto Physical Server, será redirecionado para a visualização Single Model dos Physical Servers.
3. Atualize o documento clicando em Atualizar documento na faixa de opções. Como agora há custos associados a todos os servidores com base na localização dos data centers, você pode ver o valor fluindo para os hipervisores.
4. Para alocar os custos do hipervisor recém-alocados aos servidores, configure a alocação do hipervisor ao servidor usando as configurações mostradas no exemplo a seguir.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6833_2.png)

## Informações relacionadas

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentários sobre a Central de Ajuda](productfeedback@apptio.com "(Abre em uma nova guia ou janela)")
