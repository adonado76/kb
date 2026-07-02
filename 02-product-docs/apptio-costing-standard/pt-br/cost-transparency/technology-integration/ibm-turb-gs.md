---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "IBM Turbonomic Introdução"
breadcrumb:
  - "Costing Standard"
  - "Integrações tecnológicas"
  - "IBM Turbonomic"
source_path: "cost-transparency/technology-integration/ibm-turb-gs.html"
images:
  - "resources/images/ct_images/trb-arch-1.jpg"
  - "resources/images/ct_images/trb-arch-addr.jpg"
  - "resources/images/ct_images/trb-arch-et.jpg"
  - "resources/images/ct_images/trb-cnfg-1.jpg"
  - "resources/images/ct_images/trb-cnfg-2.jpg"
  - "resources/images/ct_images/trb-cnfg-3.jpg"
  - "resources/images/ct_images/trb-cnfg-4.jpg"
  - "resources/images/ct_images/trb-cnfg-5.jpg"
  - "resources/images/ct_images/trb-cnfg-6.jpg"
  - "resources/images/ct_images/trb-comp-1.jpg"
  - "resources/images/ct_images/trb-framework.jpg"
  - "resources/images/ct_images/trb-model-alloc.jpg"
  - "resources/images/ct_images/trb-prereq-1.jpg"
  - "resources/images/ct_images/trb-prerq.jpg"
  - "resources/images/ct_images/trb-stp-10.jpg"
  - "resources/images/ct_images/trb-stp-3b.jpg"
  - "resources/images/ct_images/trb-stp-4.jpg"
  - "resources/images/ct_images/trb-stp-6rc.jpg"
  - "resources/images/ct_images/trb-stp3a.jpg"
  - "resources/images/ct_images/trb-stp6.jpg"
  - "resources/images/ct_images/trb-stp6filt.jpg"
  - "resources/images/ct_images/trb-stp7-oi.jpg"
  - "resources/images/ct_images/trb-stp7b.jpg"
  - "cost-transparency/technology-integration/clip_image002_69970998.gif"
  - "cost-transparency/technology-integration/clip_image004_1503612513.gif"
  - "cost-transparency/technology-integration/clip_image006_-595341153.gif"
  - "cost-transparency/technology-integration/clip_image008_-537983876.gif"
  - "cost-transparency/technology-integration/clip_image010_-1349679255.gif"
  - "cost-transparency/technology-integration/clip_image012_672310785.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# IBM Turbonomic Introdução

A integração entre IBM Turbonomic e IBM Apptio é atualmente uma integração unidirecional, em que os dados fluem apenas de IBM Turbonomic para IBM Apptio Costing. As etapas abaixo fornecem detalhes sobre os passos necessários para iniciar essa integração.

## Pré-requisitos

Para iniciar a integração entre IBM Turbonomic e IBM Apptio, os seguintes pré-requisitos devem ser configurados:

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-prerq.jpg)

**Configuração de um Datadrop IBM Apptio**

A integração dos dados da Turbonomic IBM no IBM Apptio utiliza o Datadrop da IBM Apptio, um servidor SFTP (protocolo de transferência segura de arquivos) baseado em nuvem.

Para obter instruções detalhadas de configuração, consulte [Configurar uma conexão Datadrop](../../datalink/datalink_datadrop.dita "(Abre em uma nova guia ou janela)").

**Configuração no Turbonomic d IBM**

Depois que o IBM Apptio Datadrop for provisionado, siga as etapas a seguir para configurar IBM Apptio como um destino no IBM Turbonomic:

1. Navegue até IBM Turbonomic e selecione **Configurações** na coluna à esquerda.
2. Selecione **Novo destino** no canto superior direito.
3. Selecione *Gestão de TI* como a **Categoria Alvo**.
4. Entre os **tipos de destino** disponíveis, selecione “ *IBMApptio* ”. ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-prereq-1.jpg)
5. Na janela de configuração, insira os dados nos campos obrigatórios:
   - **Endereço** : Digite o nome do host de destino ou o endereço IP associado ao IBM Apptio account.Example: ` datadrop.apptio.com `
   - **Nome de exibição** : forneça um nome de exibição de sua escolha para este destino.
   - **Porta** : Defina o número da porta como 22.
   - **Nome de usuário** : Digite o nome de usuário associado a esta conta IBMApptio.
   - **Nome do host Turbonomic** : especifique o endereço da instância de origem do Turbonomic IBM.
