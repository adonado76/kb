---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Azure Mapeamento de serviços"
breadcrumb: []
source_path: "cost-transparency/configuration/azuremap.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Azure Mapeamento de serviços

Apptio os conectores CBM e AWS DataLink da TBM permitem mapear os itens de linha de faturamento dos itens de linha de faturamento do provedor de nuvem para os atributos do site ATUM, incluindo torres e subtorres de TI, a hierarquia de serviços da TBM, bem como uma unidade de medida normalizada.

Aplica-se a: Cloud for Costing Standard em TBM Studio 12.5.x

## Visão geral

Esses mapeamentos permitem que você faça o seguinte:

- Analisar vários serviços de nuvem em vários provedores usando uma classificação comum de serviços de nuvem
- Visualize o custo, o consumo e os custos unitários de todos os serviços de nuvem pública de maneira semelhante em vários provedores
- Alocar automaticamente os custos da nuvem nas Torres de Recursos de TI apropriadas

Você pode fazer o download dos arquivos de mapeamento na comunidade Apptio :

[https://community.apptio.com/viewdocument/azure-services-mapping](https://community.apptio.com/viewdocument/azure-services-mapping "(Abre em uma nova guia ou janela)")

## Atualizações de mapeamento

Como os provedores de nuvem atualizam suas ofertas de serviços de forma consistente e rápida, os mapeamentos criados e mantidos pelo Apptio podem ficar desatualizados. Para lidar com esse ambiente dinâmico, o site Apptio atualiza os arquivos de mapeamento mensalmente. A ação que você precisa tomar depende do fato de você usar o Multicloud Connector.

Os arquivos de mapeamento atualizados estão anexados a este artigo e rastreados na tabela Histórico de alterações, abaixo.

- Conector multicloud. Para automatizar a ingestão do faturamento da nuvem, o mapeamento ATUM é realizado no pré-processador de faturamento da nuvem Apptio. Os arquivos de mapeamento ficam em um local central e o mapeamento ocorre antes que a fatura chegue ao ambiente CBM do cliente. Se ocorrerem lacunas no mapeamento do ATUM, nenhuma ação de sua parte será necessária. Em vez disso, o Apptio identifica as lacunas, preenche-as e, em seguida, atualiza o arquivo de mapeamento para garantir que essas lacunas sejam eliminadas de seu ambiente.
- Azure Conector. Se você usar o conector Azure legado, os mapeamentos ATUM continuarão a ocorrer no CBM por meio do conjunto de dados Cloud Service Provider Lookup, no qual você precisará anexar o arquivo Microsoft Azure Service Mapping. O arquivo de mapeamento deve ser atualizado manualmente, substituindo o conjunto de dados pelo arquivo de mapeamento.

Para atualizar o arquivo de mapeamento:

1. Clique com o botão direito do mouse no anexo do arquivo abaixo e clique em Salvar link (ou destino) como.
2. Navegue até o local onde deseja salvar o arquivo e clique em Salvar.
3. Descompacte e abra o arquivo.cvs em um aplicativo adequado, como o Microsoft Excel.
4. Selecione o arquivo da versão do ATUM que você deseja.
5. Faça login em Apptio TBM Studio.
6. No Project Explorer, navegue até Tabelas > Microsoft Azure Mapeamento de serviços.
7. Verifique o arquivo Microsoft Azure Service Mapping e substitua-o pelo arquivo.csv atualizado.

O arquivo de mapeamento é atualizado com frequência. Consulte este artigo para obter a versão mais atualizada do conteúdo.

## Mapeamento automatizado para ATUM 2.1 e 3.0

A partir de abril de 2019, o CBM foi atualizado para dar suporte ao mapeamento automatizado dos serviços do provedor de nuvem para as classificações ATUM. O CBM pode mapear os serviços do provedor de nuvem pública para ATUM 1.0, 2.0, 2.1 e 3.0, dependendo dos requisitos de sua organização.

## Histórico de alterações

Os arquivos do Microsoft Azure Mapping Services foram atualizados nas seguintes datas. Apptio recomenda que você clique em **Action > Follow (Ação > Seguir** ) para que possa ser notificado quando os arquivos de mapeamento recém-atualizados estiverem disponíveis.

| Data de inclusão | Versão | Descrição |
| --- | --- | --- |
| 30 de novembro de 2020 | 2.19 | Novas entradas para ATUM 2.0 e lacunas relatadas pelo cliente. |
| 12 de outubro de 2020 | 2.17 | Novas entradas para ATUM 2.0 e lacunas relatadas por clientes a partir do final de setembro de 2020 |
| 1º de setembro de 2020 | 2.16 | Novas entradas para ATUM 2.0 e lacunas relatadas por clientes a partir de agosto de 2020. |
| 22 de maio de 2020 | 2.15 | Novas entradas para ATUM 2.0 e lacunas relatadas pelo cliente. |
| 23 de abril de 2020 | 2.14 | Novas entradas para ATUM 2.0 e lacunas relatadas pelo cliente. |
| 30 de janeiro de 2020 | 2.13 | Novas entradas para ATUM 2.0 e lacunas relatadas pelo cliente. |
| 15 de novembro de 2019 | 2.12 | Novas entradas no site Azure para atender às lacunas relatadas pelos clientes. |
| 3 de junho de 2019 | 2.11 | Novas entradas para ATUM 1.0 e 2.0 e lacunas relatadas por clientes. |
| 7 de março de 2019 | 2.10 | Novas entradas baseadas no conteúdo da API de preços de março Azure com ATUM 2.0 e lacunas relatadas por clientes. |
| 15 de janeiro de 2019 | 2.9.2 | Correção da formatação da coluna e adição de dados ausentes. |
| 10 de janeiro de 2019 | 2.9.1 | Correção do arquivo de dezembro. |
| 26 de dezembro de 2018 | 2.9 | Inclui novas entradas com base em dezembro Azure Pricing API Content with ATUM 2.0 e lacunas nos relatórios de clientes. |
| 24 de outubro de 2018 | 2.8.1 | Foi adicionada uma nova coluna, Subtower 2.0, como uma cópia direta de SubTower 2.0 para resolver problemas de casos nas funções de pesquisa do CCM. |
| 23 de outubro de 2018 | 2.8 | Incorporou um grande número de alterações de nomes de serviços introduzidas pelo Azure em meados de outubro de 2018 |
| 20 de setembro de 2018 | 2.7 | Inclui novas entradas com base em Ago Azure Pricing API Content with ATUM 2.0. |
| 7 de maio de 2018 | 2.6 | Inclui novas entradas com base em abril Azure Pricing API Content with ATUM 2.0 e lacunas nos relatórios de clientes. |
| 2 de março de 2018 | 2.5 | Inclui novas entradas com base em fevereiro Azure Pricing API Content with ATUM 2.0. |
| 19 de janeiro de 2018 | 2.4 | Inclui novas entradas com base em janeiro Azure Pricing API Content with ATUM 2.0. |
| 9 de janeiro de 2018 | 2.3 | Inclui novas entradas com base em dezembro Azure Pricing API Content com ATUM 2.0 e atualizações com mapeamentos de medidores renomeados Azure. |
| 8 de setembro de 2017 | 2.2 | Inclui todos os serviços de novas entradas com base em setembro Azure Conteúdo da API de preços com ATUM 2.0. |
| 27 de julho de 2017 | 2.1 | Inclui todos os serviços de novas entradas com base em julho Azure Conteúdo da API de preços com ATUM 2.0. |
| 24 de maio de 2017 | 2.0 | Adição de novos campos ATUM 2.0 (Tower 2.0, Subtower 2.0, Service Type, Service Category, Service Name); Inclui todos os serviços do catálogo de serviços publicado em maio de 2017. |
| 24 de janeiro de 2017 | 1.5.1 | Erro de digitação atualizado do catálogo de serviços Azure, onde o armazenamento do Windows Azure foi erroneamente rotulado como Windows Azure Service Bus for Resource GUID5E7A80E5-0273-44B8-A179-E4F62EA6EC9F. |
| 19 de janeiro de 2017 | 1.5 | Inclui todos os serviços do catálogo de serviços publicado em janeiro de 2017. |
| 4 de dezembro de 2016 | 1.4 | Inclui todos os serviços do catálogo de serviços publicado em novembro de 2016 e um grande número de melhorias na normalização de unidades. |
| 23 de maio de 2016 | 1.3 | Inclui todos os serviços do catálogo de serviços publicado em abril de 2016. |
| 2 de fevereiro de 2016 | 1.2 | Publicação inicial. |

Você pode fazer o download dos arquivos de mapeamento na comunidade Apptio :

[https://community.apptio.com/viewdocument/azure-services-mapping](https://community.apptio.com/viewdocument/azure-services-mapping "(Abre em uma nova guia ou janela)")

## Informações relacionadas

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentários sobre a Central de Ajuda](productfeedback@apptio.com "(Abre em uma nova guia ou janela)")
