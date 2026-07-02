---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "pt-br"
doc_type: "it-benchmarking"
title: "Benchmarking de infraestrutura"
breadcrumb: []
source_path: "it-benchmarking/infrastructure_benchmarking.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Benchmarking de infraestrutura

Esta seção descreve a finalidade das métricas de Benchmarking de Infraestrutura. O produto Apptio Benchmarking é um aplicativo de autoatendimento SaaS que você pode usar para fazer comparações de custos de benchmark entre pares. O Benchmarking aborda o quê, mas não o porquê, como ou o que virá a seguir. Você pode usar os custos de sua organização, compará-los com as métricas de benchmark e pesquisar/racionalizar seus valores reais para determinar o porquê e como. Em seguida, você pode usar esse entendimento para criar as próximas etapas e resultados acionáveis e agregar valor. Você pode até trabalhar com consultores terceirizados para ajudar a interpretar as comparações e fornecer conselhos/recomendações.

**Métricas de benchmarks de infraestrutura**

Essa categoria inclui métricas de benchmark de pares em nível de torre e subtorre. Os clientes podem comparar os custos unitários de suas torres e subtorres e as eficiências de FTE.

| Tipo | Descrição |
| --- | --- |
| **Público-alvo** | Liderança de TI, I&O, Finanças de TI, TBMO |
| **Finalidade** | - Validação - Use essas métricas de infraestrutura para alinhar e validar as métricas por torre/subtorre com a taxonomia da TBM - Comparação - compare os custos unitários e as eficiências de FTE com os padrões de referência dos colegas e avalie a posição da organização em relação às amostras de referência - Rastreamento - rastreie e analise os custos unitários e o desempenho de eficiência do FTE ao longo do tempo - Análise - analisar as tendências de custo unitário e o desempenho de eficiência do FTE - Iniciativa - criar iniciativas para promover melhorias e definir metas |
| **Uso** | - Validação - Mensalmente por I&O, IT Finance, TBMO - Comparação - Trimestral ou ad-hoc por I&O, TBMO - Acompanhamento - Mensalmente por I&O, TBMO - Revisão - trimestral ou mensal pela liderança de TI, I&O, finanças de TI - Iniciativa - Semestralmente ou ad-hoc pela Liderança de TI, I&O, Finanças de TI, TBMO |
| **Orientação** | Essas métricas se concentram nas características de gastos com torres por infraestrutura. Eles incorporam volumes de infraestrutura para calcular os custos unitários das subtorres a partir dos custos totais das subtorres da Transparência de custos. Obtenha uma comparação entre pares com os custos unitários de referência de seus pares. O custo e o volume de TI da organização precisam ser atribuídos e alocados ao nível da subtorre.  A métrica de eficiência FTE fornece uma visão dos custos sob o gerenciamento de TI para a subesfera. Isso é útil porque a mão de obra é o custo dominante da infraestrutura. Isso ajuda a entender a cobertura de TI da torre e a racionalizá-la. Por exemplo, uma empresa pode ter uma baixa eficiência de FTE, mas isso é justificável, pois a estratégia de TI é fornecer suporte de alta qualidade. As métricas de TI OpEx fornecem comparações gerais, enquanto as métricas de infraestrutura entram na análise específica de torres/subtorres. Normalmente, os benchmarks de infraestrutura são usados após a análise da TI OpEx para analisar os custos específicos da infraestrutura. |

Tabela 5: Intenção de infraestrutura

