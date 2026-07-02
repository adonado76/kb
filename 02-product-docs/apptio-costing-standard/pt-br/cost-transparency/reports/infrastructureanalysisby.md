---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Análise de infraestrutura por aplicativo"
breadcrumb:
  - "Costing Standard"
  - "Relatório detalhado"
  - "Coleta de inscrições"
source_path: "cost-transparency/reports/infrastructureanalysisby.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Análise de infraestrutura por aplicativo

Esse relatório fornece uma análise detalhada da porcentagem de uso de aplicativos por torre de TI (computação, armazenamento e central de serviços).

Este relatório foi elaborado para:

- Proprietários de aplicativos
- Proprietários de infraestrutura
- Arquitetos corporativos

O relatório fornece uma visão de alto nível da infraestrutura em seus aplicativos. Você pode encontrar detalhes sobre o armazenamento de computação da infraestrutura, bem como uma visão dos dados da nuvem e dos tíquetes da central de serviços e da central de ajuda que estão associados aos seus aplicativos. Você pode usar esse relatório para detalhar os dados sobre os servidores subjacentes e os dispositivos de armazenamento (unidades de armazenamento lógico) associados a cada aplicativo. Por exemplo, você poderia usar os dados deste relatório para analisar um esforço de migração para a nuvem.

O relatório Análise de infraestrutura por aplicativo contém os seguintes elementos:

![](../../resources/images/ct_images/ct%20report%20collections/infrastructure%20analysis%20by.jpg)

| Elemento-chave | Descrição |
| --- | --- |
| (1) Coleta de relatórios | Essa coleção de relatórios fornece os detalhes financeiros de TI de que você precisa para analisar o uso e os gastos com aplicativos:   - [Relatório de revisão de aplicativos](application-review.html "Este relatório fornece uma visão geral executiva dos gastos com aplicativos, divididos por execução de aplicativos (custos operacionais) e desenvolvimento de aplicativos (investimentos) para seus principais aplicativos, famílias de aplicativos e custos de infraestrutura subjacentes com base nas torres de TI ATUM (Data Center, Computação, Armazenamento e Rede). Um instantâneo simplificado de qualquer aplicativo está disponível com um clique rápido em qualquer gráfico de barras.") (aberto por padrão) - [Relatório do portfólio de aplicativos](application-portfolio.html "Esse relatório amplia as informações do relatório Application Review para todo o portfólio de aplicativos. Esse relatório permite que você veja quem é responsável pelo conjunto geral de aplicativos em sua organização de TI, os gastos por unidade de negócios, os geradores de custos separados por torre de TI e fornecedor e o impacto dos projetos relacionados aos aplicativos.") - [Relatório da lista de aplicativos](#infrastructure_analysis_by "Esse relatório fornece uma análise detalhada da porcentagem de uso de aplicativos por torre de TI (computação, armazenamento e central de serviços).") - [Análise de infraestrutura por aplicativo](infrastructureanalysisby.html "Esse relatório fornece uma análise detalhada da porcentagem de uso de aplicativos por torre de TI (computação, armazenamento e central de serviços).") (descrita nesta página) - [Aplicativos novos e aposentados](new-retired-apps.html "Esse relatório fornece dados relacionados ao número de aplicativos, ao uso e às alterações no acumulado do ano.") |
| (2) Cortadores | As segmentações globais na coleção de relatórios Aplicativos persistem de relatório para relatório, portanto, os filtros definidos nesse relatório podem afetar o que você vê em outros relatórios Aplicativos. Para obter mais informações, consulte a seção **Slicers** no [relatório Application Review](application-review.dita "(Abre em uma nova guia ou janela)"). |
| (3) Análise de computação por aplicativo | Veja as porcentagens de uso de virtualização e ambiente por aplicativo. A tabela fornece uma análise do perfil de virtualização com métricas para a porcentagem de horas físicas, virtuais, de nuvem privada e de nuvem pública usadas por cada aplicativo. Há também uma análise de ambiente que mostra a porcentagem de uso em cada ambiente (produção, desenvolvimento, teste e DR).    Selecione qualquer item na coluna Nome do aplicativo da tabela para acessar o [relatório detalhado Nome do aplicativo](../reports-v104/applicationnamedetail.html) com detalhes sobre esse item. |
| (4) Análise de armazenamento por aplicativo | Visualize as porcentagens de uso do nível de armazenamento e do ambiente por aplicativo. A tabela fornece a porcentagem de uso de Nível 1, 2 e 3, além da porcentagem de uso em cada ambiente (produção, desenvolvimento, teste ou DR).    Selecione qualquer item na coluna Nome do aplicativo da tabela para acessar o [relatório detalhado Nome do aplicativo](https://tbmcouncil.jiveon.com/docs/DOC-9217 "(Abre em uma nova guia ou janela)") com detalhes sobre esse item. |
| (5) Análise do Service Desk por aplicativo | Visualize análises por tipo de contato do cliente (incidente, problema, solicitação de alteração ou solicitação de serviço) e nível de gravidade (crítico, alto, médio ou baixo) por aplicativo.    Selecione qualquer item na coluna Nome do aplicativo da tabela para acessar o [relatório detalhado Nome do aplicativo](../reports-v104/applicationnamedetail.html "(Abre em uma nova guia ou janela)") com detalhes sobre esse item. |
| (6) Horas de servidor, total OpEx, OpEx por hora, detalhes do ambiente | Use esse conjunto de gráficos e tabelas para visualizar seus gastos gerais com aplicativos por horas de servidor, custo total e custo por hora de servidor por ambiente ou aplique filtros na parte superior do relatório para ver uma exibição específica. |

Você pode usar esse relatório para responder às seguintes perguntas:

|  |  |  |
| --- | --- | --- |
|  | • | Qual infraestrutura é compatível com cada aplicativo? |

|  |  |  |
| --- | --- | --- |
|  | • | Qual é a quantidade de infraestrutura que os aplicativos estão consumindo? |

|  |  |  |
| --- | --- | --- |
|  | • | Quanto do meu portfólio de aplicativos está sendo executado na infraestrutura de nuvem pública? |

|  |  |  |
| --- | --- | --- |
|  | • | Como o TCO de um aplicativo mudou quando ele foi migrado para a infraestrutura de nuvem pública? |

|  |  |  |
| --- | --- | --- |
|  | • | Quais custos de infraestrutura estão associados aos meus aplicativos? |

|  |  |  |
| --- | --- | --- |
|  | • | Quais são os servidores associados aos meus aplicativos por ambiente? |

|  |  |  |
| --- | --- | --- |
|  | • | Quais camadas de armazenamento estão associadas aos meus aplicativos por ambiente? |

|  |  |  |
| --- | --- | --- |
|  | • | Quais aplicativos estão usando produtos de infraestrutura não padrão? |

|  |  |  |
| --- | --- | --- |
|  | • | Que porcentagem dos custos dos aplicativos é atribuída aos custos da infraestrutura subjacente? |
