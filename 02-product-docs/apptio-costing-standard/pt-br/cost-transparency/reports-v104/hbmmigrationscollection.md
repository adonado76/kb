---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Coleção de relatórios de recomendações de migração - HBM"
breadcrumb: []
source_path: "cost-transparency/reports-v104/hbmmigrationscollection.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Coleção de relatórios de recomendações de migração - HBM

- Aplica-se a: Hybrid Business Management em TBM Studio TBM Studio e posterior

Use os relatórios de Recomendações de migração para refinar sua estratégia de migração de servidores locais para servidores na nuvem. Os relatórios permitem que você compare seus gastos atuais com os gastos potenciais com infraestrutura em nuvem. Use essa coleção de relatórios para entender quais áreas de sua infraestrutura atual podem se beneficiar mais da migração, com KPIs acionáveis e perspicazes e análises de alto nível. Essas informações são especialmente úteis para destacar o valor contínuo da migração para a nuvem.

Nota:

Os preços dos serviços em nuvem são coletados das listas de preços publicadas por cada provedor de nuvem pública. As listas de preços são importadas e atualizadas uma vez por mês. Os preços são combinados com descontos, impostos sobre vendas e custos de suporte.

Para uma introdução aos conceitos em HBM, veja [Sobre Hybrid Business Management](../home.htm "(Abre em uma nova guia ou janela)"). Para obter uma lista completa de relatórios, consulte [Hybrid Business Management Reports](../../..hbm-reports.htm "(Abre em uma nova guia ou janela)").

Esta coleção de relatórios foi projetada para as seguintes funções:

- Diretor de TI
- Grupo de aplicativos
- Centro de excelência em nuvem

Essa coleção de relatórios está alinhada às seguintes metas de negócios:

- Tomar decisões de migração informadas com base em dados
- Compare os custos da infraestrutura local com a possível infraestrutura em nuvem
- Compreender o valor da migração

Esses relatórios permitem que você determine o seguinte:

- Quais servidores devem ser migrados primeiro?
- Como podemos demonstrar claramente o valor da migração?
- Como devemos priorizar a migração ao longo do tempo?

## Exibir a coleção de relatórios

1. Faça login em Apptio.
2. Na página **inicial**, clique em **Hybrid Business Management**.
3. No menu da coleção de relatórios, selecione **Migration Recommendations (Recomendações de migração** ). O relatório **Resumo da migração** é aberto.

## Relatório de resumo de migração

Use este relatório para comparar seus custos atuais de servidor local com os possíveis custos de serviços em nuvem.

Esse relatório tem os seguintes elementos:

**(1) KPIs** - os KPIs fornecem uma comparação de alto nível de seus gastos atuais com servidores em relação aos custos potenciais com servidores em nuvem:

- **Custo anual atual do servidor** - Esse KPI mostra o gasto geral com servidores. Os gastos por hora são mostrados como **Custo por hora**.
- **Custo anual de AWS** - Esse KPI mostra o custo anual potencial de Amazon Web Services ( AWS ). O gasto por hora é mostrado em **AWS Custo por hora**.
- **Custo anual do Azure** - Esse KPI mostra o custo anual potencial do Microsoft Azure. O gasto por hora é mostrado em **Azure Custo por hora**.
- **Custo anual de Google** - Esse KPI mostra o custo anual potencial do provedor de Google Cloud (GCP). O gasto por hora é mostrado em **Google Custo por hora**.

**(2) Filtros** - Os seguintes filtros estão disponíveis neste relatório. Esses filtros são cumulativos e afetam todos os dados da página, inclusive os KPIs:

- **Aplicativo** - Selecione um aplicativo para ver o impacto da sua estratégia de migração em um aplicativo específico.
- **Ambiente** - Selecione um ambiente para ver o impacto da sua estratégia de migração em um ambiente específico.
- **SO** - Selecione um sistema operacional para ver o impacto da sua estratégia de migração em um sistema operacional específico.
- **Local** - Selecione um local para ver o impacto da sua estratégia de migração nos servidores em um local específico.
- **Perfil de virtualização** - Selecione um perfil de virtualização para ver o impacto de sua estratégia de migração em um tipo específico de servidor.

