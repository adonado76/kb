---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Guia de configuração do AI TCO"
breadcrumb: []
source_path: "cost-transparency/configuration/ai-tco-configguide.html"
images:
  - "resources/images/ct_images/aiarch.png"
  - "resources/images/ct_images/aicomcon.png"
  - "resources/images/ct_images/aiconfig.png"
  - "resources/images/ct_images/aicst.png"
  - "resources/images/ct_images/aictapp.png"
  - "resources/images/ct_images/aictf.png"
  - "resources/images/ct_images/aitco.png"
  - "resources/images/ct_images/aitcoreport.png"
  - "resources/images/ct_images/aius.png"
  - "resources/images/ct_images/arch1.png"
  - "resources/images/ct_images/cldcst.png"
  - "resources/images/ct_images/dataench.png"
  - "resources/images/ct_images/datamap.png"
  - "resources/images/ct_images/inptok.png"
  - "resources/images/ct_images/labcst.png"
  - "resources/images/ct_images/modcnt.png"
  - "resources/images/ct_images/opta.png"
  - "resources/images/ct_images/optb.png"
  - "resources/images/ct_images/othcst.png"
  - "resources/images/ct_images/outtok.png"
  - "resources/images/ct_images/ovr1.png"
  - "resources/images/ct_images/solcnt1.png"
  - "resources/images/ct_images/solcnt2.png"
  - "resources/images/ct_images/solusr.png"
  - "resources/images/ct_images/solusr1.png"
  - "resources/images/ct_images/tokencom.png"
  - "resources/images/ct_images/typenorm.png"
  - "resources/images/ct_images/uc1.png"
  - "resources/images/ct_images/vencnt.png"
  - "resources/images/ct_images/vencst.png"
  - "resources/images/ct_images/wrkbench.png"
  - "resources/images/icons/aitco.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Guia de configuração do AI TCO

## Visão geral

A solução AI TCO & Usage foi projetada para resolver os principais problemas de negócios e fornecer insights valiosos.

![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/ovr1.png)

Ele oferece suporte aos seguintes casos de uso

![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/uc1.png)

## Pré-requisitos

Os pré-requisitos para a solução AI TCO & Usage são:

- IBM Apptio Costing Standard licença
- IBM Apptio Versão do servidor: R12.11.14 (ou superior)
- Versão dos componentes v120 em Configurações do projeto

## Etapas de configuração

![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/aiconfig.png)

A visão geral a seguir descreve as etapas de configuração necessárias para obter relatórios de TCO e uso de IA, com documentação detalhada fornecida nas próximas páginas sections.:

