---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Relatórios de faturamento no Padrão de Faturamento"
breadcrumb:
  - "Billing"
  - "Trabalhando com relatórios de faturamento"
source_path: "boit/billing/work-bill-reports/billrep-bs.html"
images:
  - "resources/images/boit_images/apprecrep.png"
  - "resources/images/boit_images/apprep.png"
  - "resources/images/boit_images/brsrep.png"
  - "resources/images/boit_images/budvar.png"
  - "resources/images/boit_images/cloudrep.png"
  - "resources/images/boit_images/configsumrep.png"
  - "resources/images/boit_images/consfeedrep.png"
  - "resources/images/boit_images/datafreshrep.png"
  - "resources/images/boit_images/detinv.png"
  - "resources/images/boit_images/detrec.png"
  - "resources/images/boit_images/distrep.png"
  - "resources/images/boit_images/invover.png"
  - "resources/images/boit_images/invrep.png"
  - "resources/images/boit_images/itsprep.png"
  - "resources/images/boit_images/modelrep.png"
  - "resources/images/boit_images/projrec.png"
  - "resources/images/boit_images/projrep.png"
  - "resources/images/boit_images/recanalrep.png"
  - "resources/images/boit_images/recbybus.png"
  - "resources/images/boit_images/sllib.png"
  - "resources/images/boit_images/slqrep.png"
  - "resources/images/boit_images/unitranal.png"
  - "resources/images/boit_images/ussum.png"
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Relatórios de faturamento no Padrão de Faturamento

O Padrão de Faturamento inclui visualizações específicas do domínio, faturas e relatórios resumidos. Os relatórios são agrupados em seções exibidas na página inicial do relatório. A menos que seja indicado o contrário, os relatórios são instalados através do componente “ ““BoIT- Foundation”.

Observação: aplica-se apenas ao padrão de faturamento.

## Proprietário do Negócio

**Relatório resumido de uso**

- Objetivo: fornecer uma visão única e fácil de entender para os executivos sobre o que está sendo consumido e cobrado, como esse uso está mudando ao longo do tempo e o que está impulsionando a mudança em todas as unidades de negócios, incluindo tendências de serviço, atividade da unidade, concentração de cobranças por uma dimensão selecionável (exemplo mostrado: localização) e variação orçamentária.
- Perguntas respondidas:
  - Qual é o custo total do período atual e como ele mudou mês a mês?
  - Qual é a mudança em relação ao período anterior?
  - Qual é a cobrança atual do período, trimestre e acumulado do ano (YTD)?
  - Qual é o custo por departamento, unidade de negócios, localização e centro de custos, e ele está aumentando ou diminuindo?
  - Quais serviços estão crescendo mais rapidamente (em MoM %) e provavelmente impulsionando aumentos nos gastos?
  - Como estão as tendências das cobranças nos últimos 13 períodos por tipo de serviço (entrega, compartilhado, usuário final etc.)?
  - Qual é a variação orçamentária para o mês atual, trimestre ou acumulado no ano, no geral e por tipo de serviço?
  - Quais tipos de serviço são os que mais contribuem para o excedente/déficit orçamentário (treemap e detalhes da variação)?
- Usuários-alvo: Consumidor, Líder Sênior, Proprietário de Serviço ou Produto, Parte Interessada, Analista

![](../../../../../../03-media/apptio-billing/resources/images/boit_images/ussum.png)

Fig. #: Relatório resumido de uso no padrão de faturamento

**Relatório de faturas** (também conhecido como Fatura Mensal)

- Objetivo: Fornecer uma visualização da fatura do período de cobrança que mostre o que foi cobrado em comparação com o orçamento, como estão as tendências das cobranças (mensal e trimestral) e, mais importante, uma explicação baseada nos fatores que motivaram as alterações nas cobranças (serviços novos ou cancelados, alterações de preço, alterações de taxa, alterações de consumo e alterações de alocação).
- Perguntas respondidas:
  - Qual é o valor total cobrado no mês atual e ele aumentou ou diminuiu em relação ao mês anterior?
  - Qual era o orçamento para o mês e estamos acima ou abaixo do orçamento?
  - Quais são os encargos do trimestre atual e como eles se comparam trimestre a trimestre?
  - Qual é o orçamento acumulado no trimestre (QTD) e qual é a variação QTD?
  - Como estão as tendências das despesas anualizadas, despesas acumuladas no ano e orçamento anual ao longo do ano fiscal (tendência de variação)?
  - Algum serviço começou a ser cobrado neste mês ou deixou de ser cobrado neste mês (serviços adicionados e removidos)?
  - Qual foi o impacto das alterações efetivas nos preços?
  - Qual foi o impacto nas cobranças resultante das alterações nas taxas unitárias (alterações nas taxas utilizando as unidades do mês anterior)?
  - Qual foi o impacto das alterações no consumo (alterações unitárias utilizando o preço efetivo do mês anterior)?
  - Qual foi o impacto financeiro das alterações na alocação das ofertas de serviços contínuos?
  - Quais ofertas de serviços específicas contribuíram mais para o aumento ou diminuição, e em que medida?
  - Se alguém perguntar “por que minha conta mudou?”, Quais são as principais categorias de fatores impulsionadores e seus impactos financeiros?
- Usuários-alvo: Consumidor, Líder sênior, Proprietário de serviço ou produto, Parte interessada, Analista, Administrador

![](../../../../../../03-media/apptio-billing/resources/images/boit_images/invrep.png)

Fig. #: Relatório de faturas no Padrão de Faturamento

**Relatório de visão geral das faturas**

- Objetivo: Fornece um resumo de alto nível das faturas para o período e escopo selecionados (exemplo mostrado: Todas as Unidades de Negócio) que destaca os encargos atuais, os totais do trimestre até à data e do ano até à data, mostra onde a fatura se concentra (principais serviços e tipos de serviços ao longo do tempo) e apresenta uma repartição por serviço, incluindo unidades, preço efetivo, unidades planeadas, alteração de encargos e variação orçamental, com um fácil acesso à Fatura Detalhada quando é necessária uma explicação mais aprofundada.
- Perguntas respondidas:
  - Qual é o valor total cobrado no período atual?
  - Quais são os totais de cobrança QTD e cobrança YTD?
  - Quais são os principais serviços por cobrança mensal atual e qual é a sua contribuição?
  - Como estão as tendências das cobranças nos últimos meses por tipo de serviço (entrega, compartilhado, usuário final etc.)?
  - Dentro de um tipo de serviço, quais categorias de serviços e serviços compõem os gastos?
  - Para um determinado serviço, quais são as unidades, a unidade de medida e o preço efetivo que determinam o custo?
  - As unidades planejadas estão presentes e como as unidades reais se comparam (quando preenchidas)?
  - Quais serviços apresentaram a maior variação positiva/negativa em relação ao período anterior (indicador de tendência na tabela)?
  - Qual é o orçamento, a variação orçamentária e a variação percentual por serviço (quando o orçamento é preenchido)?
  - Quais serviços são os que mais contribuem para o excedente/déficit orçamentário?
  - Onde devo perfurar a seguir para explicar “por que isso mudou?” (via Ver fatura detalhada)?
