---
source_system: "apptio-costing-essentials"
practice: "tbm"
language: "pt-br"
doc_type: "apptio-cost-management"
title: "Revisão do trabalho"
breadcrumb:
  - "Costing Essentials"
  - "Relatórios prontos para uso"
source_path: "apptio-cost-management/out_of_the_box_reports/labor-review.html"
images:
  - "resources/images/acm_images/headcount-by-category.png"
  - "resources/images/acm_images/headcount-by-role.png"
  - "resources/images/acm_images/headcount-var.png"
  - "resources/images/acm_images/la-trends.png"
  - "resources/images/acm_images/labor-activity.png"
  - "resources/images/acm_images/labor-analysis-new.png"
  - "resources/images/acm_images/labor-opex-acc-grps.png"
  - "resources/images/acm_images/labor-report_991x1074.png"
  - "resources/images/acm_images/labor-ytd-acc-sub-grps.png"
  - "resources/images/acm_images/lc-model.png"
capability_ids: []
last_updated: "2026-02-27"
summary: ""
---
# Revisão do trabalho

Esse relatório fornece métricas de alto nível relacionadas ao custo e ao número de funcionários da mão de obra interna e de contratados externos, incluindo o número e a natureza das posições em aberto, o equilíbrio entre mão de obra interna e externa e a porcentagem de gastos com mão de obra.

O custo da mão de obra (o custo total da mão de obra) é um dos custos operacionais mais substanciais para todas as organizações de TI. As revisões mensais do número de funcionários internos e externos são essenciais para eliminar as variações orçamentárias. O relatório de revisão de mão de obra ajuda você a entender os fatores que provocam essas variações.

Quando você usa esse relatório para entender os fatores que impulsionam a variação da mão de obra externa, pode incorporar esses fatores às suas previsões trimestrais e revisões executivas, identificar oportunidades de conciliar o orçamento e planejar com mais eficiência as principais iniciativas.

## Casos de uso

Esse relatório resolve os seguintes casos de uso:

- Comparar a equipe com o plano de pessoal
- Analisar os gastos e as taxas de mão de obra por tipo de funcionário, função, local e fornecedor
- Analisar os custos de mão de obra por classificação de conta
- Analisar as ofertas de tecnologia atribuídas à mão de obra e executar atividades de comparação com mudanças

## Personagens

Este relatório foi elaborado para as seguintes funções:

- Liderança de TI, para ter uma visão agregada e poder controlar os custos
- Gerentes de recursos, para que você possa acompanhar onde e como a mão de obra é tratada
- Proprietários de centros de custo e proprietários de orçamentos (CIO -1)) ), para que você possa gerenciar seu pessoal e seus orçamentos

## Perguntas respondidas

- Estamos cumprindo nosso plano de contratação e gastos com mão de obra?
- Quais habilidades e funções estão apoiando meus aplicativos? Quantos são DBAs, desenvolvedores, etc.?
- De onde vêm meus custos de mão de obra: FTEs internos, contratados ou algum outro prestador de serviços?
- Qual é a composição de nossos custos de mão de obra?
- Como os custos de conjuntos de habilidades semelhantes variam de acordo com a região e o contratante?
- Qual é a combinação de mão de obra interna e externa que dá suporte a cada função de TI?
- Quais contas GL contribuem para o trabalho de uma determinada função (como administrador do sistema)?
- Quais departamentos têm o maior número de vagas de funcionários no plano de contratação? Quais delas excedem o plano de pessoal?

## Visualização

O relatório contém os seguintes elementos:

![Imagem](../../../../../03-media/apptio-costing-essentials/resources/images/acm_images/labor-report_991x1074.png)