1. Arquitetura de projetos - Consulte a seção *de arquitetura* [aqui](#aitoconfig__arch)
2. Instalação de componentes - Consulte a seção *de instalação de componentes* [aqui](#aitoconfig__compinst)
3. Baseado na fatura ou no Razão. Essas duas opções são descritas em alto nível na seção *de arquitetura* [aqui](#aitoconfig__arch)
4. Carregar fontes de dados relacionadas à IA - Consulte a seção *de requisitos de dados* [aqui](#aitoconfig__datreq)
5. Ilumine as novas métricas do modelo - Consulte a seção *do modelo* [aqui](#aitoconfig__models)
6. Relatórios de uso e TCO de IA - Consulte a seção *de relatórios* [aqui](#aitoconfig__rep)

## Instalação do componente

O núcleo da solução AI TCO & Usage é apresentado por meio de 4 componentes. 2 novos componentes, criados especificamente para esta solução + 2 componentes existentes que foram estendidos e, portanto, devem ser atualizados. Para novos clientes, os outros componentes "típicos" de mão de obra, fornecedor, nuvem etc. precisariam ser instalados, de acordo com a arquitetura geral pretendida. Os clientes existentes podem reutilizar esses componentes instalados anteriormente sem nenhuma alteração. Antes de instalar esses componentes, é essencial analisar cuidadosamente a arquitetura do seu ambiente para determinar a melhor abordagem para a implementação. Você precisará decidir se deseja:

- Instale os componentes em um projeto existente ou
- Criar um novo projeto especificamente para a solução AI TCO & Usage

A seguir, apresentamos uma visão geral dos quatro componentes a serem considerados e instalados em ordem de prioridade.

![Imagem 1](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/aicomcon.png)

Observação: Para instalar os componentes necessários, defina temporariamente *a Versão dos componentes* como Versão 120 nas Configurações do projeto. Instale os componentes necessários e, em seguida, reverta a alteração de versão para evitar o acionamento de indicadores de atualização desnecessários.

![Um quadrado verde com uma cabeça com um fone de ouvido](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/aitco.png)

1. Componente **TCO e uso de IA** : Esse componente oferece uma visão clara dos gastos e da utilização de IA em modelos de IA, soluções de IA e unidades de negócios. Esse componente estabelece a estrutura subjacente por meio de um conjunto de novos conjuntos de dados mestre específicos de IA, bancos de trabalho, modelos e métricas, facilitando a modelagem e o cálculo do TCO da IA e dos resultados de uso.

   Instale como o primeiro componente.

   ![Figura](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/aictf.png)
2. Componente **CTF – Fonte de Custo** : Uma nova versão do componente CTF – Fonte de Custo está disponível, adicionando os seguintes **novos campos** aos Dados Mestres de Fonte de Custo para dar suporte à solution.:
   1. Porcentagem de custo de IA: Traz a porcentagem de custo de IA conforme definido pelo usuário na tabela AI Tablematch.
   2. Valor da IA: Multiplica o valor da origem de custo existente com a porcentagem de custo de IA para criar um novo valor de IA que parece alimentar o novo modelo de custo de IA. A ser instalado como segundo componente. Se você não instalar esse componente, não verá a métrica "% of Total IT Cost YTD" ou o detalhamento "AI Cost by Cost Pool" em seus relatórios.

      Observação: para os clientes existentes (que pretendem preencher essa solução usando a fonte de custos - Razão), é necessário atualizar o seguinte componente:

   ![Um quadrado verde com um logotipo branco e azul](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/aictapp.png)
3. Componente **CT Apps - Serviços** : Está disponível uma nova versão do componente CT Apps - Services, que adiciona novos campos a All Business Services para dar suporte à solução AI TCO & Usage.

   Observação: os clientes existentes devem atualizar o componente a seguir para garantir a compatibilidade e o acesso aos novos recursos.

   1. IsAISolution: Precisa ser definido como "Sim" para qualquer oferta de serviço que seja considerada direta ou indiretamente uma solução de IA.
   2. Tipo de solução de IA: Metadados que são usados como um slicer na solução AI TCO & Usage. Os valores sugeridos são:
      1. *Autônoma:* Uma solução de IA dedicada que opera de forma independente como seu próprio produto ou serviço.
      2. *Incorporada:* IA incorporada profundamente em um produto existente, tornando-se um recurso nativo essencial.
      3. *Aumentada:* A IA é acrescentada ou levemente adicionada para aprimorar um recurso/processo, mas não é essencial.
   3. Usuários de soluções de IA: Resume o nº. de usuários únicos de soluções de IA.
   4. Contagem de soluções de IA: Conta o número. de soluções de IA.

   A ser instalado como terceiro componente. Observação: A não atualização desse componente interromperá os relatórios de TCO e uso do AI, pois a maioria dos relatórios é criada no nível de AI Solutions = Business Services com o filtro definido em IsAISolution = "Yes".

   ![Um logotipo verde e branco](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/aitcoreport.png)
4. **Componente AI TCO & Usage Reporting** : Esse componente fornece os relatórios para a solução AI TCO & Usage. Ele consiste em 2 relatórios, introduzidos em uma nova coleção de relatórios de IA. O principal relatório de TCO e uso de IA permite que as organizações monitorem todo o ciclo de vida dos investimentos em IA, abordando proativamente a expansão da IA por meio do rastreamento do custo total de propriedade (TCO), das tendências de uso, das falhas e das anomalias. As principais pessoas-alvo são executivos C-suite, líderes de negócios e soluções e equipes de IA e ciência de dados. Além disso, há um relatório secundário do modelo de custo de IA que permite aos usuários rastrear dinamicamente as alocações de custo e uso de IA por meio de visualizações interativas do diagrama de Sankey.

   A ser instalado como o componente final.

## Arquitetura

A primeira etapa é decidir onde instalar os componentes da solução AI TCO & Usage. Você tem várias opções, e descrevemos duas abordagens possíveis abaixo.

**Opção A**

Integrar a solução AI TCO & Usage em um projeto existente e optar por uma abordagem orientada por GL e Resource Tower.

Essa abordagem é recomendada para clientes existentes que desejam aproveitar/reutilizar a lógica de alocação que já existe na métrica principal do modelo de custo. Se você acha que seus usuários-alvo se beneficiariam de uma abordagem orientada pelo Razão, com visões detalhadas dos Resource Towers e dos Cost Pools, esta solução é uma boa opção. O diagrama abaixo mostra como integrar o novo objeto AI Platforms em seu modelo padrão.

![Um diagrama de uma empresa](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/aiarch.png)

*Modelo de métrica de modelo de custo de IA - Baseado em GL com Resource Towers*

A solução AI TCO & Usage apresenta novas métricas que funcionam de forma independente, mesmo quando adicionadas ao seu projeto existente. O novo modelo de custo de IA é destacado no diagrama, com o **azul** mostrando as partes existentes e **o verde** mostrando os novos acréscimos, como plataformas de IA e novos campos em origem de custos e serviços empresariais. Isso permite que você use suas linhas de alocação existentes com o novo modelo de custo de IA conforme a necessidade, proporcionando mais flexibilidade e controle.

O driver do objeto Fonte de custo na métrica do modelo de custo de IA se baseia em uma nova coluna chamada "AI amount", que é preenchida a partir do conjunto de dados "Cost Source AI Tablematch". Esse conjunto de dados foi projetado para identificar transações do Razão relacionadas à Inteligência Artificial (IA).

![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/opta.png)

É essencial identificar e preencher a tabela com as contas, os centros de custo, os fornecedores e as descrições de linhas de diário relevantes que você associa ao **AI Costs & Usage**, conforme demonstrado no exemplo acima. Além disso, a coluna AI Cost % é obrigatória e deve conter valores numéricos.

Observação: Em caso de dúvida com relação à % de custo de IA, defina-a como 100. As regras de alocação e os mapeamentos refinarão ainda mais os valores das transações para incluir apenas os custos relacionados à IA.

A lógica de correspondência de tabela recuperará detalhes de colunas adicionais dos dados da fonte de custos, fazendo a correspondência das entradas da extração carregada e preenchendo as colunas relevantes, desde que existam nos dados da fonte de custos.

**Opção B**

Crie um novo projeto para a solução AI TCO & Usage + opte por uma abordagem orientada por faturamento, excluindo os Resource Towers.

Observação: Optar pela abordagem orientada pela fatura e excluir as Torres de Recursos nesse momento seria considerado uma abordagem personalizada. Tecnicamente viável, mas provavelmente exigirá suporte do Apptio Professional Services.

Essa abordagem é recomendada para clientes novos ou existentes que desejam primeiro fazer referência completa a essa nova solução e ao conjunto de casos de uso relacionados à IA. Além disso, é adequado para clientes que acreditam que as personas-alvo dessa solução se beneficiariam de uma fonte de verdade orientada pelo faturamento, com linhas de alocação mais diretas e sem a necessidade de relatar os detalhamentos de custos dos Resource Towers e dos Pools de custos. A imagem abaixo mostra o esquema da arquitetura.

![Um diagrama de uma empresa](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/optb.png)

*Modelo de métrica de modelo de custo de IA - Baseado em faturamento sem torres de recursos*

A estrutura acima se afasta da abordagem mais tradicional do Razão - orientada pela fonte de custos e, ao mesmo tempo, remove os Resource Towers da arquitetura. Se isso pudesse acelerar o tempo de implantação, dependeria da criação de mais alocações personalizadas. Se você adotar essa abordagem, as seguintes exibições de relatório prontas para uso não funcionarão mais:

- KPI de "% do custo total de TI no acumulado do ano"
- Detalhamento do custo de IA por "pool de custos"
- Detalhamento do custo de IA por "torres de recursos"

## Rastejar, andar, correr

Ao começar a usar a solução AI TCO & Usage, você não precisa ter tudo configurado desde o início para começar a perceber o valor. A solução foi projetada para ser flexível, permitindo que você comece aos poucos e, ao longo do tempo, tenha um entendimento completo dos seus custos de IA. Isso significa que você pode começar com o básico e adicionar mais detalhes à medida que avança, sem a necessidade de ter todas as peças no lugar imediatamente. Você pode pensar nisso como uma abordagem **Crawl-Walk-Run**, em que você começa dando pequenos passos e, em seguida, aumenta gradualmente o ritmo à medida que se sente mais confortável com a solução. Essa abordagem permite que você forneça valor rapidamente e crie um impulso ao longo do tempo, facilitando a obtenção do máximo de seus investimentos em IA.

![Figura](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/arch1.png)

*TCO e uso de IA - Rastejar, caminhar, correr*

**Engatinhar**

Na fase de rastreamento, determinadas soluções de IA podem ser configuradas com relativa rapidez, bastando trazer conjuntos de dados relacionados a determinadas áreas. O foco aqui está nas soluções de IA que estão sendo compradas predominantemente.

- Exemplo de solução de IA: Microsoft Copilot
- Principais objetos do modelo:
  - Fornecedor: Licença do fornecedor
  - Trabalho: Treinamento e gerenciamento de mudanças
  - Outros: Segurança e integração
  - Service Allocations Direct: Arquivo de consumo/utilização
- Valor: Entenda o TCO do Microsoft Copilot como uma solução de IA, incluindo visões das contribuições trabalhistas. Relate e acompanhe a adoção do Microsoft Copilot em toda a organização, trazendo e aproveitando os dados de consumo/utilização associados.

**Caminhar**

Na fase de caminhada, o foco mudaria para soluções de IA que começam a trazer o uso de plataformas de IA e/ou modelos de IA, sustentando o TCO; juntamente com usos mais avançados de mão de obra qualificada. Essas soluções de IA normalmente seriam uma combinação de compra e construção.

- Exemplo de solução de IA: AskIT
- Objetos do modelo principal (além dos objetos da fase de rastreamento):
  - Nuvem: Custo e uso do modelo de IA
  - Plataformas de IA: Dados que representam as plataformas de IA e os modelos de IA reais
  - Dados: No caso de dados proprietários, certifique-se de capturar e representar o custo relacionado à preparação e ao treinamento dos dados
- Valor: Entenda o TCO de uma solução de IA interna, como AskIT, começando a trazer dados relacionados às plataformas de IA e/ou aos modelos de IA que a solução está consumindo. Relatar e rastrear os fatores de custo, além de obter insights sobre o uso do modelo de IA.

**Executar**

Na fase de execução mais avançada, espera-se que a maioria, se não todos, os objetos modelados típicos se tornem aplicáveis para iluminar os resultados e os insights de TCO e uso da IA. Espera-se que as soluções de IA representadas nessa fase sejam, em sua maioria, soluções de IA criadas internamente.

- Exemplo de solução de IA: IndexGPT
- Objetos do modelo principal (além dos objetos da fase de rastreamento e execução):
  - Infraestrutura: Computação de IA dedicada (GPU), armazenamento, banco de dados etc.
  - Controle de horas: Maneira mais econômica de garantir que o controle de atividades adequado esteja em vigor para atividades de trabalho de alto nível
- Valor: Obtenha insights de ponta a ponta sobre o TCO e o uso de IA em todas as suas soluções de IA, inclusive as mais complexas. Alguns deles são alojados e construídos internamente e, portanto, contêm uma pegada de infraestrutura significativa que precisa ser contabilizada.

## Requisitos de dados

**Dados básicos**

Conforme mostrado na seção focada na arquitetura, a solução AI TCO & Usage introduz um novo objeto modelado chamado AI Platforms. Esse objeto destina-se a ser abastecido com dados focados no custo, no uso e na adoção associados a plataformas e modelos de IA.

O arquivo incorporado se concentra em:

- Os dados necessários (listando todas as colunas com suas respectivas descrições, se são necessárias ou não e o efeito se estiverem faltando)
- Esclarecimentos sobre a coluna (descreve alguns valores de amostra e sua descrição)
- Dados de amostra (um exemplo de como os dados se pareceriam nas plataformas de IA)
- Sistemas de origem (exemplos de referências de sistemas de origem em potencial para os dados da Plataforma de IA)

Além do novo objeto principal das plataformas de IA, dois conjuntos de dados mestre foram atualizados para refletir algumas das alterações necessárias para iluminar os principais relatórios de TCO e uso de IA.

Várias colunas novas foram adicionadas ao Cost Source Master Data e All Business Services, que estão documentadas no mesmo arquivo incorporado.

Observação: os dados necessários para preencher os outros objetos modelados que fazem parte do projeto desta solução não são abordados aqui. Entre em contato com o seu representante Apptio para obter insights sobre os outros requisitos de dados tradicionais.

Para obter os detalhes dos requisitos de dados destacados acima, clique aqui:

[![](../../../../../03-media/apptio-tbm-studio/resources/images/icons/aitco.png)](../../resources/AITCO-usage.xlsx "(Abre em uma nova guia ou janela)")

**Ambiente de Trabalho**

À medida que os dados são obtidos para as plataformas de IA, eles passam pela seguinte arquitetura:

![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/wrkbench.png)

Como se pode ver acima, espera-se que seus dados brutos sejam anexados primeiro ao feed das plataformas de IA. A partir daí, ele é exposto em duas tabelas editáveis ("AI Platforms Metadata Enriched" e "AI Platforms Mapping Enriched") que compõem o AI Workbench (que é instalado como parte do componente AI TCO & Usage). O conjunto de dados mestre do AI Platforms acaba sendo usado para expor os dados nas métricas do modelo de IA por meio do objeto modelado do AI Platforms. Veja abaixo uma breve descrição de cada uma das duas tabelas editáveis:

- Plataformas de IA Enriquecimento de dados

  A tabela "AI Platforms Data Enrichment" (Enriquecimento de dados de plataformas de IA) no Workbench permite o enriquecimento de metadados, usados para relatórios, nas plataformas de IA e nos modelos de IA. Todas as atualizações nessa tabela são refletidas diretamente na tabela editável "AI Platforms Metadata Enriched", aprimorando os dados relacionados às plataformas de IA para dar suporte ao rastreamento e aos relatórios de custos precisos. Os dados aprimorados são mapeados posteriormente para as "AI Platforms", passando pela "AI Platforms Mapping ET Transform".

  ![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/dataench.png)
- Plataformas de IA Mapeamento de dados

  Essa tabela no workbench permite o mapeamento dos consumidores das plataformas de IA e dos modelos de IA. Ele espera o mapeamento de uma plataforma de IA ou modelo de IA para uma ou várias ofertas de soluções. Como alternativa, ele pode ser mapeado para uma unidade de negócios ou ID de usuário, caso as plataformas de IA ou os modelos de IA estejam sendo consumidos diretamente pelos usuários finais. A coluna Ponderação de custos é importante, pois permite uma alocação/distribuição ponderada de custos entre os consumidores. Todas as atualizações nessa tabela são refletidas diretamente na tabela editável "AI Platforms Mapping Enrichment", que é mapeada posteriormente para as AI Platforms por meio da "AI Platforms Mapping ET Transform".

  ![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/datamap.png)
- Normalização do tipo de token de IA

  Essa tabela editável permite a categorização e a normalização de diferentes tipos de tokens (provenientes dos dados brutos) nos tipos de tokens simplificados de entrada e saída. Essa categorização ajuda a simplificar as visualizações de análises e relatórios no que se refere à exposição dos detalhes do uso de IA. Todas as atualizações nessa tabela são refletidas diretamente na tabela editável "AI Token Type Normalization" e na tabela "AI Token Type Normalization ET Transform". O último é pesquisado na tabela AI Platforms Master por meio de uma fórmula.

  ![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/typenorm.png)

## Modelos

Quando os requisitos de dados estiverem claros, é importante entender como esses dados são usados nas diferentes métricas do modelo, especialmente em termos de iluminação dos relatórios do usuário final.

O componente AI TCO & Usage instala 13 métricas de modelo, o que pode parecer extenso, mas, na verdade, oferece o máximo de flexibilidade para modelagem e alocações, além de permitir visualizações fáceis de relatórios. Conforme descrito anteriormente na seção de arquitetura, que apresentou o novo modelo de custo de IA e as duas abordagens possíveis, esta seção se aprofundará nos detalhes de todos os 13 modelos, explicando sua finalidade e lógica. Os modelos são categorizados em três grupos:

- 5 Modelos relacionados a custos de IA
- 5 Modelos relacionados ao uso de IA
- 3 Modelos relacionados à contagem de IA

A seção a seguir fornece um resumo detalhado das métricas modeladas, juntamente com a lógica do driver correspondente

|  |  |  |
| --- | --- | --- |
| **Métrica modelada** | **Origem do objeto modelado** | **Lógica do driver** |
| **Custo de IA** | Custo | Fórmula:  If(Cost Source Master Data.Cost Source Model Driver IN ("OPEX - ACTUALS - FIXED", "OPEX - ACTUALS - VARIABLE"), Cost Source Master Data. Valor da IA),0)  Observação: filtrado para despesas com IA, via AI Tablematch |
| Custo da nuvem de IA | Provedor de serviços em nuvem | Métrica:  Custo de IA |
| Custo do fornecedor de IA | Fornecedores | Fórmula:  Se (CSP não for "Sim", Custo de IA, 0) |
| Custo de mão de obra de IA | Trabalhadores | Fórmula:  Custo de IA - Custo do fornecedor de IA |
| AI Outros custos | Outros pools de custos | Métrica:  Custo de IA |
| **Uso de IA** | Plataformas de IA | Coluna:  "Quantidade de uso" das plataformas de IA |
| Consumo de tokens de IA | Plataformas de IA | Fórmula:  If(AI Platforms.Billing Type="Token Usage",AI Platforms.Usage Quantity,0 ) |
| Tokens de entrada de IA | Plataformas de IA | Fórmula:  Se(AI Platforms. Tipo de token normalizado = "Entrada", uso de IA, 0) |
| Tokens de saída de IA | Plataformas de IA | Fórmula:  Se (Plataformas de IA. Tipo de token normalizado = “Saída”, uso de IA, 0) |
| Usuários de soluções de IA | Plataformas de IA | Coluna:  "Total de usuários da solução de IA" das plataformas de IA |
|  | Serviços comerciais | Fórmula:  If( {AI Solution Users to Business Services (AI Platforms- AI Solution Users driver) } =0, {All Business Services.AI Solution Total Users Prep},0) |
| **Contagem de IA** |  |  |
| Contagem de fornecedores de IA | Fornecedores | Fórmula:  If( {AI Cost}!=0,( 1/SumIF(Vendor Master Data.Vendor ID,Vendor Master Data.Vendor ID,1 )),0) |
| Contagem de modelos de IA | Plataformas de IA | Coluna:  "Número de modelos de IA" das plataformas de IA |
| Contagem de soluções de IA | Plataformas de IA | Coluna:  " Contagem de soluções de IA" das plataformas de IA |
| Contagem de soluções de IA | Serviços comerciais | Fórmula:  If(AI Soution Count to Business Services(AI Platforms-AI Solution Count Driver))!=0,0, {All Business Services.AI Solution Count} |

**Modelos de custo de IA (5)**

Custo de IA

Principal métrica de modelo de custo que alimenta todos os relatórios de TCO e uso de IA. Na visualização abaixo (abordagem orientada pela fonte de custos - Razão), espera-se que as despesas de IA sejam identificadas (no nível da fonte de custos), que as alocações existentes (do modelo de custos) sejam reutilizadas, marcando-as para essa nova métrica do modelo de custos de IA e que novas alocações sejam estabelecidas no que se refere às alocações de entrada e saída do novo objeto AI Platforms.

Essa métrica foi criada tendo em mente o seguinte:

- Não perturbar o modelo de custo existente.
- Permitir que seja feita uma ligação entre as Torres de TI e o objeto Plataformas de IA (que contém as despesas de IA)
- Permitir que quaisquer drivers adicionais sejam definidos (relacionados especificamente aos custos de IA) conforme a necessidade do cliente (que deseja expandir ainda mais essa métrica modelada)

![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/aicst.png)

Custo da nuvem de IA

Essa métrica foi criada para permitir que o usuário final compreenda de forma rápida e fácil o driver de custo do AI Cloud mensal e anualmente, como parte da análise detalhada do TCO. Ele simplesmente parece imitar o modelo principal de custo de IA, concentrando-se e começando pelo objeto do provedor de serviços em nuvem. Marque as linhas de alocação ascendente que devem ser consideradas parte do custo do AI Cloud.

![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/cldcst.png)

Custo do fornecedor de IA

Essa métrica foi criada para permitir que o usuário final compreenda de forma rápida e fácil o fator de custo do fornecedor de IA em uma base mensal e anual, como parte da análise detalhada do TCO. Ele simplesmente parece imitar o modelo principal de custo de IA, concentrando-se e partindo do objeto do fornecedor. Observação: ele remove os provedores de serviços de nuvem dessa métrica para garantir que não haja contagem dupla com a métrica AI Cloud Cost.

Marque as linhas de alocação ascendente que devem ser consideradas parte do custo do fornecedor de IA.

![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/vencst.png)

Custo de mão de obra de IA

Essa métrica foi criada para permitir que o usuário final compreenda de forma rápida e fácil o fator de custo de mão de obra de IA mensalmente e no ano, como parte da análise detalhada do TCO. Ele simplesmente parece imitar o modelo principal de Custo de IA, concentrando-se e começando pelo objeto Trabalho. Observação: ele remove o serviço de custo do fornecedor de IA dessa métrica para garantir que não ocorra contagem dupla com as métricas de custo do fornecedor de IA e da nuvem.

Marque as linhas de alocação ascendente que devem ser consideradas parte do custo de mão de obra de IA.

![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/labcst.png)

AI Outros custos

Essa métrica foi criada para permitir que o usuário final compreenda de forma rápida e fácil quaisquer outros fatores de custo de IA mensalmente e no ano, como parte da análise detalhada do TCO. Ele simplesmente parece imitar o modelo principal de custo de IA, concentrando-se e começando pelo objeto Other Cost Pools.

Marque as linhas de alocação ascendente que devem ser consideradas parte do AI Other Cost.

![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/othcst.png)

**Modelos de uso de IA (5)**

Uso de IA

Juntamente com a métrica de modelo de custo de IA, essa métrica de uso de IA é a métrica mais importante, pois também alimenta todos os relatórios de TCO e uso de IA. No entanto, é uma métrica mais simplificada, pois se origina imediatamente no objeto modelado pela AI Platform e, portanto, percorre menos camadas. O driver para essa métrica modelada vem diretamente da coluna Usage Quantity (Quantidade de uso) do conjunto de dados mestre AI Platforms. Ele aponta para o uso das plataformas de IA e/ou modelos de IA. Se os dados de relacionamento estiverem em vigor, espera-se que sejam vinculados aos Serviços de Negócios (com base na Solução de IA = Oferta de Serviço) e espera-se que os dados sejam reutilizados no Service Allocations Direct para destacar potencialmente qualquer consumo direto de Plataformas de IA e/ou Modelo de IA pelas Unidades de Negócios (com base no ID de usuário pertencente a uma determinada Unidade de Negócios).

![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/aius.png)

Consumo de tokens de IA

Essa métrica foi criada como um subconjunto do uso de IA, concentrando-se especificamente nos casos em que o tipo de cobrança = uso de token. Ele é usado no relatório como um KPI principal e para várias exibições de consumo de token. Embora apenas destaquemos o driver na visualização abaixo, espera-se que ele siga a mesma lógica/linhas de alocação que a métrica do modelo de uso de IA.

![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/tokencom.png)

Tokens de entrada de IA

Essa métrica foi criada como um subconjunto do uso de IA e um subconjunto adicional do consumo de tokens de IA, pois se concentra especificamente nos tokens de entrada de IA. Ele é usado predominantemente nas guias de detalhes de uso nos relatórios. Observação: ele depende da tabela AI Token Normalization, na qual diferentes tipos de token parecem ser normalizados em "Input" nesse caso. Espera-se que siga a mesma lógica/linhas de alocação que a métrica do modelo de consumo de tokens de IA.

![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/inptok.png)

Tokens de saída de IA

Essa métrica foi criada como um subconjunto do uso de IA e um subconjunto adicional do consumo de tokens de IA, pois se concentra especificamente nos tokens de saída de IA. Ele é usado predominantemente nas guias de detalhes de uso nos relatórios. Observação: ele depende da tabela AI Token Normalization, na qual diferentes tipos de token parecem ser normalizados em "Output" nessa instância. Espera-se que siga a mesma lógica/linhas de alocação que a métrica do modelo de consumo de tokens de IA.

![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/outtok.png)

Usuários de soluções de IA

Essa métrica aponta para um tipo diferente de uso de IA, ou seja, a adoção de IA. Ele procura informar o número de usuários que estão usando/adotando as soluções de IA. É um KPI de relatório importante e instrumental para os insights mostrados na guia Unidades de negócios no relatório. Para garantir que essa métrica funcione em todos os níveis, incluindo o fatiamento de dados relacionados ao modelo de IA, como o tipo de modelo de IA, ela é obtida em dois níveis. Primeiro no objeto modelado AI Platform (facilitado por meio de uma pesquisa no mestre AI Platforms), em uma segunda instância no objeto modelado Business Services. O driver para o último garante que não haja contagem dupla ao subtrair o driver anterior, definido no objeto modelado da Plataforma de IA. Marque as linhas de alocação ascendente para garantir que a métrica funcione quando os slicers dos serviços comerciais ou das unidades de negócios estiverem sendo aplicados.

![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/solusr.png)

![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/solusr1.png)

**Modelos de contagem de IA (3)**

Contagem de fornecedores de IA

Essa métrica foi criada para garantir a geração de relatórios precisos sobre o número de fornecedores distintos que estão em jogo no que se refere aos custos de IA. Ele é mostrado como um KPI principal no relatório. Ele só seleciona os fornecedores com um custo de IA associado para garantir que nem todos os fornecedores sejam representados. Marque as linhas de alocação ascendente para garantir que a métrica funcione quando os slicers dos serviços comerciais ou das unidades de negócios estiverem sendo aplicados.

![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/vencnt.png)

Contagem de modelos de IA

Essa métrica foi criada para garantir a geração de relatórios precisos sobre o número de modelos de IA distintos que estão em jogo. Ele é mostrado como um KPI principal no relatório. Ele é obtido diretamente de uma fórmula criada no conjunto de dados mestre das plataformas de IA. Marque as linhas de alocação ascendente para garantir que a métrica funcione quando os slicers dos serviços comerciais ou das unidades de negócios estiverem sendo aplicados.

![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/modcnt.png)

Contagem de soluções de IA

Essa métrica foi criada para garantir a geração de relatórios precisos sobre o número de soluções de IA distintas que estão em jogo. Ele é mostrado como um KPI principal no relatório. Para garantir que essa métrica funcione em todos os níveis, incluindo o fatiamento de dados relacionados ao modelo de IA, como o tipo de modelo de IA, ela é obtida em dois níveis. Primeiro no objeto modelado AI Platform (facilitado por meio de uma pesquisa no mestre AI Platforms), em uma segunda instância no objeto modelado Business Services. O driver para o último garante que não haja contagem dupla ao subtrair o driver anterior, definido no objeto modelado da Plataforma de IA. Marque as linhas de alocação ascendente para garantir que a métrica funcione quando os slicers dos serviços comerciais ou das unidades de negócios estiverem sendo aplicados.

![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/solcnt1.png)

![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/solcnt2.png)

## Relatório

O componente AI TCO & Usage Reporting instala os recursos de relatório da solução AI TCO & Usage. Dois relatórios são instalados em uma nova coleção de relatórios de IA.

O principal relatório de TCO e uso de IA permite que as organizações monitorem todo o ciclo de vida dos investimentos em IA, abordando proativamente a expansão da IA por meio do rastreamento do custo total de propriedade (TCO), das tendências de uso, das falhas e das anomalias. O relatório foi desenvolvido para executivos C-suite, líderes de negócios e soluções e equipes de IA e ciência de dados e apresenta quatro guias com insights alinhados para cada uma dessas personas-alvo:

- *Resumo* - Executivos da cúpula
- *Modelos de IA* - equipes de IA e ciência de dados
- *Soluções de IA* - Líderes de soluções (proprietários de serviços)
- *Unidades de negócios* - Líderes de negócios

Além disso, um relatório secundário de modelo de custo de IA está disponível, permitindo que os usuários acompanhem dinamicamente as alocações de custo e uso de IA por meio de visualizações interativas de diagramas Sankey.

Para ver as visualizações e os principais benefícios fornecidos com os relatórios acima, clique [aqui](../reports/ai-tco-report-collection.html).

## Chamadas telefônicas

- Os componentes AI TCO & Usage e AI TCO & Usage Reporting são lançados com o Component Template v120. Portanto, as Configurações de modelo devem ser alteradas para visualizar e fazer download desses dois componentes.
- “isAISolution” é uma nova coluna crucial, criada na tabela All Business Services (por meio da atualização para o respectivo componente). Certifique-se de que o valor esteja definido como "Sim" para as ofertas de serviço que você identificar como soluções de IA. Esse é um pré-requisito para ativar o AI TCO & Usage Reporting.
- Os clientes existentes devem atualizar o componente "CTF - Cost Source", se estiverem usando o método baseado no Razão, e o componente "CT - App Services", conforme descrito acima.