- Usuários-alvo: Consumidor, Líder Sênior, Proprietário de Serviço ou Produto, Parte Interessada, Analista

![](../../../../../../03-media/apptio-billing/resources/images/boit_images/invover.png)

Fig. #: Relatório de visão geral da fatura no padrão de faturamento

**Relatório detalhado de faturas** (também conhecido como Análise Ad Hoc)

- Objetivo: fornecer uma plataforma interativa e ad hoc para faturas que permita aos usuários filtrar e segmentar cobranças entre serviços e hierarquias de unidades de negócios, além de visualizar métricas importantes de faturamento (cobrança, unidades, preço efetivo, cobrança anualizada, contagem de ofertas de serviços e diferenças em relação ao período anterior) para visualizações do mês atual, trimestre, acumulado no ano e anual. É o relatório que você usa para responder “o que exatamente estou pagando, de onde vem esse valor e o que mudou?” com precisão, sem precisar sair do contexto da fatura.
- Perguntas respondidas:
  - Quais são os meus encargos para o escopo selecionado (todas as unidades de negócios, uma unidade de negócios, centro de custos, etc.)? para o mês atual / trimestre / acumulado no ano / anual?
  - Que tipos de serviços, categorias, serviços ou ofertas de serviços compõem a conta e quanto cada um contribui?
  - Para qualquer fatia, quais são as unidades, a unidade de medida e o preço efetivo associados à cobrança?
  - Qual é a taxa anualizada para um serviço ou grupo, com base na taxa de execução do período atual?
  - Quantos serviços estão contribuindo para o total?
  - O que mudou em relação ao período anterior?
  - As unidades mudaram em relação ao período anterior?
  - Quais serviços ou organizações são os maiores impulsionadores da mudança período a período?
  - Como os encargos são divididos por atributos comerciais, como localização, fase do ciclo de vida, processo comercial, capacidade comercial ou criticidade comercial?
  - Como as cobranças diferem quando se alterna entre Unidade de Negócios, Proprietário, Departamento ou Centro de Custos?
  - Se alguém contestar uma fatura, posso isolar a parte exata dos dados que a explica (serviço + organização + atributo + período de tempo)?
- Usuários-alvo: Consumidor, Líder Sênior, Proprietário de Serviço ou Produto, Parte Interessada, Analista

![](../../../../../../03-media/apptio-billing/resources/images/boit_images/detinv.png)

Fig. #: Relatório detalhado de faturas no padrão de faturamento

**Relatório de variação orçamentária**

Observação: instalado por meio do componente “Variação do plano”

- Objetivo: Fornecer um único local para monitorar como as despesas reais estão se comportando em relação ao orçamento e à previsão para o escopo selecionado (exemplo mostrado: Todas as Unidades de Negócios), mostrar a tendência ao longo do ano fiscal e identificar os serviços que estão gerando os maiores excedentes ou déficits para o mês atual, trimestre atual ou ano até o momento.
- Perguntas respondidas:
  - Qual é a variação orçamentária para o período atual e qual é a variação acumulada no ano?
  - Qual é o orçamento mensal e o orçamento acumulado no ano, e como ele se compara aos valores reais?
  - Qual é a cobrança real do mês e qual é a cobrança acumulada no ano?
  - Ao longo do ano fiscal atual, como estão as tendências mensais de cobrança, orçamento comercial e previsão comercial?
  - Estamos tendendo a ficar acima ou abaixo do orçamento, e quando essa diferença começou a aumentar?
  - Quais serviços são os principais impulsionadores da variação (principais serviços acima do orçamento do mês atual)?
  - Para cada serviço, quais são o orçamento, a cobrança, a previsão e a variação orçamentária resultante?
  - Quais serviços apresentam a tendência ascendente/descendente mais clara que possa explicar a variação recorrente?
  - Como as variações mudam ao alternar a lente temporal entre Mês atual, Trimestre atual e Ano até a data?
  - Onde devo me concentrar primeiro para reduzir a variação, com base nos maiores fatores que contribuem para ela?
- Usuários-alvo: Consumidor, Líder Sênior, Proprietário de Serviço ou Produto, Parte Interessada, Analista

![](../../../../../../03-media/apptio-billing/resources/images/boit_images/budvar.png)

Fig. #: Relatório de variação orçamentária no padrão de faturamento

**Relatório de aplicações**

Observação: instalado através do componente “ ““BoIT- Applications”

- Objetivo: fornecer uma visão consolidada das cobranças e do uso no nível do aplicativo para que você possa entender quais aplicativos estão gerando cobranças, como essas cobranças estão se comportando ao longo do tempo e como os gastos são divididos por dimensões comuns do aplicativo (hierarquia de serviços, tipo de aplicativo, ciclo de vida, hierarquia, proprietário do negócio, criticidade do negócio). É essencialmente “a conta, mas através de uma lente de aplicação”, incluindo detalhes detalhados por nome de aplicação.
- Perguntas respondidas:
  - Qual é o custo total relacionado ao aplicativo para o mês atual e como ele mudou MoM?
  - O que são cobrança QTD e cobrança YTD para aplicativos?
  - Quantas aplicações estão no escopo (contagem de aplicações) e qual é a contagem de licenças de aplicações (se preenchida)?
  - Quais domínios ou agrupamentos de aplicativos estão aumentando ou diminuindo ao longo do tempo (visualização de alterações em árvore)?
  - Quais são os principais aplicativos por cobrança e como estão as tendências ao longo do tempo (gráfico das 5 principais tendências)?
  - Quais aplicativos apresentaram os maiores aumentos ou reduções nas cobranças em relação ao período anterior?
  - Para uma aplicação individual, quais são as unidades faturáveis, a unidade de medida e o custo?
  - Quais aplicativos têm as taxas mais altas e quais estão mudando mais?
  - Como as cobranças diferem por tipo de aplicação, estágio do ciclo de vida, criticidade do negócio ou hierarquia da aplicação?
  - Quais serviços (da hierarquia de serviços) estão associados a cada aplicação e quais são os seus custos?
  - Onde temos candidatos potenciais para revisão com base em combinações como alto custo + baixa criticidade ou custo crescente + fim do ciclo de vida?
