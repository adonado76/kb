---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Preencher a tabela Fonte de custos para o cadastro de recursos de TI"
breadcrumb: []
source_path: "cost-transparency/configuration/populatecostsource2.html"
images:
  - "resources/images/ct_images/6869_1.png"
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Preencher a tabela Fonte de custos para o cadastro de recursos de TI

Para preencher a tabela Fonte de custos para dados mestre de recursos de TI, carregue uma tabela de dados que defina a porcentagem dos outros custos a serem alocados a cada centro de custo. Depois de criar a tabela, mapeie-a para a tabela Cost Source to IT Resource Master Data.

Aplica-se a: Costing Standard em TBM Studio 12.0 e posterior

## Introdução

Use a tabela Outros pools de custos para alocar quaisquer valores não alocados para mão de obra ou ativos fixos para as torres e subtorres de recursos de TI. Para fazer isso, você precisará:

- Mapeie seus centros de custo para as torres e subtorres de TI.
- Defina uma alocação percentual real se um centro de custo for mapeado para várias torres e subtorres de TI.
- Definir uma alocação percentual orçada se um centro de custo for mapeado para várias torres e subtorres de TI.

A tabela Fonte de custos para dados mestre de recursos de TI define os dados necessários para "iluminar" os relatórios relacionados a custos e orçamento. Para preencher a tabela, você deve carregar um conjunto de dados que define a porcentagem dos outros custos a serem alocados a cada centro de custo. Depois de criar a tabela, mapeie-a para a tabela Cost Source to IT Resource Master Data. Um exemplo de tabela é mostrado abaixo.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6869_1.png)

## Fontes de dados típicas

Os números dos centros de custo geralmente são extraídos de aplicativos como Oracle, SAP, Lawson e Cognos Financial Statement Reporting. Os dados que você usar determinarão o nível de detalhe disponível e as colunas que você mapeará para a tabela Origem do custo para os dados mestre do recurso de TI.

## Um upload

Normalmente, você carrega uma única tabela de dados que é anexada à tabela Cost Source to IT Resource Master Data e à tabela IT Resource Towers Master Data. A tabela de dados deve conter campos que possam ser mapeados para os campos apropriados nas tabelas de dados mestre.

## Campos obrigatórios e recomendados

Os campos obrigatórios e recomendados necessários para iluminar as tabelas de dados mestre estão listados abaixo.

Fonte de custos para os dados mestre de recursos de TI

- % alocada (obrigatório)
- Centro de custos (obrigatório)
- Torre e subtorre de recursos de TI (obrigatório)
- Planejado % Alocado (recomendado)

Dados mestre das torres de recursos de TI

- Nome da subnível de recursos de TI (obrigatório)
- Nome da torre de recursos de TI (obrigatório)
- Proprietário da torre de recursos de TI (obrigatório)
- Quantidade de torres de recursos de TI (obrigatório)
- Unidade de medida (obrigatório)

## Informações relacionadas

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentários sobre a Central de Ajuda](productfeedback@apptio.com "(Abre em uma nova guia ou janela)")
