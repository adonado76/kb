---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Otimização de computação e coleta de insights"
breadcrumb:
  - "Costing Standard"
  - "Relatório detalhado"
  - "Coleção de computação"
source_path: "cost-transparency/reports-v104/hbmcomputecollection.html"
images:
  - "resources/images/hbm_images/hbmimages/11693_1.png"
  - "resources/images/hbm_images/hbmimages/11693_2.png"
  - "resources/images/hbm_images/hbmimages/11693_3.png"
  - "resources/images/hbm_images/hbmimages/11693_4.png"
  - "resources/images/hbm_images/hbmimages/11693_5.png"
  - "resources/images/hbm_images/hbmimages/11693_6.png"
  - "resources/images/hbm_images/hbmimages/11693_7.png"
  - "resources/images/hbm_images/hbmimages/11693_8.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Otimização de computação e coleta de insights

- Aplica-se a: Hybrid Business Management em TBM Studio TBM Studio e posterior

Use os relatórios de computação para entender o custo, a capacidade e a utilização de seus recursos de computação. Os relatórios permitem que você analise seu perfil de gastos, compreenda as métricas de computação, compreenda as métricas operacionais, analise a utilização do servidor e compreenda uma visão de aplicativos dos detalhes do servidor (host e lógico). Use essa coleção de relatórios para entender a integridade geral de sua infraestrutura de computação em relação ao planejado, com KPIs acionáveis e perspicazes e análises de alto nível. Essas informações são especialmente úteis para entender onde você está incorrendo em custos de computação e determinar onde estão ocorrendo anomalias de gastos. Ele fornece relatórios detalhados para que você possa otimizar o custo e a utilização do servidor.

Essa coleção de relatórios foi criada para as seguintes funções:

- Diretor de TI
- Equipe de computação dentro da TI
- Chefe de Operações
- Proprietários de serviços de TI

Essa coleção de relatórios está alinhada às seguintes metas de negócios:

- Visualizar os custos de computação em toda a empresa
- Entenda o custo por hora de virtualização e por hora de instância
- Acompanhar a estratégia de infraestrutura de computação e o uso de recursos de computação
- Acompanhe o equilíbrio entre o número de servidores, o custo por servidor, os núcleos de CPU, a memória total, o custo por GB, as horas de instância e o custo das horas de instância para determinar se os gastos com computação estão tendendo conforme o esperado

Esses relatórios permitem que você determine o seguinte:

- Quais plataformas de servidor exigem compras adicionais de unidades?
- Qual é o custo por hora de servidor para cada aplicativo?
- Quais plataformas e unidades de servidor devem ser aposentadas?
- Onde estão as oportunidades de migrar da infraestrutura local para a nuvem pública?

## Exibir a coleção de relatórios

1. Faça login em Apptio.
2. Na página **inicial**, clique em **Hybrid Business Management**.
3. No menu da coleção de relatórios, selecione **Compute**. O relatório **Compute Summary** é aberto por padrão.

## Computar relatório de resumo

O relatório Compute Summary fornece uma visão geral do gasto total com computação na empresa, no local e na nuvem, além de ajudar a visualizar o gasto em dimensões como pools de custo, ambientes, fornecedores e torres de TI.

Esse relatório tem os seguintes elementos:

![](../../../../../03-media/apptio-costing-standard/resources/images/hbm_images/hbmimages/11693_1.png)

**(1) KPIs** - os KPIs fornecem uma visão de alto nível de seus gastos com infraestrutura:

- **Cost YTD (Custo acumulado** no ano) - esse KPI mostra o gasto geral no Compute YTD. As despesas do período atual são mostradas como **Custo**.
- **Contagem de servidores** - Esse KPI mostra o número atual de servidores locais. O KPI secundário mostra a porcentagem de servidores virtuais como **% de servidores virtualizados**.
- **Virtual Instance Hours (Horas de instância virtual** ) - Esse KPI mostra o uso atual (em horas de instância) de seus servidores virtuais. O KPI secundário mostra **o custo por hora de instância**.
- **Horas de instância na nuvem** - Esse KPI mostra o uso atual (em horas de instância) de seus servidores públicos e na nuvem. O KPI secundário mostra **o custo por hora de instância**.

**(2) Filtros** - Os seguintes filtros estão disponíveis neste relatório. Esses filtros são cumulativos e afetam todos os dados da página, inclusive os KPIs:

- **Perfil de virtualização** - Selecione um tipo específico de servidor local ou na nuvem para ver o impacto dos gastos com computação nesse tipo de servidor.
- **SO** - Selecione um sistema operacional (SO) específico para ver o impacto dos gastos com computação nesse SO.
- **Ambiente** - Selecione um ambiente específico (como Desenvolvimento, Produção ou Teste) para limitar os dados do relatório aos servidores desse ambiente.
- **Localização** - Selecione uma localização específica para ver o impacto dos gastos com computação para essa localização.
- **Finalidade** - Selecione uma finalidade específica do servidor para ver o impacto dos gastos do Compute em servidores com a mesma finalidade.

**(3) Gastos com computação mês a mês** - use este gráfico para visualizar a tendência de gastos de um ano com recursos de computação em seus servidores locais e de nuvem pública.

**(4) Compute Costs by (Calcular custos por** ) - Clique nas guias **Cost Pools (Grupos de custos** ), **IT Towers (Torres de TI** ), **Environment (Ambiente** ) ou **Vendors (Fornecedores** ) para visualizar gráficos dos gastos atuais com armazenamento no mês. A tabela **Details (Detalhes** ) lista os gastos do mês atual, QTD e YTD.

Perguntas respondidas:

- Existem anomalias em nossos gastos?
- Os gastos estão de acordo com nossa estratégia de computação?
- Como a estratégia de infraestrutura está evoluindo?
- Onde estamos incorrendo em custos de computação?

## Relatório de perfil de despesas

Clique em **Perfil de despesas** na guia Coleção de relatórios para abrir o relatório. Esse relatório mostra um perfil de custo dos custos de computação.

Esse relatório tem os seguintes elementos:

![](../../../../../03-media/apptio-costing-standard/resources/images/hbm_images/hbmimages/11693_2.png)

**(1) KPIs** - Os KPIs deste relatório são os mesmos do Compute - Summary. Consulte o elemento 1 no [relatório Compute Summary (Resumo da computação](hbmcomputecollection.html) ).

**(2) Filtros** - Os filtros desse relatório são os mesmos do Compute - Summary. Consulte o elemento 2 no [relatório Compute Summary (Resumo da computação](hbmcomputecollection.html) ).

**(3) Despesas do mês atual por pool de** custos - Use este gráfico para visualizar as despesas do servidor atual por pool de custos (serviços externos, hardware, etc.).

**(4) Tendência de 13 meses dos servidores** - Use esse gráfico para visualizar a contagem mensal de servidores, o custo por servidor e o gasto médio anual com servidores para que você possa observar anomalias e tendências que não se alinham à sua estratégia de negócios.

**(5) Gasto do servidor por** - Use os gráficos de pizza **por perfil**, **por sistema operacional** e **por ambiente** para entender o equilíbrio dos custos do servidor em várias métricas.

Perguntas respondidas:

- Como a estratégia de servidor está evoluindo?
- Onde estamos incorrendo em custos de servidor?
- Há anomalias em nossos gastos com servidores?

## Relatório de resumo operacional

Clique em **Operational Summary (Resumo operacional** ) na guia Report collection (Coleção de relatórios) para abrir o relatório. Use este relatório para entender as métricas operacionais de seus recursos de computação (como custos de servidor, núcleos de CPU, custo por hora de instância, etc., por perfil de virtualização) em execução no local.

Esse relatório tem os seguintes elementos:

![](../../../../../03-media/apptio-costing-standard/resources/images/hbm_images/hbmimages/11693_3.png)

**(1) KPIs** - Os KPIs deste relatório são os mesmos do Compute - Summary. Consulte o elemento 1 no [relatório Compute Summary (Resumo da computação](hbmcomputecollection.html) ).

**(2) Filtros** - Os filtros desse relatório são os mesmos do Compute - Summary. Consulte o elemento 2 no [relatório Compute Summary (Resumo da computação](hbmcomputecollection.html) ).

**(3) Métricas operacionais por categoria** - Use as opções na parte superior desse gráfico para exibir seletivamente várias métricas. Métricas adicionais estão disponíveis na lista **Resumido por**. Use o gráfico para visualizar os gastos operacionais atuais com base nas opções que você selecionou.

**(4) Detalhes** - A tabela **Detalhes** fornece o custo mensal atual para a métrica selecionada na lista **Resumido por** e as contagens e os custos unitários de todas as CPUs, servidores, memória e horas de instância relacionados.

Perguntas respondidas:

- Como nossa estratégia operacional está evoluindo?
- Onde estamos incorrendo em custos operacionais?
- Há anomalias em nossos gastos operacionais?

## Relatório de resumo de utilização

Clique em **Utilization Summary (Resumo da utilização** ) na guia Report collection (Coleção de relatórios) para abrir o relatório. Use este relatório para ter uma perspectiva de como a utilização de recursos de computação no local está afetando o custo. Você pode visualizar as métricas de utilização relacionadas aos seus recursos de computação no local (como custos de servidor, núcleos de CPU, capacidade de memória, utilização média ou de pico, etc.) divididos por perfil de virtualização.

