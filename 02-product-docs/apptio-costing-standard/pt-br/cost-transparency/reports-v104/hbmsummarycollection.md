---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Relatório resumido da coleta"
breadcrumb:
  - "Costing Standard"
  - "Relatório detalhado"
  - "Layouts da versão anterior"
  - "Relatórios de gestão empresarial híbrida"
source_path: "cost-transparency/reports-v104/hbmsummarycollection.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Relatório resumido da coleta

Use a coleção de relatórios Summary (Resumo) para visualizar o custo, a capacidade e a utilização dos servidores no local e na nuvem pública. Os relatórios permitem que você analise seus gastos, compreenda melhor toda a sua infraestrutura com as principais métricas e entenda as diferenças de custo entre nuvens públicas e privadas. Use essa coleção de relatórios para entender a saúde financeira geral de sua implantação em relação ao plano, com KPIs acionáveis e perspicazes e análises de alto nível. Essas informações são especialmente úteis no desenvolvimento de uma estratégia eficiente de migração para a nuvem.

Esta coleção de relatórios foi projetada para as seguintes funções:

- VP ou diretor de infraestrutura ou TI
- CIO ou CTO

## Exibir a coleção de relatórios

1. Faça login em Apptio.
2. Na página **inicial**, clique em **Hybrid Business Management**.
3. No menu de coleta de relatórios, selecione **Resumo**. O relatório **Deployment** é aberto por padrão.

## Relatório de implantação

Use o relatório de implantação do HBM para entender o custo geral de seus servidores, de modo que você possa comparar o custo de execução de servidores locais versus servidores de nuvem pública.

**DICA** : *a implantação* refere-se ao local de seus servidores no local ou na nuvem pública. As implementações no local podem incluir servidores em nuvem privada, data centers no local, data centers MSP, co-lo, etc.

**Casos de uso** :

- Visualizar os custos de infraestrutura em relação ao planejado
- Veja o equilíbrio dos gastos no local e na nuvem pública
- Acompanhar a estratégia de infraestrutura e o uso de recursos de nuvem
- Rastrear o equilíbrio entre os servidores, o armazenamento e as torres de recursos de TI de rede para determinar se os gastos com infraestrutura estão tendendo conforme o esperado

Este relatório contém os seguintes elementos:

**(1) KPIs** - os KPIs fornecem uma visão de alto nível de seus gastos com infraestrutura. As setas indicam as despesas reais atuais como uma porcentagem acima ou abaixo do planejado, que é exibida como métrica secundária.

- **Custo de infraestrutura YTD** - Esse KPI mostra o gasto geral de infraestrutura YTD, com a porcentagem acima ou abaixo do planejado. As despesas planejadas são mostradas como **Despesas planejadas YTD**.
- **On Prem Cost YTD** - Esse KPI mostra o custo geral do uso do servidor local no acumulado do ano, com a porcentagem acima ou abaixo do planejado. As despesas planejadas são mostradas como **Despesas planejadas no local**.
- **Public Cloud YTD** - Esse KPI mostra o custo geral do uso do seu servidor de nuvem pública YTD, com a porcentagem acima ou abaixo do planejado. Os gastos planejados são mostrados em **Public Cloud Target**.

**(2) Resumo dos custos de infraestrutura** - Use este gráfico para visualizar a tendência geral de gastos com a nuvem pública e a infraestrutura local. Clique na guia **3 Years (3 anos** ) para visualizar a tendência em vários anos.

Perguntas respondidas:

- Meus gastos gerais com infraestrutura estão alinhados com minha estratégia de infraestrutura?
- A tendência das despesas está de acordo com o planejado?

**(3) Public Cloud Deployment (Implantação** ) - Use esse gráfico para visualizar um resumo de 12 meses de gastos com servidores de nuvem pública para o ano atual, divididos pelas torres de recursos de TI de computação, armazenamento e rede. Clique na guia **3 Years (3 anos** ) para visualizar os dados por ano para o ano atual e os dois anos anteriores. A tabela à direita apresenta a porcentagem de mudança entre as despesas reais e o planejado para o período atual.

Perguntas respondidas:

- Como a estratégia de infraestrutura está evoluindo?
- Nosso uso de recursos de nuvem é muito alto?
- Nossa estratégia de migração para a nuvem está funcionando bem?
- Quais recursos (computação/armazenamento/rede) formam a maior parte de nosso uso no local e na nuvem? Está de acordo com o esperado?

**(4) Implantação no local** - use este gráfico para visualizar um resumo de 12 meses das despesas com servidores no local para o ano atual, separadas pelas Torres de recursos de TI de computação, armazenamento e rede. Clique na guia **3 Years (3 anos** ) para visualizar os dados por ano para o ano atual e os dois anos anteriores. A tabela à direita apresenta a porcentagem de mudança entre os gastos reais e o planejado para o período atual.