- Usuários-alvo: Consumidor, Líder Sênior, Proprietário de Serviço ou Produto, Parte Interessada, Analista

![](../../../../../../03-media/apptio-billing/resources/images/boit_images/apprep.png)

Fig. #: Relatório de aplicações no padrão de faturamento

**Relatório sobre a nuvem**

Observação: instalado através do componente “ ““BoIT- Cloud”

- Objetivo: fornecer uma visão focada na nuvem do faturamento que compare os custos brutos do provedor de nuvem com o custo total para fornecer serviços em nuvem e, em seguida, divida esses gastos por serviço, itens de linha de provedor/produto e dimensões comerciais importantes (hierarquia de serviços, localização, criticidade comercial, ciclo de vida). Ele foi criado para ajudar você a ver quanto custa a nuvem, o que você está cobrando/mostrando e o que está impulsionando as mudanças ao longo do tempo.
- Perguntas respondidas:
  - Qual é a taxa de nuvem atual e qual é a tendência ao longo do tempo?
  - Qual é a proporção entre o custo do provedor e o custo total da prestação do serviço (aumento devido a alocações, serviços compartilhados, despesas gerais etc.)?
  - Quais serviços em nuvem estão gerando mais custos no momento (detalhamento dos custos por serviço)?
  - Como a diferença entre o preço do provedor e o preço total mudou nos últimos períodos?
  - Que tipos de serviço (Entrega, Compartilhado, Usuário Final, etc.) contêm as taxas da nuvem, e quais são suas taxas e alterações?
  - Para cada serviço em nuvem, quais são as unidades associadas, a unidade de medida, o preço efetivo e a alteração na cobrança?
  - Onde se concentram os custos da nuvem quando divididos por:
    - Hierarquia de serviços
    - Local
    - Criticidade dos negócios
    - Fase do ciclo de vida
  - Quais provedores (por exemplo, AWS, Azure, GCP, etc., dependendo dos seus dados) estão a impulsionar os encargos?
  - Quais produtos/itens (computação, armazenamento, serviços de banco de dados, itens de SaaS, etc.) estão a impulsionar os custos dos prestadores?
  - Quais itens do fornecedor apresentam a maior variação de unidades ou movimento de cobrança ao longo do período?
- Usuários-alvo: Consumidor, Líder Sênior, Proprietário de Serviço ou Produto, Parte Interessada, Analista

![](../../../../../../03-media/apptio-billing/resources/images/boit_images/cloudrep.png)

Fig. #: Relatório de nuvem no Padrão de Faturamento

**Relatório de projetos**

Observação: instalado através do componente “ ““BoIT- Projects”

- Objetivo: fornecer uma visão centrada no projeto do faturamento para que você possa ver quais projetos estão gerando despesas, como os gastos do projeto estão se comportando ao longo do tempo e como esses gastos são divididos por dimensões comuns do projeto (hierarquia de serviços, tipo de projeto, ciclo de vida, iniciativa de negócios, tipo de gasto). É basicamente “a conta, mas através de uma perspectiva de portfólio de projetos”, com detalhes suficientes para apoiar revisões de portfólio e conversas sobre cobranças.
- Perguntas respondidas:
  - Qual é o custo total relacionado ao projeto para o mês atual e como ele mudou MoM?
  - O que são cobrança QTD e cobrança YTD para projetos?
  - Quantos projetos estão dentro do escopo (e quantos estão ativos, se houver)?
  - Qual é a tendência geral dos gastos com o projeto nos últimos períodos?
  - Quais projetos têm os custos mais elevados no período atual?
  - Quais projetos apresentam a maior variação de despesas entre os períodos (em dólares e porcentagem)?
  - Como é a tendência recente para cada projeto (gráfico de tendência de 6 períodos)?
  - Como os custos são acumulados por portfólio de projetos/programa/iniciativa de negócios?
  - Quais gerentes de projeto estão associados às taxas mais altas ou ao crescimento mais rápido?
  - Como os custos dos projetos variam de acordo com o tipo de projeto, o ciclo de vida do projeto ou o tipo de despesa?
  - Quais serviços (da hierarquia de serviços comerciais) estão vinculados a cobranças de projetos e quais são essas cobranças?
- Usuários-alvo: Consumidor, Líder Sênior, Proprietário de Serviço ou Produto, Parte Interessada, Analista

![](../../../../../../03-media/apptio-billing/resources/images/boit_images/projrep.png)

Fig. #: Relatório de projetos no padrão de faturamento

**Relatório da Biblioteca de Serviços**

- Objetivo: Fornecer um catálogo confiável e filtrado de serviços faturáveis/showback e ofertas de serviços, incluindo seus proprietários (gerente de serviços), preços, unidade de medida e principais atributos de classificação (hierarquia de serviços, metodologia de preços, capacidade de negócios, criticidade de negócios, processo de negócios, descrições, datas de entrada em serviço e retirada de serviço). Este é o lugar onde as pessoas vão para responder: “quais serviços oferecemos, quem os possui e como são precificados?”
- Perguntas respondidas:
  - Que serviços e ofertas de serviços existem no catálogo de faturamento?
  - Como os serviços são organizados na Hierarquia da Biblioteca de Serviços (tipo de serviço, categoria, etc.)?
  - Quem é o gerente de serviço (proprietário) de cada serviço ou oferta?
  - Qual é o preço de cada serviço oferecido?
  - Qual é a unidade de medida para cada oferta de serviço (como é cobrada)?
  - Quais serviços utilizam qual metodologia de precificação (se preenchida)?
  - Quais serviços estão mapeados para uma determinada capacidade ou processo de negócios?
  - Quais serviços são marcados com um determinado nível de criticidade comercial?
  - Qual é a descrição do serviço (e outros campos descritivos) para cada serviço/oferta?
  - Quais serviços estão em funcionamento e quais foram descontinuados ou estão programados para serem descontinuados (em funcionamento, datas de descontinuação)?
  - Existem serviços com dados ausentes ou suspeitos (sem proprietário, preço $0, sem UoM, sem descrições), para que possamos corrigir o catálogo?
