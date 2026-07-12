---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Guia de configuração do impacto do TCO da TI híbrida"
breadcrumb: []
source_path: "cost-transparency/reports/hybrid-it-tco-config.html"
images:
  - "resources/images/ct_images/cg-200.jpg"
  - "resources/images/ct_images/cg-300.jpg"
  - "resources/images/ct_images/cg-sum.jpg"
  - "resources/images/ct_images/cg0200a.jpg"
  - "resources/images/ct_images/config-hyb-3.jpg"
  - "resources/images/ct_images/fw-2-hyb.jpg"
  - "resources/images/ct_images/hyb-3.jpg"
  - "resources/images/ct_images/hyb-comp.jpg"
  - "resources/images/ct_images/hyb-frame.jpg"
  - "resources/images/ct_images/hyb-s-1.jpg"
  - "resources/images/ct_images/hyb-s-2.jpg"
  - "resources/images/ct_images/hyb-s1.jpg"
  - "resources/images/ct_images/hyb-s3.jpg"
  - "resources/images/ct_images/hyb-s4.jpg"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Guia de configuração do impacto do TCO da TI híbrida

A tela a seguir apresenta uma visão geral das etapas de configuração. Os requisitos detalhados de configuração para cada etapa são descritos mais adiante neste documento.

![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/config-hyb-3.jpg)

## Instalação de componentes

O primeiro passo é instalar os três novos componentes que foram criados para a solução Hybrid IT TCO Impact.

![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/hyb-comp.jpg)

Observação: certifique-se de que a versão dos componentes nas configurações do projeto esteja definida como versão 120. Depois de instalado, você pode alterar a versão do componente de volta para o modelo desejado/(anterior).

**Componente Applications Workbench**

O primeiro componente a ser instalado é *o* componente Applications Workbench.

Este componente não tem a referência Hybrid IT TCO Impact no nome, mas é essencial para os relatórios Hybrid IT TCO Impact, pois permite que os usuários adicionem metadados essenciais da aplicação. O campo (novo) mais importante neste Workbench é a coluna “**Hospedado em** ”. Este campo deve ser preenchido para todas as aplicações com o valor: *On Prem, Nuvem Privada ou Public Cloud* . Além desse novo campo, permite aos usuários enriquecer os metadados existentes de suas aplicações. Outro campo importante para essa solução é **o “Objetivo de Investimento** da Aplicação”. Certifique-se de que o valor esteja definido como “Migrar” para os aplicativos sujeitos à migração.

**Componente de impacto do TCO da TI híbrida**

O segundo componente é *o* impacto do TCO da TI híbrida.

Isso cria a estrutura e, portanto, instala todas as tabelas necessárias (tanto editáveis quanto normais), métricas e modelos associados à solução Hybrid IT TCO Impact. Apresenta a plataforma de trabalho para migração de aplicativos.

Observação: também implementa três relatórios. Estes não se destinam aos usuários finais, mas sim a facilitar a etapa em que o TCO médio, o custo unitário e os volumes de uso do conjunto atual de aplicativos são capturados e “congelados” como um instantâneo no tempo (conforme a Etapa 3 do processo acima). Para obter mais detalhes sobre o conteúdo deste componente, consulte a descrição ao navegar até o componente.

**Componente de relatórios de impacto do TCO da TI híbrida**

O terceiro e último componente é *o* componente Relatórios de impacto do TCO de TI híbrida.

Isso instala três relatórios do usuário final. Ele vai desde um relatório de alto nível do tipo “nível 100”, destinado a executivos de alto escalão, até o “nível 300”, onde aplicativos individuais podem ser analisados quanto a benefícios/desvantagens financeiras.

Para obter mais detalhes sobre o conteúdo deste componente, consulte a descrição ao navegar até o componente.

## Arquitetura

**IBM Apptio Estrutura**

![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/hyb-frame.jpg)

O diagrama acima apresenta uma visão geral da estrutura IBM Apptio no que se refere à arquitetura subjacente à solução Hybrid IT TCO Impact. É possível ver os vários fluxos desde a fonte bruta até os relatórios do usuário final. Os principais itens a serem destacados são os seguintes:

1. Introdução do Application Workbench e do Application Migration Workbench: Conjunto de tabelas editáveis que permitem edições necessárias tanto em dados existentes quanto em novas colunas. O mapeamento de aplicativos requer a remoção (manual) dos dados do mestre de aplicativos para permitir que a transformação editável (ET Transform) se torne o novo feed (editado) nos dados do mestre de aplicativos.
2. Alterações mínimas nos dados mestre das aplicações: Além da troca do feed, esta arquitetura tem como objetivo minimizar qualquer impacto direto nos dados mestre das aplicações. Algumas novas colunas (e. g.: Hosted On, Migration Strategy etc.) são introduzidos, indiretamente, através da etapa Colunas mapeadas do Applications ET Transform nos dados mestre da aplicação.
3. Relatórios não destinados ao usuário final essenciais para “congelar” os dados migrados: conforme mostrado na arquitetura, há três relatórios no lado esquerdo (posição inicial), em oposição ao lado direito (posição final). Isso é intencional, uma vez que esses arquivos capturam os dados de migração e são criados de forma que esses dados precisem ser trazidos de volta para Apptio, em tabelas, para facilitar a comparação entre o antes e o depois.
4. Após a migração dos aplicativos, a nova tabela de chaves atua como fonte principal para a maioria das configurações, modelos e relatórios.

**IBM Apptio Alocações de modelos**

![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/fw-2-hyb.jpg)

A estrutura IBM Apptio oferece uma visão geral das novas tabelas, conjuntos de dados principais etc. que serão introduzidos, enquanto o diagrama acima se concentra nas novas métricas e alocações do modelo.

- **Custo pós-migração** : métrica modelada criada como uma métrica modelada “paralela” ao modelo de custo principal, com o objetivo de:
  - Não “perturbar” o modelo de custos existente
  - Permitir que seja feita uma ligação entre o objeto Aplicativos (que contém os novos dados do aplicativo de destino) e o objeto Aplicativos Migrados (que contém os dados antigos do aplicativo migrado)
  - Permite que quaisquer fatores adicionais sejam definidos (relacionados especificamente aos custos de migração) conforme a necessidade do cliente (que deseja expandir ainda mais essa métrica modelada)

    Observação: se você já é um cliente, terá que garantir (manualmente) que essa métrica modelada tenha todas as linhas de alocação necessárias marcadas, de acordo com seu modelo de custo existente:
  - Da fonte de custos às torres de recursos de TI
  - Das torres de recursos de TI às aplicações
  - De aplicativos para aplicativos migrados
    - Peso por: Ponderação alvo
    - Relação de dados: ID do aplicativo = ID do aplicativo de destino
- **Contagem de aplicativos após a migração** : métrica modelada necessária para capturar a contagem de aplicativos novos e de destino. Isso é necessário para garantir que o cálculo da Média Móvel de Desempenho ( 12months ) leve em consideração os meses em que o aplicativo está “em funcionamento”. I.e. em certos casos, o aplicativo pode existir apenas por, por exemplo, 8 meses. Se for esse o caso, precisamos garantir que os custos sejam divididos por 8 e não por uma contagem “fixa” de 12.

A contagem das aplicações antigas/migradas já é obtida quando os relatórios “intermediários” estão sendo criados. Essa métrica modelada é aproveitada posteriormente em algumas das outras métricas e relatórios calculados para garantir que a nova contagem de aplicativos alvo seja representada corretamente.

Observação: se você já é um cliente, terá que garantir (manualmente) que essa métrica modelada tenha todas as linhas de alocação necessárias, conforme o diagrama acima. Isso significa que:

- Crie um driver “falso” definido como 1 na Origem de Custo
- Crie uma alocação da fonte de custos para as torres de TI.
  - Não é necessário peso nem relação de dados
- Crie uma alocação de IT Towers para Aplicativos Migrados
  - Usando o método “Valor padrão”
  - Valor definido na coluna Contagem de Aplicações Alvo
- **Custo pré-migração** : métrica modelada que expõe o valor principal do “ 12months”” médio mensal do TCO obtido a partir dos dados “congelados” para as aplicações migradas.

Este modelo é pré-criado, ou seja, não requer configuração manual.

## Configurações

Esta seção descreve todas as atividades de configuração associadas à ativação dos relatórios de impacto do TCO da TI híbrida.

Os passos 1 a 4 requerem alguma configuração (destacados a amarelo ), enquanto os passos 5 e 6 são o resultado final, focado nos benefícios e insights que os relatórios proporcionam.

![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/hyb-s1.jpg)