Perguntas respondidas:

- Como a estratégia de infraestrutura está evoluindo?
- Nosso uso de recursos de nuvem é muito alto?
- Nossa estratégia de migração para a nuvem está funcionando bem?
- Quais recursos (servidor/armazenamento/rede) formam a maior parte de nosso uso local e na nuvem? Está de acordo com o esperado?

## Relatório de domínios

Clique em **Domains (Domínios** ) na guia Report collection (Coleção de relatórios) para abrir o relatório. Use o relatório HBM Domains para entender a distribuição de serviços de nuvem pública e no local em vários domínios. O relatório permite que você veja os gastos em seus domínios de infraestrutura, capacidade e custos unitários.

**DICA** : *Domains* refere-se às Torres de Recursos de TI na taxonomia ATUM : Computação, armazenamento, data centers e rede.

**Casos de uso** :

- Visualizar os custos de infraestrutura por torre de recursos de TI
- Entenda como o custo e a capacidade são distribuídos entre a computação e o armazenamento para diferentes implementações
- Determinar se a capacidade de recursos está corretamente distribuída entre as implementações no local e na nuvem em relação à capacidade e ao custo unitário
- Visão de alto nível dos custos do data center no local

O relatório contém os seguintes elementos:

**(1) KPIs** - Os KPIs deste relatório são os mesmos do relatório de implantação. Consulte o elemento 1 no [relatório de implantação](hbmsummarycollection.html).

**(2) Resumo da torre de infraestrutura** - use este gráfico para ver as tendências de gastos de um ou três anos por domínio (computação, armazenamento, data centers e rede) para servidores locais e na nuvem.

Perguntas respondidas:

- Meus gastos gerais com infraestrutura estão de acordo com o planejado?
- A distribuição das despesas entre os domínios está alinhada com o plano?

**(3) Compute (Computar** ) - Clique em **Compute (Computar** ) para acessar o relatório **Compute Summary (Resumo de computação** ).

- A guia **Custo de computação** mostra a tendência de gastos de um ano com recursos de computação por implementação. A tabela à direita lista os custos do mês atual e a porcentagem de alteração nas despesas desde o mês anterior.
- Clique na guia **Compute Capacity (Capacidade de computação** ) para visualizar a tendência de um ano de horas de instância usadas por implementação. A tabela à direita lista o uso de horas de instância para o mês atual e a porcentagem de alteração no uso desde o mês anterior.
- Clique na guia **Compute Unit Cost (Custo da unidade de computação** ) para visualizar a tendência de um ano do custo de hora da instância por implementação. A tabela à direita lista o custo por hora de instância para o mês atual.

Perguntas respondidas:

- Como os custos e a capacidade da computação são distribuídos em diferentes implementações?
- A métrica de custo unitário comprova ou refuta nossa hipótese de migração para a estratégia de nuvem?
- Temos um gasto alto ou baixo no local ou na nuvem? Por quê?

**(4) Armazenamento** - Clique em **Armazenamento** para acessar o relatório **Resumo de armazenamento**.

- A guia **Custo de armazenamento** mostra a tendência de gastos de um ano com recursos de armazenamento por implementação. A tabela à direita lista os custos do mês atual e a porcentagem de mudança nos gastos desde o mês anterior.
- Clique na guia **Storage Capacity (Capacidade de armazenamento)** para visualizar a capacidade de 1 ano de evolução do espaço endereçável no local e do espaço usado na nuvem pública.
- Clique na guia **Custo unitário de armazenamento** para visualizar o custo unitário de tendência de um ano para o espaço endereçável no local e o espaço usado na nuvem pública.

Perguntas respondidas:

- Como os custos e a capacidade de armazenamento são distribuídos em diferentes implementações?
- A métrica de custo unitário comprova ou refuta nossa hipótese de migração para a estratégia de nuvem?
- Temos um gasto alto ou baixo no local ou na nuvem? Por quê?
- A capacidade de recursos está corretamente distribuída entre o local e a nuvem?

**(5) Data Center (Centro de dados** ) - Clique em **Data Center (Centro de dados** ) para acessar o relatório **Data Center Summary (Resumo do centro de dados** ). Use este gráfico e esta tabela para visualizar a tendência de custo de seus data centers. Essas informações podem ajudá-lo a avaliar as mudanças nos custos no acumulado do ano e o custo de seus data centers por pé quadrado.

Perguntas respondidas:

- Há anomalias no uso de recursos?
- A organização está gastando muito em um desses domínios/recursos? Por quê?

## Relatório de nuvem pública vs. privada

