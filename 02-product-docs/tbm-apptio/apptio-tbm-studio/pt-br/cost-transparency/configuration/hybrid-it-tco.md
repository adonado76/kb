---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Solução de impacto do TCO da TI híbrida"
breadcrumb: []
source_path: "cost-transparency/configuration/hybrid-it-tco.html"
images:
  - "resources/images/ct_images/cg-200.jpg"
  - "resources/images/ct_images/cg-300.jpg"
  - "resources/images/ct_images/cg-sum.jpg"
  - "resources/images/ct_images/cg0200a.jpg"
  - "resources/images/ct_images/config-hyb-1.jpg"
  - "resources/images/ct_images/config-hyb-2.jpg"
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
# Solução de impacto do TCO da TI híbrida

## Visão geral

Antes de configurar a solução Hybrid IT TCO Impact, vamos nos certificar de que sabemos por que estamos fazendo isso e entender os motivos e as metas que nos levaram a esse ponto. Isso garantirá que o processo de configuração seja claro e focado, facilitando a compreensão e o uso eficaz da solução.

![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/config-hyb-1.jpg)

Os seguintes problemas específicos podem ser resolvidos por essa solução.

![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/config-hyb-2.jpg)

A tela a seguir apresenta uma visão geral de alto nível das etapas de configuração. Os requisitos de configuração detalhados para cada etapa são descritos posteriormente no documento.

![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/config-hyb-3.jpg)

## Instalação do componente

A primeira etapa é instalar os três novos componentes que foram criados para a solução Hybrid IT TCO Impact.

![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/hyb-comp.jpg)

Observação: verifique se a versão dos componentes em Configurações do projeto foi definida como Versão 120. Depois de instalado, você pode mudar a versão do componente de volta para o modelo desejado/(anterior).

**Componente do Workbench de aplicativos**

O primeiro componente a ser instalado é o componente *Applications Workbench*.

Esse componente não tem a referência Hybrid IT TCO Impact no nome, mas é essencial para o relatório Hybrid IT TCO Impact, pois permite que os usuários adicionem metadados essenciais do aplicativo. O campo (novo) mais importante desse Workbench é a coluna " **Hosted On** ". Isso deve ser preenchido para todos os aplicativos com o valor de *:On Prem, Private Cloud ou Public Cloud* . Além desse novo campo, ele permite que os usuários enriqueçam os metadados dos aplicativos existentes. Outro campo importante para essa solução é " **Objetivo de investimento do aplicativo** ". Certifique-se de que o valor esteja definido como "Migrar" para os aplicativos sujeitos à migração.

**Componente de impacto do TCO da TI híbrida**

O segundo componente é o *componente de impacto do TCO da TI* híbrida.

Isso cria a estrutura e, portanto, instala todas as tabelas necessárias (editáveis e normais), métricas e modelos associados à solução Hybrid IT TCO Impact. Apresenta o workbench de migração de aplicativos.

Observação: Ele também implementa três relatórios. Eles não se destinam aos usuários finais, mas sim a facilitar a etapa em que o TCO médio, o custo unitário e os volumes de uso do conjunto atual de aplicativos são capturados e "congelados" como um instantâneo no tempo (conforme a Etapa 3 do processo acima). Para obter mais detalhes sobre o conteúdo desse componente, consulte a descrição ao navegar até o componente.

**Componente de relatório de impacto de TCO da TI híbrida**

O terceiro e último componente é o *componente Relatório de impacto de TCO da TI* híbrida.

Isso instala três relatórios de usuário final. Ele vai de um relatório de alto nível, do tipo "nível 100", destinado a executivos de alto escalão, até o "nível 300", em que aplicativos individuais podem ser analisados quanto a benefícios/vantagens financeiras.

Para obter mais detalhes sobre o conteúdo desse componente, consulte a descrição ao navegar até o componente.

## Arquitetura

**IBM Apptio Estrutura**

![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/hyb-frame.jpg)

O diagrama acima apresenta uma visão geral da estrutura IBM Apptio em relação à arquitetura que sustenta a solução Hybrid IT TCO Impact. É possível ver os vários fluxos da Raw Source até os relatórios do usuário final. Os principais itens a serem destacados são os seguintes:

