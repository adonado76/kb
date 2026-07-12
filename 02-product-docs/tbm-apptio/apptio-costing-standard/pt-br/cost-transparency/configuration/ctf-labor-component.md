---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "CTF - Componente de trabalho: instalar e configurar"
breadcrumb: []
source_path: "cost-transparency/configuration/ctf-labor-component.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# CTF - Componente de trabalho: instalar e configurar

Use o componente CTF - Trabalho para importar os custos do projeto. Esse componente não é instalado automaticamente com o projeto padrão Costing Standard . O componente Labor fornece insights sobre os gastos com projetos por tipo, centro de custos, projetos e torres de TI.

Aplica-se a: Costing Standard em TBM Studio 12.4 e posterior

## Introdução

A tabela Dados mestre de mão de obra define os dados necessários para preencher os relatórios relacionados a custos e orçamento. Os dados fornecem uma análise detalhada dos custos de mão de obra para funcionários FTE e contratados, incluindo comparações de custos reais e número de funcionários em relação ao plano. Para preencher a tabela de dados mestre de mão de obra, carregue uma tabela de dados de mão de obra e mapeie-a para a tabela de dados mestre de mão de obra.

## Usa

Use os relatórios do componente CTF - Trabalho para fazer o seguinte:

- Gerenciar despesas de acordo com o orçamento
- Identificar alavancas de gastos
- Alinhar as despesas com os objetivos comerciais
- Alinhar as despesas à estratégia
- Confirmar o valor ou cancelar projetos

## Instalar o componente

O componente CTF - Labor não é instalado com o projeto padrão Costing Standard .

Para instalar os componentes:

1. Abra o projeto Costing Standard .
2. Na guia Projeto, clique em **Componentes**.
3. Clique no componente **CTF - Trabalho**.
4. Clique em **Install (Instalar** ).

A tabela Dados mestre de mão de obra define os dados necessários para preencher os relatórios relacionados a custos e orçamento. Os dados fornecem uma análise detalhada dos custos de mão de obra para funcionários FTE e contratados, incluindo comparações de custos reais e número de funcionários em relação ao plano. Para preencher a tabela de dados mestre de mão de obra, carregue uma tabela de dados de mão de obra e mapeie-a para a tabela de dados mestre de mão de obra.

## Fontes de dados típicas

Os números da mão de obra geralmente são extraídos de aplicativos de RH, como Oracle EBS, PeopleSoft, Workday e SAP. Os dados devem incluir uma lista de funcionários e informações de controle de tempo.

O aplicativo exige que os funcionários ou as atividades dos funcionários sejam mapeados para a taxonomia ATUM Tower/Sub-tower. Uma abordagem comum é criar uma tabela de mapeamento fora do aplicativo e, em seguida, fazer o upload da tabela.

## Um upload

Normalmente, você carrega uma única tabela de dados de mão de obra que é anexada à tabela de dados mestre de mão de obra. A tabela de dados deve conter campos que possam ser mapeados para os campos apropriados na tabela de dados mestre da mão de obra.

## Dados principais

Para obter uma descrição dos campos na tabela de dados mestre, consulte as informações na página do componente CTF - Trabalho no produto. Para exibir a página:

1. Clique na guia **Projeto**.
2. Clique em **Components (Componentes** ).
3. Clique no componente **CTF - Trabalho**.

## Campos obrigatórios e recomendados

Os campos obrigatórios e recomendados necessários para iluminar os relatórios trabalhistas padrão do site Costing Standard estão listados abaixo.

- Tipo de remuneração (obrigatório)
- Centro de custos (obrigatório)
- Nome do centro de custos (obrigatório)
- Pool de custos (obrigatório)
- Subgrupo de custos (recomendado)
- Tipo de funcionário (obrigatório)
- Subnível de recursos de TI (obrigatório)
- Torre de recursos de TI (obrigatório)
- Número de funcionários (obrigatório)
- ID do trabalho (obrigatório)
- Nome do trabalhador (obrigatório)
- Localização (obrigatório)
- Número de funcionários planejados (obrigatório)
- Posição (obrigatório)
- ID do projeto (recomendado)
- Região (obrigatório)
- Identificador exclusivo (obrigatório)

## Informações relacionadas

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentários sobre a Central de Ajuda](productfeedback@apptio.com "(Abre em uma nova guia ou janela)")
