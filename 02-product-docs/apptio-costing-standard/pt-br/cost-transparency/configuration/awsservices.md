---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "AWS Mapeamento de serviços"
breadcrumb: []
source_path: "cost-transparency/configuration/awsservices.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# AWS Mapeamento de serviços

Apptio os conectores CBM e AWS DataLink da TBM permitem mapear os itens de linha de faturamento dos itens de linha de faturamento do provedor de nuvem para os atributos do site ATUM, incluindo torres e subtorres de TI, a hierarquia de serviços da TBM, bem como uma unidade de medida normalizada.

Aplica-se a: Cloud for Costing Standard e Cloud Business Management em TBM Studio 12.5.x

## Visão geral

Esses mapeamentos permitem que você faça o seguinte:

- Analisar vários serviços de nuvem em vários provedores usando uma classificação comum de serviços de nuvem
- Visualizar o custo, o consumo e os custos unitários de todos os serviços de nuvem pública de maneira semelhante em vários provedores
- Alocar automaticamente os custos da nuvem nas Torres de Recursos de TI apropriadas

## Atualizações de mapeamento

Como os provedores de nuvem atualizam suas ofertas de serviços de forma consistente e rápida, os mapeamentos criados e mantidos pelo Apptio podem ficar desatualizados. Para lidar com esse ambiente dinâmico, o site Apptio atualiza os arquivos de mapeamento mensalmente. A ação que você precisa tomar depende do fato de você usar o Multicloud Connector:

- Conector multicloud. Para automatizar a ingestão do faturamento da nuvem, o mapeamento ATUM é realizado no pré-processador de faturamento da nuvem Apptio. Os arquivos de mapeamento ficam em um local central e o mapeamento ocorre antes que a fatura chegue ao ambiente CBM do cliente. Se ocorrerem lacunas no mapeamento do ATUM, nenhuma ação de sua parte será necessária. Em vez disso, o Apptio identifica as lacunas, preenche-as e, em seguida, atualiza o arquivo de mapeamento para garantir que essas lacunas sejam eliminadas de seu ambiente.
- AWS Conector. Se você usar o conector AWS legado, os mapeamentos ATUM continuarão a ocorrer no CBM por meio do conjunto de dados Cloud Service Provider Lookup, no qual você precisará anexar o arquivo AWS Service Mapping. O arquivo de mapeamento pode ser atualizado automaticamente por meio do conector legado AWS ou substituindo manualmente o conjunto de dados pelo arquivo de mapeamento.

Para atualizar o arquivo de mapeamento:

1. Clique com o botão direito do mouse no anexo do arquivo abaixo e clique em Salvar link (ou destino) como.
2. Navegue até o local onde deseja salvar o arquivo e clique em Salvar.
3. Descompacte e abra o arquivo.cvs em um aplicativo adequado, como o Microsoft Excel.
4. Selecione o arquivo da versão do ATUM que você deseja.
5. Faça login em Apptio TBM Studio.
6. No Project Explorer, navegue até **Tabelas > AWS Mapeamento de serviços**
7. Verifique o arquivo AWS Service Mapping e substitua-o pelo arquivo .csv atualizado.

O arquivo de mapeamento é atualizado com frequência. Consulte este artigo para obter a versão mais atualizada do conteúdo.

## Mapeamento de lacunas

Se você for um usuário do AWS e encontrar lacunas no mapeamento, envie uma lista dessas lacunas por e-mail para Apptio em [cloudmapping@apptio.com](mailto:cloudmapping@apptio.com "(Abre em uma nova guia ou janela)"). Faremos o possível para preencher as lacunas identificadas na próxima versão de atualização do mapeamento. Em seu e-mail, exporte e anexe o relatório ATUM Mapping Quality (na coleção de relatórios Maintenance) e inclua as seguintes informações para cada item de linha do provedor de serviços de nuvem com um campo Subtower em branco:

- Provedor
- Produto
- Item
- Procedimento
- Custo (opcional, mas útil para entender o impacto das lacunas)

## Mapeamento automatizado para ATUM 2.1 e 3.0

A partir de abril de 2019, o CBM foi atualizado para dar suporte ao mapeamento automatizado dos serviços do provedor de nuvem para as classificações ATUM. O CBM pode mapear os serviços do provedor de nuvem pública para ATUM 1.0, 2.0, 2.1 e 3.0, dependendo dos requisitos de sua organização.

## Histórico de alterações

