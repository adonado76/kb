---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "CTF - Componente do ativo fixo: instalar e configurar"
breadcrumb: []
source_path: "cost-transparency/configuration/ctf-fa-component.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# CTF - Componente do ativo fixo: instalar e configurar

Use o componente CTF - Ativo Fixo para obter insights sobre seus custos de depreciação e capacitar suas decisões sobre o gerenciamento de ativos. A tabela Dados mestre do ativo fixo define os dados necessários para preencher os relatórios relacionados a custos e orçamento. Para preencher o conjunto de dados, você deve carregar os valores de custo do ativo fixo e mapeá-los para a tabela de dados mestre do ativo fixo.

Aplica-se a: Costing Standard em TBM Studio 12.4 e posterior

## Usa

Use os relatórios do componente CTF - Ativos fixos para fazer o seguinte:

- Gerenciar custos de depreciação
- Identificar a alocação de recursos
- Alinhar o gerenciamento de ativos com os objetivos comerciais
- Alinhar o gerenciamento de ativos à estratégia
- Confirmar as baixas contábeis resultantes de alterações orçamentárias

## Instalar o componente

O componente CTF - Ativos fixos não é instalado com o projeto padrão Costing Standard .

Para instalar o componente CTF - Ativos fixos:

1. Abra o projeto Costing Standard .
2. Na guia Projeto, clique em **Componentes**.
3. Clique em **Install (Instalar** ).

## Fontes de dados típicas

Os números de ativos fixos geralmente são extraídos de um aplicativo de gerenciamento de ativos ou CMDB (Configuration Management Data Base), como BMC Asset Mgmt, BMC Atrium CMDB, HP Univ Config Mgmt, Sage, AssetWorks, SAP Enterprise Asset Mgmt, CA Unicenter, SAP, Lawson, Oracle, ou PeopleSoft.

Os aplicativos geralmente incluem um registro de ativos fixos. O registro de ativos fixos rastreia ativos como máquinas, equipamentos de escritório, edifícios, etc., para fins de produção de bens ou serviços. Frequentemente, o registro do ativo fixo rastreia a vida útil em meses do ativo, a data de compra, o valor da compra e a depreciação mensal.

## Um upload

Normalmente, você carrega um único conjunto de dados de ativo fixo que é anexado e mapeado para a tabela de dados mestre do ativo fixo. O conjunto de dados deve conter campos que possam ser mapeados para os campos apropriados na tabela Dados mestre do ativo fixo.

## Dados principais

Para obter uma descrição dos campos na tabela de dados mestre, consulte as informações na página do componente CTF - Ativo fixo no produto. Para exibir a página:

1. Clique na guia **Projeto**.
2. Clique em **Components (Componentes** ).
3. Clique no componente **CTF - Ativos fixos**.

## Campos obrigatórios e recomendados

Os campos obrigatórios e recomendados necessários para iluminar os relatórios padrão de ativos fixos do site Costing Standard estão listados abaixo.

- Data de aquisição (obrigatório)
- Idade (obrigatório)
- Contagem de ativos (obrigatório)
- Número do ativo (obrigatório)
- Tipo de ativo (recomendado)
- Categoria (recomendado)
- Classe (obrigatório)
- Centro de custo (recomendado)
- Valor da depreciação (obrigatório)
- Descrição (obrigatório)
- LIM de depreciação de ativos fixos (obrigatório)
- Custo inicial do ativo fixo (obrigatório)
- ID do Ledger de ativos fixos (obrigatório)
- Em serviço (obrigatório)
- Data de entrada em serviço (obrigatório)
- Subnível de recursos de TI (obrigatório)
- Torre de recursos de TI (obrigatório)
- Localização (obrigatório)
- Identificador de objeto (obrigatório)
- Fornecedor (obrigatório)

## Informações relacionadas

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentários sobre a Central de Ajuda](productfeedback@apptio.com "(Abre em uma nova guia ou janela)")
