---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Compreender as métricas do modelo (custo, orçamento, previsão)"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "Criar modelos de custos"
  - "Noções básicas sobre modelos"
source_path: "studio/new-uc/howtoguides/build-cost-model/understand-model-metrics.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Compreender as métricas do modelo (custo, orçamento, previsão)

|  |  |
| --- | --- |
| **Tipo de Conteúdo** | Guia prático / Conceitual |
| **Público-alvo** | Analistas de negócios, equipes de TI e finanças |
| **Tempo estimado** | 10 a 15 minutos |
| **Pré-requisitos** | Conhecimentos básicos do TBM Studio; familiaridade com conceitos financeiros |

## Objetivo

Entenda o que são métricas de modelo, como funcionam as métricas principais (Custo, Orçamento, Previsão) e como elas se refletem nas alocações do seu modelo de custos.

## Quando usar essas informações

Este guia conceitual ajuda você quando:

- Configurar um novo modelo e decidir quais métricas monitorar
- Configurar alocações que se aplicam a métricas específicas
- Interpretação de relatórios de modelos que exibem várias métricas
- Criação de relatórios de variação que comparam custos com o orçamento
- Solução de problemas: por que certos valores não estão fluindo como esperado

## O que são métricas de modelo?

**Uma métrica de modelo** é um valor numérico que circula pelo seu modelo de custos por meio de alocações. Embora o TBM Studio ofereça suporte a diversos tipos de métricas, três delas são fundamentais para a maior parte da gestão financeira de TI:

|  |  |
| --- | --- |
| **Métrica** | **Descrição** |
| **Custo** | Despesas efetivamente incorridas. Essa é normalmente a principal métrica em um modelo TBM, obtida do seu razão geral, faturas ou outros sistemas financeiros. O custo representa o que você realmente gastou. |
| **Orçamento** | Valores de despesas planejados ou alocados. O orçamento representa o que você pretendia gastar, geralmente definido durante o planejamento anual. A comparação entre o orçamento e os custos revela desvios. |
| **Previsão** | Despesas futuras previstas com base nas tendências atuais. A previsão é normalmente atualizada ao longo do ano, à medida que os padrões reais de gastos vão se revelando, proporcionando uma visão mais precisa da evolução dos custos. |

Sua organização também pode utilizar métricas adicionais, como despesas de capital ( CapEx ), taxa de utilização ou métricas personalizadas específicas para as necessidades do seu negócio.

## Métricas do modelo vs. métricas calculadas

O TBM Studio oferece suporte a dois tipos de métricas:

**As métricas de modelo** (também chamadas de métricas modeladas) têm origem nos seus dados de origem e passam pelas alocações. Custo, orçamento e previsão são, normalmente, métricas do modelo. São os valores brutos que entram no seu modelo no nível mais baixo (como a fonte de custo) e se propagam para cima ao longo de cada etapa de alocação.

**As métricas calculadas** são derivadas das métricas do modelo por meio de fórmulas. Por exemplo, você pode criar uma métrica calculada chamada “Desvio do Orçamento”, definida como Orçamento menos Custo. As métricas calculadas não são afetadas pelas alocações — elas são calculadas na camada de relatórios.

**Observação:** as métricas do modelo são somadas ao agrupar os dados. As métricas calculadas são recalculadas usando suas fórmulas. Essa distinção é importante ao agregar dados entre períodos ou hierarquias.

## Como as métricas são distribuídas pelas alocações

Ao criar uma alocação, você especifica a quais métricas ela se aplica. Veja como funciona o processo:

1. **Os motoristas da Unidade agregam valor.** Na tabela de custos (o nível inferior do seu modelo), os drivers unitários extraem valores das colunas dos seus dados. Por exemplo, um motorista de unidade pode consultar a coluna “Valor” para incluir o custo no modelo.
2. **As alocações distribuem valor.** Cada alocação retira um valor de uma tabela e o distribui para outra com base em regras de ponderação. Por exemplo, você pode alocar custos da fonte de custos aos fornecedores com base nos valores das faturas dos fornecedores.
3. **As métricas são propagadas de forma independente.** Se você configurar uma alocação para ser aplicada tanto ao Custo quanto ao Orçamento, cada métrica será contabilizada separadamente. Os valores de custo são transferidos da origem para o destino usando os pesos de alocação, e os valores do orçamento fazem o mesmo — mantendo seus totais separados em todo o modelo.
4. **Os valores são transmitidos através dos níveis.** À medida que você constrói um modelo em várias camadas (Fonte de Custo → Fornecedores → Serviços de Tecnologia → Unidades de Negócio), as métricas percorrem cada camada, acumulando-se e distribuindo-se de acordo com suas regras de alocação.

## Visualizando métricas no modelo

Você pode alternar entre métricas ao visualizar o modelo:

1. Abra um objeto de modelo clicando na etapa “Modelo” no fluxo de transformação.
2. Procure o seletor de métricas na parte superior do painel do modelo. Este menu suspenso mostra todas as métricas disponíveis (Custo, Orçamento, Previsão, etc.).
3. Selecione uma métrica diferente para ver como esse valor se comporta ao longo do modelo. As larguras do diagrama de Sankey são atualizadas para refletir os valores da métrica selecionada.

Dica: Ao criar relatórios modelo, você pode selecionar quais métricas incluir usando o botão “Editar métricas” no Editor de camadas. Incluir menos métricas melhora o desempenho dos cálculos.

## Criação e gerenciamento de métricas

As métricas são definidas no nível do projeto e aparecem na seção Métricas do Explorador de Projetos. Para criar uma nova métrica:

1. Na guia Início, clique em **Novo** e, em seguida, clique em **Métrico**.
2. Digite um nome e clique em **OK**.
3. Configure as propriedades da métrica, incluindo o tipo de modelo (Modelo ou Calculada), a formatação e o tipo de métrica (Cálculo de custos, Precificação ou Numérica).
4. Salve e verifique a métrica.

## Principais propriedades métricas

**Tipo de modelo:** Selecione “Modelo” para métricas que passam por alocações ou “Calculado” para métricas baseadas em fórmulas.

**Tipo de métrica:** Selecione “Cálculo de custos” para valores monetários provenientes de fontes com cálculo de custos completo (como um razão geral), “Precificação” para modelos de preço × quantidade ou “Numérico” para valores não monetários.

**Formato da tabela:** controla como a métrica aparece nos relatórios. Use =Currency($\_) para que os valores monetários sejam exibidos em dólares.

**Comportamento temporal:** Determina como a métrica é agregada ao longo dos períodos — Soma, Média ou Recalcular.

## O que vem a seguir

- [Configurar alocações](setup-sa.html) para métricas de fluxo entre tabelas
- Crie métricas calculadas para análise de variação — consulte [a Referência do Model Studio](../../reference/model-studio-ref.html)
- Saiba mais sobre propriedades e fórmulas métricas — consulte [Arquitetura do modelo](../../concepts-architecture/model-architecture/model-concepts-overview.html).

## Conceitos relacionados

- [Arquitetura do modelo](../../concepts-architecture/model-architecture/model-concepts-overview.html) — Explicação detalhada de como o mecanismo de alocação processa as métricas
- [Fórmulas e funções](../../reference/formula-function.html) — Criação de métricas calculadas com fórmulas

**Tópico principal:** [Noções básicas sobre modelos](../../../../studio/new-uc/howtoguides/build-cost-model/model-basics.html)