1. Introdução do Application Workbench e do Application Migration Workbench: Conjunto de tabelas editáveis que permitem a edição necessária dos dados existentes e de algumas novas colunas. O mapeamento de aplicativos requer o cancelamento (manual) da anexação dos dados mestre do aplicativo para permitir que a transformação editável (ET Transform) se torne o novo feed (editado) nos dados mestre do aplicativo.
2. Alterações mínimas nos dados mestre dos aplicativos: Além da troca do feed, essa arquitetura tem como objetivo minimizar qualquer impacto direto nos dados mestre dos aplicativos. Algumas colunas novas (e. g.: Hosted On, Migration Strategy etc.) são introduzidos, indiretamente, por meio da etapa Mapped Columns do Applications ET Transform nos dados mestre do aplicativo.
3. Relatórios de usuários não finais essenciais para "congelar" os dados migrados: Conforme mostrado na arquitetura, há três relatórios no lado esquerdo (posição inicial), em oposição ao lado direito (posição final). Isso é intencional, uma vez que eles capturam os dados de migração e são criados de tal forma que esses dados precisam ser trazidos de volta para Apptio, em tabelas para facilitar a comparação entre Antes e Depois.
4. Após a migração dos aplicativos, a nova tabela principal atua como a fonte principal para a maioria das configurações, modelos e relatórios.

**IBM Apptio Alocações de modelos**

![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/fw-2-hyb.jpg)

A estrutura IBM Apptio oferece uma visão geral das novas tabelas, conjuntos de dados mestre etc. que são introduzidos, enquanto o diagrama acima se concentra nas novas métricas e alocações do modelo.

- **Custo pós-migração** : Métrica modelada que é criada como uma métrica modelada "paralela" ao modelo de custo principal, a fim de:
  - Não "perturbar" o modelo de custos existente
  - Permitir que seja feita uma ligação entre o objeto Applications (que contém os novos dados do aplicativo de destino) e o objeto Applications Migrated (que contém os dados do aplicativo antigo e migrado)
  - Permite que quaisquer drivers adicionais sejam definidos (relacionados especificamente aos custos de migração) conforme a necessidade do cliente (que deseja expandir ainda mais essa métrica modelada)

    Observação: se você for um cliente existente, terá que garantir (manualmente) que essa métrica modelada tenha todas as linhas de alocação necessárias marcadas, de acordo com seu modelo de custo existente:
  - Da fonte de custos às torres de recursos de TI
  - De torres de recursos de TI a aplicativos
  - De aplicativos para aplicativos migrados
    - Ponderação por: Ponderação de destino
    - Relação de dados: ID do aplicativo = ID do aplicativo de destino
- **Contagem de aplicativos após a migração** : Métrica modelada que é necessária para capturar a contagem de aplicativos dos novos aplicativos de destino. Isso é necessário para garantir que o cálculo da Trailing 12months Average leve em conta os meses em que os aplicativos estão "em vigor". I.e. em alguns casos, o aplicativo pode existir apenas por, por exemplo, 8 meses. Se esse for o caso, precisamos garantir que os custos sejam divididos por 8 e não por uma contagem "codificada" de 12.

A contagem dos aplicativos antigos/migrados já é detectada quando os relatórios "intermediários" estão sendo criados. Essa métrica modelada é aproveitada posteriormente em algumas das outras métricas e relatórios calculados para garantir que a nova contagem de aplicativos-alvo seja representada corretamente.

Observação: se você for um cliente existente, terá que garantir (manualmente) que essa métrica modelada tenha todas as linhas de alocação necessárias em vigor, conforme o diagrama acima, o que significa:

- Criar um driver "falso" definido como 1 na fonte de custos
- Criar uma alocação da fonte de custos para as torres de TI.
  - Não é necessário peso por ou relacionamento de dados
- Criar uma alocação das torres de TI para os aplicativos migrados
  - Usando o método "Valor padrão
  - Valor definido para a coluna Contagem de aplicativos de destino
- **Custo antes da migração** : Métrica modelada que expõe o valor principal do "Trailing 12months” Avg Monthly TCO extraído dos dados "congelados" dos aplicativos migrados.

Esse modelo é pré-criado, ou seja, não é necessária nenhuma configuração manual.

## Configurações

Esta seção descreve todas as atividades de configuração associadas à iluminação dos relatórios Hybrid IT TCO Impact.

As etapas de 1 a 4 requerem alguma configuração (destacada em amarelo ), enquanto as etapas de 5 a 6 são o resultado final, com foco nos benefícios e insights que os relatórios oferecem.

![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/hyb-s1.jpg)

