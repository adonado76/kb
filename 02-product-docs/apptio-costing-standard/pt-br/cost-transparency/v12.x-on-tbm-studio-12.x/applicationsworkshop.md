---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Workshop de aplicativos"
breadcrumb: []
source_path: "cost-transparency/v12.x-on-tbm-studio-12.x/applicationsworkshop.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Workshop de aplicativos

Preparação dos dados do aplicativo

1. Se ainda não tiver feito isso, carregue os dados do aplicativo, incluindo:
   - Lista de aplicativos
   - Detalhes do aplicativo suplementar
2. Seguindo as Apptio práticas padrão, categorize cada conjunto de dados brutos na categoria de Aplicativos.
3. Se apropriado, aplique um filtro de data aos dados do aplicativo.

## Sobre o identificador de aplicativos

O identificador do conjunto de dados mestre de aplicativos é o ID do aplicativo. Esse deve ser um identificador exclusivo para cada aplicativo que está sendo rastreado dentro de Apptio

## Sobre as chaves do aplicativo

As chaves no conjunto de dados mestre de aplicativos são todas geradas pelo sistema. A lógica recomendada está na tabela abaixo.

| Chave | A chave de campo é baseada em | Lógica recomendada |
| --- | --- | --- |
| Ticket\_App Key (em 11.6 ) | Definido pelo usuário | ="Chave do aplicativo Ticket\_App"&&ID do aplicativo Use essa chave somente se você instalar o componente Service Desk. Para vincular o Service Desk e os aplicativos, você deve ter um ID de aplicativo vinculado aos tickets sobre esse aplicativo. |
| Chave Project\_App | ID do aplicativo | ="Chave do aplicativo do projeto"&&ID do aplicativo Use essa chave somente se você instalar o componente Projects. Para vincular projetos e aplicativos, você deve ter um ID de aplicativo vinculado a projetos sobre esse aplicativo. |
| Chave Server\_App | Definido pelo usuário | ="Chave do aplicativo do servidor" e ID do aplicativo |
| Chave App\_Service | Definido pelo usuário | ="App\_Service" e nome do aplicativo Se você pretende que seus serviços sejam grupos de aplicativos, poderá usar Application Group em vez de Application Name na fórmula acima. |
| Chave do aplicativo de armazenamento | Definido pelo usuário | ="Storage\_App"&& ID do aplicativo |

## Colunas computadas comuns necessárias para aplicativos

Não há colunas computadas específicas que você precise criar. Isso varia de acordo com seus dados e com as necessidades do cliente em relação a como ele deseja dinamizar os dados.

## Mapear dados para dados mestre de aplicativos

Mapeie os dados do seu aplicativo para o conjunto de dados mestre de aplicativos. A maior parte do mapeamento deve ser autoexplicativa neste ponto. As unidades reais, a contagem de aplicativos e as unidades orçadas provavelmente serão definidas como =1. Em 12.7, agora você pode aproveitar a função Column Map em seu conjunto de dados brutos para mapear para os dados mestre dos aplicativos (Map Columns)

## Adicionar uniões aos dados mestre de aplicativos

Una seus conjuntos de dados mestre de servidor e armazenamento ao conjunto de dados mestre de aplicativos. A etapa Join vincula a tabela atual a outras tabelas, fazendo a correspondência entre os valores de uma coluna na tabela atual e os valores de uma coluna em outra tabela. (Juntar dados)

| Conjunto de dados | Ações |
| --- | --- |
| Dados mestre de aplicativos | Adicione uma etapa de união. Crie um novo vínculo entre os dados mestre de aplicativos e os dados mestre de servidores.  **De** : `Applications Master Data.Application ID`  **Para** : `Servers Master Data.App Consumer`  Crie um novo link entre os dados mestre de aplicativos e os dados mestre de armazenamento.  **De** : `Applications Master Data.Application ID`  **Para** : `Storage Master Data.App Consumer` |

## Revise o objeto Aplicativos nos modelos