- Usuários-alvo: Consumidor, Líder sênior, Proprietário de serviço ou produto, Parte interessada, Analista, Administrador

![](../../../../../../03-media/apptio-billing/resources/images/boit_images/sllib.png)

Fig. #: Relatório da biblioteca de serviços no padrão de faturamento

## Gerente de Relacionamento Comercial

**Relatório resumido das relações comerciais**

- Objetivo: Fornecer uma visão única, em estilo executivo, que reúna o que foi cobrado, quanto custou para entregar e quanto foi recuperado dos consumidores, destacando então onde a recuperação está acima ou abaixo por serviço. É a questão: “estamos recuperando o que gastamos e quais serviços são os culpados?” painel, com tendências, principais movimentações e detalhes detalhados.
- Perguntas respondidas:
  - Qual é o custo total do período atual e como ele mudou MoM?
  - Qual é o custo para prestar esses serviços (atual e acumulado no ano)?
  - O que é a variação de recuperação (custo menos despesas), atual e acumulada no ano?
  - Temos um orçamento comercial para este escopo e qual é o orçamento acumulado no ano (se preenchido)?
  - Quais serviços estão crescendo mais rapidamente MoM em termos percentuais?
  - Como estão as tendências das cobranças nos últimos 13 períodos por tipo de serviço?
  - Quais serviços estão apresentando menor recuperação (principais serviços abaixo da média, variação negativa na recuperação)?
  - Quais serviços estão recuperando mais (principais serviços acima, variação positiva de recuperação)?
  - Para um determinado serviço, quais são a cobrança, o custo, a variação de recuperação e o preço efetivo?
  - Para um determinado serviço, quais são as unidades faturáveis, a unidade de medida e o custo por unidade (se preenchido)?
  - Onde estão as maiores variações orçamentárias (mês atual/trimestre atual/acumulado no ano) e quais tipos de serviço as impulsionam?
  - O problema é principalmente de preços/recuperação (diferença entre cobrança e custo) ou principalmente de gestão orçamentária (variação orçamentária)?
- Usuários-alvo: Líder sênior, analista, administrador

![](../../../../../../03-media/apptio-billing/resources/images/boit_images/brsrep.png)

Fig. #: Relatório resumido das relações comerciais no padrão de faturamento

**Relatório de recuperação por empresa** (também conhecido como Recuperação de serviços por empresa)

Observação: instalado através do componente “ ““BoIT- Cost Variance” (Controle de custos e variação de custos)

- Objetivo: fornecer uma visão focada na unidade de negócios do desempenho da recuperação, comparando encargos com custos (e, opcionalmente, orçamento/previsão) em um nível organizacional selecionável (unidade de negócios, proprietário, departamento, centro de custos), destacando onde há recuperação excessiva ou insuficiente e projetando expectativas de ajuste (crédito/débito) para o restante do ano com base nos padrões acumulados no ano. É a questão de “quem está pagando versus quem está custando, e qual será o ajuste final?” em seu relatório.
- Perguntas respondidas:
  - No nível organizacional selecionado (BU/Proprietário/Departamento/Centro de Custos), onde estamos recuperando em excesso ou em falta este mês (mapa de variação)?
  - Para uma determinada fatia da organização, quais são os encargos em comparação com os custos (ou encargos acumulados no ano em comparação com custos acumulados no ano)?
  - Quais organizações são as que mais contribuem para a variação geral da recuperação (positiva ou negativa)?
  - Como é a variação da recuperação no acumulado do ano por nível organizacional selecionado (linha de tendência ao longo do ano)?
  - Qual é a porcentagem recuperada para cada organização (quanto do custo está sendo recuperado por meio de cobranças)?
  - Como os resultados mudam quando a métrica principal é Encargo vs. Custo vs. Encargo acumulado no ano vs. Custo acumulado no ano, e a métrica de comparação é Custo/Orçamento/Previsão (e suas versões acumuladas no ano)?
  - Com base no comportamento acumulado no ano, qual é a projeção de despesas e custos para o ano inteiro por organização?
  - Qual é o crédito ou débito de ajuste esperado por organização (custo projetado menos despesa projetada)?
  - Quais organizações têm um comportamento mensal consistente (boas candidatas para o método de projeção) em comparação com aquelas voláteis que podem precisar de revisão manual?
  - Como os resultados da recuperação mudam quando se filtra por hierarquia de serviços (por exemplo, apenas Serviços de Entrega ou apenas Serviços em Nuvem)?
  - Onde devo aprofundar minha análise (link para a Visualização detalhada da transparência de custos)?
- Usuários-alvo: Líder sênior, analista, administrador

![](../../../../../../03-media/apptio-billing/resources/images/boit_images/recbybus.png)

Fig. #: Relatório de recuperação por negócio no padrão de faturamento

**Relatório detalhado de recuperação** (também conhecido como Recuperação de serviço ad hoc)

- Objetivo: Fornecer uma plataforma interativa e ad hoc para analisar a recuperação, permitindo que os usuários filtrem e organizem cobranças, custos, orçamentos, previsões, unidades e variações de recuperação em todas as camadas da hierarquia de serviços e níveis da hierarquia da unidade de negócios, para várias perspectivas temporais (visualizações do mês atual, trimestre, acumulado no ano, anual e multipériodo). É o relatório que você usa quando alguém pergunta: “Estamos recuperando nossos custos? Onde exatamente estamos perdendo e o que está causando isso?”
- Perguntas respondidas:
  - Para o escopo selecionado, quais são os encargos versus custos e qual é a variação de recuperação resultante?
  - Quais serviços (por tipo, categoria, nome, oferta) são os principais fatores que levam à sub-recuperação ou super-recuperação?
  - Em que nível organizacional (unidade de negócios, proprietário, departamento, centro de custos) estamos recuperando menos ou mais do que o esperado, e em que proporção?
  - Qual é a porcentagem recuperada implícita pela relação entre cobrança e custo para uma determinada fatia (cobrança dividida pelo custo)?
  - Como os resultados da recuperação mudam quando filtrados por atributos como criticidade do negócio, capacidade do negócio, processo de negócio, estágio do ciclo de vida ou unidade de medida (quando preenchida)?
  - Para cada fatia, quais são as unidades e as unidades faturáveis planejadas, e elas apresentam uma tendência que explique as lacunas de recuperação?
  - Como o orçamento e a previsão se comparam aos valores reais para a mesma fatia (e qual é a variação do orçamento da empresa)?
  - Como é a recuperação ao longo do tempo: mês atual vs. trimestre atual vs. acumulado no ano, ou ao longo dos meses (ano) / trimestres (ano)?
  - Se uma unidade de negócios contestar a recuperação ou o ajuste, posso isolar a combinação exata de serviço + organização + atributo + tempo que explica a variação?
