---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "CT Apps - Componente de serviços"
breadcrumb: []
source_path: "cost-transparency/configuration/services.html"
images:
  - "resources/images/ct_images/6848_1.png"
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# CT Apps - Componente de serviços

O componente CT Apps - Services fornece informações sobre os gastos de TI com serviços empresariais, incluindo alterações mês a mês nos gastos e desempenho em relação ao planejado.

Aplica-se a: Costing Standard em TBM Studio 12.0 e posterior

Ícone do componente

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6848_1.png)

## Tabelas de suporte

Quando você instala o componente CT Apps - Services, um novo grupo de Business Service é criado com três tabelas: Serviços de negócios (tabela de modelo), Todos os serviços de negócios, Lista de referência de todos os serviços de negócios.

A tabela All Business Services Reference List inclui uma lista de tipos de serviço (por exemplo, g.: Business Application Services, End User Services, etc.) e as várias categorias de serviço associadas a cada tipo de serviço. Você não deve modificar essa tabela.

## Dados necessários e recomendados

Não há uma tabela mestre para o componente CT Apps - Services. No entanto, a tabela All Business Services tem uma função semelhante.

Os campos obrigatórios e recomendados estão listados abaixo. Todos os campos podem ser mapeados para a tabela All Business Services.

- Descrição (recomendado)
- Estágio do ciclo de vida (recomendado)
- Objetivo (recomendado)
- Quantidade (recomendada)
- .PK (obrigatório)
- Tipo de alocação (recomendado)
- Verificação de SAD (obrigatório)
- Categoria de serviço (recomendado)
- Contagem de serviços (obrigatório)
- ID do serviço (obrigatório)
- Nome do serviço (obrigatório)
- Oferta de serviços (recomendado)
- Proprietário do serviço (recomendado)
- Tipo de serviço (recomendado)
- Tipo (obrigatório)
- Unidade de medida (recomendado)

## Informações relacionadas

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentários sobre a Central de Ajuda](productfeedback@apptio.com "(Abre em uma nova guia ou janela)")