1. **Etapa 1: Aplicações atuais do TCO**
   - Para esclarecer os três relatórios de impacto do TCO da TI híbrida (voltados para o usuário final), o primeiro passo é garantir que o custo total de propriedade (TCO), os volumes de uso e os custos unitários estejam definidos e sejam calculados para o conjunto atual de aplicativos. Utilizando as alocações e o modelo normais e recomendados de ATUM.
   - Mesmo antes de qualquer aplicativo ser selecionado para migração, utilize o novo Applications Workbench para garantir que os valores sejam inseridos pelo menos para:

   Hospedado em: Local, nuvem privada ou Public
   Cloud

   Objetivo do investimento da aplicação: Sustentar, Aposentar-se, Migrar, Investir

   Ambos devem ser definidos diretamente no nível do aplicativo.

   Observação: para começar a usar a funcionalidade da área de trabalho Aplicativos, será necessário remover manualmente os dados brutos/de origem do aplicativo dos dados mestre do aplicativo e reinseri-los na tabela de feed de origem do aplicativo. Conforme destacado na visão da arquitetura acima, esta etapa desbloqueia os dados do aplicativo para que fiquem disponíveis para edição.

   Amostra:

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/hyb-s-1.jpg)

   *A amostra acima mostra a aplicação ABC atual, vivendo sua “vida normal” com TCO, volumes e custo unitário estabelecidos como ponto de partida fundamental*.
2. **Passo 2: Capturar os dados dos aplicativos alvo**

   Depois que o aplicativo atual for definido como Migrar, é essencial começar a capturar os metadados relacionados à migração do aplicativo, assim que estiverem disponíveis. É aqui que entra em cena o novo Application Migration Workbench, com três áreas de configuração de informações. Observação: as tabelas abaixo mostram apenas os aplicativos que têm o Objetivo de Investimento do Aplicativo definido como “Migrar”

   **Migração de aplicativos** : esta tabela editável contém os seguintes campos:
   - *Estratégia de migração* (rehost, replataforma, recompra, refatoração)

     Campo de texto livre, mas idealmente deve ser definido com um dos valores acima

     Usado nos relatórios como uma opção de Pivô e/ou Filtro.
   - *Status da migração* (Planejamento, Em andamento, Revisão, Concluído)

     Indica principalmente o estado operacional da migração.

     Campo de texto livre, mas idealmente deve ser definido com um dos valores acima

     O valor “Concluído” é usado para indicar que os dados do aplicativo estão prontos para serem “congelados” e, portanto, é usado como um filtro crítico nos relatórios “intermediários”. Observação: usado em conjunto com o campo Status da migração Apptio definido como “Concluído”.
   - *Apptio Status da migração* (Planejamento, Em andamento, Revisão, Concluído)

     Indica principalmente o status de alocação do Apptio e da migração.

     Campo de texto livre, mas idealmente deve ser definido com um dos valores acima

     O valor “Concluído” é usado para indicar que os dados do aplicativo estão prontos para serem “congelados” e, portanto, é usado como um filtro crítico nos relatórios “intermediários”. Observação: usado em conjunto com o campo Status da migração definido como “Concluído”.
   - *Mês Ano Migrado*

     Indica quando o aplicativo foi oficialmente migrado.

     Campo de texto livre, mas idealmente definido como e. g.: Out 2025.

   **Relação de migração de aplicativos** : esta tabela editável contém os seguintes campos:
   - *ID do aplicativo de destino* : ID do aplicativo novo, de destino. Espera-se que seja incorporado e exista nos dados mestre das aplicações (como de costume). Observação: pode ser mais de 1, ou seja, suporta cenários em que 1 aplicativo atual está sendo migrado para 1, 2, 3, n número de novos aplicativos.
   - *Ponderação da meta* : No caso de um cenário de 1 m, isso permite que uma ponderação seja definida e associada às novas aplicações. Se não for aplicável, deixe em branco, pois será definido como 1.
   - **ID do grupo de migração de aplicativos** : a ser criado e definido manualmente. No caso de um cenário de 1 m, isso permitiria ao usuário analisar os dados financeiros antes e depois da comparação através da lente de um grupo agregado, em oposição a aplicações individuais (onde alguns dos dados financeiros podem não fazer sentido para serem visualizados)

   E.g:

   Aplicativo atual/antigo | Aplicativo novo/alvo | ID do grupo de migração do aplicativo

   ABC 123 App Grupo A

   ABC 456 Grupo de aplicativos A

   **Configurações de migração de aplicativos** :

   Tabela editável que permite ao usuário definir determinadas configurações relacionadas ao rastreamento de metas e personalizar o texto HTML nos relatórios. A coluna Descrição fornece os detalhes necessários sobre cada uma das configurações.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/hyb-s-2.jpg)

   *Na Etapa 2, o aplicativo ABC foi marcado para migração, o processo de migração foi iniciado e está em andamento. O aplicativo XYZ foi identificado como o ID do aplicativo de destino.*