1. **Etapa 1: aplicativos atuais de TCO**
   - Para iluminar os 3 relatórios de impacto de TCO da TI híbrida (voltados para o usuário final), a etapa 1 é garantir que o custo total de propriedade (TCO), os volumes de uso e os custos unitários estejam em vigor e sendo calculados para o conjunto atual de aplicativos. Usando as alocações e o modelo normais e de melhores práticas do site ATUM.
   - Mesmo antes de qualquer aplicativo ser direcionado para migração, aproveite o novo Applications Workbench para garantir que os valores sejam inseridos pelo menos para:

   Hospedado em: no local, em nuvem privada ou Public Cloud

   Objetivo de investimento em aplicativos: Sustentar, aposentar, migrar, investir

   Ambos devem ser definidos diretamente no nível do aplicativo.

   Observação: para começar a usar a funcionalidade do workbench Aplicativos, será necessário desanexar manualmente os dados do Aplicativo bruto/fonte dos dados mestre de Aplicativos e reanexá-los à tabela de feed Fonte de Aplicativos. Conforme destacado na visualização da arquitetura acima, essa etapa desbloqueia os dados do aplicativo para que fiquem disponíveis para edição.

   Amostra:

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/hyb-s-1.jpg)

   *O exemplo acima mostra o aplicativo ABC atual, vivendo sua "vida normal" com TCO, volumes e custo unitário estabelecidos como ponto de partida fundamental*.
2. **Etapa 2: Capturar dados dos aplicativos de destino**

   Depois que o aplicativo atual estiver configurado para migrar, é essencial começar a capturar metadados relacionados à migração de aplicativos, à medida que eles se tornam disponíveis. É nesse ponto que o novo Application Migration Workbench entra em ação, com três áreas de configuração de informações. Observação: As tabelas abaixo estão expondo apenas os aplicativos que têm o objetivo de investimento em aplicativos definido como "Migrar"

   **Migração de aplicativos** : Essa tabela editável contém os seguintes campos:
   - *Estratégia de migração* (rehost, replatform, repurchase, refactor)

     Campo de texto livre, mas o ideal é que seja definido com um dos valores acima

     Usado nos relatórios como uma opção de Pivô e/ou Filtro.
   - *Status da migração* (Planejamento, Em andamento, Revisando, Concluído)

     Indica principalmente o status operacional da migração.

     Campo de texto livre, mas o ideal é que seja definido com um dos valores acima

     O valor "Done" (Concluído) é usado para indicar que os dados do aplicativo estão prontos para serem "congelados" e, portanto, é usado como um filtro crítico nos relatórios "intermediários". Observação: usado em conjunto com o campo Apptio Migration Status definido como "Done" (Concluído).
   - *Apptio Status da migração* (Planejamento, Em andamento, Revisando, Concluído)

     Indica principalmente o status de alocação Apptio da migração.

     Campo de texto livre, mas o ideal é que seja definido com um dos valores acima

     O valor "Done" (Concluído) é usado para indicar que os dados do aplicativo estão prontos para serem "congelados" e, portanto, é usado como um filtro crítico nos relatórios "intermediários". Observação: usado em conjunto com o campo Status da migração definido como "Concluído".
   - *Mês Ano da migração*

     Indica quando o aplicativo foi oficialmente migrado.

     Campo de texto livre, mas o ideal é que seja definido como e. g.: Oct 2025.

   **Relação de migração de aplicativos** : Essa tabela editável contém os seguintes campos:
   - *ID do aplicativo de destino* : ID do aplicativo do novo aplicativo de destino. Espera-se que seja integrado e exista nos dados mestre dos aplicativos (como de costume). Observação: pode ser mais de 1, ou seja, suporta cenários em que 1 aplicativo atual está sendo migrado para 1,2,3, n número de novos aplicativos.
   - *Ponderação de destino* : No caso de um cenário de 1m, isso permite que uma ponderação seja definida e associada aos m(quaisquer) novos aplicativos. Se não for aplicável ou for deixado em branco, será definido como 1.
   - **ID do grupo de migração de aplicativos** : A ser criado e definido manualmente. No caso de um cenário de 1 milhão de pessoas, isso permitiria ao usuário analisar os dados financeiros antes e depois da comparação por meio das lentes de um grupo agregado, em vez de aplicativos individuais (em que alguns dos dados financeiros podem não fazer sentido para serem visualizados)

   E.g:

   Aplicativo atual/antigo| Aplicativo novo/destino | ID do grupo de migração de aplicativos

   Aplicativo ABC 123 Grupo A

   ABC 456 Grupo de aplicativos A

   **Configurações de migração de aplicativos** :

   Tabela editável que permite ao usuário definir determinadas configurações com relação ao rastreamento de destino e à personalização do texto HTML nos relatórios. A coluna Descrição fornece os detalhes necessários sobre cada uma das configurações.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/hyb-s-2.jpg)

   *Na Etapa 2, o aplicativo ABC foi marcado para migrar, o processo de migração foi iniciado e está em andamento. O aplicativo XYZ foi identificado como o ID do aplicativo de destino.*
