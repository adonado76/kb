---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Componente CT Apps - Servidores"
breadcrumb: []
source_path: "cost-transparency/configuration/servers.html"
images:
  - "resources/images/ct_images/6864_1.png"
  - "resources/images/ct_images/6864_2.png"
  - "resources/images/ct_images/6864_3.png"
  - "resources/images/ct_images/6864_4.png"
  - "resources/images/ct_images/6864_5.png"
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Componente CT Apps - Servidores

O componente Servers é um componente de pré-requisito fundamental que é usado pelo componente Servers Insights. O componente Servers não fornece novos relatórios, mas é usado para criar métricas que são expostas no componente Server Insights.

Aplica-se a: Costing Standard em TBM Studio 12.0 e posterior

Ícone do componente:

![Componente CT Apps - Servidores](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6864_1.png)

## Tabelas de suporte

Quando você instala o componente CT Apps - Servidores, três novos grupos de tabelas são criados, conforme mostrado na imagem a seguir.

![grupos de tabelas](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6864_2.png)

Cada grupo contém no mínimo duas tabelas: uma tabela de dados mestre e uma tabela de modelo. As tabelas de modelo são: Hipervisor, Servidor físico e Servidores.

## Relacionamento entre as tabelas Servidores, Hipervisor e Servidor físico

A tabela Servers (Servidores) lista todos os servidores físicos e virtuais. Ele não inclui os servidores de hipervisor. Os servidores do hipervisor são alocados para os servidores virtuais de duas maneiras, com base nos dados:

- Se um servidor virtual PUDER ser associado ao servidor no qual está hospedado, liste o servidor na tabela Hypervisor.
- Se um servidor virtual NÃO PUDER ser associado ao servidor no qual está hospedado, distribua os custos do hipervisor entre os servidores virtuais, ponderados pelo tamanho do servidor virtual.

A tabela Servidores físicos lista apenas os servidores físicos.

- A tabela Hypervisors (Hipervisores) lista os servidores físicos que hospedam servidores virtuais. Muitas vezes, você pode identificar esses servidores porque os dados do servidor mostrarão essas IDs de servidor em uma coluna HOSTED ON. Isso significa que há servidores hospedados no servidor físico. Além disso, alguns dados do servidor exibem uma coluna de hipervisor com um "sim" ou "não". Por fim, outra maneira de identificar esses servidores é com base no software associado a eles - o VMWare ESX é comumente associado a hipervisores.

## Dados principais

Para obter uma descrição dos campos nas três tabelas de dados mestre, consulte as informações na página do componente Servidores de aplicativos CT no produto. Para exibir a página:

1. Clique na guia **Project (Projeto** ) na faixa de opções.
2. Clique em **Components (Componentes** ).
3. Clique no componente **CT Apps - Servidores**.

## Transformar os dados do servidor

Normalmente, você carregará um arquivo que contém os dados das três tabelas de dados mestre: Dados mestre dos servidores, Dados mestre do servidor físico, Dados mestre do hipervisor. Você criará uma cópia do arquivo e o modificará para incluir os dados necessários para cada uma das tabelas de dados mestre.

Para acomodar os três conjuntos de dados mestre, crie três novas tabelas a partir da tabela original de dados do servidor:

1. Clique em New > Table (Novo > Tabela) na faixa de opções.
2. Dê à tabela um nome que seja facilmente associado à tabela de dados mestre.
3. Para a fonte, clique em Existing Table (Tabela existente) e selecione a tabela de dados original do servidor.
4. Repita o procedimento para as outras duas mesas.

## Tabela de dados dos servidores

Quando você mapeia os dados dos servidores para a tabela de dados mestre dos servidores, ela deve incluir todos os servidores físicos e virtuais, mas não os servidores de hipervisor. Você deve filtrar os dados dos servidores para excluir os servidores de hipervisor.

1. Abra a tabela de dados de servidores que você criou.
2. Adicione uma etapa **de filtro** ao pipeline de transformação semelhante ao exemplo de filtro a seguir.

   ![transformar o pipeline](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6864_3.png)

## Dados de servidores físicos

Quando você mapeia os dados dos servidores para a tabela Physical Servers Master Data, ela deve incluir todos os servidores físicos e hipervisores, mas não os servidores virtuais. Você deve filtrar os dados dos servidores para excluir os servidores virtuais usando um filtro semelhante ao mostrado abaixo.

![Servidores físicos Dados mestre](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6864_4.png)

**AVISO**

Ao mapear os dados para a tabela Physical Servers Master Data, você deve incluir o texto "Asset\_Resource - Compute" no início do campo ITRT\_Server Key. Por exemplo:

="Recurso\_de\_ativo - Computação"&&Categoria\_do\_sistema\_operacional

## Dados do hipervisor

Quando você mapeia os dados dos servidores para a tabela Hypervisor Master Data, ela deve incluir apenas hipervisores, mas não servidores físicos ou virtuais. Você deve filtrar os dados dos servidores para excluir os servidores físicos e virtuais usando um filtro semelhante ao mostrado abaixo.

![Dados do hipervisor](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6864_5.png)

## Mapear os dados

Depois de criar as três tabelas de dados, mapeie-as para suas respectivas tabelas de dados mestre.

## Informações relacionadas

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentários sobre a Central de Ajuda](productfeedback@apptio.com "(Abre em uma nova guia ou janela)")