Esse relatório tem os seguintes elementos:

![](../../../../../03-media/apptio-costing-standard/resources/images/hbm_images/hbmimages/11693_4.png)

**(1) KPIs** - Os KPIs deste relatório são os mesmos do Compute - Summary. Consulte o elemento 1 no [relatório Compute Summary (Resumo da computação](hbmcomputecollection.html) ).

**(2) Filtros** - Os seguintes filtros estão disponíveis neste relatório. Esses filtros são cumulativos e afetam todos os dados da página, inclusive os KPIs:

- **Perfil de virtualização** - Selecione um tipo específico de servidor local ou na nuvem para ver o impacto dos gastos com computação nesse tipo de servidor.
- **SO** - Selecione um sistema operacional (SO) específico para ver o impacto dos gastos com computação nesse SO.
- **Ambiente** - Selecione um ambiente específico (como Desenvolvimento, Produção ou Teste) para limitar os dados do relatório aos servidores desse ambiente.
- **Classe** - Selecione uma classe (o tamanho das instâncias reservadas) para limitar os dados do relatório a uma classe específica.
- **Localização** - Selecione uma localização específica para ver o impacto dos gastos com computação para essa localização.
- **Finalidade** - Selecione uma finalidade específica do servidor para ver o impacto dos gastos do Compute em servidores com a mesma finalidade.
- **Fabricante** - Selecione um provedor de serviços em nuvem específico para limitar os dados do relatório aos serviços desse provedor.

**(3) Métricas operacionais por categoria**

- Esse relatório é semelhante ao relatório Resumo operacional, mas com métricas sobre o uso médio e de pico da CPU e o uso médio e de pico da memória.
- Use as opções na parte superior desse gráfico para exibir seletivamente várias métricas. Métricas adicionais estão disponíveis na lista **Resumido por**.
- A tabela fornece o custo mensal atual para a métrica que você selecionou na lista **Resumido por** e as contagens, os custos unitários, o uso médio e o pico de uso de CPUs, servidores, memória e horas de instância relacionados.

Perguntas respondidas:

- Como nossa estratégia de utilização de computação está evoluindo?
- Onde estamos incorrendo em custos de utilização?
- Há anomalias na utilização de nossa computação?

## Relatório de detalhes do servidor host

Clique em **Host Server Details** na guia Report collection (Coleção de relatórios) para abrir o relatório. Use este relatório para visualizar seus gastos com computação específicos para máquinas host físicas no local. O relatório fornece o custo do período atual, o número de servidores físicos e o custo unitário, juntamente com a utilização média e de pico.

**OBSERVAÇÃO** : um *hipervisor*, também chamado de monitor de máquina virtual (VMM), é um programa de software executado em uma plataforma de hardware de host real e que supervisiona a execução dos sistemas operacionais convidados nas máquinas virtuais.

Esse relatório tem os seguintes elementos:

![](../../../../../03-media/apptio-costing-standard/resources/images/hbm_images/hbmimages/11693_5.png)

**(1) KPIs** - os KPIs fornecem uma visão de alto nível dos gastos com seu servidor host:

- **Cost YTD (Custo acumulado no** ano) - Esse KPI mostra o gasto geral com servidores host no acumulado no ano. As despesas do período atual são mostradas como **Custo**.
- **Núcleos de CPU do servidor** - Este KPI mostra o número atual de núcleos físicos do servidor. O KPI secundário mostra o custo por núcleo como **Custo por núcleo de CPU**.
- **Núcleo da CPU do hipervisor** - este KPI mostra o número atual de processadores do hipervisor. O KPI secundário mostra a instância média por hipervisor como **Número médio de instâncias virtuais por hipervisor**.
- **Virtual Instance Hours (Horas de instância virtual** ) - Esse KPI mostra a capacidade atual (como horas de instância) de seus servidores virtuais. O KPI secundário mostra **o custo por hora de instância**.

**(2) Filtros** - Os filtros desse relatório são os mesmos do Resumo de utilização. Consulte o elemento 2 no [relatório Resumo de utilização](hbmcomputecollection.html).

**(3) Detalhes do servidor host**

- Use as opções na parte superior desse gráfico para adicionar colunas com **SO do hipervisor**, **nome da nuvem** e **local** ao gráfico.
- Use as guias **CPU Cores (Núcleos de CPU** ) e **Memory Capacity (Capacidade de memória** ) para visualizar a capacidade atual, o custo por unidade, a alocação e a utilização média/pico dos núcleos de CPU e da memória.

