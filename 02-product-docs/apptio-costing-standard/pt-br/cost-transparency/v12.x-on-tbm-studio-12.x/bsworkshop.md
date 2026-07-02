---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Workshop de serviços empresariais"
breadcrumb: []
source_path: "cost-transparency/v12.x-on-tbm-studio-12.x/bsworkshop.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Workshop de serviços empresariais

## Etapas para preencher seus serviços comerciais

Nesse ponto, você precisa preencher os serviços comerciais com os dados dos serviços comerciais. Se você não tiver uma lista de serviços comerciais, poderá usar uma lista de seus aplicativos ou grupos de aplicativos. As etapas a seguir descrevem como preencher os Serviços comerciais.

1. Se você tiver uma lista de serviços comerciais, poderá carregá-la no Apptio e colocá-la na seção Serviços comerciais
2. Se você não tiver uma lista, pode fazer o seguinte:
   1. Localize a Lista de Referência de Todos os Serviços Empresariais
   2. Exportar a lista para fora do Apptio
   3. Carregar em uma nova tabela chamada "Customer" Business Services List
   4. Configure com pesquisas para extrair todas as informações necessárias e anexá-las aos Business Services.

## Sobre o identificador de serviço comercial

O identificador do conjunto de dados All Business Services é o Service ID. Esse deve ser um identificador exclusivo para cada serviço.

## Sobre as Chaves de Serviço Comercial

As chaves do conjunto de dados All Business Services são, em sua maioria, definidas pelo usuário. A lógica recomendada está na tabela abaixo.

| Chave | A chave de campo é baseada em | Lógica recomendada |
| --- | --- | --- |
| **Chave App\_Service** | Definido pelo usuário | ="App\_Service" e ID do serviço Se você estiver usando uma lista de aplicativos como serviços, a lógica recomendada é:  ="App\_Service" e ID do aplicativo |
| **Chave Project\_Service** | ID do Serviço | ="Project\_Service" && ID do serviço |
| **Chave ITRT\_Service** | Definido pelo usuário | ="ITRT\_Service" && ID do serviço |
| **Service\_Service Allocations Direct Key (em 11.6 )** | Definido pelo usuário | ="Chave direta de alocações de serviço" && ID do serviço |

## Colunas computadas comuns necessárias para serviços comerciais

Não há colunas computadas específicas que você precise criar. Isso varia de acordo com seus dados.

## Dados do mapa para os dados de todos os serviços comerciais

Quando você publicou a Biblioteca de serviços, o conjunto de dados Todos os serviços comerciais foi preenchido. Não é necessário mapear nenhum dado nesse momento.

## Analise o objeto Business Services nos modelos

| Modelo | Ações |
| --- | --- |
| **Custo** | Certifique-se de que os valores estejam fluindo para o objeto Service Allocations Indirect. De Serviços comerciais a Alocações de serviços indiretos, aloque usando a Referência baseada em dados com uma ponderação uniforme (essa é a configuração padrão). As chaves que unem os Aplicativos aos Serviços de negócios são as colunas Chave de ID de serviço em ambos os conjuntos de dados.  Da alocação indireta de serviços à alocação da unidade de negócios, aloque usando ponderação, como o número de funcionários. |
| **CapEx** | Certifique-se de que os valores estejam fluindo para o objeto Service Allocations Indirect. De Serviços comerciais a Alocações de serviços indiretos, aloque usando a Referência baseada em dados com uma ponderação uniforme (essa é a configuração padrão). As chaves que unem os Aplicativos aos Serviços de negócios são as colunas Chave de ID de serviço em ambos os conjuntos de dados.  De alocações de serviços indiretos para alocação de unidades de negócios, usando ponderações como o número de funcionários. |

## Revisar relatórios de serviços comerciais

Os relatórios a seguir são atualizados após a configuração do objeto Business Services:

- Revisão de serviços
- Portfólio de serviços
- Lista de serviços
- Categoria de serviço - Detalhe
- Detalhes do serviço
- Detalhes da oferta de serviços
- Revisão do serviço - detalhes
- Serviços - detalhes do grupo
- Serviços - Tendência do custo unitário
- Portfólio de aplicativos - Detalhe - Grupos de custos
- Portfólio de aplicativos - detalhes - IT Towers

Para ver os detalhes desses relatórios (incluindo navegação, funções, objetivos e perguntas respondidas para cada relatório), consulte o Guia do Usuário do Costing Standard disponível na Ajuda on-line.

## Informações relacionadas

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentários sobre a Central de Ajuda](productfeedback@apptio.com "(Abre em uma nova guia ou janela)")