6. Crie chaves para conectar o Turbo e o Datadrop d Apptio
   1. **Criar par de chaves pública/privada no formato.PEM**
      1. Baixe “ OpenSSL ” aqui: [https://sourceforge.net/projects/openssl-for-windows/](https://sourceforge.net/projects/openssl-for-windows/ "(Abre em uma nova guia ou janela)")
      2. Execute os seguintes comandos separadamente em uma linha de comand OpenSSL :
         - genrsa -out private-key.pem
         - rsa -in private-key.pem -pubout -out public-key.pem

           ![](../../../../../03-media/apptio-costing-standard/cost-transparency/technology-integration/clip_image002_69970998.gif)
   2. **Configurando as chaves Turbonomic**
      1. Cole o texto da chave PEM privada no Turbonomic. *Exemplo conforme abaixo:*

         ![](../../../../../03-media/apptio-costing-standard/cost-transparency/technology-integration/clip_image004_1503612513.gif)

         Observação: a chave privada não pode ter uma senha. Se uma ferramenta como o Putty estiver sendo usada para gerar a chave privada, é provável que ela esteja no formato PPK incorreto.
      2. Baixe a chave pública PGP na seção de configurações do datalink

         ![](../../../../../03-media/apptio-costing-standard/cost-transparency/technology-integration/clip_image006_-595341153.gif)
      3. Cole a chave pública PGP na chave GPG no Turbonomic
   3. **Configurando chaves Datadrop**
      1. O Datadrop só aceita chaves no formato OpenSSH, por isso precisamos converter a chave privada na etapa anterior.
      2. Baixe o utilitário de geração de chaves RSA/DSA do putty: [https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html "(Abre em uma nova guia ou janela)")
      3. Inicie o gerador de chaves e carregue sua chave privada no formato.PEM. Isso criará uma chave pública no formato OpenSSH. *Exemplo conforme abaixo:*

         ![](../../../../../03-media/apptio-costing-standard/cost-transparency/technology-integration/clip_image008_-537983876.gif)
      4. Copie a chave pública e cole-a em Chave Pública do seu nome de usuário turbo nas configurações do Datadrop

      Exemplo de janela do tipo de destino Apptio totalmente preenchida no Turbonomic:

      ![Captura de tela de uma caixa branca Descrição gerada automaticamente](../../../../../03-media/apptio-costing-standard/cost-transparency/technology-integration/clip_image010_-1349679255.gif) ![Uma captura de tela de um computador Descrição gerada automaticamente](../../../../../03-media/apptio-costing-standard/cost-transparency/technology-integration/clip_image012_672310785.gif)

## Instalação de componentes

Para permitir a integração entre IBM Turbonomic e IBM Apptio, é necessário instalar três componentes.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-comp-1.jpg)

Observação: certifique-se de que a versão dos componentes nas configurações do projeto esteja definida como versão 120. Após a instalação dos componentes, você pode reverter a versão do componente para o modelo desejado ou anterior.

## Componente de otimização de TI híbrida

O primeiro componente a ser instalado é o NOVO componente *Otimização de TI Híbrida*. Este componente apresenta um conjunto de novos conjuntos de dados mestres, métricas (tanto modeladas quanto calculadas) e alocações de modelos. Esses elementos foram projetados para dar suporte a uma arquitetura que permite modelar e gerar relatórios sobre otimizações da infraestrutura de TI híbrida.

Como esse componente é destinado a clientes existentes, pode ser necessário personalizar determinadas pesquisas de tabelas, métricas e alocações para se alinhar ao modelo existente de otimização de TI ( Apptio ) dentro da nova estrutura de otimização de TI híbrida.

Para obter informações mais detalhadas sobre o componente, consulte a descrição fornecida ao navegar até o componente no sistema.

## Turbonomic – Componente Ações

Enquanto o primeiro componente, *Otimização de TI Híbrida*, estabelece a estrutura, o segundo componente, Turbonomic – Ações, instala as tabelas e os conjuntos de dados mestres necessários para permitir a integração perfeita dos dados *do IBM Turbonomic Action* — via Datadrop — no IBMApptioTBM Studio.

Observação: o componente *Otimização de TI híbrida* deve ser instalado primeiro, pois a tabela Turbo Actions Master depende de pesquisas em três tabelas editáveis incluídas no componente *Otimização de TI híbrida*.

