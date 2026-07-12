---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Componente CT Apps - Dispositivos do usuário final"
breadcrumb: []
source_path: "cost-transparency/configuration/enduserdevices.html"
images:
  - "resources/images/ct_images/6859_1.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Componente CT Apps - Dispositivos do usuário final

O componente CT - Apps End User Devices faz parte do módulo Costing Standard Applications and Services. Ele é usado para entender o TCO dos dispositivos do usuário final, incluindo PCs, laptops, smartphones, tablets e outros equipamentos de computação do cliente, e para alocar esses custos usados pela força de trabalho da empresa.

Ícone do componente:

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6859_1.png)

O componente Dispositivos do usuário final instala novas tabelas de dados e estratégias de alocação recomendadas para determinar o TCO do dispositivo do usuário final e para distribuir os custos do dispositivo do usuário final para os seguintes serviços típicos:

- Serviços para usuários finais - para dispositivos de usuários finais usados como ofertas de serviços do Client Compute pela força de trabalho
- Serviços comerciais específicos - para necessidades específicas da empresa, como recursos de computação distribuídos (por exemplo, quiosque) para uma oferta de varejo (por exemplo, caixa eletrônico)

## Tabelas de suporte

Quando você instala o componente CT Apps - Dispositivos do usuário final, um novo grupo de Dispositivos do usuário final é criado com duas tabelas: Dispositivos de usuário final (tabela de modelo), Dados mestre de dispositivos de usuário final.

## Dados principais

Para obter uma descrição dos campos na tabela de dados mestre, consulte as informações na página do componente CT Apps - Dispositivos do usuário final no produto. Para exibir a página:

1. Clique na guia **Project (Projeto** ) na faixa de opções.
2. Clique em **Components (Componentes** ).
3. Clique no componente **CT Apps - Dispositivos do usuário final**.

## Fazer upload dos dados

Faça o upload dos dados dos dispositivos do usuário final. Os campos obrigatórios e recomendados estão listados abaixo. Todos os campos podem ser mapeados para a tabela de dados mestre dos dispositivos do usuário final.

- Número de identificação do ativo (recomendado)
- Contagem de dispositivos (obrigatório)
- Tipo de dispositivo (obrigatório)

## Mapear os dados

Depois de fazer o upload dos dados de comunicação, mapeie a tabela para a tabela de dados mestre dos dispositivos do usuário final.

Depois de mapear os dados, deve haver um valor alocado de Torres de recursos de TI e Comunicações para Dispositivos do usuário final e de Dispositivos do usuário final para Serviços empresariais no modelo de custo.