3. **Etapa 3: “Congelar” as métricas atuais do aplicativo**

   Em algum momento, o aplicativo atual será considerado migrado. Apptio confirmará isso quando AMBAS as colunas Status da migração e Status da migração Apptio tiverem sido atualizadas e definidas como “Concluído”.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/hyb-3.jpg)

   *Na Etapa 3, o aplicativo ABC foi totalmente migrado. Portanto, é hora de “congelar” e capturar os dados médios 12months (em azul) com relação ao TCO, volumes e custo* unitário.

   Isso é considerado o ponto de partida para o “congelamento” dos dados do aplicativo atual. Esse congelamento ocorrerá da seguinte forma: o conjunto dos três relatórios abaixo selecionará todas as aplicações nos Dados Mestre de Aplicações em que as colunas Status da Migração e Status da Migração do Apptio estejam iguais a Concluído. Esses relatórios calcularão a média dos últimos doze meses para as principais métricas de custo total de propriedade (TCO), volumes e custo unitário. As duas últimas métricas serão calculadas apenas no nível Resumo e, portanto, não se aplicam aos relatórios Pool de Custos e Torre de TI.

   Observação: a fórmula que calcula a média garante que seja verificado há quanto tempo o aplicativo existe, verificando a contagem de aplicativos (já que nem todos os aplicativos podem existir há um 12months ).

   Enquanto a parte a ocorre automaticamente, a parte b requer que o usuário configure um conector de link de dados Apptio -to- Apptio. Este conector é necessário para obter a saída do relatório, “congelá-la” nesse período e colocá-la de volta na tabela associada.

   Apptio Datalink Conector: Veja o exemplo abaixo. Para mais detalhes, consulte a Central de Ajuda.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/hyb-s3.jpg)

   Tabelas “Recebedor” associadas

   Aplicativos migrados Raw

   Aplicativos migrados CP Raw

   Aplicações migradas TI Raw

   Observação: este conector destina-se a inserir TODAS as aplicações migradas, uma vez que se refere a um determinado mês. Nesse sentido, será uma visão cumulativa ao longo do tempo. O mês 1 pode ter 10 inscrições. O segundo mês pode ter 15 inscrições.
4. **Etapa 4: Modelo antigo e novo**

   Depois de concluir a Etapa 3, todos os dados necessários “antes da migração” estão agora disponíveis nas três tabelas, conforme descrito acima.

   O conjunto de dados principal de Aplicações Migradas é utilizado e automaticamente exposto à (nova) métrica modelada de Custo Pré-Migração. Não é necessária nenhuma ação aqui, pois o driver para essa métrica modelada é criado automaticamente para usar a coluna Custo total de propriedade médio mensal. Os outros dois conjuntos de dados não são expostos a nenhuma métrica modelada, uma vez que são utilizados apenas no relatório Análise do impacto do TCO da TI híbrida (nível 300). Eles têm uma etapa modelada adicionada para que possam ser relatados conforme necessário.

   A atividade de configuração principal nesta etapa está relacionada com a (nova) métrica modelada de Custo Pós-Migração. O componente introduz uma alocação de Aplicativos para Aplicativos Migrados, utilizando o modelo de Custo existente como o Driver. Isso é suficiente para iluminar o relatório Hybrid IT TCO Impact Insights (nível 200). No entanto, para iluminar o relatório Análise do Impacto do TCO da TI Híbrida (nível 300), o modelo de Custo Pós-Migração precisa replicar todas as linhas de alocação desde a Origem do Custo até as Aplicações e nas Aplicações Migradas. Portanto, é necessário marcar (manualmente) todas essas linhas de alocação de custos existentes com a nova métrica modelada de Custo pós-migração, para que as análises detalhadas do pool de custos e da torre de TI funcionem no relatório Análise de impacto do TCO de TI híbrida (nível 300).

   A terceira e última métrica modelada, Contagem de aplicativos após a migração, é necessária para capturar a contagem de aplicativos novos e de destino. Isso é necessário para garantir que o cálculo da Média Móvel de Desempenho ( 12months ) leve em consideração os meses em que o aplicativo está “em funcionamento”.

   Observação: se você já é cliente, deverá garantir que essa métrica modelada tenha todas as linhas de alocação necessárias, conforme o diagrama acima, o que significa:
   - Crie um driver “falso” definido como 1 na Origem de Custo
   - Crie uma alocação da fonte de custos para as torres de TI.
   - Não é necessário peso nem relação de dados
   - Crie uma alocação de IT Towers para Aplicativos Migrados
   - Usando o método “Valor padrão”
   - Valor definido na coluna Contagem de Aplicações Alvo