Para obter mais detalhes sobre o conteúdo deste componente, consulte a descrição fornecida ao navegar até o componente.

## Otimização de TI híbrida - Componente de relatórios

O terceiro e último componente é o componente *Otimização de TI híbrida - Relatórios*. Este componente instala dois relatórios que visualizam insights acionáveis a partir da integração. Ele fornece:

- Finanças de TI e o Proprietário do Serviço Técnico (Provedor de TI) com uma visão das economias potenciais e realizadas do ponto de vista dos custos.
- Proprietário da solução/aplicação (consumidor de TI) com uma visão das economias potenciais e realizadas do ponto de vista dos custos.

Para obter mais detalhes sobre o conteúdo deste componente, consulte a descrição fornecida ao navegar até o componente.

## Arquitetura

O diagrama a seguir ilustra o fluxo de dados de IBM Turbonomic para IBM Apptio 's Datalink. Os passos estão descritos abaixo:

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-arch-1.jpg)

1. **IBM Configuração do Turbonomic e descoberta de dados** : IBM O Turbonomic realiza sua configuração normal e descobre dados para cada destino adicionado. Uma lista completa dos destinos suportados está disponível [aqui](https://www.ibm.com/docs/en/tarm/8.13.0?topic=documentation-target-configuration "(Abre em uma nova guia ou janela)"). A Turbonomic descobre recursos, monitora a utilização e recomenda ações. O diagrama mostra alguns alvos de exemplo em azul.
2. **IBM Apptio Configuração do tipo de destino** : Configure o tipo de destino “ IBMApptio ” (Destino de saída) no Turbonomic ( IBM ) de acordo com os pré-requisitos. Essa configuração envia dados de IBM Turbonomic para IBM Datadrop da Apptio. Certifique-se de que o Datadrop do IBM Apptio foi configurado corretamente. As instruções para configurar o Datadrop/SFTP Server no lado do Apptio podem ser encontradas na [Central de Ajuda do Apptio ](#).
3. **Carregamento e atualização de arquivos** : Os arquivos em formato JSON são carregados diariamente no servidor Datadrop/SFTP baseado em nuvem d Apptio. A carga útil consiste em quatro conjuntos de dados: Ações pendentes e executadas para ambientes locais e na nuvem. Todos os dias, quatro novos arquivos aparecerão no repositório do visualizador Datadrop. Para obter detalhes sobre o conteúdo do arquivo, consulte a seção Carga útil de dados.
4. **Datalink Configuração dos conectores** : Crie conectores Datalink para extrair dados do repositório Datadrop para TBM Studio:
   - Para Ações pendentes, defina o comportamento do upload como “SOBRESCREVER” Cada arquivo diário de IBM Turbonomic mostra as últimas ações pendentes, portanto, ele deve substituir o arquivo anterior em TBM Studio.
   - Para ações executadas, defina o comportamento de upload como “APPEND” O arquivo contém as ações executadas nas últimas 24 horas, portanto, acrescente os dados para criar uma visualização do mês até o momento.
   - O TBMA pode programar execuções do conector (diárias, semanais ou mensais). Para automatizar o processo, atribua os nomes de destino da tabela diretamente aos conjuntos de dados criados pelo IBM Apptio Framework.
5. **Integração de dados em TBM Studio** : Após executar os conectores, a carga útil será armazenada nas seguintes TBM Studio tabelas:
   - Ações pendentes do Turbo Cloud
   - Ações pendentes do Turbo On-Prem
   - Ações executadas pelo Turbo Cloud
   - Ações executadas pelo Turbo On-Prem

## IBM Apptio Estrutura

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-framework.jpg)

O diagrama da estrutura fornece uma visão geral da arquitetura de otimização de TI híbrida com tecnologia d IBM Ações pendentes e executadas da Turbonomic. Ele introduz novas tabelas e conjuntos de dados mestres a partir de uma perspectiva do Turbonomic do IBM (instalado através do componente Turbonomic – Ações do IBM ) e de uma perspectiva mais ampla de Otimização de TI Híbrida (instalado através do componente Otimização de TI Híbrida).

Essa arquitetura relaciona novos pontos de dados aos dados existentes no modelo IBM Apptio. Existem 12 etapas de configuração, com bolhas vermelhas indicando configurações exigidas pelo usuário e bolhas laranja para etapas automatizadas/pré-configuradas. Essas etapas são detalhadas na seção Configuração.

## IBM Apptio Alocações de modelos

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-model-alloc.jpg)