3. **Etapa 3: "Congelar" as métricas atuais do aplicativo**

   Em algum momento, o aplicativo atual será considerado migrado. Apptio reconhecerá isso quando AMBAS as colunas Status da migração e Status da migração Apptio tiverem sido atualizadas e definidas como "Done" (Concluído).

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/hyb-3.jpg)

   *Na Etapa 3, o aplicativo ABC foi totalmente migrado. Portanto, é hora de "congelar" e capturar os dados médios do 12months (em azul) com relação a TCO, Volumes e Custo Unitário*.

   Esse é considerado o ponto de disparo quando ocorre o "congelamento" dos dados do aplicativo atual. Esse congelamento ocorrerá da seguinte forma: o conjunto dos três relatórios abaixo selecionará todos os aplicativos no cadastro de aplicativos em que as colunas Status de migração e Status de migração Apptio forem iguais a Concluído. Esses relatórios calcularão a média dos últimos doze meses para as principais métricas de custo total de propriedade (TCO), volumes e custo unitário. As duas últimas métricas serão calculadas apenas no nível de Resumo e, portanto, não se aplicam aos relatórios Pool de custos e Torre de TI.

   Observação: A fórmula que calcula a média garante que ela verifique há quanto tempo o aplicativo existe, verificando a contagem de aplicativos (já que nem todos os aplicativos podem ter existido por 12months ).

   Enquanto a parte a acontece automaticamente, esta parte b exige que o usuário configure um conector de datalink Apptio para Apptio. Esse conector é necessário para obter a saída do relatório, "congelá-la" nesse período de tempo e colocá-la de volta na tabela associada.

   Apptio Datalink Conector: Amostra abaixo. Para obter mais detalhes, consulte a Central de Ajuda.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/hyb-s3.jpg)

   Tabelas "Receptor" associadas

   Aplicativos Migrados Raw

   Aplicativos migrados CP Raw

   Aplicativos migrados TI Raw

   Observação: esse conector destina-se a inserir TODOS os aplicativos migrados referentes a um determinado mês. Nesse sentido, será uma visão cumulativa ao longo do tempo. O mês 1 pode ter 10 solicitações. O mês 2 pode ter 15 solicitações.
4. **Etapa 4: Modelo antigo e novo**

   Depois que a Etapa 3 for concluída, todos os dados necessários "Antes da migração" estarão disponíveis nas três tabelas, conforme descrito acima.

   O conjunto de dados principal de aplicativos migrados é usado e exposto automaticamente à (nova) métrica modelada de custo pré-migração. Nenhuma ação é necessária aqui, pois o driver para essa métrica modelada é criado automaticamente para usar a coluna Avg Monthly TCO. Os outros dois conjuntos de dados não são expostos a nenhuma métrica modelada, pois estão sendo usados apenas no relatório Hybrid IT TCO Impact Analysis (nível 300). Eles têm uma etapa modelada adicionada a eles para que possam ser relatados conforme necessário.

   A principal atividade de configuração nessa etapa está relacionada à (nova) métrica modelada do Cost Post Migration. O componente introduz uma alocação de Aplicativos para Aplicativos Migrados, aproveitando o modelo de Custo existente como o Direcionador. Isso é suficiente para iluminar o relatório Hybrid IT TCO Impact Insights (nível 200). No entanto, para iluminar o relatório Hybrid IT TCO Impact Analysis (nível 300), o modelo de custo pós-migração precisa replicar todas as linhas de alocação da origem do custo até os aplicativos e para os aplicativos migrados. Portanto, é necessário marcar (manualmente) todas essas linhas de alocação de custos existentes com a nova métrica modelada de Custo pós-migração, para que as divisões do pool de custos e da análise da torre de TI funcionem no relatório Hybrid IT TCO Impact Analysis (nível 300).

   A terceira e última nova métrica modelada de contagem de aplicativos pós-migração é necessária para capturar a contagem de aplicativos dos novos aplicativos de destino. Isso é necessário para garantir que o cálculo da Trailing 12months Average leve em conta os meses em que os aplicativos estão "em vigor".

   Observação: se você for um cliente existente, deverá garantir que essa métrica modelada tenha todas as linhas de alocação necessárias em vigor, conforme o diagrama acima, o que significa:
   - Criar um driver "falso" definido como 1 na fonte de custos
   - Criar uma alocação da fonte de custos para as torres de TI.
   - Não é necessário peso por ou relacionamento de dados
   - Criar uma alocação das torres de TI para os aplicativos migrados
   - Usando o método "Valor padrão
   - Valor definido para a coluna Contagem de aplicativos de destino