Perguntas respondidas:

- Como nossa estratégia de servidor host está evoluindo?
- Onde estamos incorrendo em custos de utilização?

## Relatório de detalhes do servidor lógico

Clique em **Logical Server Details (Detalhes do servidor lógico** ) na guia Coleção de relatórios para abrir o relatório. Use este relatório para visualizar seus gastos com computação específicos para máquinas lógicas ou máquinas virtuais. O relatório fornece o custo do período atual, o número de servidores e os custos unitários, juntamente com a utilização média e de pico.

Esse relatório tem os seguintes elementos:

![](../../../../../03-media/apptio-costing-standard/resources/images/hbm_images/hbmimages/11693_6.png)

**(1) KPIs** - Os KPIs deste relatório são os mesmos do Compute - Summary. Consulte o elemento 1 no [relatório Compute Summary (Resumo da computação](hbmcomputecollection.html) ).

**(2) Filtros** - Os filtros desse relatório são os mesmos do Compute - Summary. Consulte o elemento 2 no [relatório Compute Summary (Resumo da computação](hbmcomputecollection.html) ).

**(3) Detalhes do servidor lógico**

- Use as opções à direita desse gráfico para adicionar colunas que listam o nome do host, o modelo da instância, o nome do ambiente, a memória total e o custo por GB ao gráfico.
- Use a tabela para visualizar a capacidade atual, as horas de instância, a contagem de núcleos, o custo unitário, a alocação e a utilização média/pico de seus servidores lógicos.

Perguntas respondidas:

- Como nossa estratégia de servidor lógico está evoluindo?
- Onde estamos incorrendo em custos?

## Relatório de visão financeira

Clique em **Financial View** na guia Report collection (Coleção de relatórios) para abrir o relatório. Use este relatório para obter uma visão financeira de seus gastos com computação por classe, ambiente, local, sistema operacional ou perfil de virtualização.

Esse relatório tem os seguintes elementos:

![](../../../../../03-media/apptio-costing-standard/resources/images/hbm_images/hbmimages/11693_7.png)

**(1) KPIs** - Os KPIs deste relatório são os mesmos do Compute - Summary. Consulte o elemento 1 no [relatório Compute Summary (Resumo da computação](hbmcomputecollection.html) ).

**(2) Filtros** - Os filtros desse relatório são os mesmos do Compute - Summary. Consulte o elemento 2 no [relatório Compute Summary (Resumo da computação](hbmcomputecollection.html) ).

**(3) Custo acumulado até a data**

- Use as opções na parte superior desse gráfico para visualizar os gastos acumulados no ano com recursos de computação por pool de custos (serviços externos, hardware, etc.) versus subtorre de TI (servidores, transporte, voz, etc.). Essas informações fornecem uma visão geral de seus gastos gerais com computação por ATUM torre e subtorre.
- A tabela mostra os mesmos dados mês a mês, com base em sua seleção na lista **Summarize Costs By (Resumir custos por** ).

Perguntas respondidas:

- Como nossa estratégia de computação está evoluindo?
- Onde estamos incorrendo em custos de computação?
- Existem anomalias em nossos gastos com computação?

## Por relatório de aplicativos

Clique em **By Applications (Por aplicativos** ) na guia Report collection (Coleção de relatórios) para abrir o relatório. Use este relatório para visualizar seus gastos com computação por aplicativo em todo o seu perfil de implementação.

Esse relatório tem os seguintes elementos:

![](../../../../../03-media/apptio-costing-standard/resources/images/hbm_images/hbmimages/11693_8.png)

**(1) KPIs** - Os KPIs deste relatório são os mesmos do Compute - Summary. Consulte o elemento 1 no [relatório Compute Summary (Resumo da computação](hbmcomputecollection.html) ).

**(2) Filtros** - Os filtros desse relatório são os mesmos do Compute - Summary. Consulte o elemento 2 no [relatório Compute Summary (Resumo da computação](hbmcomputecollection.html) ).

**(3) Cost YTD By (Custo acumulado até** a data) - Use essa tabela para visualizar os gastos acumulados até a data para recursos de computação por aplicativo (por exemplo, Active Directory, SAP Data Warehouse e Office 365). A tabela mostra o proprietário do aplicativo, o perfil da carga de trabalho e o perfil de risco de cada aplicativo. Além disso, as horas de servidor e o custo por hora de servidor são detalhados para cada aplicativo.

Perguntas respondidas:

- Como nossa estratégia de computação está evoluindo?
- Onde estamos incorrendo em custos de computação?
- Existem anomalias em nossos gastos com computação?
- Qual é a distribuição dos gastos de computação para um aplicativo híbrido?
