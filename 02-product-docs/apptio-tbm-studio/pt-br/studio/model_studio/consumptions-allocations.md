---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Alocações de consumo"
breadcrumb: []
source_path: "studio/model_studio/consumptions-allocations.html"
images:
  - "resources/images/studio_images/studioimages/studio/stu589.png"
  - "resources/images/studio_images/studioimages/studio/stu594.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Alocações de consumo

**Aplica-se a** : TBM Studio 12.0 e posterior

A opção **Consumo** é usada para alocar as unidades disponíveis na tabela de origem para as unidades reais consumidas pela tabela de destino. Por exemplo, se você estiver modelando o consumo de serviços, poderá indicar o número de cada serviço a ser alocado a uma unidade de negócios.

Quando você seleciona essa opção, o aplicativo exibe as opções de **Consumo**, nas quais você escolhe uma coluna de consumo e uma coluna de capacidade.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu589.png)

No campo **Coluna de consumo**, selecione um valor da tabela de destino que indique o número de unidades consumidas.

No campo **Coluna de capacidade**, selecione um valor da tabela de destino de origem que indique a capacidade total disponível.

## Opções de distribuição

Há três opções de distribuição:

- Mesmo
- Peso por
- Relacionamento de dados

## Mesmo

A opção **Even** é a opção padrão e entra em vigor quando as opções **Weight By** e **Data Relationship** não estão selecionadas.

![](../../resources/images/studio_images/studioimages/studio_products%20allocation_distributing.png)

Ele distribui a alocação uniformemente entre todas as unidades identificadas na tabela de alvos pela propriedade **To**. Por exemplo, se houver uma tabela de **destino de aplicativos** com cinco aplicativos e US$ 100.000 estiverem sendo alocados, US$ 20.000 serão alocados para cada aplicativo.

## Peso por

A opção **Weight By (Ponderar por** ) distribui a alocação com base na proporção (tamanho relativo) dos valores em uma coluna que você selecionar.

Por exemplo, suponha que haja cinco aplicativos com vários números de usuários, conforme mostrado na tabela abaixo, e que US$ 100.000 estejam sendo alocados. Você deseja ponderar a distribuição pelo número de usuários. Os US$ 100.000 seriam distribuídos conforme mostrado na coluna **Alocação** a seguir:

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu594.png)

Observação: se você tentar ponderar uma alocação por uma coluna numérica que contenha pelo menos um valor não numérico, a ponderação será ignorada. Para corrigir o problema, remova os valores não numéricos da coluna.

## Relacionamento de dados

A opção **Relacionamento de dados** distribui a alocação uniformemente entre as unidades que correspondem aos valores em uma coluna na tabela de origem com os valores em uma coluna na tabela de destino. Por exemplo, suponha que a tabela de origem inclua informações sobre aplicativos. As tabelas de origem e destino incluem uma coluna **Application Category (Categoria do aplicativo** ). Uma das categorias é identificada como **Bancos de dados**, mas há dois aplicativos de banco de dados: Oracle e SAP. O valor das entradas do banco de dados na tabela de origem seria agregado e alocado igualmente às entradas do banco de dados na tabela de destino. Se estivessem sendo alocados US$ 20.000, eles seriam divididos em US$ 10.000 para Oracle e US$ 10.000 para SAP.

Você pode especificar mais de um relacionamento. Se você especificar mais de uma relação, todas as relações deverão corresponder para que o valor seja alocado.