| Modelo | Ações |
| --- | --- |
| Custo | Certifique-se de que os valores estejam fluindo para o objeto Applications. De Projetos a Aplicativos, aloque usando a Referência baseada em dados com uma ponderação uniforme (essa é a configuração padrão). As chaves que unem os projetos aos aplicativos são as colunas Project\_App Key em ambos os conjuntos de dados.  De Servidores a Aplicativos, aloque usando a Reverência baseada em dados com uma ponderação uniforme (essa é a configuração padrão). As chaves que unem Servidores e Aplicativos são as colunas Server\_App Key em ambos os conjuntos de dados.  De tíquetes a aplicativos, aloque usando a referência baseada em dados com uma ponderação uniforme (essa é a configuração padrão). As chaves que unem Tickets e Aplicativos são as colunas Ticket\_App Key em ambos os conjuntos de dados.  Do armazenamento aos aplicativos, aloque usando a referência baseada em dados, com uma ponderação uniforme (essa é a configuração padrão). As chaves que unem o armazenamento e os aplicativos são a chave Storage\_App no lado do armazenamento e a chave Storage\_App no lado dos aplicativos. |
| Orçamento | Certifique-se de que os valores estejam fluindo para o objeto Applications. De Projetos a Aplicativos, aloque usando a Referência baseada em dados com uma ponderação uniforme (essa é a configuração padrão). As chaves que unem os projetos aos aplicativos são as colunas Project\_App Key em ambos os conjuntos de dados.  De Servidores a Aplicativos, aloque usando a Reverência baseada em dados com uma ponderação uniforme (essa é a configuração padrão). As chaves que unem Servidores e Aplicativos são as colunas Server\_App Key em ambos os conjuntos de dados.  De tíquetes a aplicativos, aloque usando a referência baseada em dados com uma ponderação uniforme (essa é a configuração padrão). As chaves que unem Tickets e Aplicativos são as colunas Ticket\_App Key em ambos os conjuntos de dados.  Do armazenamento aos aplicativos, aloque usando a referência baseada em dados, com uma ponderação uniforme (essa é a configuração padrão). As chaves que unem o armazenamento e os aplicativos são a chave Storage\_App no lado do armazenamento e a chave Storage\_App no lado dos aplicativos. |
| CapEx | Certifique-se de que os valores estejam fluindo para o objeto Applications. De Projetos a Aplicativos, aloque usando a Referência baseada em dados com uma ponderação uniforme (essa é a configuração padrão). As chaves que unem os projetos aos aplicativos são as colunas Project\_App Key em ambos os conjuntos de dados. |
| Orçamento CapEx | Certifique-se de que os valores estejam fluindo para o objeto Applications. De Projetos a Aplicativos, aloque usando a Referência baseada em dados com uma ponderação uniforme (essa é a configuração padrão). As chaves que unem os projetos aos aplicativos são as colunas Project\_App Key em ambos os conjuntos de dados. |

## Revisar relatórios de aplicativos

Os relatórios a seguir são atualizados após a configuração do objeto Applications:

- Análise do aplicativo
- Portfólio de aplicativos
- Lista de aplicativos
- Análise de infraestrutura por aplicativo
- Aplicativos novos e aposentados
- Avaliação do aplicativo - Detalhes
- Aplicativo - Detalhe
- Aplicativo - Detalhe - Pools de custos
- Aplicativo - Detalhe - Torres de TI
- Aplicativo - Detalhes - Servidores
- Aplicativo - Detalhe - Armazenamento
- Aplicativo - Detalhe - Ingressos
- Tabela de alocação de infraestrutura de aplicativos
- Avaliação do aplicativo - Family Detail
- Validade dos aplicativos
- Dimensões de dados - Aplicativos
- Qualidade dos dados - Recursos de TI
- Qualidade de dados - Serviços
- Detalhes da torre de TI
- Infra - Detalhes do aplicativo

Para ver os detalhes desses relatórios (incluindo navegação, funções, objetivos e perguntas respondidas para cada relatório), consulte o Guia do Usuário do Costing Standard disponível na Ajuda on-line.

## Informações relacionadas

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentários sobre a Central de Ajuda](productfeedback@apptio.com "(Abre em uma nova guia ou janela)")