Os dados de benchmark dos pares são da [ISG](https://isg-one.com/ "(Abre em uma nova guia ou janela)"), uma organização líder em insights sobre tecnologia, inteligência de mercado e serviços de consultoria (as métricas de torres de storage são a exceção e vêm da Rubin Worldwide).

As métricas incluídas são:

| Torre de TI | Subtorre de TI | Unidade de medida | Custo unitário | Custo por pool de custos | Eficiência FTE |
| --- | --- | --- | --- | --- | --- |
| Informática | Windows | Servidores lógicos/físicos | √ | √ | √ |
| Linux | Servidores lógicos/físicos | √ | √ | √ |
| Unix | Servidores lógicos/físicos | √ | √ | √ |
| Mainframe | MIPS | √ | √ | √ |
| Armazenamento (consulte a OBSERVAÇÃO abaixo) | Camada 1 | TBs instalados | √ | √ |  |
| Camada 2 | TBs instalados | √ | √ |  |
| Camada 3 | TBs instalados | √ | √ |  |
| Camada 4 | TBs instalados | √ | √ |  |
| Rede | LAN | Portas LAN ativas | √ | √ | √ |
| WAN | Dispositivos conectados ao usuário final | √ | √ | √ |
| Voz | Fone de ouvido | √ | √ | √ |
| Usuário final | Espaço de trabalho (PC) | Desktops, laptops e thin clients | √ | √ |  |
| Central de serviços | Contatos | √ | √ | √ |
| Comunicações |  | Usuários de TI | √ | √ |  |
| Saída |  | Milhões de imagens | √ | √ | √ |
| Administração da TI |  | Usuários de TI | √ | √ | √ |
| E-mail |  | Usuários de TI | √ | √ |  |

Tabela 6 Métricas de referência de infraestrutura

**Notas**

- Para o armazenamento, a distribuição do custo por pool de custos é fornecida (pelo provedor de benchmark) no nível geral de armazenamento. Em seguida, ele é aplicado a cada uma das quatro camadas.
- A lista acima é para a TBM Taxonomy v1.0.

Usando essas métricas, você pode fazer o seguinte:

| Uso | Como interpretar - resultados e questões a serem consideradas |
| --- | --- |
| **Validação** - Alinhar os gastos à taxonomia da TBM | - Articular o valor da TI e justificar o custo do fornecimento de TI, - Melhorar o diálogo e o alinhamento com os usuários corporativos com base em dados reais padronizados e benchmarks de colegas   Esses valores do cliente exigem o alinhamento dos dados aos compartimentos corretos da taxonomia da TBM e a verificação da qualidade das alocações. Ele ajuda a estabelecer e manter a confiança nos custos reais de TI (saiba mais).  É comum que os usuários iniciem a infraestrutura inicialmente com dados incompletos. Além disso, essas métricas introduzem e incorporam o volume ao modelo de transparência de custos. Isso gera uma compreensão mais profunda dos fatores de custo.   - Os dados nunca são perfeitos, e o benchmarking ajudará a identificar, priorizar e conduzir dados acionáveis e melhorias no processo que geram melhores decisões - Reconhecer a natureza iterativa da qualidade dos dados e da alocação e as comparações com os benchmarks impulsiona a capacidade de começar hoje e melhorar ao longo do tempo - Comece essa jornada identificando áreas de alta prioridade com oportunidades e concentre os refinamentos nessas áreas primeiro. Use o processo de comparação de benchmark para ajudar a identificar áreas de alta prioridade |
| **Comparação** - Gastos de TI com referências de infraestrutura | Os benchmarks abordam o quê, mas não o porquê, como ou o que virá a seguir:   - A pesquisa da variação dos benchmarks e a racionalização das comparações orientarão o porquê e o como - É essencial criar próximas etapas e resultados acionáveis e reconhecer o valor   Uma sequência típica de variância (comparação) é:   1. Comece no nível da torre para entender os gastos com materiais e identificar grandes oportunidades. Algumas possíveis questões a serem investigadas são:    - Qual é a torre que mais gasta?    - Onde está a maior variação em relação à referência? Isso leva à visualização das subtorres. 2. Revisar os detalhes do custo unitário da subtorre, discriminados pela composição do pool de custos, para identificar áreas acionáveis para análises, decisões e oportunidades adicionais. Identificar áreas de otimização :    - Racionalizar as comparações com o benchmark para entender por que está acima/abaixo    - Benchmark é um ponto de referência - estar acima ou abaixo não é ruim ou bom Algumas possíveis questões a serem investigadas são:     - Qual subtorre tem o maior gasto com base no custo total?    - Qual subtorre tem a maior variação em relação à referência com base no custo unitário? Isso ajuda a aprofundar a composição do pool de custos e a abordar questões como:     - A composição corresponde ao modelo operacional?    - Onde estão as diferenças em relação aos pares de referência?    - As decisões do modelo operacional atual são pertinentes ou há uma oportunidade de mudança? 3. Revisar a eficiência do FTE da Sub Torre para identificar áreas para melhorar a eficiência das operações. Algumas perguntas possíveis aqui são:    - A infraestrutura está sendo operada de forma eficiente?    - Vale a pena considerar estratégias alternativas de sourcing? |
| **Rastreamento** - Custo unitário e eficiência de FTE | As métricas de benchmark são pontos de referência; identifique e defina metas incrementais alcançáveis que sejam informadas por benchmarks. As decisões tomadas a partir da análise de comparação acima podem levar a melhorias incrementais e iniciativas potencialmente maiores (identificadas abaixo e, normalmente, em conjunto com revisões de liderança).  Estabeleça metas fiscais bem informadas - Com base nas ações identificadas por meio de comparações entre pares, estabeleça metas para acompanhar o progresso do custo unitário e da eficiência de FTE. Esse rastreamento pode ser feito ao longo do tempo com dados reais atualizados e dados de benchmark de pares (os dados de benchmark são atualizados a cada 6 meses) - Obtenha comparações de pares atualizadas. |
| **Revisão** - Revisão da liderança sobre o progresso | Use o acompanhamento das métricas acima em relação às metas em revisões periódicas com a equipe de liderança. |
| **Iniciativa** - Identificar e conduzir a iniciativa | As análises orientam as decisões estratégicas sobre os investimentos em TI e acionam as iniciativas. O impacto dessas iniciativas pode ser monitorado pela visualização do impacto no custo usando as diretrizes acima. |

Tabela 7: Resultados de infraestrutura

Para cada uma dessas métricas, o provedor de dados de benchmark ISG fornece uma média juntamente com ajustadores em três dimensões independentes:

- **Escala** - Ajustadores baseados em volumes de unidades de medida. Esse é o principal influenciador das métricas de infraestrutura. O modelo de escala ISG para o custo unitário é uma função de etapa do custo unitário sobre o volume de unidades. O modelo é aplicável a uma faixa de volume especificada. A função de etapa, consulte  **Error! Fonte de referência não encontrada.**  , é aplicável em uma faixa de limite alto (custo) a um limite baixo (custo).
- **Região** - Ajustadores com base na região. O ISG fornece ajustadores para as regiões NA, EMEA e APAC; a definição de região é o local onde uma organização tem sua sede.
- **Setor** - Ajustes baseados em grupos de setores. A ISG fornece ajustadores para os seguintes grupos: Bancos, serviços financeiros e seguros (BFSI), energia, manufatura, comunicações e mídia e entretenimento (MCM), tecnologia e outros.

No Produto de Benchmarking, consulte ( Apptio, Infrastructure Benchmarking, 2015), as métricas de pares de infraestrutura podem ser calculadas visualizando a distribuição e selecionando os ajustadores. Normalmente, o ajustador de escala é usado por ser o contribuinte mais significativo.

A apresentação em vídeo do produto Benchmarking fornece uma descrição dos componentes do benchmarking, seu valor e a lista de métricas e seus provedores de dados.