Por meio das três métricas modeladas acima, a estrutura agora está em vigor para permitir que os resultados da migração Antes x Depois sejam calculados e expostos nos relatórios.

Existem várias métricas calculadas para facilitar isso, sendo que as mais notáveis são aquelas que começam com "TTM..." no nome. Eles estão em vigor para garantir que o TCO, o custo unitário e os dados de volume do aplicativo após a migração estejam igualmente usando os métodos TTM (Average Trailing Twelve Months) para garantir uma comparação homogênea entre os resultados de antes e depois.

![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/hyb-s4.jpg)

*Na Etapa 4, o novo aplicativo XYZ já está pronto e, portanto, está sendo comparado continuamente com os dados "congelados" do aplicativo ABC migrado.*

## Relatório

O componente Hybrid IT TCO Impact Reporting instala 3 relatórios, como parte da coleção de relatórios chamada "Hybrid IT". Você verá uma referência aos níveis 100, 200 e 300, o que implica que o conjunto de relatórios expõe cada vez mais dados e vai um passo além e mais fundo.

**Nível 100: Impacto do TCO da TI híbrida - Resumo**

![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/cg-sum.jpg)

Observação: esse relatório usa principalmente o conjunto de dados Mestre de Aplicativos (como de costume), bem como a nova coluna "Hosted On", introduzida pelo novo componente Applications Workbench. Essa coluna deve ser definida em todos os aplicativos, no nível dos aplicativos. A definição do alvo deve ser feita usando o novo Applications Migrations Workbench.

**Nível 200: Impacto do TCO da TI híbrida - Insights**

![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/cg-200.jpg)

![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/cg0200a.jpg)

Observação: Este relatório usa principalmente o (novo) conjunto de dados de Aplicativos Migrados. Isso requer que os dados de Before Migration sejam trazidos por meio do "método de congelamento", conforme descrito anteriormente.

**Nível 300: impacto do TCO da TI híbrida - análise**

![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/cg-300.jpg)

Observação: Este relatório usa principalmente o (novo) conjunto de dados de Aplicativos Migrados. Isso requer que os dados de Before Migration sejam trazidos por meio do "método de congelamento", conforme descrito anteriormente. Isso também exige que os dados do Pool de custos e dos detalhes da torre de TI estejam fluindo, conforme descrito anteriormente.

## Chamadas telefônicas

Esta última seção tem como objetivo resumir um conjunto de "chamadas" a serem observadas ao configurar e operar essa solução como parte de seus processos mensais de gerenciamento de negócios IBM Apptio.

**Horizonte de tempo de comparação**

O método que está sendo usado para a comparação Antes vs. Depois é o método Trailing 12 meses. Ao revisar os aplicativos migrados ao longo do tempo e compará-los com os novos aplicativos de destino, lembre-se de que, após 12 meses, o aplicativo antigo/migrado não será mais selecionado ou, pelo menos, nenhum custo aparecerá mais para esses aplicativos.

Em outras palavras, neste momento, o horizonte de tempo de comparação (o período de tempo durante o qual você pode fazer uma comparação significativa entre o TCO antes e depois, os volumes e o custo unitário) está definido, de certa forma, em no máximo 12 meses.

**Adicionar outros drivers ao Cost Post Migration**

Aproveite o fato de que essa nova métrica modelada Cost Post Migration é um modelo de custo "paralelo".

Acrescente quaisquer outros fatores financeiros que você acredite que devam ser considerados como parte da visualização do custo pós-migração, caso algum deles não esteja sendo "naturalmente" captado pelo modelo de custo.