Por meio das três métricas modeladas acima, a estrutura está agora pronta para permitir que os resultados antes e depois da migração sejam calculados e apresentados nos relatórios.

Várias métricas calculadas estão em vigor para facilitar isso, sendo as mais notáveis aquelas cujo nome começa com “TTM...”. Elas existem para garantir que os dados de TCO, custo unitário e volume para a aplicação após a migração utilizem igualmente os métodos de média dos últimos doze meses (TTM) para garantir uma comparação equitativa entre os resultados antes e depois.

![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/hyb-s4.jpg)

*Na Etapa 4, o novo aplicativo XYZ está pronto e, portanto, sendo comparado continuamente com os dados “congelados” do aplicativo ABC migrado.*

## Relatório

O componente Relatórios de impacto do TCO de TI híbrida instala três relatórios, como parte da coleção de relatórios chamada “TI híbrida”. Verá uma referência aos níveis 100, 200 e 300, o que implica que o conjunto de relatórios expõe cada vez mais dados e vai um passo além e mais a fundo.

**Nível 100: Impacto do TCO da TI híbrida - Resumo**

![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/cg-sum.jpg)

Observação: este relatório utiliza principalmente o conjunto de dados Applications Master (como de costume), bem como a nova coluna “Hosted On” (Hospedado em), introduzida pelo novo componente Applications Workbench. Esta coluna deve ser definida em todas as aplicações, no nível das aplicações. A definição de metas deve ser feita usando o novo Applications Migrations Workbench.

**Nível 200: Impacto do TCO da TI híbrida - Insights**

![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/cg-200.jpg)

![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/cg0200a.jpg)

Observação: este relatório utiliza principalmente o (novo) conjunto de dados de aplicativos migrados. É necessário que os dados anteriores à migração sejam importados através do “método de congelamento”, conforme descrito anteriormente.

**Nível 300: Impacto do TCO da TI híbrida - Análise**

![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/cg-300.jpg)

Observação: este relatório utiliza principalmente o (novo) conjunto de dados de aplicativos migrados. É necessário que os dados anteriores à migração sejam importados através do “método de congelamento”, conforme descrito anteriormente. Também requer que os dados do Pool de Custos e dos Detalhes da Torre de TI estejam fluindo, conforme descrito anteriormente.

## Chamadas

Esta seção final tem como objetivo resumir um conjunto de “alertas” a serem considerados ao configurar e operar esta solução como parte de seus processos mensais de gestão de negócios IBM Apptio.

**Horizonte temporal da comparação**

O método utilizado para a comparação Antes vs. Depois é o método dos últimos 12 meses. Ao analisar as aplicações migradas ao longo do tempo e compará-las com as novas aplicações de destino, tenha em atenção que, após 12 meses, as aplicações antigas/migradas deixarão de ser selecionadas ou, pelo menos, não serão mais apresentados custos para essas aplicações.

Em outras palavras, neste momento, o horizonte temporal da comparação (o período durante o qual é possível fazer uma comparação significativa entre o TCO, os volumes e o custo unitário antes e depois) está definido em, no máximo, 12 meses.

**Adicionar outros controladores ao custo pós-migração**

Aproveite o fato de que essa nova métrica modelada, Custo pós-migração, é um modelo de custo “paralelo”.

Adicione quaisquer outros fatores financeiros que você acredita que devam ser considerados como parte da visão de Custos Pós-Migração, caso algum deles não seja “naturalmente” capturado pelo modelo de Custos.