**(3) Economia potencial por ambiente** - Use este gráfico para visualizar sua economia potencial de migração para a nuvem por ambiente. Use as opções acima da tabela para mostrar ou ocultar ambientes específicos.

**(4) Economia potencial por data center** - Use este gráfico para visualizar sua economia potencial de migração para a nuvem por data center. Use as opções acima da tabela para mostrar ou ocultar data centers específicos.

**(5) Economia potencial por finalidade** - Use este gráfico para visualizar sua economia potencial de migração para a nuvem por tipo de servidor (servidores de aplicativos, servidores da Web, servidores de banco de dados, servidores de diretório e servidores de e-mail).

Perguntas respondidas:

- Quais provedores de serviços em nuvem são os mais econômicos?
- É melhor mover as cargas de trabalho do ambiente de desenvolvimento e teste primeiro para a nuvem para permitir o teste?
- Podemos arriscar o tempo de inatividade em nosso ambiente de produção ou ele contém dados confidenciais que não queremos na nuvem pública?
- É melhor migrar os servidores da Web para a nuvem?
- Devemos consolidar nossos data centers?

## Relatório de migração de carga de trabalho

Use esse relatório para mostrar uma visão baseada em carga de trabalho da comparação de migração.

Esse relatório tem os seguintes elementos:

**(1) KPIs** - Os KPIs deste relatório são os mesmos do relatório Resumo da migração. Consulte o elemento 1 no [relatório Resumo da Migração](hbmmigrationscollection.html).

**(2) Cargas de trabalho, cargas de trabalho de rehost e utilização** - use as guias a seguir para visualizar os custos e a utilização de cargas de trabalho de migração e cargas de trabalho rehosted:

- **Todas as cargas de trabalho** - Use este gráfico para comparar o custo das dez principais cargas de trabalho em seus servidores locais atuais com o custo de execução de serviços de computação semelhantes (CPU/RAM) em AWS, Azure e GCP. Use os seletores à direita do gráfico para controlar quais dados são exibidos. Abaixo do gráfico, a tabela **Workload Details (Detalhes da carga de** trabalho) exibe dados detalhados de todas as suas cargas de trabalho.
- **Cargas de trabalho de rehost** - Use este gráfico para visualizar suas dez principais cargas de trabalho designadas para serem rehosted na nuvem e para comparar os custos dessas cargas de trabalho em servidores locais com o custo de execução de serviços de computação semelhantes (CPU/RAM) em AWS, Azure e Google. Abaixo do gráfico, a tabela **Rehost Workload Details (Detalhes da carga de trabalho de rehost** ) exibe dados detalhados de suas cargas de trabalho que foram designadas para serem rehospedadas na nuvem.
- **Utilização** - Use essa tabela para visualizar e comparar os custos de todas as cargas de trabalho. Clique nas caixas de seleção acima da tabela para adicionar colunas adicionais à tabela. Essa tabela é semelhante à da guia **All Workloads**, mas com dados adicionais exibidos.

Perguntas respondidas:

- Quais provedores de serviços em nuvem são os mais econômicos?
- É melhor mover as cargas de trabalho do ambiente de desenvolvimento e teste primeiro para a nuvem para permitir o teste? Podemos arriscar o tempo de inatividade em nosso ambiente de produção ou ele contém dados confidenciais que não queremos na nuvem pública?
- É melhor migrar os servidores da Web para a nuvem?
- Devemos consolidar nossos data centers?

## AWS Relatório de migração

Use esse relatório para explorar as estatísticas de migração com metadados adicionais fornecidos pelo site AWS.

Esse relatório tem os seguintes elementos:

**(1) Filtros** - Controle quais dados são exibidos na tabela selecionando filtros. Os filtros são cumulativos.

**OBSERVAÇÃO** : o filtro **Term Type (Tipo de termo)** define como os serviços de computação são consumidos e pagos, se sob demanda ou reservados. Se você selecionar Reservado, o tipo de pagamento poderá ser Todo adiantado, Parcial adiantado ou Sem adiantamento.