A estrutura IBM Apptio fornece uma visão geral das novas tabelas e conjuntos de dados, enquanto o diagrama acima se concentra nas novas métricas e alocações do modelo:

**Custo híbrido/carga híbrida**

Trata-se de novas métricas paralelas que aproveitam os modelos de custo/cobrança existentes, concentrando-se exclusivamente no custo total da camada de infraestrutura. As métricas existentes não são reutilizadas para evitar alocações duplicadas e conflitos.

Os usuários precisam criar drivers para esses modelos. Depois que as alocações para o novo objeto de modelo de infraestrutura forem configuradas, o modelo restante seguirá o fluxo descrito.

**Contagem de ações**

Novas métricas independentes para relatórios mensais (MTD) e anuais (YTD) sobre o número de ações pendentes e executadas.

**Poupança potencial/poupança realizada**

Essas são métricas importantes na estrutura de otimização de TI híbrida.

- As economias potenciais baseiam-se em ações pendentes.
- As economias realizadas baseiam-se nas ações executadas. Ambas as métricas são divididas em duas dimensões: Custo e Encargo
  - **Custo** : Para a nuvem, a economia em dólares é obtida diretamente da Turbonomic IBM. Para On-Prem, as economias são calculadas usando a mudança no valor da ação (por exemplo, 12 vCPU reduzido para 2 vCPU,, resultando em uma economia de 10 vCPU ) e o custo unitário dos serviços técnicos. Os ajustes são feitos com base na porcentagem de endereçamento definida pelo usuário.
  - **Cobrança** : Segue uma abordagem semelhante, utilizando o preço dos serviços técnicos e ajustando com base na porcentagem definida pelo usuário. Essas economias são direcionadas para o consumidor de serviços ou aplicativos voltados para negócios.

**Nível de endereçamento**

Os usuários devem definir e editar a % Endereçável tanto para o custo unitário quanto para o preço. A definição dessa porcentagem afeta os cálculos de economia de custos e encargos. A composição das poupanças é dividida em:

- Economia direta
- Poupança diferida
- Redução de custos

Os usuários têm total autonomia para definir a alocação da porcentagem endereçável entre essas categorias. Isso pode ser definido na guia Workbench do relatório Otimização da infraestrutura – Exibição do provedor.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-arch-addr.jpg)

As colunas em cinza claro devem ser anexadas à Tabela Editável, com origem no Catálogo de Serviços existente, enquanto as colunas em branco devem ser definidas pelo usuário.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-arch-et.jpg)

## Carga útil de dados

Conforme descrito nos pré-requisitos, o fluxo de dados é iniciado em um Turbonomic d IBM. Depois que o tipo de destino IBM Apptio estiver configurado, os dados, incluindo as ações pendentes e executadas do Turbo, serão transferidos para o Datadrop do IBM Apptio. A partir daí, os conectores Datalink transmitem os dados para IBM Apptio TBM Studio para processamento posterior.

Os quatro arquivos a seguir serão carregados

- Ações pendentes do Turbo On Prem
- Ações executadas pelo Turbo On Prem
- Ações pendentes do Turbo Cloud
- Ações executadas pelo Turbo Cloud

Os arquivos são diferenciados por duas dimensões principais:

- **Estado da ação** : PENDENTE ou EXECUTADO.
- **Entrega** : CLOUD ou ON-PREM.

A principal diferença reside nos dados que são transmitidos. Para o CLOUD, apenas dados agregados são enviados, incluindo 14 colunas, em contraste com as 25 colunas enviadas para os dados On-Prem. As principais razões para essa diferença na granularidade são as seguintes:

- Os dados locais são quantificados usando o modelo e os dados do IBM Apptio, como IBM A Turbonomic não fornece detalhes financeiros para ambientes locais. Para realizar esses cálculos, é necessário um nível mais alto de granularidade, razão pela qual colunas detalhadas, como ID da entidade e ID da ação, são incluídas. Em contrapartida, os dados na nuvem já vêm com economias pré-calculadas, conforme determinado por IBM Turbonomic, eliminando a necessidade de detalhes tão granulares.
- IBM Apptio não foi projetado para armazenar dados granulares da nuvem — esse é o objetivo do produto Cloudability. Semelhante à forma como as contas da nuvem CSP são inseridas sem incluir as informações mais detalhadas (por exemplo, ID do recurso), essa integração também evita o envio de dados granulares de otimização da nuvem.