| Data | ATUM v1.0 | ATUM v2.0 | Atualizar |
| --- | --- | --- | --- |
| 30/11/2020 | v1.35 | v2.25 | Inclui novas entradas para ATUM v1 e v2 e lacunas de relatórios de clientes a partir do final de novembro de 2020 |
| 12/10/2020 | v1.33 | v2.23 | Inclui novas entradas para ATUM v1 e v2 e lacunas de relatórios de clientes a partir do final de setembro de 2020 |
| 09/01/2020 | v1.32 | v2.22 | Inclui novas entradas para ATUM v1 e v2 e lacunas de relatórios de clientes a partir de agosto de 2020 |
| 22/05/2020 | v1.31 | v2.21 | Inclui novas entradas para ATUM 1.0 e 2.0 e lacunas relatadas por clientes |
| 23/04/2020 | v1.30 | v2.20 | Inclui novas entradas para ATUM 1.0 e 2.0 e lacunas relatadas por clientes |
| 23/01/2020 | v1.29 | v2.19 | Inclui novas entradas para ATUM 1.0 e 2.0 e lacunas relatadas por clientes |
| 15/11/2019 | v1.28 | v2.18 | Inclui novas entradas para ATUM 1.0 e 2.0 e lacunas relatadas por clientes |
| 09/06/2019 | v1.27 | v2.17 | Inclui novas entradas para ATUM 1.0 e 2.0 e lacunas relatadas por clientes |
| 06/03/2019 | v1.26 | v2.14 | Inclui novas entradas para ATUM 1.0 e 2.0 e lacunas relatadas por clientes |
| 24/04/2019 | v1.25 | v.2.13 | Inclui novas entradas para ATUM v1 e v2 e lacunas relatadas por clientes |
| 09/04/2019 | v1.24 | v.2.12 | Inclui novas entradas para ATUM v1 e v2 |
| 15/02/2019 | v1.23 | v.2.11 | Inclui novas entradas para ATUM v1 e v2 |
| 4/12/2018 | v1.22 | v2.10 | Inclui novas entradas para ATUM v1 e v2 |
| 23/10/2018 | v1.21 | v2.9 | Inclui novas entradas para ATUM v1 e v2 |
| 28/08/2018 | v1.20 | v2.8 | Inclui entradas adicionais de instâncias pontuais e entradas de RI para as famílias de instâncias R4 e R5 |
| 16/08/2018 | v1.19 | v2.07 | Inclui novas entradas para ATUM v1 & v2 |
| 12/07/2018 | v1.18 | v2.06 | Inclui novas entradas para ATUM v1 & v2 |
| 18/04/2018 | v1.17 | v2.05 | Inclui novas entradas para ATUM v1 & v2 |
| 16/03/2018 | v1.16 | v2.04 | Inclui novas entradas para ATUM v1 & v2 |
| 11/01/2018 | v1.15 | v2.03 | Inclui novas entradas para ATUM v1 & v2 |
| 13/12/2017 | v1.14 | v2.02 | Inclui novas entradas para ATUM v1 & v2 |
| 27/10/2017 | v1.13 | v2.01 | Inclui novas entradas para ATUM v1 & v2  Atualize os mapeamentos ausentes para ATUM v1 |
| 09/08/2017 | v1.12 | v2.0 | Atualizado ATUM v1 mapeamento de lacunas |
| 27/07/2017 | v1.11 | v2.0 | Inclui uma grande quantidade de novas entradas com base em lacunas conhecidas e AWS API de preços  ATUM v2 mapeamento incluído como arquivo adicional v2.0 |
| 15/05/2017 | v1.10 |  | Inclui novas entradas com base no conteúdo da API de preços do site AWS |
| 13/03/2017 | v1.9.1 |  | Inclui novas entradas com base no conteúdo da API de preços do site AWS |
| 19/01/2017 | v1.9 |  | Inclui uma grande quantidade de novas entradas com base no conteúdo da API de preços do site AWS |
|  | v1.8 |  | Inclui novas entradas para lacunas conhecidas |
|  | v1.7 |  | Inclui uma grande quantidade de novas entradas com base no conteúdo da API de preços do site AWS |
| 06/10/2016 | v1.6 |  | Várias lacunas nas subtorres | Novo conteúdo da API de preços AWS | Subtorres e unidades de medida limpas  *Observação sobre v1.6 - uma nova coluna, ProductCode,, foi adicionada. Essa nova parte dos dados não afetará as pesquisas e foi adicionada para dar suporte ao processo de atualização do mapeamento* |
|  | v1.5.1 |  | Inclui uma grande quantidade de novas entradas com base no conteúdo da API de preços do site AWS |
|  | v1.5 |  | Inclui algumas novas entradas CloudSearch + uma entrada de suporte padrão (onde UsageType e Operação estão em branco na fatura) |
|  | v1.4 |  | Inclui um grande número de novas entradas para novos produtos e regiões |

Você pode fazer o download do arquivo de mapeamento na comunidade Apptio :

[https://community.apptio.com/viewdocument/aws-services-mapping](https://community.apptio.com/viewdocument/aws-services-mapping "(Abre em uma nova guia ou janela)")

## Informações relacionadas

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentários sobre a Central de Ajuda](productfeedback@apptio.com "(Abre em uma nova guia ou janela)")