**(2) Tabela** - Esta tabela compara sua infraestrutura de servidor atual com as recomendações do site AWS.

Perguntas respondidas:

- Como podemos adaptar o site AWS para atender melhor às nossas necessidades?
- Quais opções do site AWS estão disponíveis?

## Recomendações de migração - Casos de uso adicionais

Use este relatório para explorar opções adicionais a serem adotadas como parte de uma estratégia de migração. Atualmente, dois casos são cobertos. Cada caso tem uma tabela em sua própria guia.

- A guia **Tech Refresh** concentra-se em servidores antigos, que são os principais candidatos à migração para a nuvem pública.
- A guia **Dev/Test Environments (Ambientes de desenvolvimento/teste** ) concentra-se em servidores que executam ambientes de teste. Esses servidores podem ser migrados seletivamente primeiro, com baixo risco, enquanto você continua a avaliar sua estratégia geral.

Esse relatório tem os seguintes elementos:

**(1) KPIs** - Os KPIs deste relatório são os mesmos do relatório Resumo da migração. Consulte o elemento 1 no [relatório Resumo da Migração](hbmmigrationscollection.html).

**(2) Filtros** - Os cinco primeiros filtros desse relatório são os mesmos do relatório Resumo da migração. Consulte o elemento 2 no [relatório Resumo da Migração](hbmmigrationscollection.html).

- **Fabricante** - Selecione um fabricante de servidor.

**(3) Recomendações** - Use esta tabela para visualizar os servidores locais que atendem a determinados critérios relacionados à idade. Observe que na imagem acima, nenhum desses servidores é exibido. Clique na guia **Dev/Test Environments (Ambientes de desenvolvimento/teste** ) para ver uma tabela que exibe os servidores de desenvolvimento e teste.

Perguntas respondidas:

- Quais opções do site AWS estão disponíveis?
- Como podemos adaptar o site AWS para atender melhor às nossas necessidades?

## Comparação de migração

Use este relatório para analisar sua infraestrutura de servidor com base em uma variedade de combinações de requisitos.

Esse relatório tem os seguintes elementos:

**(1) KPIs** - Os KPIs deste relatório são os mesmos do relatório Resumo da migração. Consulte o elemento 1 no [relatório Resumo da Migração](hbmmigrationscollection.html).

**(2) Filtros** - Os filtros desse relatório são os mesmos do relatório Additional Use Cases. Consulte o elemento 2 no [relatório de casos de uso adicionais](hbmmigrationscollection.html).

**(3) Configuração do servidor** - Use esta tabela para comparar os custos de servidores locais com possíveis alternativas de nuvem, com dados adicionais, como a localização do servidor em nuvem. Selecione as opções acima da tabela para adicionar colunas adicionais à tabela.

Perguntas respondidas:

- Como os locais dos meus servidores serão alterados com a migração?
- Qual é o custo por hora do uso de um servidor em nuvem específico?

## Recomendações de migração - Comparação de utilização

Use este relatório para analisar sua infraestrutura de servidor com base em uma variedade de combinações de requisitos.

Esse relatório tem os seguintes elementos:

**(1) KPIs** - Os KPIs deste relatório são os mesmos do relatório Resumo da migração. Consulte o elemento 1 no [relatório Resumo da Migração](hbmmigrationscollection.html).

**(2) Filtros** - Os filtros desse relatório são os mesmos do relatório Additional Use Cases. Consulte o elemento 2 no [relatório de casos de uso adicionais](hbmmigrationscollection.html).

**(3) Configuração do servidor** - Use esta tabela para comparar os custos de servidores locais com possíveis alternativas de nuvem, com dados adicionais, como a localização do servidor em nuvem. Selecione as opções acima da tabela para adicionar colunas adicionais à tabela.

Perguntas respondidas:

- Como os locais dos meus servidores serão alterados com a migração?
- Qual é o custo por hora do uso de um servidor em nuvem específico?
