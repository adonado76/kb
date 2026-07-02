---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Métricas: modeladas vs. calculadas"
breadcrumb:
  - "TBM Studio"
  - "Conceitos e Arquitetura"
  - "Arquitetura do modelo"
source_path: "studio/new-uc/concepts-architecture/model-architecture/metrics-modeled-calculated.html"
images:
  - "resources/images/studio_images/model-metric-flow.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Métricas: modeladas vs. calculadas

As métricas são as medidas numéricas que circulam pelo seu modelo e aparecem nos seus relatórios. O TBM Studio oferece suporte a dois tipos de métricas fundamentalmente diferentes, e compreender essa distinção é essencial para a criação de modelos de custo eficazes.

## Métricas modeladas

Uma métrica modelada é um valor numérico fundamental que participa diretamente do mecanismo de alocação. Quando os custos são alocados de um objeto para outro, as métricas modeladas são os valores que estão sendo distribuídos.

**As métricas padronizadas incluem:**

- **Custo:** Despesas efetivas — o indicador mais comum e o padrão em todos os projetos
- **Orçamento:** Despesas planejadas para comparação com os valores reais
- **Previsão:** Despesas futuras estimadas
- **Métricas personalizadas:** qualquer valor alocável adicional que você definir, como número de funcionários d CapEx,, ou taxa de utilização

**Como funcionam as métricas modeladas**

Quando o TBM Studio calcula um modelo, cada métrica modelada percorre toda a cadeia de alocação de forma independente. Isso significa que a métrica de Custo é alocada de acordo com seus fatores determinantes; a métrica de Orçamento é alocada de acordo com seus fatores determinantes (que podem ser os mesmos ou diferentes), e assim por diante.

![Modelo de fluxo métrico](../../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/model-metric-flow.png)

**Principais comportamentos das métricas modeladas:**

- Cada objeto de modelo armazena seu próprio conjunto de valores métricos modelados por período
- As métricas têm origem nas tabelas de transformação ( Data Studio ) e são propagadas através das alocações
- Ao agrupar dados em relatórios, as métricas modeladas somam seus valores
- As métricas modeladas não podem ser calculadas ao longo de períodos de tempo — elas representam valores de um único período
- Há um modelo por projeto, mas esse modelo pode conter várias métricas modeladas

## Métricas calculadas

Uma métrica calculada é derivada de uma fórmula que faz referência a métricas modeladas, colunas de tabela ou outras métricas calculadas. As métricas calculadas não são consideradas pelo mecanismo de alocação — elas são calculadas no momento da geração do relatório.

**Padrões comuns de métricas calculadas:**

|  |  |  |
| --- | --- | --- |
| **Padrão** | **Exemplo de fórmula** | **Propósito** |
| Variância | = Orçamento - Custo | Mostrar a diferença entre os gastos planejados e os gastos reais |
| Variação % | = (Orçamento - Custo) / Orçamento | Mostrar o excesso ou a falta de gastos em porcentagem |
| Custo unitário | = Custo/ ServerCount | Normalizar os custos para permitir a comparação entre entidades de diferentes tamanhos |
| No acumulado do ano | = YearToDate(CapEx) | Agregar uma métrica modelada desde o início do exercício fiscal até o período atual |
| Compartilhamento de custos | = Custo / SOM(Custo) | Mostre qual porcentagem do custo total cada entidade representa |

**Principais características das métricas calculadas:**

- Definido na seção Métricas do Explorador de Projetos e disponível para todos os relatórios do projeto
- As fórmulas são avaliadas durante os cálculos dos relatórios, e não durante os cálculos do modelo
- Ao agrupar dados, as métricas calculadas são recalculadas (não são somadas), a menos que sejam explicitamente marcadas como somáveis
- É possível realizar cálculos entre períodos de tempo utilizando funções de análise temporal, como YearToDate, MonthToDate
- Para alterar uma fórmula, é necessário fazer o check-out da métrica e, em seguida, fazer o check-in novamente
- Não pode ser convertido em métricas modeladas nem vice-versa

## Guia de Decisão sobre o Sistema Métrico

Use este guia para determinar qual tipo de métrica é mais adequado às suas necessidades:

|  |  |  |
| --- | --- | --- |
| **Você precisa de...** | **Tipo de métrica** | **Por que escolher o ?** |
| Dados brutos de custos que passam pelas alocações | Métrica modelada | Apenas as métricas modeladas participam do mecanismo de alocação |
| Uma combinação matemática de outras métricas | Métrica calculada | As fórmulas fazem referência a métricas modeladas e calculam valores derivados |
| Dados agregados ao longo do tempo (acumulado no ano, acumulado nos últimos 12 meses) | Métrica calculada | As funções de inteligência temporal só funcionam em métricas calculadas |
| Um valor utilizado em diversas áreas, em diferentes níveis | Métrica modelada | As métricas modeladas se aplicam a toda a hierarquia do modelo |
| Um cálculo de relatório com finalidade única | Métrica calculada | Mantenha a lógica de relatórios separada da lógica do modelo |
| Dados categóricos (rótulos, nomes, códigos) | Dimensão/Coluna | Os atributos não numéricos devem constar como colunas da tabela, e não como métricas |

Nota:

**Equívoco comum**

As métricas calculadas não alteram os fluxos do modelo. Se você criar uma métrica calculada que divida o Custo pelo Orçamento, esse cálculo aparecerá apenas nos relatórios. Isso não tem efeito sobre a forma como os custos são alocados. Se você precisar de um valor para participar das alocações, ele deve ser uma métrica modelada.