- Usuários-alvo: Líder sênior, analista, administrador

![](../../../../../../03-media/apptio-billing/resources/images/boit_images/detrec.png)

Fig. #: Relatório detalhado de recuperação no padrão de faturamento

**Relatório de distribuição** (também conhecido como Gerenciar e enviar faturas)\*

- Objetivo: Fornecer um console operacional para distribuir faturas por e-mail para o período de faturamento selecionado, mostrando quem receberá cada fatura, a mensagem pré-criada que será enviada e o status do envio. É basicamente a parte do processo de faturamento mensal que consiste em “apertar o botão, comprovar que foi enviado e reenviar, se necessário”.
- Perguntas respondidas:
  - Quais faturas estão na fila para serem enviadas por e-mail neste período de faturamento (por unidade de negócios, departamento, localização etc.)?
  - Para quem cada fatura está sendo enviada (endereço de e-mail do destinatário)?
  - Que mensagem será incluída no e-mail para cada fatura?
  - Quais faturas não foram enviadas e quais foram enviadas (acompanhamento do status)?
  - Pode indicar operacionalmente: o que ainda está pendente se eu ocultar o que foi enviado e me concentrar no que resta.
  - Posso encontrar rapidamente um item específico de distribuição de fatura (pesquisa)?
  - Posso enviar todos os e-mails de uma vez ou enviá-los seletivamente (por meio dos controles de ação)?
  - Após o envio, quais destinatários posso comprovar que receberam uma tentativa de envio do sistema (por meio do status)?
- Orientação adicional:
  - As pessoas que podem receber uma fatura são inseridas na tabela Lista de destinatários de faturas. Considere manter a lista em um arquivo Excel e fazer o upload conforme necessário.
  - Para incluir uma mensagem global, cabeçalho e rodapé para todas as faturas, adicione uma entrada nos seguintes campos na tabela Mensagens de Fatura por E-mail:
    - Mensagem global (exibida na parte superior de cada fatura, além de qualquer cabeçalho)
    - Mensagem padrão do cabeçalho (exibida na parte superior de cada fatura se o campo com o mesmo nome não estiver definido na tabela Lista de faturas do destinatário)
    - Mensagem padrão no rodapé (exibida na parte superior de todas as faturas se o campo com o mesmo nome não estiver definido na tabela Lista de faturas do destinatário).
- Usuários-alvo: Administrador, Analista

![](../../../../../../03-media/apptio-billing/resources/images/boit_images/distrep.png)

Fig. #: Relatório de distribuição no padrão de faturamento

## Provedor de serviços

**Relatório resumido do provedor de serviços de TI**

- Objetivo: Fornecer uma visão do provedor de serviços sobre o faturamento que resuma cobranças, custos, orçamento e variação de recuperação em todo o portfólio de serviços (a perspectiva de “TI como provedor”), destaque serviços em alta e os principais impulsionadores e revele onde os serviços estão recuperando acima ou abaixo do esperado e acima/abaixo do orçamento nos níveis de serviço, categoria e oferta.
- Perguntas respondidas:
  - Qual é o custo total de todos os serviços neste período e como ele mudou MoM?
  - Qual é o custo total para prestar todos os serviços (atual e acumulado no ano)?
  - O que é a variação total de recuperação (custo menos despesas), atual e acumulada no ano?
  - Qual é o orçamento total (e o orçamento acumulado no ano) e estamos acima ou abaixo do orçamento (se preenchido)?
  - Quais serviços estão crescendo mais rapidamente MoM em termos percentuais?
  - Como estão as tendências das cobranças nos últimos 13 períodos por tipo de serviço (entrega, compartilhado, usuário final etc.)?
  - Quais serviços são os maiores fatores de sub-recuperação (principais serviços abaixo)?
  - Quais serviços são os maiores impulsionadores da recuperação excessiva (principais serviços acima)?
  - Para cada serviço em detalhes, quais são as unidades faturáveis, o preço efetivo, o custo por unidade, a cobrança, o custo e a variação de recuperação?
  - Quais tipos/categorias/ofertas de serviços estão causando variações entre os custos e o orçamento e entre os custos e o orçamento (árvore de dados + tabela)?
  - A questão da recuperação é motivada pelo custo (aumento dos custos) ou pela cobrança/preços (cobrança que não acompanha os custos)?
- Usuários-alvo: Proprietário do serviço ou produto, parte interessada, líder sênior, analista, administrador

![](../../../../../../03-media/apptio-billing/resources/images/boit_images/itsprep.png)

Fig. #: Relatório resumido do provedor de serviços de TI no padrão de faturamento

**Relatório de análise de recuperação** (também conhecido como análise de recuperação de serviço)

Observação: instalado através do componente “ ““BoIT- Cost Variance” (Controle de custos e variação de custos)

- Objetivo: fornecer uma visão focada na recuperação da saúde do portfólio de serviços, mostrando como as cobranças se comparam aos custos (e, opcionalmente, ao orçamento/previsão), como está a tendência da variação da recuperação (mês atual vs. acumulado no ano fiscal), onde a recuperação está concentrada por unidade de negócios e quanto da conta é influenciado por ajustes. É o painel para responder: “Estamos recuperando o que gastamos, onde estamos errando e a situação está melhorando ou piorando?”
- Perguntas respondidas:
  - Quais são os totais atuais para Encargo, Custo, Orçamento e Variação de Recuperação (e seus valores acumulados no ano)?
  - Estamos recuperando em excesso ou em falta no geral, e em que medida?
  - Como está a tendência da variação da recuperação ao longo do ano fiscal, para o mês atual e no acumulado do ano?
  - Quais serviços estão crescendo mais rapidamente em termos percentuais ( MoM ) (alerta precoce para pressão de recuperação)?
  - Onde está concentrada a recuperação por unidade de negócios (custo do mês atual vs. mapa de árvore de custos)?
  - Quais unidades de negócios geram mais custos e quais geram mais variação na recuperação (tabela com % do custo)?
  - No nível dos serviços, quais ofertas de serviços têm o custo mais alto e como o orçamento/previsão se comparam (tabela de detalhes de recuperação de serviços)?
  - Quais serviços têm os maiores ajustes e qual a proporção do custo total que é determinada por esses ajustes?
  - Se os ajustes estão a impulsionar a variação da recuperação, quais os serviços que devem ser revistos em primeiro lugar no que diz respeito à política de preços/ajustes?
  - Onde devo procurar para obter um rastreamento mais detalhado dos custos (link para a Visualização detalhada da transparência dos custos)?