Os conjuntos de 25 colunas para dados locais e 14 colunas para dados na nuvem foram cuidadosamente selecionados por meio de um esforço colaborativo entre IBM, Apptio e IBM Turbonomic. Este exercício se concentrou em identificar as colunas mais importantes que seriam valiosas tanto para modelagem quanto para relatórios na integração.

## Configuração

Conforme destacado na seção [Arquitetura](architecture.html), a integração técnica envolve 12 etapas distintas. Esta seção descreve cada etapa em detalhes. Qualquer coisa marcada em **vermelho** requer configuração do usuário, enquanto **laranja** indica uma etapa automatizada.

![Configuração](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-cnfg-1.jpg)

**Etapa 0** : Configuração dos pré-requisitos

Certifique-se de que tanto **o** IBM Apptio Datadrop quanto o **IBM Apptio Target Type em IBM Turbonomic** estejam configurados. Essas configurações são explicadas nas seções anteriores. Uma vez implementados, os arquivos de dados serão enviados diariamente para o Datadrop. Os arquivos ficam visíveis no seu Datadrop Viewer em Datalink, conforme mostrado na captura de tela abaixo.

![Visualizador Datadrop](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-cnfg-2.jpg)

Em seguida, crie um novo conector Datalink usando o tipo de conector Datadrop.

![Conector Datadrop](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-cnfg-3.jpg)

![Conexões](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-cnfg-4.jpg)

Defina a opção Transformar da seguinte forma:

- SUBSTITUIR para ações pendentes
- ANEXO para ações executadas

Certifique-se de que o conector recupere o período de tempo dinamicamente a partir do nome do arquivo, selecionando a opção “Mês e ano do nome do arquivo”.

![Ações pendentes](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-cnfg-5.jpg)

Na seção Sistema de origem, use o padrão de nome de arquivo fixo fornecido por IBM Turbonomic:

**Turbonomic\_<cloud/onprem>\_<executado/pendente>\_ações\_<nome do destino> \_MMDDYYYY.json**

- Dado um nome de destino de "ApptioA"
- E a data atual de “12 de outubro de 2024”
- E dados de ações pendentes no local
- Então, o nome do arquivo é:   
  Turbonomic\_onprem\_pending\_actions\_ApptioA\_10122024.json
- Dado um nome de destino “Apptio\_B”
- E a data atual de “1º de novembro de 2024”
- E dados de ações executadas na nuvem
- Então, o nome do arquivo é Turbonomic\_cloud\_executed\_actions\_Apptio\_B\_11012024.json

Para o destino, defina os nomes das tabelas como:

- Ações pendentes do Turbo On Prem
- Ações pendentes do Turbo Cloud
- Ações executadas pelo Turbo On Prem
- Ações executadas pelo Turbo Cloud

![Ações pendentes no local](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-cnfg-6.jpg)

Discuta as opções de arquivamento com seu gerente de sucesso do cliente ou com a equipe DAT.

1. Após configurar os conectores Datalink, o feed de dados fluirá automaticamente para TBM Studio as tabelas: Ações pendentes do Turbo On Prem, Ações pendentes do Turbo Cloud, Ações executadas do Turbo On Prem, Ações executadas do Turbo Cloud. Essas tabelas são pré-criadas durante a instalação do componente, e a carga útil dos dados seguirá a mesma sintaxe de coluna. Na primeira execução, faça uma verificação de integridade para garantir que o formato e o conteúdo dos dados estejam corretos.
2. Os conjuntos de dados serão transferidos automaticamente para a tabela Turbo Actions Feed, combinando as ações pendentes e executadas para processamento posterior.
3. À medida que os dados são inseridos na tabela Turbo Actions Feed, eles serão vinculados aos modelos de dados existentes do Apptio, especialmente para quantificação de dados no local. Esta etapa envolve:
   1. Anexar conjuntos de dados mestres de infraestrutura (por exemplo, dados mestres de servidores) à tabela Feed de infraestrutura.

      ![Conjuntos de dados mestres de infraestrutura](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-stp3a.jpg)
   2. Criação de novos controladores para os modelos de custo híbrido e cobrança híbrida, vinculando o custo e a cobrança dos modelos existentes ao novo objeto do modelo de infraestrutura.

      ![Modelos híbridos de custo e cobrança](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-stp-3b.jpg)