| Elemento-chave | Descrição |
| --- | --- |
| (1) Coleta de relatórios | Essa coleção de relatórios fornece os detalhes de que você precisa para analisar seus recursos de mão de obra:  - Revisão do trabalho  - Análise trabalhista  - Atividade trabalhista |
| (2) Cortadores | Use as segmentações para refinar os dados em seu relatório. Os fatiadores nesse relatório permitem que você veja seus dados de mão de obra por região e responsabilidade organizacional, incluindo centro de custo e ID, proprietário do centro de custo e proprietário (por exemplo, CIO -1)).  As seguintes funções podem usar as segmentações neste relatório para obter uma visualização mais personalizada:  - Controlador financeiro de TI ou CIO: Sem definir quaisquer segmentações, você pode ver a visão geral das despesas de cada pool de custos em toda a organização. É possível detalhar os pools de custos, os proprietários de centros de custos e as contas individuais.  - Proprietário do centro de custo ou CIO -1 : Defina as segmentações do centro de custo ou do proprietário do centro de custo para filtrar suas áreas de responsabilidade.  - Analista financeiro: Defina o fatiador de centro de custos para as áreas às quais você dá suporte ou defina um grupo de contas específico para permitir uma análise detalhada e interorganizacional das despesas por categoria. |
| (3) KPIs | Os KPIs fornecem uma visão de alto nível de seus gastos com mão de obra:  - Total de gastos no acumulado do ano: esse KPI expressa seus gastos com mão de obra como uma porcentagem dos gastos gerais de TI no acumulado do ano e os compara com o acumulado do ano anterior.  - Mão de obra como % dos gastos de TI no acumulado do ano: esse KPI compara seus custos de mão de obra no acumulado do ano com o acumulado do ano anterior.  - Número de funcionários: Esse KPI compara seu número de funcionários atual com o do ano anterior, com a porcentagem de mudança.  - % HC externo: esse KPI exibe o número de posições externas atuais e a porcentagem dessas posições em relação ao número total de funcionários.  - Endereçável: Esse KPI compara seu custo endereçável YTD com o YTD anterior. |

## Revisão do trabalho

|  |  |
| --- | --- |
| Número de funcionários por [centro de custo, nome] | Use esses gráficos para visualizar suas despesas com mão de obra por proprietário, proprietário do centro de custos e centro de custos e nome:  - Mão de obra por categoria: Use o gráfico de rosca para comparar a porcentagem de gastos com mão de obra por proprietário ou centro de custo. Se você selecionar Cost Center Owner, por exemplo, os gráficos mostrarão os 10 principais centros com o maior número de funcionários. Use o gráfico de tendências para ver as despesas com mão de obra mês a mês. Você verá picos quando um grande número de novos funcionários ingressar na organização, ou o contrário, quando uma equipe estiver diminuindo o ritmo. Avalie essas informações para garantir que elas correspondam às suas expectativas. Você pode ver mais informações no relatório de análise de mão de obra, onde os dados reais são comparados aos planejados.  Você pode remover pontos de dados individuais de qualquer gráfico clicando na lista de itens abaixo dos gráficos. Selecione qualquer barra no gráfico de rosca para abrir a caixa de diálogo Detalhes do trabalho com mais informações sobre o item selecionado.  Imagem |
| Número de funcionários por função | Use esses gráficos para visualizar suas despesas com mão de obra por função. Esses dados podem ajudar um proprietário de recursos ou um executivo a analisar as funções em todos os centros de custo ou por local, ao considerar uma estratégia de mão de obra de longo prazo.  - Trabalho por função: Use o gráfico de rosca para comparar a porcentagem de gastos com mão de obra por função. Use o gráfico de tendências para ver as despesas com mão de obra mês a mês.  Selecione uma barra no gráfico de rosca para abrir uma caixa de diálogo Detalhes do trabalho com mais detalhes sobre o item em que você clicar. Os relatórios disponíveis na caixa de diálogo são os mesmos que os de Trabalho por categoria (acima), exceto pelo fato de os dados serem por função.  Imagem |
| Labor YTD OpEx por subgrupos de contas | Imagem |
| Trabalho OpEx Detalhes da composição por grupos de contas | Imagem |

## Análise trabalhista

Essa tabela contém uma visão completa das despesas com mão de obra em todos os centros de custos por função, número de funcionários internos e externos, orçamento OpEx, OpEx, variação do orçamento e taxa média por padrão. Na tabela, são usados os seguintes códigos:

- (E-xxx) = Funcionário
- (C-xxx) = Empreiteira
- (CC-xxx) = Orçamento planejado para o número de funcionários por departamento

![Imagem](../../../../../03-media/apptio-costing-essentials/resources/images/acm_images/labor-analysis-new.png)

Selecione itens adicionais nos elementos (1) e (2) para personalizar a tabela com as métricas que você deseja ver.

Na coluna Tendência, selecione para abrir uma caixa de diálogo com detalhes mês a mês do item em que você clicar.

![Imagem](../../../../../03-media/apptio-costing-essentials/resources/images/acm_images/la-trends.png)

## Atividade trabalhista

Essa tabela contém todos os dados relacionados às atividades trabalhistas. Você pode usar as segmentações para filtrar os dados desejados.

![Imagem](../../../../../03-media/apptio-costing-essentials/resources/images/acm_images/labor-activity.png)

## Variação do número de funcionários

![Variação de HC](../../../../../03-media/apptio-costing-essentials/resources/images/acm_images/headcount-var.png)

## Modelo de custo de mão de obra

![Modelo LC](../../../../../03-media/apptio-costing-essentials/resources/images/acm_images/lc-model.png)