- Usuários-alvo: Proprietário do serviço ou produto, parte interessada, líder sênior, analista, administrador

![](../../../../../../03-media/apptio-billing/resources/images/boit_images/recanalrep.png)

Fig. #: Relatório de análise de recuperação no padrão de faturamento

**Análise de taxa unitária reportNotice: Instalado através do componente “ ““BoIT- Units”**

- Objetivo: fornecer uma visão da cobrança por unidade de medida que acompanha o custo por unidade em comparação com a cobrança por unidade ao longo do tempo, para que você possa avaliar a economia por unidade, a estabilidade das taxas e o desempenho de recuperação para as principais unidades de consumo (contas, caixas de correio, dispositivos, desktops etc.). Ajuda a responder se suas taxas unitárias têm preços adequados, estão variando ou criando recuperação excessiva/insuficiente, e vincula essas taxas unitárias ao orçamento, à previsão e às unidades planejadas.
- Perguntas respondidas:
  - Para uma unidade de medida selecionada, como o custo por unidade e a cobrança por unidade evoluíram ao longo do tempo?
  - A diferença entre o custo por unidade e o preço por unidade está aumentando ou diminuindo (pressão de recuperação)?
  - Qual é o custo unitário médio atual e a tendência do custo unitário é de alta ou de baixa?
  - Quais unidades de medida têm o maior custo por unidade ou a maior cobrança por unidade neste momento?
  - Para cada unidade de medida, quais são as unidades faturáveis e como elas se comparam às unidades faturáveis planejadas?
  - Qual é a variação de recuperação por unidade (recuperação acima/abaixo por unidade) por unidade de medida?
  - Qual é o orçamento por unidade e a previsão por unidade, e como eles se comparam ao custo e ao custo real por unidade?
  - Quais unidades estão apresentando alterações anormais mês a mês que sugerem uma atualização de preços, alteração de alocação ou problema de dados?
  - A tarifa de um serviço específico cobrado por unidade (como “Conta de usuário” ou “Caixa postal”) deve ser ajustada com base na economia unitária sustentada?
- Usuários-alvo: Proprietário do serviço ou produto, parte interessada, líder sênior, analista, administrador

![](../../../../../../03-media/apptio-billing/resources/images/boit_images/unitranal.png)

Fig. #: Relatório de análise de taxa unitária no padrão de faturamento

**Relatório de recuperação de aplicativos**

Observação: instalado através do componente “ ““BoIT- Applications”

- Objetivo: fornecer uma visão de recuperação centrada em aplicativos que compare os custos com os encargos dos aplicativos (e seus serviços relacionados), destaque as tendências de variação da recuperação ao longo do tempo e revele os aplicativos que estão causando recuperação excessiva ou insuficiente. Foi concebido para responder às seguintes perguntas: “Estamos a recuperar o custo de fornecer/operar esta aplicação e o que está a mudar?” conversas, com filtros para atributos e proprietários de aplicativos e um link de detalhamento para uma visualização detalhada dos custos.
- Perguntas respondidas:
  - Qual é o custo total da inscrição para o período atual e como ele mudou MoM?
  - O que são cobrança QTD e cobrança YTD para aplicativos?
  - Qual é a variação orçamentária (atual e acumulada no ano) para despesas com inscrições (quando o orçamento é preenchido)?
  - Quais aplicativos são os que mais contribuem para a variação mensal de recuperação (os 5 principais + gráfico de tendências acima/abaixo)?
  - A recuperação de aplicativos está melhorando ou piorando com o tempo, e quais aplicativos impulsionam essa tendência?
  - Para uma aplicação específica (ou fatia de aplicativo), quais são as unidades faturáveis e a unidade de medida que sustentam a cobrança?
  - Para cada aplicação, quais são o custo, a variação de custo, a cobrança, a variação de cobrança e a variação de recuperação resultante?
  - Quais aplicações mostram um aumento de custos sem uma cobrança correspondente, indicando uma recuperação insuficiente emergente?
  - Como a recuperação varia de acordo com o proprietário do negócio da aplicação (quem é o responsável pelo problema de recuperação)?
  - Como os resultados mudam quando filtrados por tipo de aplicação, ciclo de vida, hierarquia ou criticidade do negócio?
  - Quais serviços estão vinculados a cada aplicativo e como eles influenciam o resultado da recuperação do aplicativo?
  - Onde devo aprofundar para validar as alocações e os fatores de custo (link para a Visualização detalhada da transparência de custos)?
- Usuários-alvo: Proprietário do serviço ou produto, parte interessada, líder sênior, analista, administrador

![](../../../../../../03-media/apptio-billing/resources/images/boit_images/apprecrep.png)

Fig. #: Relatório de recuperação de aplicações no padrão de faturamento

**Relatório de recuperação na nuvem**

Observação: instalado através do componente “ ““BoIT- Cloud”

- Objetivo: fornecer uma visão específica da recuperação e transparência na nuvem que permite analisar as taxas de consumo do provedor de nuvem pública (e a recuperação relacionada) por dimensões-chave da nuvem, como provedor, produto, localização, tipo de instância e hierarquia de serviços, com a capacidade de analisar tendências e detalhar as taxas ao longo do tempo, além de inspecionar os detalhes subjacentes do estilo de item de linha.
- Perguntas respondidas:
  - Qual consumo do provedor de nuvem está incluído no escopo para o período e a organização selecionados (por meio da Hierarquia da Unidade de Negócios)?
  - Como as cobranças da nuvem são divididas por uma dimensão selecionada (por exemplo, localização, provedor, produto ou tipo de instância)?
  - Como as taxas para a avaria selecionada variam ao longo do tempo (comparação de taxas ao longo do tempo)?
  - Quais combinações específicas de localização + produto + fornecedor + tipo + item estão gerando cobranças?
  - Existem fatores inesperados que geram custos “novos” ou “elevados” na nuvem quando você altera os filtros (provedor/produto/tipo de instância)?
  - Como as cobranças da nuvem mudam ao filtrar para um agrupamento específico da hierarquia de serviços em nuvem?
  - Quais produtos ou serviços em nuvem parecem não ter consumo/cobranças (sinal de qualidade dos dados quando os gráficos mostram zeros)?
  - Qual é a descrição detalhada dos itens da linha do provedor por trás das visualizações resumidas dos encargos?