Clique em **Nuvem pública vs. privada** na guia Coleção de relatórios para abrir o relatório. Use o relatório Nuvem Pública vs. Nuvem Privada para entender o custo total de propriedade (TCO) dos serviços de nuvem pública e privada. O relatório permite que você veja a tendência de gastos com a nuvem pública por torre de TI (categoria de serviço) e a tendência de gastos com a nuvem privada por reserva de host. Essas informações são especialmente úteis para analisar a eficiência e a capacidade dos recursos.

**DICA** : *a nuvem privada* é um modelo de implantação de infraestrutura que é executado como nuvem na nuvem, mas gerenciado pela empresa. Ela não tem recursos compartilhados como a nuvem pública.

**Casos de uso** :

- Compare o TCO da nuvem pública com o da nuvem privada
- Entenda seus custos atuais de CPU, RAM e armazenamento
- Acompanhe o uso de recursos ao longo do tempo para informar sua estratégia de migração para a nuvem
- Determinar se os custos estão alinhados com os recursos e a capacidade das implantações

O relatório contém os seguintes elementos:

**(1) KPIs** - Os KPIs deste relatório são os mesmos do relatório de implantação. Consulte o elemento 1 no [relatório de implantação.](hbmsummarycollection.html)

**(2) Public Cloud TCO** - Clique em **Public Cloud TCO** para acessar a página inicial Public Cloud . Use este gráfico para visualizar a tendência de gastos de um ano por domínio e por serviço. A tabela à direita lista o custo de cada serviço para o período atual e a porcentagem de mudança desde o período anterior. Clique na guia **3 Years (3 anos** ) para visualizar os dados por ano para o ano atual e os dois anos anteriores.

Perguntas respondidas:

- Meus gastos gerais com a nuvem pública estão de acordo com o planejado?
- A distribuição dos gastos por categoria de serviço está alinhada com o plano?

**(3) Nuvem privada** - Clique em **Nuvem privada** para acessar o relatório Nuvem privada - VMWare. Use este gráfico para visualizar a tendência de gastos de um ano de todos os servidores de nuvem privada provisionados e a tendência de custo por host de nuvem privada. A tabela à direita lista os custos de CPU, RAM e armazenamento para o período atual. Clique na guia **3 Years (3 anos** ) para visualizar os dados por ano para o ano atual e os dois anos anteriores.

Perguntas respondidas:

- Meus gastos gerais com a nuvem privada estão de acordo com o planejado?
- Em um nível resumido, os recursos estão sendo usados de forma eficiente?
- Qual é o custo da capacidade não utilizada?
- Posso reutilizar essa capacidade antes de adquirir mais recursos para atender às demandas futuras da organização?

## Relatório de variação de infraestrutura

Clique em **Infrastructure Variance (Variação de infraestrutura** ) na guia Report collection (Coleção de relatórios) para abrir o relatório. Use esse relatório para entender os custos reais de infraestrutura em comparação com o orçamento. O relatório fornece várias visualizações de variações de infraestrutura para ajudá-lo a analisar a eficiência e os gastos do orçamento. Essas informações são especialmente úteis para determinar se os gastos com infraestrutura estão alinhados com o orçamento e se o orçamento precisa ser revisado.

**Casos de uso** :

- Comparar os gastos reais com infraestrutura com os gastos previstos
- Entenda seus custos atuais por torre de recursos de TI
- Acompanhar o desvio de despesas para o mês, trimestre e ano atuais

O relatório contém os seguintes elementos:

**(1) KPIs** - Os KPIs deste relatório são os mesmos do relatório de implantação. Consulte o elemento 1 no [relatório de implantação](hbmsummarycollection.html).

**(2) Gastos reais versus gastos pretendidos** - Use este gráfico para visualizar a tendência de um ano do custo real versus o plano de gastos com infraestrutura. O filtro **Deployment** permite que você restrinja os dados a dados locais ou dados de nuvem pública. A tabela **Detalhes** lista os custos por torre de TI por mês.

Perguntas respondidas:

- Qual é a tendência dos meus custos reais de infraestrutura em comparação com os gastos planejados?
- Estou alinhado com o orçamento?
- Devo revisar meu orçamento?

**(3) Variância de gastos reais planejados** - Este gráfico mostra a variação entre os gastos com infraestrutura no acumulado do ano e o planejado, de acordo com a métrica selecionada na lista. As barras vermelhas à esquerda representam custos acima do orçamento. A tabela à direita lista os custos YTD, a meta de gastos e a variação de cada métrica com base em sua seleção da lista. Clique nas guias **Quarter to Date (Trimestre até a data** ) ou **Current Month (Mês atual** ) para alternar entre intervalos de datas.

Perguntas respondidas:

- Qual é a variação entre o gasto planejado e o gasto real?
- Onde está a maior variação?