4. Depois que os conjuntos de dados existentes da infraestrutura do Apptio forem anexados, valide a pesquisa pronta para uso (OOTB) entre a tabela Turbo Actions Feed e a tabela Infrastructure. Esta pesquisa vincula o nome da entidade do Turbo com o nome da infraestrutura do Apptio. Esta etapa está destacada em vermelho porque a pesquisa OOTB pode precisar de personalização para maximizar a conexão de dados.

   ![OOTB](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-stp-4.jpg)
5. Os dados *do Feed de Ações Turbo* serão automaticamente anexados ao conjunto de dados *Mestre de Ações Turbo*. A tabela *Feed* pré-filtra e normaliza os dados, enquanto a tabela *Master* é onde os cálculos principais, como economias, são realizados.
6. O componente *Otimização de TI híbrida* cria um conjunto de tabelas editáveis do Workbench, que são expostas por meio da interface de relatórios. As principais tabelas a serem configuradas incluem:
   - **Meta e configurações** : Certifique-se de que as metas COIN sejam definidas de acordo com os acordos internos.

     ![Meta e configurações](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-stp6.jpg)
   - **Filtros** : Exclua quaisquer ações ou tipos de entidade que não tenham impacto nas economias potenciais ou realizadas.

     ![Filtros](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-stp6filt.jpg)
   - **Tabela de Preços** : A tabela editável mais importante é a Tabela de Preços Unitários. Defina a porcentagem endereçável (%) e suas divisões detalhadas; caso contrário, o sistema utilizará por padrão as colunas Custo unitário e Preço com base no custo total de propriedade (TCO).

     ![Lista de taxas](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-stp-6rc.jpg)
7. Como parte do componente *Otimização de TI híbrida*, várias tabelas adicionais são criadas automaticamente. Uma dessas tabelas é a tabela “*Infraestrutura não encontrada na otimização* ”, que fornece informações sobre a parte do conjunto completo de infraestrutura carregada pelo Apptio que tem otimizações Turbo aplicadas. Esses dados são visualizados no relatório Exibição do provedor em duas áreas:
   - **Impacto da otimização** : A medida em que a infraestrutura é otimizada ou afetada.

     ![Impacto da otimização](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-stp7-oi.jpg)
   - **Infra sem nenhuma ação** : Infraestrutura sem ações pendentes ou executadas.

     Isso pode ocorrer porque a infraestrutura não está dentro do escopo da otimização do Turbo ou já está totalmente otimizada.

     ![Infra sem nenhuma ação](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-stp7b.jpg)
8. O objeto *Detalhes da otimização da infraestrutura* é atribuído à *Otimização da infraestrutura*. A estrutura inclui um objeto detalhado e um objeto resumido para otimizar os recursos de relatórios e detalhamento. Ambos os objetos são instalados como parte do componente *Otimização de TI híbrida*.
9. Para permitir a geração de relatórios a partir da perspectiva do aplicativo (consumidor), os dados de infraestrutura devem estar relacionados aos aplicativos. Esta etapa aloca métricas do modelo ao objeto Relações de infraestrutura.
10. Anexe os dados *de relacionamento* da infraestrutura existente Apptio ao novo objeto Infraestrutura de Relacionamentos. Isso é feito por uma questão de eficiência, e não para expandir o conjunto de dados anterior. ![Relacionamento](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-stp-10.jpg)

    Se a relação com o consumidor da infraestrutura existir dentro do mesmo conjunto de dados (por exemplo, Conjunto de Dados Mestre do Servidor), ela é anexada ao modelo nesta fase por uma questão de eficiência, em vez de expandir o conjunto de dados original da infraestrutura.
11. O componente *Otimização de TI híbrida* inclui linhas de alocação pré-construídas que transferem automaticamente todas as métricas do modelo do objeto Relação de infraestrutura para o objeto Aplicativos. Isso permite relatórios de visualização do consumidor prontos para uso (OOTB) da perspectiva das aplicações.
12. Esta etapa final fornece um espaço reservado para que os clientes ampliem os relatórios além dos aplicativos, permitindo alocações posteriores para Serviços Comerciais ou Unidades Comerciais, conforme necessário. Isso permite relatórios adicionais sobre oportunidades de otimização e economia.