- Usuários-alvo: Proprietário do serviço ou produto, parte interessada, líder sênior, analista, administrador

**Relatório de recuperação de projetos**

Observação: instalado através do componente “ ““BoIT- Projects”

- Objetivo: Fornecer uma visão de recuperação centrada no projeto que compare os custos do projeto com os encargos do projeto e destaque a sub-recuperação e a sobre-recuperação por projeto e pelos serviços que financiam esses projetos. É usado para responder: “Quais projetos estamos subsidiando (ou lucrando com eles), como está essa tendência e quais projetos ou portfólios de projetos devemos ajustar, interromper ou reavaliar?”
- Perguntas respondidas:
  - Quais são os totais atuais para custo do projeto, cobrança do projeto, orçamento e variação de recuperação (e seus valores acumulados no ano)?
  - Os projetos estão, em geral, a recuperar menos ou mais do que o necessário, e em que medida?
  - Como é a tendência dos custos e encargos do projeto ao longo do tempo (mês a mês)?
  - Quais projetos apresentam as maiores lacunas de recuperação (maior sub-recuperação ou sobre-recuperação)?
  - Quais portfólios de projetos estão gerando mais recuperação insuficiente ou recuperação excessiva?
  - Para um determinado projeto, quem é o gerente do projeto e qual é o status (geral, cronograma, escopo) juntamente com o resultado da recuperação?
  - Como a recuperação varia de acordo com o tipo de projeto, ciclo de vida, iniciativa de negócios ou tipo de gasto?
  - Quais serviços estão associados à recuperação do projeto (visualização Recuperação do projeto por serviço) e quais são seus encargos, custos, variação de recuperação e porcentagem de recuperação?
  - As questões orçamentárias estão contribuindo (variação orçamentária e % de variação orçamentária) quando o orçamento é preenchido?
  - Onde devo aprofundar para validar as alocações e os fatores de custo (link para a Visualização detalhada da transparência de custos)?
- Usuários-alvo: Proprietário do serviço ou produto, parte interessada, líder sênior, analista, administrador

![](../../../../../../03-media/apptio-billing/resources/images/boit_images/projrec.png)

Fig. #: Relatório de recuperação de projetos no padrão de faturamento

**Relatório sobre preços de transferência entre empresas e cobranças cruzadas**

Observação: instalado através do componente “ ““BoIT- Transfer Pricing Inter Company” (Preços de transferência interempresariais)

- Objetivo: Fornecer visibilidade sobre as cobranças modificadas criadas pelas regras de preços de transferência e cobranças cruzadas, para que os líderes financeiros e de tecnologia possam entender quanto da conta está sendo ajustado para atender às necessidades contábeis baseadas na entidade jurídica e na localização (por exemplo, impostos, liquidação entre empresas e cobranças cruzadas internas) e como esses ajustes evoluem ao longo do tempo.
- Perguntas respondidas:
  - Qual é o valor da cobrança antes de quaisquer ajustes nos preços de transferência?
  - Qual é o valor do preço de transferência e quaisquer impostos sobre o preço de transferência aplicados?
  - Qual é a cobrança modificada após o preço de transferência e qual é a cobrança modificada acumulada no ano?
  - Quais entidades jurídicas estão gerando preços de transferência e impostos, e em que valores?
  - Como têm evoluído as taxas modificadas entre empresas nos últimos 13 meses?
  - Como os resultados mudam quando filtrados por localização do provedor, gerente de serviço ou nome do serviço?
  - Quais serviços ou gerentes de serviço são os maiores impulsionadores das cobranças modificadas entre empresas?
  - Qual é o valor do preço de transferência + impostos aplicado no nível interno selecionado (por exemplo, por entidade jurídica ou localização)?
  - Como os encargos modificados dentro da empresa evoluíram nos últimos 13 meses por unidade de negócios ou outro nível selecionado?
  - Quais unidades de negócios (ou outro nível selecionado) estão gerando a maior atividade de cobrança cruzada?
  - As cobranças cruzadas são estáveis mês a mês ou há picos que sugerem mudanças nas políticas ou no mapeamento?
  - Para um determinado nome de serviço, que parte de seus encargos está sendo modificada pela lógica de cobrança cruzada?
- Usuários-alvo: Analista, Administrador

\* Acessível a partir do relatório inicial, mas parte da coleção de relatórios “Qualidade dos dados de faturamento”.

Com exceção do relatório “Distribuição”, os outros relatórios da coleção “Qualidade dos dados de faturamento” podem ser acessados pelo TBM Studio. Outros relatórios na coleção de relatórios “Qualidade dos dados de faturamento” são:

**Relatório resumido da configuração**

- Objetivo: realiza as principais verificações ao longo do processo mensal de publicação de faturamento, atualização de dados, qualidade dos dados, qualidade do modelo e distribuição, para que um operador possa confirmar rapidamente se o modelo está pronto para publicação, identificar problemas e corrigi-los antes do envio das faturas.
- Perguntas respondidas:
  - As minhas regras de atualização de dados estão sendo cumpridas ou há algo desatualizado/faltando para este período?
  - Quais verificações de atualização não apresentam resultados ou estão falhando?
  - Preciso revisar o Feed de Consumo antes de publicar? Quantas linhas estão envolvidas?
  - Preciso revisar a Biblioteca de Serviços antes de publicar? Quantas linhas estão envolvidas?
  - Qual conta teve a maior variação percentual na cobrança neste mês e qual foi o valor/porcentagem da variação?
  - Tenho encargos líquidos não alocados (itens não alocados ou não recuperáveis) e qual é o valor deles?
  - As contas estão configuradas para serem distribuídas e quantos nomes de contas aparecem na lista de faturas do destinatário?
  - Existe um conjunto de mensagens globais atual que aparecerá com as faturas distribuídas?
- Usuários-alvo: Administrador, Analista

![](../../../../../../03-media/apptio-billing/resources/images/boit_images/configsumrep.png)

Fig. #: Relatório resumido da configuração no padrão de faturamento

**Relatório de atualização dos dados**

- Objetivo: inventaria os conjuntos de dados que alimentam o modelo e mostra se cada um deles é recente o suficiente para o ciclo de faturamento atual, com base na data da última atualização e em quaisquer regras de atualização ou expiração configuradas, para que você possa detectar entradas obsoletas antes de publicar e distribuir as faturas.
- Perguntas respondidas:
  - Quando foi a última atualização?
  - Que tipo é (Dados API vs Tabela editável) e que categoria suporta?
  - Qual é o sistema de origem (por exemplo, XLSX Apptio, etc.)?
  - Existe uma regra de frescura e qual é essa regra?
  - Qual é a data de validade e ela está definida para nunca expirar?
  - O conjunto de dados está expirado neste momento?
  - Foi atualizado no mês corrente?
  - Há algum conjunto de dados pendente de aprovação?
  - Qual é a contagem de linhas e ela parece suspeitamente baixa ou alta em relação às expectativas?
- Usuários-alvo: Administrador, Analista

![](../../../../../../03-media/apptio-billing/resources/images/boit_images/datafreshrep.png)

Fig. #: Relatório de atualização de dados no padrão de faturamento

**Relatório sobre a qualidade da ração para consumo**

- Objetivo: ajuda os administradores a validar se os registros de consumo que geram unidades faturáveis e cobranças estão estruturalmente corretos antes que as faturas sejam publicadas ou distribuídas, especificamente monitorando a estabilidade do volume de feed, a consistência da unidade de medida e se algum campo importante está faltando ou não foi publicado (o que pode levar a taxas erradas, unidades misturadas ou faturas confusas).
- Perguntas respondidas:
  - O feed de consumo carregou a quantidade esperada de dados este mês? (tendência do número de linhas nos últimos 13 períodos)
  - Existem picos ou quedas no volume de consumo que sugiram um arquivo ausente, carga duplicada ou quebra de mapeamento?
  - As unidades faturáveis estão sendo relatadas na unidade de medida correta para cada serviço?
  - Em que pontos a unidade de medida “Serviços empresariais” e a unidade de medida “Feed de consumo” divergem?
  - Quais serviços e ofertas de serviços apresentam incompatibilidades nas unidades de medida que podem resultar em taxas ou cobranças efetivas incorretas?
  - Quais registros estão falhando na validação no momento (sinalizadores de status) e qual é o tamanho do impacto (cobranças, unidades faturáveis)?
  - Existem campos não publicados ou ausentes que impeçam a exibição dos detalhes esperados da fatura?
  - A porcentagem de campos não publicados está aumentando (uma degradação lenta da qualidade)?
  - Quais IDs/registros de serviço específicos são afetados para que eu possa encaminhar as correções ao responsável correto (gerente de serviço, proprietário dos dados)?
- Usuários-alvo: Administrador, Analista

![](../../../../../../03-media/apptio-billing/resources/images/boit_images/consfeedrep.png)

Fig. #: Relatório de qualidade da alimentação de consumo no padrão de faturamento

**Biblioteca de serviços Relatório de qualidade**

- Objetivo: Verifica se a hierarquia de serviços é estruturalmente válida e se os campos de serviço obrigatórios estão preenchidos, para que o Padrão de Faturamento possa calcular preços e unidades de forma consistente, agregar serviços corretamente e produzir faturas claras e defensáveis (sem serviços órfãos, sem relações quebradas, sem metadados obrigatórios ausentes).
- Perguntas respondidas:
  - Todos os serviços têm relações 1:1 válidas em todas as camadas da hierarquia de serviços (ID do serviço, nome do serviço, oferta do serviço) ou existem duplicatas/órfãos?
  - Quais IDs de serviço apresentam erros de relacionamento e quantos erros existem por ID de serviço?
  - Existem campos obrigatórios em branco em algum registro de serviço?
  - Quantos campos em branco existem por campo obrigatório (ID do serviço, unidade de medida, tipo de serviço, categoria de serviço, oferta de serviço, nome do serviço, descrição)?
  - Quais registros de serviço específicos têm campos obrigatórios em falta, para que eu possa corrigi-los (e quem é o proprietário deles)?
  - Existem serviços que deixarão de ser publicados ou causarão imprecisões na cobrança devido à falta de identificadores-chave ou UoM?
  - Temos definições de serviço inconsistentes que podem fragmentar os relatórios, como o mesmo nome de serviço vinculado a várias ofertas de forma inadequada (ou vice-versa)?
  - Estamos caminhando para uma “morte por mil cortes” na higiene dos serviços (aumento do número de erros mês a mês, se a tendência se repetir em outros lugares ou por meio de revisões repetidas)?
- Usuários-alvo: Administrador, Analista

![](../../../../../../03-media/apptio-billing/resources/images/boit_images/slqrep.png)

Fig. #: Relatório de qualidade da biblioteca de serviços no padrão de faturamento

**Relatório de qualidade do modelo**

- Objetivo: Mostra se o seu modelo de alocação está funcionando corretamente: se os encargos, custos, orçamentos, previsões e unidades estão sendo alocados aos objetos corretos, com o mínimo de valores não atribuídos, e se há variações inesperadas mês a mês que precisam ser investigadas antes de você publicar as contas.
- Perguntas respondidas:
  - Qual é a proporção entre meus dados alocados e não alocados (e isso está melhorando ou piorando com o tempo)?
  - Qual objeto está perdendo valor (maior carga não atribuída, custo, orçamento, previsão ou unidades)?
  - Qual é a porcentagem atribuída por objeto e quais objetos estão abaixo de um limite aceitável?
  - Os valores não atribuídos mudaram em relação ao último período e em quanto?
  - Quais alocações configuradas específicas estão impulsionando o modelo e o que elas estão fazendo (objeto de origem, objeto de destino, método, filtros, estratégia, valor)?
  - Alguma alocação está se comportando como uma armadilha do tipo “Não alocar para cima”, deixando cobranças retidas devido à falta de mapeamentos de referência?
  - Por onde devo começar a solucionar o problema, com base no objeto que tem o maior valor não atribuído?
  - Quais serviços apresentam a maior variação mensal nas cobranças (maior variação percentual absoluta)?
  - Uma grande variação é causada por uma mudança real ou por um problema de modelagem/configuração, com base na tabela detalhada MoM (cobrança atual vs. anterior, variação absoluta)?
  - As maiores variações estão concentradas em um tipo/categoria/oferta de serviço específico, sugerindo um problema sistêmico (como uma alteração no feed de entrada ou uma interrupção na alocação)?
- Usuários-alvo: Administrador, Analista

![](../../../../../../03-media/apptio-billing/resources/images/boit_images/modelrep.png)

Fig. #: Relatório de qualidade do modelo no padrão de faturamento
